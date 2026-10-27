# Cross-session handoffs and project gotchas

For ongoing multi-session work, use one handoff and maintain it while work is active. Respect narrower requested scope and keep AUDIT/EVALUATE read-only. Gotchas are optional and evidence-based.

## Working-state handoff

Use one repo-local `HANDOFF.md`. If an equivalent handoff already exists, reuse its established path instead of creating or renaming files without permission. Update the same file, not dated copies. Do not create a generic `MEMORY.md` by default.

```md
# Working state
Updated: YYYY-MM-DD
Branch/commit: <when useful>
Task: <one-sentence goal>

## Status
- Done: <verified result>
- In progress: <current state>

## Next
1. <next concrete action>

## Decisions / constraints
- <only what affects the next step>

## Relevant files
- `<path>` — <why it matters>

## Verification / blocker
- <checks actually run and outcomes>
- <blocker, if any>
```

Keep it roughly 10–20 lines: a handoff, not a transcript. Update at meaningful milestones and when pausing, while work remains active. State one precise next action, distinguishing confirmed decisions from proposals; a next action is not authorization to implement it. Link to the existing roadmap or tracker instead of copying the backlog; keep durable decisions and gotchas in their owning docs. Never store secrets. Add a short `AGENTS.md` pointer: read the handoff when resuming ongoing work. On resume, verify branch, working tree, and relevant files; treat the note as a pointer, not ground truth. Do not invent progress or next steps.

## Gotchas

Keep a short `## Gotchas` section in `AGENTS.md` only for verified, high-impact, non-obvious traps. Each bullet says the trap and the corrective action. Examples (include only when confirmed in that repo):

- Do not edit `generated/`; regenerate with the verified `pnpm codegen` command.
- Wrap every new API route with the verified authentication middleware.

Do not add generic advice, temporary task notes, or a one-off failed attempt. Remove stale items when the code/workflow changes. If there are more than a few bullets or a gotcha applies only to one subsystem, move it to `docs/GOTCHAS.md` or a scoped `AGENTS.md`; keep a short pointer in the root and load detail only for affected work. During UPDATE/AUDIT, verify existing gotchas and check for duplication. A reusable lesson from a task may be added only when evidence supports it and scope permits.
