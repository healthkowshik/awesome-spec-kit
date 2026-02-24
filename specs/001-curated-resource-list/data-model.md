# Data Model: Initial Curated Resource List

**Branch**: `001-curated-resource-list` | **Date**: 2026-02-24

## Overview

This feature has no runtime data storage. All "data" lives as structured Markdown in `README.md`. The entities below describe the logical structure that the Markdown must encode.

## Entities

### Resource Entry

A single curated item in the list.

| Field | Type | Required | Constraints |
|-------|------|----------|-------------|
| Name | Text | Yes | Human-readable name of the resource. |
| URL | URL | Yes | Must be canonical (primary source, not mirror/fork). Must resolve to a live page. Must be publicly accessible without login or payment. |
| Description | Text | Yes | Exactly one sentence. Starts with capital letter. Ends with period. Must not repeat the resource name as its first word. |
| Access Marker | Enum | No | Only valid value: `[Archived]`. Applied when the resource is no longer maintained but remains substantively useful. |

**Markdown format**: `- [Name](URL) - Description.`
(With optional marker: `- [Name](URL) [Archived] - Description.`)

**Uniqueness**: A resource is uniquely identified by its canonical URL. No two entries may share the same URL (after normalization).

**Categorization**: Each resource belongs to exactly one category. No cross-listing.

### Category

A named grouping of related resource entries.

| Field | Type | Required | Constraints |
|-------|------|----------|-------------|
| Name | Text | Yes | Used as a `##` heading in the README. Must appear in the `## Contents` TOC. |
| Entries | List of Resource Entry | No | If empty, display placeholder: *"No entries yet — contributions welcome!"* |

**Initial categories** (in display order):

1. **Tools** — Software that supports spec-driven development workflows.
2. **Tutorials** — Step-by-step guides for learning spec-driven practices.
3. **Articles** — Essays, case studies, and opinion pieces on spec-driven development.
4. **Example Projects** — Open-source repositories that demonstrate spec-driven workflows.

**Ordering**: Within a category, entries are listed alphabetically by name.

### Access Marker

| Value | Meaning |
|-------|---------|
| `[Archived]` | Resource is no longer actively maintained but still contains substantively useful content. |

No other markers are used. Paid or login-required resources are excluded entirely.

## Relationships

```
Category 1──* Resource Entry
Resource Entry 0──1 Access Marker
```

- A Category contains zero or more Resource Entries.
- A Resource Entry belongs to exactly one Category.
- A Resource Entry has at most one Access Marker.

## Validation Rules

1. Every Resource Entry URL must be unique across the entire README.
2. Every Resource Entry description must be one sentence, capitalized, ending with a period.
3. Every Resource Entry description must not start by repeating the resource name.
4. Every Category listed in `## Contents` must have a corresponding `##` heading.
5. Every `##` content heading must have a corresponding entry in `## Contents`.
6. Entries within a category are alphabetically ordered by name.
