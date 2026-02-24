# Feature Specification: Initial Curated Resource List

**Feature Branch**: `001-curated-resource-list`
**Created**: 2026-02-24
**Status**: Draft

## Clarifications

### Session 2026-02-24

- Q: Should entry format use em-dash (`—`) or hyphen-minus (`-`) as separator? → A: Use hyphen-minus (`-`) consistently, per awesome-lint requirements.
- Q: Should the README contain a "License" heading section? → A: No. License stays in the LICENSE file only; no heading in README.
**Input**: User description: "Create the initial awesome-spec-kit curated resource list with categories for tools, tutorials, articles, and example projects related to spec-driven development and Spec-Kit workflows."

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Browse Resources by Category (Priority: P1)

A developer interested in spec-driven development visits the awesome-spec-kit list to discover tools, tutorials, articles, and example projects. They scan the table of contents to locate the category most relevant to their need, then scroll to that section to browse curated entries. Each entry gives them a name, a direct link, and a one-sentence description so they can quickly decide whether to click through.

**Why this priority**: This is the core value proposition of the list. Without a browsable, well-structured collection of resources, there is no product. Everything else builds on this.

**Independent Test**: Can be fully tested by opening the README in a browser (or markdown viewer) and verifying that every category is reachable from the table of contents, every entry follows the required format, and every link resolves to a live, canonical URL.

**Acceptance Scenarios**:

1. **Given** a reader opens the README, **When** they view the table of contents, **Then** they see all defined categories listed as clickable anchor links.
2. **Given** a reader clicks a category link in the table of contents, **When** the page scrolls, **Then** they land at the correct category heading with its entries visible below.
3. **Given** a reader views any entry, **When** they read it, **Then** it follows the format `- [Resource Name](URL) - One-sentence description.` with a capital first letter and trailing period.
4. **Given** a reader clicks any resource link, **When** the browser navigates, **Then** the link resolves to the primary/canonical source (not a mirror, fork, or redirect).

---

### User Story 2 - Understand the List's Purpose and Scope (Priority: P2)

A first-time visitor lands on the awesome-spec-kit page and needs to quickly understand what this list is about, what kinds of resources it contains, and what "spec-driven development" means in this context. A clear header, badge, and introductory paragraph orient them before they dive into categories.

**Why this priority**: Without clear framing, visitors won't understand the list's scope and may leave or misjudge the content. This is essential for discoverability and retention but secondary to having actual content.

**Independent Test**: Can be tested by having someone unfamiliar with Spec-Kit read only the header and introduction, then asking them to describe what the list covers. They should be able to articulate the scope accurately.

**Acceptance Scenarios**:

1. **Given** a visitor opens the README, **When** they read the header section, **Then** they see the project name, an "Awesome" badge linking to the awesome-list standard, and a one-paragraph description of the list's scope.
2. **Given** a visitor reads the introduction, **When** they finish, **Then** they understand that the list focuses on spec-driven development tools, learning materials, and examples.

---

### User Story 3 - Identify Archived Resources (Priority: P3)

A reader browsing the list encounters a resource that is no longer actively maintained but still contains substantively useful content. They need a clear marker so they understand the resource's maintenance status before investing time in it.

**Why this priority**: Transparency about maintenance status prevents frustration and builds trust. This is a polish feature that improves user experience but does not block the core browsing flow.

**Independent Test**: Can be tested by checking that every archived/unmaintained resource includes "(no longer maintained)" in its description and that no actively maintained resource is incorrectly marked.

**Acceptance Scenarios**:

1. **Given** a resource is archived or no longer maintained, **When** a reader views its entry, **Then** the description includes "(no longer maintained)" before the trailing period.
2. **Given** a resource is actively maintained, **When** a reader views its entry, **Then** no maintenance status note is present in the description.

---

### Edge Cases

- What happens when a category has no qualifying resources yet? The category heading is included with a note: *"No entries yet — contributions welcome!"* to signal the gap and invite participation.
- What happens when a resource fits multiple categories? It is placed in the single most specific category, per the constitution. It is never cross-listed.
- What happens when a resource URL redirects? The entry MUST use the final canonical URL, not the redirect source.
- What happens when a previously valid resource goes offline? The entry is removed or, if the content is historically significant, marked `[Archived]` with a note.

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: The README MUST contain a header section with the project name, an Awesome List badge, and a one-paragraph description of the list's scope.
- **FR-002**: The README MUST contain a table of contents listing every category as a clickable anchor link.
- **FR-003**: The README MUST include the following top-level categories: **Tools**, **Tutorials**, **Articles**, and **Example Projects**.
- **FR-004**: Each category MUST use a `##` heading. Subcategories, if needed, MUST use `###` headings. No deeper nesting is permitted.
- **FR-005**: Every resource entry MUST follow the format: `- [Resource Name](URL) - One-sentence description.` The separator is a hyphen-minus (` - `), not an em-dash. Descriptions MUST start with a capital letter and end with a period.
- **FR-006**: Every link MUST point to the primary/canonical source for the resource.
- **FR-007**: No resource MUST appear in more than one category.
- **FR-008**: All resources MUST be freely and publicly accessible. Paywalled or login-required resources MUST NOT be included. Archived but substantively useful resources MAY be included with "(no longer maintained)" appended to the description.
- **FR-009**: Categories with no qualifying resources MUST display a placeholder note inviting contributions.
- **FR-010**: The README MUST include a "Contributing" section that links to contribution guidelines or briefly describes how to propose additions.
- **FR-011**: The project MUST have a LICENSE file at the repository root. The README MUST NOT contain a "License" heading (awesome-lint forbids it).
- **FR-012**: The initial list MUST include at least 3 curated resources per category (12 total minimum) to demonstrate value from launch.

### Key Entities

- **Resource Entry**: A single curated item consisting of a name, URL, one-sentence description, and optional access marker. Belongs to exactly one category.
- **Category**: A named grouping of related resource entries. Defined by a `##` heading and listed in the table of contents. The initial set is: Tools, Tutorials, Articles, Example Projects.
- **Maintenance Note**: An optional "(no longer maintained)" phrase appended to a resource entry's description to indicate the resource is no longer actively maintained but still substantively useful.

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: The README contains all four required categories, each with at least 3 curated entries (12+ total resources).
- **SC-002**: 100% of resource entries follow the required format (`- [Name](URL) - Description.`) using hyphen-minus as separator.
- **SC-003**: 100% of links resolve to live, canonical URLs with no broken links or redirects.
- **SC-004**: A first-time visitor can identify the list's purpose and navigate to any category within 30 seconds of opening the page.
- **SC-005**: 100% of included resources are freely and publicly accessible. Archived resources are correctly noted with "(no longer maintained)" in the description.
- **SC-006**: The list passes the awesome-lint validation tool (standard quality gate for awesome lists).

## Assumptions

- The project uses the standard awesome-list conventions (badge, lint compliance, contributing section) as the baseline format.
- "Spec-driven development" encompasses specification-first workflows, structured planning tools, and frameworks that use formal specs to drive implementation — not limited to Spec-Kit itself.
- The initial set of resources will be curated by the maintainer(s) based on personal knowledge and research; community contributions will expand the list over time.
- The README.md in the repository root is the primary artifact for this feature. No additional pages or sites are required.
- The license is defined in the LICENSE file at the repository root (currently MIT). No license heading appears in the README.
