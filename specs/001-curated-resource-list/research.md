# Research: Initial Curated Resource List

**Branch**: `001-curated-resource-list` | **Date**: 2026-02-24

## R-001: Awesome-Lint Compliance Requirements

**Decision**: The README must conform to awesome-lint rules, which override general Markdown conventions where they conflict.

**Rationale**: SC-006 in the spec requires awesome-lint compliance. Awesome-lint enforces 15 custom rules and 39 remark-lint rules. Key constraints discovered:

- Badge must be inside the `h1` heading using `https://awesome.re/badge.svg`
- Heading must be title case: `# Awesome Spec-Kit`
- TOC section must be named exactly `## Contents` and appear first
- List items require ` - ` (space, hyphen, space) as separator between link and description
- `contributing.md` must exist at root or `.github/` and must not be empty
- A "License" heading in the README is **forbidden** — license must be in a separate file only
- No CI badges allowed in the README
- GitHub repo must have "awesome" and "awesome-list" topics and a description

**Alternatives considered**: Ignoring awesome-lint and using custom validation. Rejected because awesome-lint compliance is a stated success criterion and signals quality to the awesome-list community.

## R-002: Entry Format — Constitution vs. Awesome-Lint Conflict

**Decision**: Use ` - ` (space, hyphen-minus, space) as the separator in entry format, not ` — ` (space, em-dash, space).

**Rationale**: The constitution (Principle II) specifies the format `- [Resource Name](URL) — One-sentence description.` using an em-dash. However, awesome-lint's `list-item` rule requires ` - ` (hyphen-minus). Since awesome-lint compliance is a success criterion (SC-006), the hyphen-minus format takes precedence. The constitution should be updated in a follow-up PR to align with this standard.

**Alternatives considered**:
1. Keep em-dash and disable the awesome-lint rule — Rejected; defeats the purpose of lint compliance.
2. Keep em-dash and skip awesome-lint — Rejected; SC-006 explicitly requires it.

**Action required**: File a follow-up issue to update the constitution's entry format from `—` to `-`.

## R-003: License Section in README vs. Awesome-Lint

**Decision**: Do NOT include a "License" heading in the README. Reference the license only via a sentence in the Contributing section or as a footer note without a heading.

**Rationale**: The spec's FR-011 requires "a License section stating the project's license." However, awesome-lint's `license` rule explicitly forbids a "License" or "Licence" heading in the README. The license file (LICENSE at repo root) is the canonical source. We satisfy the intent of FR-011 by having a LICENSE file and mentioning the license type in the Contributing section.

**Alternatives considered**: Adding a "License" heading and disabling the lint rule — Rejected; same reasoning as R-002.

## R-004: License Type — MIT vs. CC0

**Decision**: Keep the existing MIT license.

**Rationale**: The awesome-list convention recommends CC0 (Creative Commons Zero), and the spec's assumptions mention "CC0 or CC-BY." However, the repository already has an MIT license established by the maintainer. Changing the license is a governance decision outside the scope of this feature. Awesome-lint only checks that a license *exists*, not that it is CC0. The MIT license passes validation.

**Alternatives considered**: Switching to CC0 — Deferred; this is a maintainer decision that can be made independently.

## R-005: Curated Resource Selection

**Decision**: Include resources across four categories with a focus on established, well-documented projects.

**Rationale**: Research identified 30+ candidate resources. Selection criteria applied:
1. Must be freely and publicly accessible (per FR-008)
2. Must be directly relevant to spec-driven development (per constitution Content Standards)
3. Must have sufficient documentation (per constitution Principle I)
4. Prefer canonical/official sources (per constitution Principle III)

### Tools (selected)

