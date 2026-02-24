# Tasks: Initial Curated Resource List

**Input**: Design documents from `/specs/001-curated-resource-list/`
**Prerequisites**: plan.md (required), spec.md (required for user stories), research.md, data-model.md, contracts/

**Tests**: No test tasks included — the spec does not request automated tests. Validation is performed via awesome-lint (T009) and manual link verification.

**Organization**: Tasks are grouped by user story to enable independent implementation and testing of each story. US2 (header/badge/intro) is integrated into US1's phase because the header and introduction are structural prerequisites of the browsable list — they share a single file (README.md) and cannot be meaningfully separated in implementation.

## Format: `[ID] [P?] [Story] Description`

- **[P]**: Can run in parallel (different files, no dependencies)
- **[Story]**: Which user story this task belongs to (e.g., US1, US2, US3)
- Include exact file paths in descriptions

## Path Conventions

This is a documentation-only project. All deliverables are Markdown files at the repository root:

```text
/
├── README.md            # The awesome list (rewritten for spec-kit focus)
├── contributing.md      # Contribution guidelines (updated for narrowed scope)
└── LICENSE              # MIT license (existing, unchanged)
```

---

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: No project initialization needed — this is a documentation-only project. The repository, branch, and LICENSE file already exist.

*No tasks in this phase.*

---

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: No foundational infrastructure needed. All work is direct Markdown authoring in root-level files.

*No tasks in this phase.*

**Checkpoint**: Ready to begin user story implementation immediately.

---

## Phase 3: User Story 1 + User Story 2 — Core Awesome List (Priority: P1/P2) 🎯 MVP

**Goal**: Deliver a fully populated, browsable awesome-spec-kit README focused exclusively on GitHub spec-kit, with header, badge, introduction, table of contents, four spec-kit categories with curated entries, and a contributing section. This phase satisfies both US1 (browse by category) and US2 (understand purpose and scope) because the header/intro are structural components of the browsable list.

**Independent Test**: Open README.md in a browser or GitHub preview. Verify: (1) title is in title case with awesome badge, (2) one-paragraph introduction clearly describes the spec-kit scope (NOT broad spec-driven development), (3) all four categories are reachable from the TOC, (4) every entry follows `- [Name](URL) - Description.` format, (5) every entry is about spec-kit or its SDD methodology — no generic OpenAPI/AsyncAPI/ADR tools, (6) every link resolves to a live canonical URL.

### Implementation

- [x] T001 [US1] Write README.md scaffold with title case heading (`# Awesome Spec-Kit [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)`), one-paragraph scope description focused on GitHub spec-kit and its SDD methodology, and `## Contents` TOC with anchor links for Spec-Kit Ecosystem, Guides, Articles, Community Projects, and Contributing in README.md
- [x] T002 [US1] Add `## Spec-Kit Ecosystem` category with curated entries from research.md R-007 Spec-Kit Ecosystem section (select the most relevant: core repo, official docs, official site, discussions, topic page, spec-kitty, spec-kit-plus, spec-kit-command-cursor, spec-kit-extensions, iac-spec-kit, spec-kit-mcp, speckit-agent-skills, SpecLang, and other high-quality extensions) in alphabetical order, each following the entry format contract in README.md
- [x] T003 [US1] Add `## Guides` category with curated entries from research.md R-007 Guides section (Microsoft Learn modules, LinkedIn Learning, LogRocket tutorial, Scalable Path tutorial, Mad Devs tutorial, and other verified guides) in alphabetical order in README.md
- [x] T004 [US1] Add `## Articles` category with curated entries from research.md R-007 Articles section (GitHub Blog announcement, Microsoft Developer Blog, Den Delimarsky deep-dive, Martin Fowler evaluation, ThoughtWorks Radar, Scott Logic review, InfoWorld coverage, EPAM analyses, and other verified articles) in alphabetical order in README.md
- [x] T005 [US1] Add `## Community Projects` category with curated entries from research.md R-007 Community Projects section (localizations, Copilot templates, starter kits, and other verified community projects) in alphabetical order in README.md
- [x] T006 [US1] Add `## Contributing` section with brief description and link to contributing.md in README.md
- [x] T007 [P] [US1] Update contributing.md with spec-kit focused project description, scope boundary (spec-kit and SDD methodology only, with explicit out-of-scope list from spec.md), quality criteria derived from constitution principles, entry format requirements per contracts/entry-format.md v1.1, PR submission process, and review expectations in contributing.md

