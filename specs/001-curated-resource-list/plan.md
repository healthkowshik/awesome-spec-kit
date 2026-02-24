# Implementation Plan: Initial Curated Resource List

**Branch**: `001-curated-resource-list` | **Date**: 2026-02-24 | **Spec**: [spec.md](spec.md)
**Input**: Feature specification from `/specs/001-curated-resource-list/spec.md`

## Summary

Rewrite the README.md to be a sharply focused awesome list of GitHub spec-kit resources, organized into four categories (Spec-Kit Ecosystem, Guides, Articles, Community Projects). Update contributing.md to reflect the narrowed scope. This replaces the previous broad "spec-driven development" list with a curated collection strictly about spec-kit and its SDD methodology.

## Technical Context

**Language/Version**: Markdown (no programming language)
**Primary Dependencies**: awesome-lint (via npx, validation-only — not a project dependency)
**Storage**: N/A (all data is Markdown in README.md)
**Testing**: awesome-lint + manual link verification
**Target Platform**: GitHub (rendered Markdown)
**Project Type**: Documentation / curated list
**Performance Goals**: N/A
**Constraints**: Must pass awesome-lint; all links must be live and canonical
**Scale/Scope**: 60+ candidate resources identified; list grows organically on daily cadence

## Constitution Check

*GATE: Must pass before Phase 0 research. Re-check after Phase 1 design.*

| Principle | Status | Notes |
|-----------|--------|-------|
| I. Quality-First Curation | PASS | All entries vetted for relevance (spec-kit only), maintenance status, documentation quality, and non-promotional nature. |
| II. Consistent Structure | PASS | Entry format follows `- [Name](URL) - Description.` with hyphen-minus separator per awesome-lint. Categories use `##` headings. |
| III. Link Integrity | PASS | All links point to canonical sources. Broken/redirect links will be caught in validation phase. |
| Content Standards: On-topic | PASS | Narrowed scope to spec-kit and SDD methodology. Explicit out-of-scope list in spec prevents scope creep. |
| Content Standards: Accessible | PASS | All resources must be freely and publicly accessible. |
| Content Standards: No duplicates | PASS | URL uniqueness enforced per data model. |
| Content Standards: Categorized correctly | PASS | Each entry in exactly one category. No cross-listing. |
| Contribution Workflow | PASS | contributing.md defines PR-based process with review requirement. |

**Post-Phase 1 Re-check**: All gates still pass. Category names updated from generic to spec-kit focused. Entry format contract updated to v1.1 with scope clause.

## Project Structure

### Documentation (this feature)

```text
specs/001-curated-resource-list/
├── plan.md              # This file
├── research.md          # Phase 0 output — 60+ curated resources
├── data-model.md        # Phase 1 output — entity definitions
├── quickstart.md        # Phase 1 output — validation & contribution guide
├── contracts/
│   └── entry-format.md  # Phase 1 output — entry format contract v1.1
└── tasks.md             # Phase 2 output (via /speckit.tasks)
```

### Source Code (repository root)

```text
/
├── README.md            # The awesome list (rewritten for spec-kit focus)
├── contributing.md      # Contribution guidelines (updated for narrowed scope)
└── LICENSE              # MIT license (existing, unchanged)
```

**Structure Decision**: Documentation-only project. All deliverables are Markdown files at the repository root. No source code directories needed.
