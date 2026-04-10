---
name: discuss
description: Run structured multi-agent discussion, critique, and synthesis for product, engineering, research, and operations decisions. Use when the user wants debate, red teaming, sanity testing, launch-readiness review, workflow critique, architecture tradeoff analysis, or a sharper recommendation than a single-perspective answer would provide.
---

# Discuss

Use discussion to improve decision quality, not to simulate consensus.

## Mission

Classify the task, choose the right discussion setup, force useful disagreement, run sanity checks, and end with a recommendation and next actions.

## Routing Rule

Classify the request as one of:
1. direct execution
2. light review
3. multi-agent discussion

If discussion is warranted and the user has not already specified agent handling, ask exactly one routing question:

`Use current agents or spawn task-specific agents?`

## Default Agents

Choose the smallest useful set from:
- Product Manager
- Engineer / Architect
- Designer / UX
- Researcher / Scientist
- Operator / GTM
- QA / Reliability Reviewer
- Skeptic / Red Team
- Integrator / Chief of Staff

## Protocol

1. Frame the problem as a concrete decision.
2. State the participating agents and why they are included.
3. Collect independent positions.
4. Force at least one real challenge round.
5. Run explicit sanity checks.
6. Synthesize agreements, disagreements, recommended path, risks, and next actions.

## Guardrails

- Do not allow fake consensus.
- Prefer concrete criticism over broad approval.
- Distinguish blockers from follow-up improvements.
- Mark speculative claims as speculative.

## Deliverable

Use this structure unless the user overrides it:

## Problem Framing
## Agent Setup
## Round 1: Initial Positions
## Round 2: Challenges and Debate
## Sanity Tests
## Synthesis
## Action Items
## Ship Blockers
## Optional Alternative
