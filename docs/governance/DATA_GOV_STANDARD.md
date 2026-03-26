# Data Governance Standard — Universal Artifact Header
**ID:** GOV-CSCF-STD-001 | **Version:** 1.0.0 | **Status:** Active

## Universal Artifact Signature Block

Every artifact in this framework MUST begin with this header:

```yaml
---
# ── UNIVERSAL ARTIFACT SIGNATURE ──────────────────────────────
artifact_id:   ""            # UUIDv7 (time-ordered, RFC 9562)
doc_id:        ""            # [DOMAIN]-[PROJECT]-[TAG]-[YYYYMMDD]-[SEQ]
title:         ""
version:       "1.0.0"       # Semantic Versioning
status:        "draft"       # draft | review | approved | deprecated | ratified

# Dublin Core ISO 15836 (compact)
dc:
  creator:     ""            # agent_id or person name
  subject:     []            # tags
  description: ""
  publisher:   ""
  contributor: []
  date:        ""            # ISO 8601: 2026-03-08T10:00:00+07:00
  type:        ""            # spec | policy | sop | artifact | decision | log
  format:      "text/markdown"
  identifier:  ""            # urn: or doi: or doc_id
  language:    "en"
  rights:      ""

# Provenance
created_at:    ""            # ISO 8601 timestamp
created_by:    ""            # agent_id
pipeline_stage: ""
input_artifacts: []          # List of upstream artifact_ids

# Integrity
sha256:        ""            # SHA-256 of content body (populated on registration)
previous_version_id: ""      # artifact_id of previous version (immutable chain)

# Change Log (append-only)
changes:
  - version: "1.0.0"
    date:    ""
    author:  ""
    summary: "Initial creation"
    type:    "create"        # create | amend | deprecate | ratify

# Approvals (for ratified artifacts)
approvals: []
# - role: "Product Owner"
#   name: ""
#   date: ""
#   approval_id: ""          # UUIDv7
---
```

## Shortened Field Reference

| Field | Required | Notes |
|---|---|---|
| `artifact_id` | ✅ | UUIDv7 — time-ordered, sortable |
| `doc_id` | ✅ | Human-readable ID per DOC_ID convention |
| `version` | ✅ | SemVer: MAJOR.MINOR.PATCH |
| `status` | ✅ | Lifecycle state |
| `dc.creator` | ✅ | ISO 15836 creator |
| `dc.date` | ✅ | ISO 8601 with timezone |
| `created_at` | ✅ | Machine timestamp |
| `sha256` | ✅ on register | Populated by `scripts/register_artifact.py` |
| `changes` | ✅ | Append-only change log |
| `approvals` | ✅ if ratified | Required for `status: ratified` |

## UUIDv7 Generation
```python
import time, os

def uuidv7() -> str:
    ms = int(time.time() * 1000)
    rand = int.from_bytes(os.urandom(10), 'big')
    uuid_int = (ms << 80) | (0x7 << 76) | ((rand >> 62) << 64) | (0b10 << 62) | (rand & 0x3FFFFFFFFFFFFFFF)
    h = f'{uuid_int:032x}'
    return f'{h[:8]}-{h[8:12]}-{h[12:16]}-{h[16:20]}-{h[20:]}'
```
