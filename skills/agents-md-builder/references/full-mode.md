# Full project documentation mode

Use only when the user explicitly asks for Full or asks for project-tracking artifacts. Do not create this set by default.

## Deliverables

- `AGENTS.md` — concise operational entry point: how to work, relevant rules, verified commands, proportional checks, boundaries, completion, and links.
- Relevant product, design (for UI projects), and codebase-map documents when explicitly requested or needed for a recurring purpose, reusing established paths. When a map is needed, it lists high-value paths, responsibilities and where to start for common tasks.
- `docs/ARCHITECTURE.md` — verified components, boundaries, auth/data/persistence flows, and important rationale.
- One human-readable roadmap: reuse the established roadmap or tracker; otherwise use a short section in `PRODUCT.md` when it fits, or a separate `ROADMAP.md` when the task list warrants it or the user requests it. Group concise plain-language task titles under Now, Next and Later where appropriate. Distinguish proposals from commitments, identify blockers, and mark completion only when verified. Link rather than duplicate tasks.
- Interactive architecture diagram of verified frontend/backend/services/stores and flows. Reuse existing tooling; do not add dependencies without approval. Link nodes to code/docs where practical. If interactivity needs disproportionate setup, explain and offer the simplest honest alternative; do not call a static diagram interactive.

Keep responsibilities separate. The diagram and architecture document must agree and must not imply auto-sync unless verified. Mark uncertain edges. Update the roadmap when relevant implementation or priorities change, not on every small edit. Do not invent roadmap priorities or claim completion based only on a plan or code inspection.

On UPDATE, reuse established project doc paths and conventions. Add missing requested artifacts without duplicating existing sources; update affected documents and remove verified obsolete or duplicated material. Check links, consistency, and source-of-truth conflicts.
