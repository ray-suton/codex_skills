---
name: simplify
description: Reduce code complexity without changing intended behavior. Use when the user asks to simplify, clean up, untangle, de-duplicate, or safely refactor a module with bloated functions, deep nesting, dead code, confusing abstractions, or inconsistent local patterns and wants a small, reviewable, behavior-preserving cleanup pass.
---

# Simplify

Favor obvious code, small diffs, and preserved behavior.

## Mission

Choose a few high-value complexity hotspots, make the smallest refactors that materially improve readability, and verify that behavior stays intact.

## Workflow

1. Pick hotspots.
- Prioritize large functions, duplicated logic, deep branching, dead paths, and hard-to-test code.
- Keep the pass local. Do not spread across the whole repo.

2. Define the simplification target.
- State what makes the area hard to reason about.
- State the smallest refactor that improves it.
- State what behavior must not change.

3. Refactor conservatively.
- Split focused helpers.
- Flatten control flow.
- Merge duplicate paths.
- Delete dead code.
- Rename only when it materially improves clarity.

4. Protect behavior.
- Preserve public contracts by default.
- Add or update tests when the behavior is subtle or risky.

5. Verify.
- Run focused checks first.
- Run broader checks only when justified and available.

## Guardrails

- Do not do cosmetic rewrites.
- Do not introduce abstractions that need explanation.
- Do not expand scope because a cleanup is going well.

## Deliverable

Report:
- hotspots chosen
- simplifications made
- validation performed
- risky areas deliberately left unchanged
- remaining debt worth tackling later
