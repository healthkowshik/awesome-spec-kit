# Contract: Resource Entry Format

**Version**: 1.0 | **Date**: 2026-02-24

## Purpose

Defines the exact Markdown format every resource entry must follow in the awesome-spec-kit README. This contract is enforced by awesome-lint and manual review.

## Entry Format

### Standard entry

```markdown
- [Resource Name](https://canonical-url.example) - One-sentence description starting with a capital letter and ending with a period.
```

### Archived entry

```markdown
- [Resource Name](https://canonical-url.example) [Archived] - One-sentence description starting with a capital letter and ending with a period.
```

## Field Rules

| Field | Rule |
|-------|------|
| Resource Name | Non-empty text. Must match the resource's official/canonical name. |
| URL | Must be HTTPS. Must resolve to a live page. Must be the canonical source (not a mirror or fork). Must not require login or payment. Must not have a trailing slash. |
| Separator | Exactly ` - ` (space, hyphen-minus, space). Not an em-dash. |
| Description | Exactly one sentence. First word must be capitalized (Capital, camelCase, PascalCase, CONSTANT, or UPPER case). Must end with `.`, `!`, or `?`. Must not start by repeating the resource name. |
| Access Marker | Optional. Only `[Archived]` is permitted. Placed between the URL closing `)` and the separator ` - `. |

## Category Heading Format

```markdown
## Category Name
```

- Uses `##` (h2) level heading.
- Subcategories use `###` (h3). No deeper nesting.
- Must have a corresponding entry in `## Contents`.

## Ordering

Entries within a category are listed alphabetically by Resource Name.

## Validation

This contract is validated by:
1. `awesome-lint` (automated): Checks separator format, description punctuation, capitalization, duplicate links, and badge presence.
2. Manual review: Checks URL liveness, canonical source, public accessibility, and content relevance.
