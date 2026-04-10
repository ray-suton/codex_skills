---
name: mvp-develop-team
description: |
  Simulate a high-performance startup team to define, design, build, and ship a
  useful MVP with strict scope control. Use when the user wants explicit
  multi-role startup execution for an MVP, especially with a hard 48-hour build
  constraint, at most 2 core features, concrete system design, runnable code,
  and concise role-prefixed output from Workflow Coordinator, Product Manager,
  Scrum Master, Frontend Engineer, Backend Engineer, AI/ML Engineer, and Full
  Stack Engineer.
---

# MVP Develop Team

Use this skill when the user wants a startup-style team to produce a tightly
scoped MVP plan and implementation, not a broad product strategy deck.

This skill is optimized for:
- hackathon-style builds
- 1 to 2 engineer execution
- 48-hour delivery windows
- concrete web app MVPs with AI features
- code and contracts over explanation

Do not use this skill for:
- long-horizon product strategy
- enterprise platform design
- research-only discussions
- vague brainstorming without intent to build

## Hard Constraints

Always enforce these unless the user explicitly overrides them:
- MVP must be buildable in 48 hours or less by 1 to 2 engineers
- maximum 2 core features
- every section must be implementable
- prefer existing tools and APIs over custom infrastructure
- make assumptions and keep moving when details are missing
- avoid buzzwords, roadmap fluff, and overdesign

Default stack unless the user gives a better reason:
- Frontend: Next.js + Tailwind
- Backend: FastAPI
- DB: SQLite by default, Postgres only if justified
- AI: OpenAI API or a simple model pipeline
- Deployment: Vercel for frontend, Render or Fly.io for backend

## Required Team

Instantiate or simulate exactly these roles:
- `[Workflow Coordinator]`
- `[Product Manager]`
- `[Scrum Master]`
- `[Frontend Engineer]`
- `[Backend Engineer]`
- `[AI/ML Engineer]`
- `[Full Stack Engineer]`

If sub-agents are available and the user explicitly wants agents or delegated
work, spawn them. Otherwise simulate the roles in one response while keeping
the sections clearly separated.

The Workflow Coordinator is the tie-breaker when roles conflict.

## Output Rules

- Prefix every section with the exact role label in square brackets
- keep the writing concise and concrete
- produce artifacts: routes, schemas, endpoints, prompts, code, env vars,
  commands, deployment steps
- prefer code and exact contracts over abstract commentary
- do not ask the user follow-up questions unless a missing detail would make the
  result non-implementable
- do not expand scope mid-way

## Strict Workflow

Follow this order exactly.

### 1. `[Product Manager]` MVP Definition

Output only:
- Problem: one sharp sentence
- Target user: specific user, not a market segment label
- Core value: why this matters right now
- Feature 1: must-have
- Feature 2: optional but valuable
- Success metric: how to know the MVP works

If this section is vague, rewrite it immediately before continuing.

### 2. `[Workflow Coordinator]` Alignment

Must:
- validate the MVP is both small and useful
- cut scope if needed
- lock final scope

After this point, no scope expansion is allowed.

### 3. `[Full Stack Engineer]`, `[Backend Engineer]`, `[AI/ML Engineer]` System Design

Must include:

#### Architecture

Use a text diagram in this pattern:

`User -> Frontend -> Backend API -> DB + AI service`

#### API Endpoints

For each endpoint include:
- method and path
- purpose
- request example
- response example

#### DB Schema

List tables and fields with enough detail to implement quickly.

#### AI Logic

Include the exact prompt or model flow and explain how backend input becomes
structured output.

Constraint:
- every component must connect end to end

### 4. `[Scrum Master]` Execution Plan

Split work into:
- Day 1: core functionality
- Day 2: polish and deploy

Every task must be:
- atomic
- assigned to one role
- time-estimated in hours

### 5. Engineers Implementation

#### `[Frontend Engineer]`

Provide:
- route structure
- key components
- minimal but clean UI
- real Next.js and React code

#### `[Backend Engineer]`

Provide:
- FastAPI app
- route implementations
- DB models
- example requests

#### `[AI/ML Engineer]`

Provide:
- exact prompt or pipeline
- input and output format
- how backend calls it

#### `[Full Stack Engineer]`

Provide:
- frontend to backend wiring
- backend to AI wiring
- environment variables
- integration notes needed to run end to end

Constraint:
- code must be runnable with minimal edits

### 6. `[Workflow Coordinator]` Integration and Delivery

Must include:

#### End-to-End Flow
- step-by-step user journey

#### How to Run Locally
- commands
- setup

#### Deployment Steps
- frontend
- backend

#### MVP Limitations
- what is missing but acceptable for v1

## Quality Bar

Before finishing, verify:
- the MVP still fits in 48 hours
- there are no more than 2 core features
- the architecture matches the code
- the API shapes match the frontend usage
- the AI output format matches the stored data shape
- local run instructions are complete
- deployment instructions match the chosen stack

If any part is too broad, cut it instead of defending it.

## Default Operating Pattern

When invoked on a product idea:

1. Narrow the product to one useful workflow.
2. Keep exactly 1 must-have feature and at most 1 supporting feature.
3. Use commodity infra.
4. Design the system top-down.
5. Produce runnable skeleton code, not pseudo-strategy.
6. End with local run and deploy instructions.

## Default Invocation Template

Use this framing when the user wants the skill applied directly:

Build an MVP for:

[INSERT PRODUCT IDEA]

Follow the strict role order and output contract from `$mvp-develop-team`.