**Checkpoint**: README.md has all four spec-kit focused categories populated with curated entries. Contributing guide updated for narrowed scope. US1 and US2 acceptance scenarios are satisfied.

---

## Phase 4: User Story 3 — Identify Unmaintained Resources (Priority: P3)

**Goal**: Ensure any archived or unmaintained resources have the "(no longer maintained)" marker appended to their description, and all actively maintained resources have no marker.

**Independent Test**: Check each entry against its source URL. Verify: (1) unmaintained resources have "(no longer maintained)" before the trailing period, (2) active resources do not have any maintenance note.

### Implementation

- [x] T008 [US3] Review all resource entries for current maintenance status by checking each source URL, and append "(no longer maintained)" to the description (before trailing period) of any unmaintained resources per the entry format contract in README.md

**Checkpoint**: All entries accurately reflect their maintenance status. US3 acceptance scenarios are satisfied.

---

## Phase 5: Polish & Cross-Cutting Concerns

**Purpose**: Validation, metadata, and final quality checks across all deliverables.

- [x] T009 Run awesome-lint validation (`npx awesome-lint`) against README.md and fix any formatting issues (badge, TOC naming, list item format, heading style, spelling, duplicate links)
- [x] T010 Verify all resource links resolve to live, canonical URLs with no redirects, broken links, or access restrictions
- [x] T011 Set GitHub repository description to "A curated list of resources for GitHub's spec-kit and spec-driven development" and add topics "awesome" and "awesome-list" via `gh repo edit`

**Checkpoint**: awesome-lint passes with zero warnings. All links verified live. GitHub metadata set. All success criteria (SC-001 through SC-006) are satisfied.

---

## Dependencies & Execution Order

### Phase Dependencies

- **Setup (Phase 1)**: Skipped — no setup needed
- **Foundational (Phase 2)**: Skipped — no blocking infrastructure
- **US1 + US2 (Phase 3)**: Can start immediately — this is the MVP
- **US3 (Phase 4)**: Depends on Phase 3 (entries must exist before reviewing maintenance status)
- **Polish (Phase 5)**: Depends on Phase 3 and Phase 4 (all content must be final before validation)

### Task Dependencies

```text
T001 → T002 → T003 → T004 → T005 → T006  (sequential: same file, top-to-bottom)
T007 ─────────────────────────────────────  (parallel: separate file)
                                      T006 → T008  (entries must exist first)
                                             T008 → T009 → T010  (validate after all edits)
                                                           T010 → T011  (metadata last)
```

### Parallel Opportunities

- **T007** (contributing.md) can run in parallel with T001–T006 (README.md) since they are different files
- All other tasks are sequential because they modify the same file (README.md) or depend on prior task output

---

## Implementation Strategy

### MVP First (Phase 3 Only)

1. Complete T001–T007 (README.md + contributing.md)
2. **STOP and VALIDATE**: Open README.md in browser, verify spec-kit focused structure
3. This delivers US1 (browse by category) and US2 (understand purpose) — the core value

### Full Delivery

1. Phase 3: T001–T007 → Core list with spec-kit entries ✅ MVP
2. Phase 4: T008 → Maintenance notes applied ✅ US3
3. Phase 5: T009–T011 → Lint validation, link checks, GitHub metadata ✅ Release-ready

---

## Notes

- All resource entries come from research.md R-007 — descriptions should be written fresh (one sentence, capitalized, ending with period) following contracts/entry-format.md v1.1
- Entry separator is hyphen-minus (` - `), not em-dash — per clarification session 2026-02-24
- No "License" heading in README — per clarification session 2026-02-24; LICENSE file at repo root is sufficient
- The `## Contents` TOC must list exactly: Spec-Kit Ecosystem, Guides, Articles, Community Projects (awesome-lint requires TOC entries to match `##` headings; "Contributing" is excluded from TOC by awesome-lint's toc rule — verify during T009)
- Entries within each category are alphabetically ordered by resource name
- Scope is strictly GitHub spec-kit and its SDD methodology — no generic OpenAPI, AsyncAPI, ADR, RFC, or Protocol Buffer tools
- This is a living document; the initial set seeds the list, which grows organically on a daily cadence
- Commit after each phase checkpoint for clean git history