| Resource | URL | Why Selected |
|----------|-----|-------------|
| OpenAPI Generator | https://github.com/OpenAPITools/openapi-generator | Leading spec-first code generator; actively maintained. |
| Spectral | https://github.com/stoplightio/spectral | Flexible API spec linter with broad format support. |
| Swagger Editor | https://github.com/swagger-api/swagger-editor | Standard browser-based spec editor; widely used. |
| Redocly CLI | https://github.com/Redocly/redocly-cli | All-in-one CLI for linting, validating, and generating docs from specs. |
| AsyncAPI Generator | https://github.com/asyncapi/generator | Spec-first code/docs generator for event-driven architectures. |
| Buf CLI | https://github.com/bufbuild/buf | Modern CLI for Protocol Buffer spec linting and breaking change detection. |
| Prism | https://github.com/stoplightio/prism | Turns OpenAPI specs into mock API servers for contract testing. |
| adr-tools | https://github.com/npryce/adr-tools | CLI for managing Architecture Decision Records as spec documents. |
| Log4brains | https://github.com/thomvaill/log4brains | Docs-as-code tool for logging and publishing ADRs as a searchable site. |
| Ajv | https://github.com/ajv-validator/ajv | The fastest JSON Schema validator for spec-driven data validation. |

### Tutorials

| Resource | URL | Why Selected |
|----------|-----|-------------|
| OpenAPI Tutorial (I'd Rather Be Writing) | https://idratherbewriting.com/learnapidoc/openapi_tutorial.html | Comprehensive, hands-on OpenAPI tutorial. |
| Learn OpenAPI (official) | https://learn.openapis.org/ | Official OpenAPI Initiative learning portal. |
| AsyncAPI Getting Started | https://www.asyncapi.com/docs/tutorials/getting-started | Official AsyncAPI tutorial for event-driven specs. |
| AWS ADR Guide | https://docs.aws.amazon.com/prescriptive-guidance/latest/architectural-decision-records/welcome.html | Enterprise-grade ADR lifecycle guide from AWS. |

### Articles

| Resource | URL | Why Selected |
|----------|-----|-------------|
| GitHub Blog — Spec-Driven Development with AI | https://github.blog/ai-and-ml/generative-ai/spec-driven-development-with-ai-get-started-with-a-new-open-source-toolkit/ | GitHub's official announcement of Spec Kit. |
| Atlassian — Spec-First API Development | https://www.atlassian.com/blog/atlassian-engineering/spec-first-api-development | Real-world case study from Atlassian engineering. |
| Martin Fowler — Understanding SDD Tools | https://martinfowler.com/articles/exploring-gen-ai/sdd-3-tools.html | Critical evaluation of SDD tools by a respected authority. |
| Allen Helton — Write Your API Spec First | https://www.readysetcloud.io/blog/allen.helton/seriously-write-your-spec-first/ | Practical argument for spec-first API development. |

### Example Projects

| Resource | URL | Why Selected |
|----------|-----|-------------|
| github/spec-kit | https://github.com/github/spec-kit | GitHub's official SDD toolkit; the namesake of this list. |
| rust-lang/rfcs | https://github.com/rust-lang/rfcs | Gold-standard RFC process; specs drive language features. |
| OAI/OpenAPI-Specification | https://github.com/OAI/OpenAPI-Specification | The canonical API specification standard itself. |
| joelparkerhenderson/architecture-decision-record | https://github.com/joelparkerhenderson/architecture-decision-record | Comprehensive ADR templates and examples collection. |
| adr/madr | https://github.com/adr/madr | Lean, structured Markdown ADR template format. |

**Alternatives considered but deferred**: ThoughtWorks SDD article (may have access issues), InfoQ article (may require login), Bruno Scheufler blog post (less authoritative than selected sources). These can be added in future contributions.

## R-006: GitHub Repository Metadata

**Decision**: Set GitHub repo topics and description to pass awesome-lint's `github` rule.

**Rationale**: The `awesome-github` rule requires: (1) a repository description, (2) "awesome" topic, (3) "awesome-list" topic, and (4) a detected license. Items 1-3 must be set via GitHub settings or CLI.

**Action required**: Run `gh repo edit` commands during implementation to set topics and description.
