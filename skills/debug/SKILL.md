---
name: debug
description: Diagnose and repair hard software failures with disciplined root-cause analysis. Use when the user reports a bug, regression, flaky behavior, runtime error, bad output, broken integration, or unexplained failure in a real codebase and wants careful tracing, minimal safe fixes, and evidence-backed validation.
---

# Debug

Treat debugging as fault isolation, not guesswork.

## Mission

Build the execution model first, then prove the failure path, then apply the smallest fix that breaks the causal chain.

## Workflow

1. Frame the failure precisely.
- State the user-visible symptom.
- State the expected behavior.
- Note known inputs, environment assumptions, and missing evidence.

2. Read the real execution path.
- Read the entry point, key callers, callees, contracts, and state transitions.
- Follow data flow across boundaries such as UI, API, services, jobs, caches, and persistence.
- Stop only when the causal path is understood end to end.

3. Reproduce or narrow.
- Prefer failing tests, logs, traces, or direct runtime checks.
- If exact reproduction is not possible, narrow the failure envelope with concrete evidence.
- Separate facts from inferences.

4. Identify root cause.
- Test plausible hypotheses against the code and observed behavior.
- Distinguish the first visible break from the underlying defect.
- Reject symptom patches unless containment is explicitly required.

5. Implement the smallest correct fix.
- Preserve intended behavior everywhere else.
- Match local architecture and style.
- Avoid broad rewrites unless structure is the confirmed cause.

6. Validate.
- Run focused checks first, then broader checks if justified.
- Verify adjacent edge cases and likely regressions.
- Add or recommend regression coverage when useful.

## Guardrails

- Do not guess.
- Do not stop at the first suspicious line.
- Do not hide uncertainty.
- Do not fix unrelated problems.
- Prefer maintainable fixes over clever fixes.

## Deliverable

Use this structure unless the user overrides it:

## Summary
State the failure narrowly.

## Root Cause
Explain the actual defect and why it produced the symptom.

## Files / Path
List the relevant files and execution path.

## Fix
Describe the concrete code changes.

## Why It Works
Tie the fix directly to the root cause.

## Risks
State remaining assumptions, regressions, or follow-up checks.

## Validation
List tests run, manual checks performed, and recommended regression tests.
