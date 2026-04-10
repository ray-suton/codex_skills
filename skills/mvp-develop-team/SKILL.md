---
name: mvp-develop-team
description: Run a tightly scoped startup-style build team for a real MVP. Use when the user wants explicit multi-role execution for a product that must stay buildable in roughly 48 hours by 1 to 2 engineers, with at most 2 core features, concrete architecture, runnable code, and concise role-labeled output.
---

# MVP Develop Team

Optimize for a useful MVP that can actually ship fast.

## Hard Constraints

- fit in 48 hours or less
- at most 2 core features
- keep every section implementable
- prefer commodity tools and APIs
- make assumptions and keep moving
- cut scope instead of defending overdesign

## Required Roles

- `[Workflow Coordinator]`
- `[Product Manager]`
- `[Scrum Master]`
- `[Frontend Engineer]`
- `[Backend Engineer]`
- `[AI/ML Engineer]`
- `[Full Stack Engineer]`

If the user explicitly wants agents and tooling allows it, spawn them. Otherwise simulate the roles while keeping sections separate.

## Workflow

1. `[Product Manager]` defines the MVP in one sharp workflow.
2. `[Workflow Coordinator]` cuts scope and locks it.
3. `[Full Stack Engineer]`, `[Backend Engineer]`, and `[AI/ML Engineer]` define the system.
4. `[Scrum Master]` creates a day-by-day execution plan.
5. Engineers provide runnable implementation details.
6. `[Workflow Coordinator]` closes with integration, local run, deploy, and limitations.

## Quality Bar

Before finishing, verify:
- the scope still fits the 48-hour constraint
- the architecture matches the code
- API shapes match frontend usage
- AI output matches stored data shape
- local run steps are complete
- deployment steps match the stack

## Deliverable

Keep all sections role-prefixed and concrete. Always include:
- scope definition
- architecture
- endpoints
- schema
- AI logic
- execution plan
- implementation details
- integration notes
- local run instructions
- deployment steps
- MVP limitations
