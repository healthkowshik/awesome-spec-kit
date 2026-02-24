# Implementation Plan: Initial Curated Resource List

**Branch**: `001-curated-resource-list` | **Date**: 2026-02-24 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `specs/001-curated-resource-list/spec.md`

## Summary

Build the initial awesome-spec-kit README as a curated list of spec-driven development resources across four categories (Tools, Tutorials, Articles, Example Projects), with a contributing guide, awesome-lint compliance, and proper GitHub repository metadata. The primary artifact is a single README.md file conforming to awesome-list conventions.

## Technical Context

**Language/Version**: Markdown (no programming language)
**Primary Dependencies**: awesome-lint (via npx, validation-only — not a project dependency)
**Storage**: N/A (static files in git)
**Testing**: awesome-lint, manual link verification
**Target Platform**: GitHub (rendered Markdown on github.com)
**Project Type**: Curated list (documentation-only)
**Performance Goals**: N/A
**Constraints**: Must pass awesome-lint validation; must comply with constitution principles
**Scale/Scope**: 23 curated resources at launch across 4 categories; growing over time via community PRs

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

### Pre-Design Check

| Principle | Status | Notes |
|-----------|--------|-------|
| I. Quality-First Curation | PASS | All selected resources meet relevance, maintenance, documentation, and non-promotional criteria. See research.md R-005 for selection rationale. |
| II. Consistent Structure | CONFLICT | Constitution specifies em-dash (`—`) in entry format, but awesome-lint requires hyphen-minus (`-`). Resolution: adopt hyphen-minus to pass lint; file follow-up to update constitution. See research.md R-002. |
| III. Link Integrity | PASS | All links will be verified as canonical and live before inclusion. Duplicate detection is part of awesome-lint. |
| Content Standards | PASS | All resources are on-topic, publicly accessible, non-duplicate, and correctly categorized. |
| Contribution Workflow | PASS | This is the initial commit; contributing.md will be created to enable the PR-based workflow going forward. |

### Post-Design Check

| Principle | Status | Notes |
|-----------|--------|-------|
| I. Quality-First Curation | PASS | Resource selection documented in research.md R-005 with rationale per entry. |
| II. Consistent Structure | PASS (with action) | Plan uses hyphen-minus format per awesome-lint. Constitution update deferred to follow-up issue. |
| III. Link Integrity | PASS | Entry format contract (contracts/entry-format.md) enforces canonical URLs. Awesome-lint's `double-link` rule prevents duplicates. |

## Project Structure

### Documentation (this feature)

```text
specs/001-curated-resource-list/
├── plan.md              # This file
├── research.md          # Phase 0: Research findings and decisions
├── data-model.md        # Phase 1: Logical data structure
├── quickstart.md        # Phase 1: Validation and contribution guide
├── contracts/
│   └── entry-format.md  # Phase 1: Entry format contract
├── checklists/
│   └── requirements.md  # Spec quality checklist
└── spec.md              # Feature specification
```

### Source (repository root)

```text
/
├── README.md            # The awesome list (primary artifact — rewritten)
├── contributing.md      # Contribution guidelines (new)
└── LICENSE              # MIT license (existing, unchanged)
```

**Structure Decision**: This is a documentation-only project. No source code directories, build systems, or test suites are needed. The deliverable is two Markdown files at the repository root.

## Key Decisions from Research

| ID | Decision | Impact |
|----|----------|--------|
| R-001 | Conform to all awesome-lint rules | Drives README structure, badge, TOC naming, list item format |
| R-002 | Use hyphen-minus (` - `) not em-dash (` — `) for entry separator | Deviates from current constitution; follow-up needed |
| R-003 | No "License" heading in README | Deviates from spec FR-011's literal wording; satisfied by LICENSE file |
| R-004 | Keep MIT license (don't switch to CC0) | Maintainer decision; awesome-lint only requires *a* license |
| R-005 | 23 initial resources selected (10 tools, 4 tutorials, 4 articles, 5 example projects) | Exceeds FR-012 minimum of 12 |
| R-006 | Set GitHub repo topics and description | Required for awesome-lint's `github` rule |

## Implementation Sequence

### Phase 1: Core List (P1 — Browse Resources)

1. Rewrite `README.md` with:
   - Title case heading with awesome badge: `# Awesome Spec-Kit [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)`
   - One-paragraph introduction describing the list's scope
   - `## Contents` section with anchor links to all categories
   - Four category sections (`## Tools`, `## Tutorials`, `## Articles`, `## Example Projects`) populated with curated entries from research.md R-005
   - Each entry in the format: `- [Name](URL) - Description.`
   - Entries alphabetically ordered within each category
   - `## Contributing` section (brief, links to contributing.md)

2. Create `contributing.md` with:
   - What the list is about
   - Quality criteria for submissions (derived from constitution)
   - Entry format requirements (link to contracts/entry-format.md pattern)
   - PR submission process
   - Review expectations

### Phase 2: Validation & Metadata (P2 + P3)

3. Validate awesome-lint compliance:
   - Run `npx awesome-lint` and fix any issues
   - Verify all links resolve to live, canonical pages

4. Set GitHub repository metadata:
   - Add repo description
   - Add "awesome" and "awesome-list" topics

### Follow-up (out of scope for this feature)

- Update constitution entry format from `—` to `-` (see R-002)
- Consider adding GitHub Actions workflow for automated awesome-lint on PRs
- Consider switching license from MIT to CC0 (maintainer decision)
