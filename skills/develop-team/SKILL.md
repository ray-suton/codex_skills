---
name: develop-team
description: Run broad software delivery as a coordinated team with explicit role separation. Use when the user wants multi-agent or team-style execution for a production feature, product slice, or end-to-end build and needs product, design, backend, frontend, integration, QA, and readiness work handled as one coherent delivery workflow. For tightly scoped 48-hour MVP work, use `mvp-develop-team` instead.
---

# Develop Team

Run the job as a coordinated delivery team, not one blended response.

## Mission

Produce an end-to-end result with explicit ownership across scope, execution, design, backend, frontend, integration, QA, and readiness.

## Roles

- `[Product Manager]`: define problem, scope, assumptions, user stories, acceptance criteria
- `[Scrum Master]`: order work, track dependencies, protect scope
- `[UI/UX Designer]`: define flow, states, validation, responsive and accessibility notes
- `[Backend Developer]`: define contracts, data model, business rules, backend risks
- `[Frontend Developer]`: implement UI and client behavior against the agreed contract
- `[Fullstack Integrator]`: resolve cross-layer mismatches and runtime requirements
- `[QA Engineer]`: test integrated flows and report defects with severity and repro
- `[Workflow Monitor]`: audit gaps, contradictions, and readiness

## Workflow

1. `[Product Manager]` locks scope, assumptions, and acceptance criteria.
2. `[Scrum Master]` turns that into an execution plan and dependency map.
3. `[UI/UX Designer]` and `[Backend Developer]` work in parallel.
4. `[Frontend Developer]` builds once UI and API contracts are clear.
5. `[Fullstack Integrator]` wires the system and resolves mismatches.
6. `[QA Engineer]` validates the integrated product.
7. `[Workflow Monitor]` gives the final readiness call.

## Operating Rules

- Keep role outputs distinct.
- Do not hide disagreements.
- Treat unresolved contract mismatches as blockers.
- Prefer implementation and verification over abstract discussion.
- If full parallel execution is not available, simulate the missing roles explicitly.

## Deliverable

Include:
1. product definition
2. execution plan
3. UI/UX definition
4. backend and frontend implementation details
5. integration notes
6. QA results
7. workflow-monitor readiness report
