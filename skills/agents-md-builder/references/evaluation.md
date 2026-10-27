# Repository agent-readiness evaluation

Use this workflow when the user asks to evaluate/audit a repository for agent effectiveness or asks how to improve its `AGENTS.md` and supporting guidance. This is an assessment, not permission to edit. Do not modify files unless the user separately asks you to implement the recommendations.

## Scope and evidence

1. Clarify the evaluation target from the request: root `AGENTS.md`, a subsystem, or repository-wide agent readiness. Avoid expanding to general code quality or security review unless requested.
2. Inventory existing root and nested agent instructions and relevant documentation by repo-relative path, including existing maps, product/design docs, architecture, roadmaps and handoffs where present. Inspect instruction files and linked docs first, then only the manifest/scripts/CI/source paths needed to verify claims and identify agent-workflow gaps. Do not read the whole repo or run the entire test suite as a default audit. Report what was found, what was actually read, and discovery limits; do not claim an exhaustive inventory if discovery was restricted.
3. Preserve every existing file during the assessment. Recommend improvements to existing owners in place; do not propose deleting, moving, or wholesale replacement of files as a default. If consolidation would help, suggest linking or removing duplicate text while retaining files, and flag conflicts for review. File deletion, relocation or replacement requires separate explicit permission.
4. Check the target agent's current discovery and precedence behavior when nested files, imports, overrides, or companion files matter. Report separately which files were found, expected to load per current primary documentation, confirmed loaded by runtime evidence, or have unknown loading status. Check applicable conflicts; do not assume every tool consumes the same files or imply a file loaded just because it exists.
5. Ground findings in concrete evidence: exact file/section/path, command or contradiction. Label each finding Verified, Likely risk, or Needs testing; separate verified defects from potential improvements and unknowns. Do not claim the agent actually wastes time or loops based only on documentation; frame those as risks unless execution traces or user reports demonstrate them.
6. For each important instruction, ask what decision it changes and whether it needs to apply to every task. Flag blanket broad reads, full test suites, or document updates on trivial changes when not required by project policy. Treat questionable rules as review candidates, not proof of waste or permission to remove them; preserve useful safety rules and project knowledge. Do not recommend or run before/after representative-task comparisons as part of the audit.

## Evaluation rubric

Assess only relevant dimensions:

- **Scope and brevity:** root instructions contain repo-wide, non-obvious rules; no generic filler or detail that should be linked.
- **Navigation:** map paths exist, identify ownership/common edit points, and avoid broad-search-first workflows.
- **Commands and environment:** package manager, runtime constraints, working directory, scripts, and CI checks agree.
- **Architecture:** important business/data/auth boundaries and existing patterns are findable and accurate.
- **Boundaries and gotchas:** verified generated-file rules, safety/approval boundaries, and recurring costly traps; no speculative or stale warnings.
- **Efficiency:** task-sized file discovery and verification; no blanket full-suite checks for trivial changes; clear stop/retry behavior; no duplicate docs that force irrelevant reads.
- **Maintenance and continuity:** meaningful map/doc updates, concise cross-session handoff when useful, and one source of truth for backlog/status.
- **Tool compatibility:** file naming, discovery, nesting, and import assumptions match the intended coding agent(s).
- **Full-mode artifacts (only if requested or already present):** map, architecture, roadmap, and diagram are evidence-based, linked, consistent, and maintained without competing sources of truth.

## Scoring

For repository-wide AUDIT or EVALUATE, score five dimensions from 0–4: (1) instruction clarity and scope, (2) navigation and architecture, (3) commands and verification, (4) boundaries and agent efficiency, and (5) documentation consistency and maintenance. Give 0 = absent or actively misleading, 1 = major gaps, 2 = mixed, 3 = sound with specific gaps, 4 = strong and verified. Cite evidence and explain each rating briefly. Score only what the evidence supports; mark insufficient evidence as Unknown and irrelevant dimensions as N/A, never as zero. Calculate the overall score as earned points / maximum points for scored dimensions × 100; state the scored dimension count and label the total provisional if any relevant dimension is Unknown. If no dimensions can be scored, give no overall score. For a narrow audit, score only applicable dimensions and clearly label the limited scope; do not imply a whole-repo score.

## Report format

Use these headings in order:

1. **Verdict and score:** overall score, scored scope, provisional status and the highest-impact 2–4 findings.
2. **Existing files and coverage:** repo-relative paths grouped by purpose, what was inspected, uninspected items and discovery limits; explicitly state that the audit made no changes.
3. **Score breakdown:** each dimension, rating, brief evidence and any Unknown/N/A status. Explain that the score reflects documented readiness, not measured agent performance.
4. **Prioritized recommendations:** concrete findings in High / Medium / Low order, using the fields below and naming the existing file to improve or an explicitly justified new file.
5. **Keep and next steps:** strengths and existing documents to preserve, assumptions or blocked checks, and a short implementation order. Clearly distinguish recommendations from changes actually made.

For each finding include:

- **Priority and evidence status:** High / Medium / Low and Verified / Likely risk / Needs testing. Reserve High for likely wasted work, incorrect commands, serious safety/architecture risk, or invalid instruction claims.
- **Evidence:** exact path and section, observed conflict, or missing artifact relevant to the requested scope.
- **Impact:** what an agent is likely to do wrong, waste, or miss.
- **Improvement:** specific change and proposed target file. For the highest-priority findings, give a short proposed wording or concrete before/after instruction when evidence permits; label it as a proposal, not an applied edit.
- **Effort:** XS / S / M / L, as a rough estimate only.

Avoid generic advice. Do not rewrite or apply changes in AUDIT or EVALUATE mode; implementing any recommendation requires separate user authorization.
