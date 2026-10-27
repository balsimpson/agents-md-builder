# Validation and quality guidance

## Validate claims and preserve curated guidance

- Verify exact documented paths against the repository and commands against manifests/CI. Distinguish configured/documented commands from commands actually executed. Run a command only when the user requests execution, it is needed to validate a claim, or repository policy requires it; do not run every project check by default.
- For UPDATE, compare before/after content. Account for meaningful removed or changed instructions: retain valid material, relocate it to its single owner, or verify it is obsolete or redundant and remove it. Do not retain obsolete content for legacy reasons or discard useful current guidance merely to meet a line target.
- Check package-manager instructions against lockfiles/manifests and relevant README onboarding steps. Reconcile confirmed user preferences across touched docs; do not leave contradictory alternatives.
- Check links, nested scope, contradictions, secrets, and stale claims. Omit uncertain claims or label them.

## Proportional verification

Use the smallest relevant check first. Small style-only changes may need a focused visual or targeted check. Changes to shared behavior, auth, persistence, data integrity, or architecture may need targeted tests plus broader typecheck/build/integration checks. Follow repository policy and CI. Tests should detect plausible regressions and assert observable outcomes, including important error/edge behavior. Prefer deterministic tests, avoid private implementation coupling unless contractual, and do not weaken/delete meaningful tests to make a suite pass. Report checks run and blocked/omitted checks honestly.

## Documentation lookup

For unfamiliar or version-sensitive framework/library/API behavior, inspect installed versions and consult current primary documentation matching those versions. Use release/migration notes where relevant, explain conflicts with repository reality, and label assumptions. Do not browse for stable facts already in the repo or trivial edits. Include external links in AGENTS.md only when they materially help future agents.

## Optional root outline

Use only supported sections; omit empty sections. Keep root `AGENTS.md` around 50–100 lines as a flexible target, not a limit. Keep it an index of high-value landmarks, not a full inventory. Move detailed or fast-changing material into linked docs or nested AGENTS.md files.

```md
# AGENTS.md
## Project
## Commands
## Project map
## Implementation references
## Working rules
## Gotchas (only if needed)
## Verification
## Maintaining this file
## Completion requirements
```

## Completion checklist

- Identified CREATE/UPDATE/AUDIT/EVALUATE and BASIC/FULL.
- Inspected repo root and applicable existing instructions.
- Paths, commands, package manager, important symbols, and references are verified or qualified.
- Project map includes only useful landmarks; framework guidance applies only to the detected stack.
- Rules are actionable, evidence-based, concise, scoped, and non-contradictory.
- UPDATE accounted for meaningful removals, retained useful current guidance, and removed verified obsolete or duplicated claims.
- Relevant existing product, map and design guidance is reused; new companion documents meet an explicit request or a clear recurring need not already served. Owners, paths, links and unknown decisions are clear; no duplicate source of truth.
- Boundaries reflect user/repo policy; do not invent approval rules.
- Gotchas and working-state handoffs are concise, relevant, current, and not duplicated.
- Verification is risk-proportionate; no test/check is claimed unless run.
- FULL roadmap and diagram have evidence/source basis, agree with architecture docs, and do not create competing sources of truth.
- Final handoff states files changed, checks performed, and unresolved assumptions.
