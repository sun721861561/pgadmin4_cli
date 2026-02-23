---
name: software-dev-skill
description: API-first software development workflow for backend refactors and feature integration with minimal UI scaffolding. Use when Codex needs to move functionality from frontend-triggered flows to interface-triggered backend endpoints, wire source/target database connections inside service logic, reuse existing modules (for example schema_diff), and deliver testable outcomes such as single-object diffs and full migration SQL generation with local PostgreSQL validation.
---

# Software Dev Skill

Apply a consistent, low-risk engineering workflow from requirement to validated change.

## Workflow

1. Define the target behavior, constraints, and non-goals from the request.
2. Inspect the codebase and identify the smallest safe set of files to modify.
3. Implement a minimal diff that preserves existing architecture unless change is requested.
4. Validate with focused checks first (unit test, lint, type check, or targeted build).
5. Expand validation scope when risk is high or targeted checks fail.
6. Report what changed, what was verified, what could not be verified, and residual risks.

## Decision Rules

- Prefer small, reviewable patches over broad rewrites.
- Preserve backward compatibility unless the request explicitly allows breaking changes.
- Keep naming, style, and project conventions consistent with nearby code.
- Add comments only for non-obvious logic or invariants.
- Avoid speculative refactors that are not needed for the requested outcome.

## Verification Guidance

- Run the narrowest relevant command first.
- Add or update tests when behavior changes or bugs are fixed.
- If tests cannot run, state the exact blocker and the unverified surface area.
- Treat flaky or environment-dependent failures separately from regression failures.

## Communication Contract

- State assumptions explicitly before high-impact edits.
- Call out tradeoffs when multiple valid approaches exist.
- Summarize final output with:
  - changed files and purpose
  - commands run and result
  - known risks and suggested next checks

For a reusable pre-delivery checklist, read `references/delivery-checklist.md`.
