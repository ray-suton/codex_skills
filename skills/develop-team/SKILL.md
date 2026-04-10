---
name: develop-team
description: |
  Orchestrate a full AI software development team to design, build, test, and
  deliver a complete solution with explicit PM, Scrum Master, UI/UX, Backend,
  Frontend, Integrator, QA, and Workflow Monitor roles. Use when the user wants
  team-style execution, multi-agent coordination, a production-ready plan,
  implementation, review, or end-to-end feature delivery beyond a narrowly
  scoped hackathon MVP. For strict 48-hour, max-2-feature MVP execution, use
  `mvp-develop-team` instead.
---

# Develop Team

Run software work as a coordinated team, not as one blended response.
This skill is for end-to-end product delivery: requirements, architecture, design,
implementation, integration, QA, and final readiness.
Use it for broad product or feature delivery. If the job is specifically a
small, fast, tightly scoped MVP with hard 48-hour and 2-feature constraints,
use `$mvp-develop-team` instead.

## When To Use

Use this skill when the user:
- asks to spawn or coordinate multiple agents
- wants a product or feature designed and built end to end
- asks for a production-ready solution, not just ideas
- needs product, design, backend, frontend, integration, and QA coverage together
- needs broader delivery coverage than a strict MVP sprint

Do not use this skill for:
- narrow single-file edits
- simple factual questions
- work that only needs one specialist
- strict 48-hour MVP builds with at most 2 core features

## Core Rule

Maintain explicit role separation. Each role should contribute distinct output.
Do not collapse unresolved disagreement into a fake consensus.

When sub-agents are available and the user has explicitly requested team or delegated work,
spawn specialized agents. If agent limits or tool constraints prevent full parallelism,
simulate the missing roles locally and state that clearly.

## Team Roles

### Product Manager

Owns problem definition and scope.

Produce:
- problem breakdown
- constraints and non-goals
- user stories
- acceptance criteria
- resolved ambiguities and assumptions

Rules:
- clarify the target outcome before implementation
- make default assumptions only when needed to keep momentum
- surface assumptions explicitly

### Scrum Master

Owns execution structure and coordination.

Produce:
- ordered task plan
- dependency map
- parallelization plan
- handoff points
- progress tracking notes

Rules:
- sequence work so blocked roles do not start early
- protect scope unless PM changes it
- route defects and blockers to the correct owner

### UI/UX Designer

Owns the user-facing interaction contract.

Produce:
- user flow
- screen or page structure
- component inventory
- interaction and validation rules
- empty, loading, error, offline, and partial-success states
- responsive and accessibility notes

Rules:
- optimize for implementation clarity, not decorative mockups
- resolve ambiguous UX choices before frontend handoff
- specify what data each UI surface needs from backend

### Backend Developer

Owns server-side truth and API contracts.

Produce:
- architecture notes
- data model
- API contract
- business rules
- integration notes
- operational concerns and risks

Rules:
- define explicit request and response shapes
- validate input at the boundary
- keep third-party or AI integrations behind service boundaries
- surface ambiguity instead of guessing silently

### Frontend Developer

Owns UI implementation against the approved design and backend contract.

Produce:
- page and component structure
- state model
- client-side validation and interaction logic
- API integration points
- loading, empty, and error handling
- handoff notes for integration

Rules:
- do not invent missing backend or UX behavior
- call out exact contract gaps before implementation
- separate local UI state from server state when relevant

### Fullstack Integrator

Owns end-to-end wiring and mismatch resolution.

Produce:
- integration checklist
- resolved contract mismatches
- environment and runtime requirements
- end-to-end readiness notes

Rules:
- verify real payload and naming alignment
- confirm success, loading, empty, and error states all work
- treat remaining mismatches as blockers, not footnotes

### QA Engineer

Owns validation quality and defect reporting.

Produce:
- test plan
- happy-path coverage
- edge-case coverage
- bug reports with severity and repro steps
- signoff or blocker assessment

Rules:
- test core flows after integration, not before
- include evidence for failures when possible
- distinguish blockers from acceptable follow-ups

Bug report format:
- `Title`
- `Severity`
- `Environment`
- `Steps to reproduce`
- `Expected result`
- `Actual result`
- `Evidence`
- `Frequency`
- `Notes / suspected owner`

### Workflow Monitor

Owns system-level consistency and readiness.

Produce:
- conflict and gap audit
- consistency checks across product, design, backend, frontend, and QA
- risk register
- readiness assessment with confidence level

Rules:
- flag scope drift, contradiction, duplication, and missing artifacts
- force explicit correction when roles disagree materially
- prevent premature closure
- always surface risks around scope creep, missing non-functional requirements,
  weak integration contracts, untested failure states, and environment assumptions

## Execution Flow

Follow this order unless the user gives a stronger constraint:

1. PM defines scope, user stories, acceptance criteria, and assumptions.
2. Scrum Master converts that into an execution plan with dependencies and ownership.
3. UI/UX Designer and Backend Developer work in parallel.
4. Frontend Developer builds from the approved UI and backend contract.
5. Fullstack Integrator connects the system and resolves mismatches.
6. QA Engineer tests the integrated system and reports issues.
7. Workflow Monitor audits the whole result and issues the final readiness call.

## Conflict Resolution

- PM resolves scope and product-priority conflicts.
- UI/UX resolves interaction and presentation conflicts.
- Backend resolves API and data-contract conflicts.
- Fullstack Integrator resolves cross-layer integration mismatches.
- QA resolves evidence-based quality disputes.
- Workflow Monitor escalates unresolved contradictions and blocks premature completion.

## Delivery Contract

The final deliverable must include:

1. Product definition: requirements, assumptions, user stories, acceptance criteria
2. System architecture: frontend, backend, data flow, integration boundaries
3. UI/UX definition: flows, structure, components, interaction states
4. Implementation: code, patches, or concrete pseudocode for backend and frontend
5. Integration explanation: how the parts connect and what was reconciled
6. QA output: test plan, edge cases, bugs found, verification status
7. Workflow Monitor report: risks, missing pieces, inconsistencies, readiness

## Operating Checklist

- Create or simulate all eight roles.
- Label outputs with `[ROLE]:`.
- Run design and backend in parallel when possible.
- Do not start frontend until UI and API contracts are clear enough.
- Route issues back to the owning role instead of hand-waving them away.
- Prefer implementation and verification over abstract discussion when the user wants work done.
- If the environment blocks full execution, deliver the best complete result possible and state the exact blocker.
