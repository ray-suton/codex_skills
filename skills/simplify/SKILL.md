---
name: simplify
description: |
  Systematically reduce unnecessary code complexity while preserving behavior.
  Use when a repository has spaghetti code, duplicated logic, deeply nested
  control flow, bloated functions, dead code, confusing abstractions, or
  inconsistent patterns that should be simplified with small, reviewable,
  high-confidence refactors. Prefer this skill for requests like "simplify
  this code", "clean up this module", "reduce complexity", "untangle this",
  or "refactor safely without changing behavior".
---

# Simplify

Reduce complexity without turning the codebase into a science project.
Prefer explicit, boring, readable code and small behavior-preserving changes.

## Workflow

### 1. Find the real hotspots
Inspect the repo before editing.
Prioritize areas with one or more of these signals:
- very large functions or files
- repeated near-duplicate logic
- deep nesting or convoluted branching
- vague naming that hides intent
- dead helpers, obsolete indirection, or unused code paths
- modules that are hard to test because side effects are mixed into logic

Do not spread work across the whole repo.
Choose 1 to 3 high-value areas for a pass.

### 2. Define the simplification target
Before editing each area, state briefly:
- what is currently making the code hard to reason about
- what small refactor will improve it
- what behavior must stay unchanged

If a module looks too risky to refactor directly, stop short of large edits.
Document the problem and suggest the safest follow-up plan instead.

### 3. Simplify with small, readable edits
Prefer these changes:
- split large functions into focused helpers
- flatten deep nesting with guard clauses or clearer control flow
- merge duplicate or near-duplicate logic into one simple path
- replace ad hoc patterns with a more consistent local structure
- delete dead code, unused helpers, and stale branching
- rename vague identifiers when that improves clarity materially
- reduce hidden side effects when it can be done safely

Avoid these traps:
- cosmetic-only rewrites
- clever abstractions that save lines but cost readability
- wide API changes unless there is a strong reason
- speculative cleanup outside the chosen hotspots

### 4. Protect behavior
Keep behavior unchanged unless a bug is clearly being fixed.
When behavior is subtle or untested, add or update tests before or during the refactor to lock it in.
Preserve public APIs by default.

### 5. Verify immediately
Run the most relevant checks after each hotspot or at the end of the pass:
- focused tests first
- then broader tests, lint, and type checks if they are relevant and available

If verification cannot run, say exactly what was not run and why.

## Refactoring Heuristics

Use these biases:
- local helper over reusable abstraction
- straight-line code over nested branching
- one obvious data flow over hidden mutation
- clear names over terse names
- delete code when it is provably unused
- smallest meaningful diff over ambitious cleanup

## Output Expectations

When using this skill, produce:
- a brief list of the hotspots chosen
- the simplification made in each area
- the verification that was run
- any risky areas deliberately left unchanged
- remaining technical debt worth tackling later

## Review Standard

A simplification is successful when:
- the code is easier to read in one pass
- the control flow is easier to explain
- the diff is easy to review
- tests still pass or behavior is otherwise verified
- no new abstraction needs a long explanation
