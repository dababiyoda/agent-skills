> **UNIIMENTE entry (refreshed 2026-11-13).** agent-skills, a fork of `addyosmani/agent-skills`, is an upstream source — role: "Upstream engineering skill source; fork-specific collaboration pointers" — contributing production-grade engineering skills for AI coding agents (a routing description, not ownership or runtime proof). The Kernel's organ map (`docs/opus-maximus/ORGAN_MAP.md`) records its connection to GREG as "Candidate rubric for commissioned coding workers; register as a Capability Genome, attach nothing" (tier: reference).
> Before new or resumed UNIIMENTE work, read the Kernel's one entry guide, [AGENTS.md § Canonical reading order](https://github.com/dababiyoda/uniimente-kernel/blob/claude/greg-full-machine-completion-whgiee/AGENTS.md#canonical-reading-order), on the integration branch `claude/greg-full-machine-completion-whgiee` (at `91aaeca0` when this note was written). That is the branch [the Kernel's work board, dababiyoda/uniimente-kernel#96](https://github.com/dababiyoda/uniimente-kernel/issues/96), acknowledges; read the board's newest comments first, and if they name a different branch, follow the board. The guide routes to [founder Discussion #89](https://github.com/dababiyoda/uniimente-kernel/discussions/89), the complete route to the destination (Body + Organs + Mind) and the collaboration procedure.
> Before editing, post a bounded claim on that board in the form the guide's collaboration procedure gives, and say in it who you are, what you were asked and how you plan to do it (the founder's direction of 2026-11-13 UTC, recorded in Kernel draft #316). A claim is a notice, not a lock and not authority. Record the revision you read in your PR receipt.
> The local rules below still apply. This note governs UNIIMENTE work in this fork only, adds no authority, and is never sent upstream.

# agent-skills

This is the agent-skills project — a collection of production-grade engineering skills for AI coding agents.

> **Scope:** This file configures agents working on the [`addyosmani/agent-skills`](https://github.com/addyosmani/agent-skills) repository itself, not other projects. Don't copy it into another project or a global agent configuration; the reusable assets are the skills in `skills/`.

## Project Structure

```
skills/       → Core skills (SKILL.md per directory)
agents/       → Reusable agent personas (code-reviewer, test-engineer, security-auditor, web-performance-auditor)
hooks/        → Session lifecycle hooks
.claude/commands/ → Slash commands (/spec, /plan, /build, /test, /review, /code-simplify, /ship; plus /webperf specialist audit)
references/   → Supplementary checklists (testing, performance, security, accessibility, observability)
evals/        → Skill eval cases + framework (see evals/README.md)
docs/         → Setup guides for different tools
```

## Skills by Phase

**Define:** interview-me, idea-refine, spec-driven-development
**Plan:** planning-and-task-breakdown
**Build:** incremental-implementation, test-driven-development, context-engineering, source-driven-development, doubt-driven-development, frontend-ui-engineering, api-and-interface-design
**Verify:** browser-testing-with-devtools, debugging-and-error-recovery
**Review:** code-review-and-quality, code-simplification, security-and-hardening, performance-optimization
**Ship:** git-workflow-and-versioning, ci-cd-and-automation, deprecation-and-migration, documentation-and-adrs, observability-and-instrumentation, shipping-and-launch

## Conventions

- Every skill lives in `skills/<name>/SKILL.md`
- YAML frontmatter with `name` and `description` fields
- Description starts with what the skill does (third person), followed by trigger conditions ("Use when...")
- Every skill has: Overview, When to Use, Process, Common Rationalizations, Red Flags, Verification
- Shared references are in the root `references/` directory; the emerging convention for self-contained, distributable skills keeps a skill's own references inside `skills/<name>/references/`
- Supporting files only created when content exceeds 100 lines

## Contributing

Before adding a new skill or significantly reworking an existing one, run the pre-flight checks in [CONTRIBUTING.md](CONTRIBUTING.md#before-proposing-a-new-skill): search the catalog, check open PRs, confirm the idea fits [docs/skill-anatomy.md](docs/skill-anatomy.md), and justify the gap. Prefer extending an existing skill over adding a near-duplicate. CONTRIBUTING.md is the single source of truth for this workflow; do not restate its checklist here or elsewhere, link to it.

## Commands

- `npm test` — Not applicable (this is a documentation project)
- Validate: Check that all SKILL.md files have valid YAML frontmatter with name and description
- Evals: `node scripts/run-evals.js` — trigger/routing evals for every skill (CI); `--behavioral <skill>` for graded runs

## Pull Requests

PRs target the upstream repository's default branch. In a typical fork setup the upstream remote is `upstream` and your fork is `origin`, but the exact remote names are not what matters here.

- Before opening a PR, search the upstream repository's open PRs and issues for work that touches the same files or rules. If any overlaps, coordinate (build on it, align your rules with it, or rebase after it merges) instead of opening a conflicting PR.
- Prefer small, focused PRs over large refactors of widely shared files (for example, files under `scripts/`), which are more likely to collide with in-flight work.

## Boundaries

- Always: Run the CONTRIBUTING.md pre-flight checks before creating a new skill directory
- Always: Follow the skill-anatomy.md format for new skills
- Always: Check the upstream repo's open PRs and issues for overlap before opening a new PR
- Never: Add skills that are vague advice instead of actionable processes
- Never: Duplicate content between skills — reference other skills instead
