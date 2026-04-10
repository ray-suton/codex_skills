---
name: fix-bug
description: Fix a concrete reported bug end to end in a real codebase. Use when the user provides a bug report, stack trace, failing test, broken workflow, or incorrect behavior and wants the directly relevant path traced completely, the full bug cluster repaired, and the result validated in a strict engineering handoff.
---

# Fix Bug

Treat the reported path as a repair job, not a narrow explanation task.

## Mission

Read the failing path end to end, find the real defect, fix all directly related breakages required for that path to work, and verify the result.

## Workflow

1. Clarify the bug.
- Restate expected behavior, actual behavior, trigger conditions, and impacted surfaces.
- Note ambiguities instead of smoothing over them.

2. Read the full relevant path.
- Start with the reported surface, then read callers, callees, contracts, tests, and final consumers.
- Follow state, data, and control flow until the broken path is fully understood.
- If the path crosses layers, read every touched layer.

3. Reproduce or construct the strongest evidence path.
- Prefer direct reproduction.
- Otherwise use logs, tests, traces, and code evidence to explain the failure precisely.

4. Isolate the root cause.
- Distinguish the underlying defect from downstream symptoms.
- Consider multiple hypotheses when needed and eliminate them with evidence.

5. Fix the bug cluster.
- Implement the smallest viable complete fix.
- Repair adjacent mismatches in the same path when leaving them would keep the workflow broken.
- Preserve unrelated behavior and public contracts by default.

6. Validate.
- Run the most relevant tests or runtime checks.
- Verify the originally reported path plus obvious nearby regressions.
- Add or recommend regression coverage when justified.

## Guardrails

- Do not patch blindly.
- Do not stop at the first plausible defect.
- Do not leave the reported path half-fixed.
- Do not broaden scope into cleanup unless it is required for correctness.

## Deliverable

Use this structure unless the user overrides it:

## Bug Summary

## Expected vs Actual Behavior
- Expected:
- Actual:

## Root Cause

## Files Involved

## Fix

## Why This Works

## Risks / Side Effects

## Tests
- Existing checks run
- New regression test added or recommended
- Edge cases to verify
