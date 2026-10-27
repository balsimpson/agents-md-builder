---
name: agents-md-builder
description: Use when creating, updating, or evaluating AGENTS.md.
version: 0.5.0
author: gb, Hermes Agent
license: MIT
platforms: [linux, macos, windows]
metadata:
  hermes:
    tags: [AGENTS.md, repository-guidance, code-maps, agent-instructions, testing]
    related_skills: []
---

# AGENTS.md Builder

Create concise, evidence-based agent guidance. `AGENTS.md` is an operational map, not a README, architecture dump, or exhaustive inventory. Inspect the repository; never invent paths, commands, architecture, policies, or test results.

## When to use

Use when asked to create, update, review, audit, or evaluate `AGENTS.md` or the repository's setup for effective coding-agent work.

## Modes

Choose CREATE, UPDATE, AUDIT, or EVALUATE.

- **CREATE:** No useful target exists. Inspect first; create only verified, project-wide guidance and a compact map.
- **UPDATE:** Read existing guidance first. Retain accurate, useful current guidance; remove verified obsolete or duplicate material rather than preserving it for legacy reasons. Replace or relocate material to its single owner when needed. Do not regenerate wholesale unless the structure is unsuitable. Account for meaningful removals and investigate uncertain conflicts.
- **AUDIT:** Assess repository agent-readiness and existing AGENTS/documentation without editing. Load [Evaluation](references/evaluation.md), inventory existing guidance, score the assessment, and deliver the structured report. Preserve all existing documents and files; recommend improvements in place without deleting, moving, or replacing files unless the user separately authorizes it.
- **EVALUATE:** Assess how well the repository is set up for efficient coding-agent work and return prioritized, evidence-backed improvements without editing. Load [Evaluation](references/evaluation.md); assess only dimensions relevant to the user's requested scope.

## Engagement level

Default to **BASIC**. Use **FULL** only when the user asks for it or clearly requests project-tracking artifacts. Keep each document's role distinct.

- **BASIC:** Create or maintain a concise root `AGENTS.md` when in scope. Reuse and maintain relevant existing product, map and design documents at their established paths. Create a companion document only when it addresses a clear recurring need not already served, or the user explicitly requests it; use `PRODUCT.md`, `CODEBASE_MAP.md`, or `DESIGN.md` as appropriate. Do not create documents just to satisfy a template. Respect explicit narrower scope; do not write in AUDIT/EVALUATE. For a new UI project, use confirmed intent and mark unknowns; do not invent a design system.
- **FULL:** All BASIC documents, plus verified architecture, an evidence-based roadmap, and an interactive architecture diagram. Read [Full mode](references/full-mode.md) before producing or maintaining this set.

Load [Product brief](references/product-brief.md) when creating or maintaining product guidance. For evaluation/audit of agent readiness, load [Evaluation](references/evaluation.md). For cross-chat handoffs or gotchas, load [Handoffs and gotchas](references/cross-session-and-gotchas.md). Apply [Nuxt profile](references/nuxt-profile.md) only when the project is Nuxt. Load [Validation and quality](references/validation-and-quality.md) for FULL mode, a detailed audit, or when the task needs the extended checklist; the core validation steps below apply to every mode.

## Procedure

### 1. Establish scope and compatibility

Identify repository root, target file(s), mode (CREATE, UPDATE, AUDIT, or EVALUATE), engagement level, project shape (single app/monorepo/subtree), and existing root/nested instruction files. Respect the user's requested scope. In EVALUATE mode, do not edit; inspect evidence and report improvements.

Before relying on nested `AGENTS.md`, imports, aliases, or companion files, check the target coding agent's current documentation for file discovery, loading, and precedence. These behaviors vary by tool; do not present one tool's behavior as universal. Consult current primary docs only when tool compatibility or other technical behavior is version-sensitive. In audits, distinguish files found, files expected to load based on documented behavior, files confirmed loaded by runtime evidence, and unknown loading status; check applicable overrides and conflicts.

### 2. Inspect only what this task needs

Treat agent time, tool calls, and context as limited. Begin with applicable instructions and the narrowest relevant map/search. Expand only when evidence shows the task crosses a boundary.

- **Small localized change or narrow audit:** inspect the target file and directly relevant neighbors; search for the named page/component/symbol. Do not read unrelated architecture, roadmap, backend, or all config files.
- **New feature/subsystem or architecture work:** inspect the relevant entry points, interfaces, data/auth boundaries, and the docs that own those decisions.
- **CREATE/FULL project documentation:** inspect the high-signal sources needed for requested deliverables: manifests/lockfiles, scripts, test and CI configuration, entry points, major subsystem boundaries, and existing architecture/product docs. Do not read the whole repository by default.

Read commands from manifests or CI when command guidance is needed. Stop discovery when the responsible code/areas and required claims have enough evidence. For small UI/style changes, do not run typecheck/build/full suites by habit; choose a proportionate check. Do not repeat a failed operation unchanged: inspect the error, change the hypothesis, and if another materially different attempt fails, stop and report the blocker unless new evidence supports another path.

### 3. Build the map and actionable rules

