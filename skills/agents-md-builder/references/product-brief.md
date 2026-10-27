# Pairing AGENTS.md with a product brief

Use when creating or maintaining product guidance, or when the user asks for a product brief with AGENTS.md. Reuse an existing product document and its established path rather than creating a duplicate. Create a new one only for a clear recurring need not already served or when explicitly requested.

- Put confirmed product positioning, intended user flows and MVP boundaries in `PRODUCT.md` or the established product-spec location. Add interaction requirements and acceptance scenarios when supported and useful. Clearly separate confirmed plans, current implementation and unknowns; ask or mark unknown rather than inventing decisions.
- For an ongoing project, maintain one easy-to-find source for planned work: reuse the established roadmap or tracker; otherwise put a short roadmap in `PRODUCT.md` when it fits, or create `ROADMAP.md` if the task list warrants a separate file or the user requests it. Link to the owner; do not duplicate tasks in the handoff or across documents.
- Make the roadmap readable at a glance: group short plain-language task titles under Now, Next and Later when appropriate, using checkboxes or equally clear status labels. Add a brief note only when needed; avoid IDs, technical essays and invented priorities. Distinguish proposals from agreed work, mark completion only when verified, show blockers when relevant, and update when work or priorities change.
- Keep `AGENTS.md` operational and link to the product and architecture references. Do not duplicate the product spec.
- Inspect existing handoffs/docs for overlap. Name the source of truth for new product decisions if guidance conflicts; preserve valid technical constraints unless the user approves a change.
- Separate desired behavior from current implementation. Mark code-inspected capabilities as unverified until exercised; types/import branches alone do not prove runtime support.
- Keep to the agreed MVP and name deferred scope. Prefer the simplest sufficient design over speculative extensibility.

Completion condition: future agents can find the product contract through `AGENTS.md` without treating it as a duplicate.
