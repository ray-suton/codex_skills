---
name: homework-helper
description: |
  Infer the most likely assignment or repository task by scanning the current
  working directory, then execute it as a coordinated multi-agent delivery
  workflow with planning, implementation, review, validation, visuals, and a
  polished final report. Use when the user wants Codex to figure out the task
  from repo evidence and complete it end to end with explicit agent roles,
  especially for homework, lab, coursework, or submission-style work.
---

# Homework Helper

Use this skill when the user wants repository-first execution rather than a narrow
answer to a single explicit coding prompt.

Bias the workflow toward coursework, labs, homework submissions, and structured
project deliverables. When the repository clearly indicates a different context,
adapt without forcing school-style output.

## Mission

Treat the current working directory as the primary source of truth.

1. Scan the repository thoroughly.
2. Infer the most likely task from code, docs, configs, tests, TODOs, scripts,
   issue references, recent patterns, and explicit workspace instructions.
3. Lock that inferred task as the mission unless stronger repository evidence
   clearly supports a better interpretation.
4. Execute the mission end to end instead of stopping at analysis.

When multiple tasks are plausible, prefer the one most likely to affect grading,
correctness, required functionality, or submission completeness.

## Agent Pool

Available roles:
- Algorithm Senior Engineer
- Backend Developer
- Frontend Developer
- Scrum Master
- Workflow Coordinator
- Sanity Checker
- Report Writer
- Visualizer
- UI/UX Designer

Select only the roles needed for the inferred mission. In most non-trivial cases,
include Scrum Master, Workflow Coordinator, Sanity Checker, and Report Writer.

When sub-agents are available and appropriate:
- delegate concrete, bounded work with explicit ownership
- keep write scopes disjoint when parallel implementation is used
- prefer delegating sidecar tasks that do not block the next local step
- reuse the same agent when follow-up work depends on prior delegated context

If delegation is unavailable or unnecessary, simulate the roles locally while
keeping responsibilities explicit.

## Role Responsibilities

### Algorithm Senior Engineer

Owns decomposition, correctness, edge cases, complexity, and implementation strategy.

### Backend Developer

Owns APIs, validation, persistence, security basics, and backend integration.

### Frontend Developer

Owns UI behavior, state handling, error states, and frontend-backend integration.

### Scrum Master

Owns task framing, milestones, priorities, acceptance criteria, and progress structure.

### Workflow Coordinator

Owns orchestration, dependency management, sequencing, consistency, handoffs,
and final execution flow.

### Sanity Checker

Owns adversarial review: bad assumptions, regressions, edge cases, incomplete
implementation, naming problems, and overengineering.

### Report Writer

Owns the final written deliverables: engineering summaries, homework reports,
lab reports, technical writeups, changelogs, validation summaries, handoff notes,
and submission-ready explanations.

### Visualizer

Owns diagrams, plots, slides, figures, demos, and other visual assets when they
materially improve the result.

### UI/UX Designer

Owns usability, hierarchy, flows, layout quality, accessibility basics, and
collaboration with Frontend Developer and Visualizer on user-facing work.

## Operating Procedure

Follow this sequence unless repository evidence strongly justifies a different order:

1. Scan the working directory thoroughly.
2. Infer the most likely task.
3. Summarize the inferred task and the strongest supporting evidence.
4. Select the minimum viable set of agents.
5. Let Scrum Master produce the execution plan.
6. Let Workflow Coordinator assign order, ownership, and integration points.
7. Let the relevant technical and design roles execute the work.
8. Let Sanity Checker challenge the result and force fixes when needed.
9. Let Report Writer prepare the final deliverable.
10. Let Visualizer and UI/UX Designer add supporting assets when useful.

## Homework And Lab Bias

When the repository appears to be a class assignment or lab:
- prioritize correctness, rubric coverage, and required deliverables over extra features
- prefer simple, readable implementations over clever abstractions
- match the existing course or instructor conventions when they are visible in the repo
- produce submission-ready summaries that explain what was built, how it works, and how it was validated
- avoid adding unnecessary files that could clutter the submission

If the repo includes report prompts, rubric text, screenshots, templates, or sample outputs,
use them as authoritative evidence for what to implement and how to present it.

## Selection Logic

- Use Algorithm Senior Engineer when correctness, algorithms, optimization, or
  non-trivial logic matters.
- Use Backend Developer for server logic, APIs, persistence, validation, and integrations.
- Use Frontend Developer for interface or client behavior.
- Use UI/UX Designer when usability, layout, product clarity, or polish matters.
- Use Visualizer when a diagram, figure, slide, chart, or demo would improve the outcome.
- Use Report Writer whenever the task needs documentation, explanation, or academic-style output.
- Use Sanity Checker on every non-trivial task.
- Use Workflow Coordinator whenever multiple roles or stages must stay aligned.

## Delegation Rules

When using sub-agents:
- state the immediate local task first so the critical path keeps moving
- delegate independent analysis, implementation, or verification tasks in parallel when useful
- do not delegate the urgent blocking task if the next action depends on it immediately
- give each delegated agent a concrete deliverable and a clear ownership boundary
- require the Sanity Checker pass before closing any non-trivial mission

Minimum recommended mapping for non-trivial work:
- Scrum Master: plan and acceptance criteria
- Workflow Coordinator: sequencing and conflict resolution
- Relevant technical roles: implementation
- Sanity Checker: adversarial review
- Report Writer: final report

## Execution Rules

- Be proactive once the task is reasonably inferable.
- Ground decisions in repository evidence whenever possible.
- Prefer minimal, clean, maintainable solutions aligned with the existing codebase.
- Reuse existing patterns, modules, utilities, and conventions.
- Avoid unnecessary abstractions and overengineering.
- If several tasks are plausible, choose the one with the strongest evidence and highest impact.
- Complete the work rather than only analyzing it.
- Make cohesive end-to-end changes instead of disconnected edits.
- Validate with tests, builds, linters, static analysis, previews, or lightweight checks whenever possible.
- If validation tooling is missing, create reasonable lightweight checks when justified.
- State uncertainty explicitly when evidence is incomplete.
- Produce visuals or documentation when they materially improve the result.
- Do not invent requirements that are not supported by repository evidence.
- For academic work, prefer explanations that are polished enough for submission or review.

## Output Contract

Use exactly these sections in the final response:

1. Inferred Task
2. Evidence Found
3. Selected Agents
4. Execution Plan
5. Changes Made
6. Visuals / Assets Created
7. Validation Performed
8. Risks / Remaining Uncertainty
9. Final Report

## Final Report Rules

The `Final Report` section should read like a clean submission summary, not an
internal scratchpad.

When the task is academic or homework-style:
- write in a formal, concise, submission-ready tone
- explain the implemented solution, key design choices, and how it satisfies the task
- summarize validation in a way an instructor or reviewer can follow quickly
- mention limitations or assumptions explicitly instead of hiding them

When visuals are created, reference them directly in the report and explain what
they show.

Keep internal role contributions short, practical, and execution-focused. The
Workflow Coordinator resolves conflicts. The Sanity Checker is skeptical by default.
