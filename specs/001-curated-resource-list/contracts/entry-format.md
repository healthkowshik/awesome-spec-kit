# Contract: Resource Entry Format

**Version**: 1.1 | **Date**: 2026-02-24

## Purpose

Defines the exact Markdown format every resource entry must follow in the awesome-spec-kit README. This contract is enforced by awesome-lint and manual review.

## Entry Format

### Standard entry

```markdown
- [Resource Name](https://canonical-url.example) - One-sentence description starting with a capital letter and ending with a period.
```

### Entry with maintenance note

```markdown
- [Resource Name](https://canonical-url.example) - One-sentence description (no longer maintained).
```

## Field Rules

| Field | Rule |
|-------|------|
| Resource Name | Non-empty text. Must match the resource's official/canonical name. |
| URL | Must be HTTPS. Must resolve to a live page. Must be the canonical source (not a mirror or fork). Must not require login or payment. Must not have a trailing slash. |
| Separator | Exactly ` - ` (space, hyphen-minus, space). Not an em-dash. |
| Description | Exactly one sentence. First word must be capitalized. Must end with `.`. Must not start by repeating the resource name. |
| Maintenance Note | Optional. Only `(no longer maintained)` is permitted. Appended to description before the trailing period. |

## Category Heading Format

```markdown
## Category Name
```

- Uses `##` (h2) level heading.
- Subcategories use `###` (h3). No deeper nesting.
- Must have a corresponding entry in `## Contents`.

## Ordering

Entries within a category are listed alphabetically by Resource Name.

## Scope

Resources must be directly about GitHub's spec-kit or the spec-driven development methodology it implements. See spec.md Out of Scope section for exclusions.

## Validation

This contract is validated by:
1. `awesome-lint` (automated): Checks separator format, description punctuation, capitalization, duplicate links, and badge presence.
2. Manual review: Checks URL liveness, canonical source, public accessibility, content relevance, and scope compliance.
