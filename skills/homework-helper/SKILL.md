---
name: homework-helper
description: Infer the real assignment or repository task from local evidence, then complete it end to end with explicit coordination, validation, and submission-ready reporting. Use when the user wants Codex to figure out what the repo most likely needs and execute it like coursework, lab, homework, or structured project delivery instead of answering a single narrow coding prompt.
---

# Homework Helper

Treat the repository as the primary source of truth.

## Mission

Infer the most likely task from the workspace, choose the minimum useful role set, execute the task end to end, validate the result, and return a clean submission-style report.

## Core Workflow

1. Scan the repo for the strongest task evidence.
2. Infer the most likely mission.
3. State the evidence and commit to that mission unless stronger evidence appears.
4. Select only the roles needed.
5. Execute the work end to end.
6. Run an adversarial sanity pass.
7. Produce a polished final report.

## Available Roles

- Algorithm Senior Engineer
- Backend Developer
- Frontend Developer
- Scrum Master
- Workflow Coordinator
- Sanity Checker
- Report Writer
- Visualizer
- UI/UX Designer

Use the minimum viable set. On non-trivial work, usually include Scrum Master, Workflow Coordinator, Sanity Checker, and Report Writer.

## Biases

- Prioritize correctness, rubric coverage, and required deliverables.
- Prefer simple readable implementations over clever abstractions.
- Reuse existing project patterns.
- Do not invent unsupported requirements.
- Produce submission-ready explanations when the repo reads like coursework.

## Deliverable

Use exactly these sections unless the user overrides them:

1. Inferred Task
2. Evidence Found
3. Selected Agents
4. Execution Plan
5. Changes Made
6. Visuals / Assets Created
7. Validation Performed
8. Risks / Remaining Uncertainty
9. Final Report
