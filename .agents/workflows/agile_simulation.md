---
description: How to run an Agile simulation loop with the loaded Agent team for planning, review, and execution tasks.
---

# Agile Simulation Workflow

## Overview

This workflow defines the procedure for conducting an **Agile task meeting in simulation** by loading the Team of Agents system prompts and executing a stakeholder feedback loop. The Master Orchestrator (Cường Q. Huỳnh) acts as the Product Owner (PO) and final authority.

## Prerequisites

- All personas in `.agents/personas/` are loaded and understood by the AI assistant.
- The current project state (version, open tasks, recent changes) is known.

## Workflow Steps

### Phase 1: Sprint Initialization

1. **Load Personas** — Read all persona files from `.agents/personas/` to understand each team role.
2. **Identify Sprint Scope** — Gather requirements from the PO (Master Orchestrator). Define the sprint goal.
3. **Draft Sprint Backlog** — Create a prioritized list of tasks with acceptance criteria.

### Phase 2: Simulation Loop

4. **Role Rotation** — For each backlog item, simulate feedback from the relevant personas:
   - **Virtual Librarian**: Are changelogs, versioning, and documentation impacts accounted for?
   - **IP Assets Professional**: Are there licensing, attribution, or IP compliance concerns?
   - **Infra & Data Architect**: Are there technical integrity, schema, or architecture concerns?
5. **Consolidate Feedback** — Merge all persona feedback into a refined plan.
6. **Present to PO** — Submit the consolidated plan to the Master Orchestrator for approval.

### Phase 3: Approval Gate

7. **PO Review** — The Master Orchestrator reviews and either:
   - **Approves** → Proceed to execution.
   - **Requests Changes** → Return to Phase 2 with feedback.
   - **Rejects** → Document reasoning and close the item.

### Phase 4: Execution

8. **Execute Approved Tasks** — Implement changes per the ratified plan.
9. **Version & Document** — For every executed step:
   - Update `CHANGELOG.md` (append-only).
   - Update `README.md` if structural changes occurred.
   - Assign version numbers to all outputs.
   - Generate signature blocks for ratified documents:
     ```
     sign(hash + uuidv7 + timestamp + context)
     Doc Hash → Signed by Contributor
              → Signed by System
              → Signed by Authority (optional)
     ```
10. **Attribution** — Every output must include:
    ```
    Author: Cường.Q.Huỳnh
    Assistances: [AI System Name(s)]
    ```

### Phase 5: Sprint Close

11. **Sprint Review** — Present completed work to the PO for final acceptance.
12. **Update Sprint Records** — Append the sprint summary to `sprint-records/`.
13. **Tag Release** — If a version milestone is reached, create a Git tag.
