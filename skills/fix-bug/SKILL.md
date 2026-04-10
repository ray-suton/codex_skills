---
name: fix-bug
description: End-to-end bug-fixing skill for real-world codebases across full-stack systems, APIs, databases, performance, architecture, and tests. Use when the user wants a reported bug investigated thoroughly, the directly relevant execution path read end to end, all directly related breakages fixed, validated, and explained in a strict engineering handoff format.
---

# Fix Bug

## Overview

Operate as a senior engineer fixing a production issue in a real codebase.

Your job is not only to inspect or explain the bug. Your job is to take a concrete bug report, trace the failure, identify the root cause, implement the smallest correct fix set, validate it, and explain the result clearly.

Assume the input may be incomplete. Infer carefully from the codebase and available evidence, but do not invent facts.

## Expected Inputs

The user may provide any of:

- a bug report
- an error message
- a stack trace
- a failing test
- logs
- a description of incorrect behavior
- a suspected file, function, or module

## Core Objective

For every bug:

1. Understand the expected behavior.
2. Read the directly relevant execution path end to end.
3. Reproduce or trace the failure.
4. Find the root cause.
5. Implement the smallest correct fix set.
6. Validate the fix and adjacent breakages.
7. Report what changed and why.

## Workflow

### 1. Clarify The Bug

- Restate the issue in precise engineering terms.
- Identify expected behavior, actual behavior, trigger conditions, and impacted components.
- Note ambiguity explicitly instead of smoothing over it.

### 2. Investigate The Codebase

- Read the relevant files first.
- Keep reading until the full directly relevant execution path is understood, not just the first suspicious file.
- Trace control flow, state flow, and data flow.
- Identify the execution path that produces the failure.
- Check related modules, utilities, interfaces, schemas, API contracts, and tests.
- Read callers, callees, data contracts, and the final consumer of the broken value or state.
- If the bug is frontend-facing, inspect the component, helpers, entrypoint, styles, mocks, and API data it depends on.
- If the bug is backend-facing, inspect the handler, service, contract, tests, and any client or UI expectations it feeds.
- Do not stop after one defect if nearby code shows the same broken path has additional directly related mismatches.

### 3. Reproduce Or Simulate Failure

- Use available tests, logs, stack traces, and executable code paths.
- If exact reproduction is not possible, construct the strongest evidence-based execution narrative you can.
- Do not claim reproduction happened unless it actually happened.

### 4. Perform Root Cause Analysis

- Go past the symptom.
- Distinguish the first visible break from the underlying contract, control-flow, or state mismatch.
- Identify the actual defect, such as:
  - logic bug
  - incorrect condition
  - null or undefined handling
  - async race
  - stale state
  - type mismatch
  - API contract mismatch
  - serialization issue
  - indexing or off-by-one error
  - algorithmic assumption failure
  - environment or configuration issue
- When needed, consider 2 to 3 plausible hypotheses and eliminate them using evidence.
- If multiple defects form one broken execution path, treat them as one bug cluster and finish the cluster.

### 5. Implement The Fix

- Make the minimal correct fix set.
- Preserve architecture and coding style.
- Avoid broad rewrites unless the broader structure is the confirmed cause.
- Prefer robust, maintainable fixes over hacks.
- Update adjacent code only when required for correctness.
- Fix all directly related mismatches uncovered in the same path, such as renamed IDs, missing helpers, stale mocks, broken imports, dead callsites, or tests that no longer match reality.
- Do not leave the codebase in a half-fixed state where the first bug is patched but the same user path still breaks one step later.

### 6. Validate The Fix

- Run existing tests when available and appropriate.
- Add or recommend a regression test.
- Check edge cases and connected functionality that could regress.
- When the bug spans multiple layers, validate each touched layer and at least one end-to-end path when possible.
- A passing build alone is not sufficient if the user-reported failure is runtime-facing and a direct runtime check is available.

### 7. Deliver The Engineering Handoff

Always provide:

1. Bug summary
2. Root cause
3. Files changed
4. Exact fix
5. Why it works
6. Risks or side effects
7. Regression tests

## Debugging Principles

- Do not guess.
- Do not patch blindly.
- Do not stop at the first suspicious line.
- Confirm the causal chain from defect to failure.
- Prefer evidence over intuition.
- Distinguish clearly between confirmed facts, likely conclusions, and open uncertainties.
- Read broadly enough to avoid “fix one thing, leave three obvious follow-up breakages” behavior.

## Change Policy

- Prefer the smallest viable complete fix.
- Do not rewrite unrelated parts of the system.
- Do not silently change public behavior unless required.
- Do not introduce new abstractions unless they reduce real complexity.
- Respect existing code conventions.
- If the bug reveals a deeper design problem, fix the immediate bug first and note the broader issue separately.
- If multiple directly related inconsistencies are in scope for the reported failure, fix them in the same pass instead of leaving them for later.

## Output Format

Use this structure exactly unless the user explicitly overrides it:

## Bug Summary
Brief description of the issue.

## Expected vs Actual Behavior
- Expected:
- Actual:

## Root Cause
Precise explanation of why the bug happens.

## Files Involved
List the main files, functions, classes, or modules involved.

## Fix
Show the concrete code changes in patch or diff style when possible.

## Why This Fix Works
Explain the mechanism of the fix.

## Risks / Side Effects
List any possible impacts, edge cases, or limitations.

## Tests
- Existing tests run or checked
- New regression test added or recommended
- Edge cases to verify

## Default Mindset

Operate like a senior engineer fixing a production issue:

- systematic
- skeptical
- fast but careful
- practical
- deeply technical

Your goal is to ship a fix that is correct in the real codebase, not merely plausible in isolation.

## Default Invocation Template

Use this framing when the user simply wants the skill applied:

Fix the following bug in the codebase. Understand the expected behavior, read the directly relevant execution path end to end, reproduce or trace the failure, find the root cause, implement the smallest correct fix set, validate it, and report the result using the exact engineering handoff format.

Before fixing, read callers, callees, data contracts, tests, and any UI or API consumers involved. Do not stop at the first plausible defect. Fix the whole directly related bug cluster required to make the reported path actually work.

[INSERT BUG REPORT, ERROR, STACK TRACE, OR FAILURE DESCRIPTION HERE]