Assign each fact one authoritative home; link instead of copying. `AGENTS.md` is the operational entry point; product guidance owns positioning and expected flows; design guidance owns current direction and reusable UI patterns; the codebase map owns navigation to important files and symbols. For ongoing projects, ensure one human-readable place for planned work: use an existing roadmap or tracker, or a short roadmap in `PRODUCT.md`; create a separate `ROADMAP.md` only when the list warrants it or the user requests it. Keep `HANDOFF.md` for the immediate session state and link to the roadmap rather than duplicating it. Use existing established paths. Before creating or editing, check nearby docs for equivalent material, reconcile conflicts against code and confirmed product decisions, and remove verified obsolete or redundant text. Do not silently resolve uncertain product intent; label unknowns or ask. Do not invent positioning, user flows, commitments or implementation status.

Map user-visible areas and common tasks to verified route, component and relevant composable/function paths and stable text or symbol search anchors. Include important shared components, utilities and ownership. Avoid exhaustive inventories and hard-coded line numbers; search current source for the actual line. Code is authoritative for implementation; confirmed product/design decisions own intent, which may differ from current code and must be labeled accordingly.

For UI projects, design guidance records the confirmed current direction, token and component locations, variants, states, usage and representative examples. Document existing inconsistencies instead of inventing a standard. Existing component code and tokens are the implementation source of truth. Link from `AGENTS.md`; require agents to read relevant design guidance before creating or materially changing reusable UI, not for every local spacing tweak.

Include a reuse-first rule for new features: consult the map and narrowly search for relevant components, composables, functions and utilities; inspect likely candidates and callers. Reuse as-is, or extend/refactor the correct shared owner where safe. Create new code only when existing code has a different responsibility or cannot fit safely. Check affected callers and relevant behavior when changing shared code; avoid broad redesign for a page-specific tweak.

Include a small-UI-change fast path: start with the supplied page, file, screenshot, visible text or map landmark; search within the likely area for text, symbol or class, inspect the match in context, check shared impact, make the smallest change and verify the diff plus a targeted or visual check when appropriate or requested. Expand search only when evidence requires it. Do not require full design/product reads, broad repository scans, full builds or test suites for a local class change by default; follow explicit project policy.

Record only high-value landmarks (for example, routes, UI, composables/hooks, state, business logic, API/services, persistence/schema, tests, and key configuration). State what each area owns and where to start for common tasks. Prefer exact repo-relative paths and useful symbols. Do not create an exhaustive tree.

Include only rules that change behavior: verified commands; where logic belongs and patterns to reuse; relevant auth/data flows; dependencies/state access; security and generated-file boundaries; approval-sensitive actions supported by user/repo policy; proportional verification; documentation lookup; completion criteria. Every rule must imply an observable action. Do not invent approval rules; ask if a material boundary is unclear.

Link only existing or explicitly requested reference docs. Point to the owning document rather than duplicating detailed specifications. Keep specialized guidance in scoped files and tell agents when to load it. Root `AGENTS.md` should usually start around 50–100 lines (flexible, not a hard cap).

### 4. Validate and deliver

In every mode, verify paths, commands against scripts/CI, links, scope, contradictions, and secrets. For UPDATE, account for removed content. Load [Validation and quality](references/validation-and-quality.md) only for FULL mode, detailed audits, or when its extended checklist is needed. Distinguish configured/documented checks from commands actually run. Never claim unrun tests, builds, or checks. State unresolved assumptions and blocked checks.

## Maintenance rules to include in generated guidance

- At completion of each change, assess which owned docs are affected; update them in the same task when the product flow, confirmed positioning/roadmap, design direction, shared pattern or relevant code ownership changes. A local spacing tweak needs no doc edit unless it changes a documented standard. Report any doc update blocked or deferred.
- When direction changes, replace superseded guidance; when important components, composables or files are added, moved, removed or change responsibility, update the map and relevant design reference. Remove verified obsolete paths, old patterns and duplicate claims instead of keeping them for legacy reasons. Do not delete still-valid constraints or undocumented live behavior merely because they look old; check evidence and flag uncertainty.
- Consult the map before broad searches; search narrowly from its landmarks when possible. Reconcile affected docs with code and confirmed intent, verify links and remove duplication. Code inspection alone cannot establish a new product or design decision.
- Keep Gotchas short, verified, and actionable; move subsystem-specific detail to a linked/scoped file when needed (see [Handoffs and gotchas](references/cross-session-and-gotchas.md)).
- For ongoing work, maintain one concise repo-local `HANDOFF.md` (reuse an existing equivalent instead of creating a duplicate). Update it at meaningful milestones and when pausing; read it on resume and verify the current repository state before relying on it. A proposed next step is not permission to implement it. See [Handoffs and gotchas](references/cross-session-and-gotchas.md). AUDIT/EVALUATE remain read-only.

## What not to encode

Avoid exhaustive file trees, generic advice, temporary task notes, copied framework documentation, long API/schema specs, fast-changing details better kept by code, rules fully enforced by tooling unless agents need them, secrets, speculative architecture, and unneeded history. If it needs detail, link a stable relevant doc.
