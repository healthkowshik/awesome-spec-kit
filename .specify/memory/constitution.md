<!--
  Sync Impact Report
  ==================
  Version change: 1.0.1 → 1.0.2 (PATCH — align entry format with awesome-lint)
  Modified principles:
    - II. Consistent Structure: entry separator changed from em-dash (—)
      to hyphen-minus (-) to comply with awesome-lint list-item rule.
  Added sections: None
  Removed sections: None
  Templates requiring updates:
    - .specify/templates/plan-template.md ✅ no changes needed
    - .specify/templates/spec-template.md ✅ no changes needed
    - .specify/templates/tasks-template.md ✅ no changes needed
  Follow-up TODOs: None
-->

# Awesome Spec-Kit Constitution

## Core Principles

### I. Quality-First Curation

Every resource in this list MUST meet a minimum quality bar before
inclusion. Entries MUST be:

- **Relevant**: Directly related to Spec-Kit, spec-driven development,
  or structured specification workflows.
- **Maintained**: Actively maintained or, if archived, still
  substantively useful with a clear note indicating archived status.
- **Documented**: The linked resource MUST have sufficient documentation
  or context for a reader to understand its purpose without guesswork.
- **Non-promotional**: Entries exist to serve readers, not promote
  authors. Self-submissions are permitted only when they meet the same
  quality bar as any other entry.

**Rationale**: A curated list derives its value from selectivity. An
unfiltered dump of links is noise, not curation.

### II. Consistent Structure

All entries and categories MUST follow a uniform format:

- Each entry MUST use the pattern:
  `- [Resource Name](URL) - One-sentence description.`
- Categories MUST be defined in the table of contents and use `##`
  headings.
- Descriptions MUST be concise (one sentence), start with a capital
  letter, and end with a period.
- Subcategories use `###` headings; deeper nesting is prohibited.
- New categories MUST be justified — prefer adding to an existing
  category over creating a new one.

**Rationale**: Uniform structure reduces cognitive load and makes the
list scannable. Readers should never wonder "how is this section
different from that one?"

### III. Link Integrity

All links MUST resolve to their intended target:

- Every link MUST point to the primary/canonical source (e.g., official
  repo, not a mirror or fork).
- Duplicate resources (same content, different URLs) MUST be
  deduplicated to the canonical URL.
- Broken or redirected links MUST be fixed or removed promptly when
  discovered.

**Rationale**: Dead links erode trust and usefulness. A curated list
that cannot be trusted to contain working links fails its core purpose.

## Content Standards

Entries are evaluated against these inclusion criteria:

1. **Directly on-topic**: The resource MUST relate to spec-driven
   development, specification tooling, or structured software planning.
   Tangentially related developer tools do not qualify unless they
   integrate with or explicitly support spec-driven workflows.
2. **Accessible**: The resource MUST be publicly accessible. Paywalled
   or gated content MUST be clearly marked (e.g., `[Paid]`, `[Login
   Required]`).
3. **No duplicates**: If a resource covers the same ground as an
   existing entry, the higher-quality or more authoritative source wins.
4. **Categorized correctly**: Each entry MUST appear in exactly one
   category. If it spans multiple, place it in the most specific one and
   do not cross-list.

## Contribution Workflow

All changes to the curated list MUST follow this process:

1. **Propose via pull request**: Every addition, removal, or edit MUST
   be submitted as a PR with a brief rationale.
2. **Batch entries are fine**: Multiple entries MAY be added in a single
   PR. Group related entries together and keep the PR description clear.
3. **Verify before submitting**: Contributors MUST confirm the link
   works and the description is accurate at the time of submission.
4. **Review required**: At least one maintainer MUST review and approve
   before merge.

## Governance

This constitution is the authoritative source of standards for the
awesome-spec-kit project. All contributions and reviews MUST verify
compliance with these principles.

- **Amendments**: Any change to this constitution MUST be proposed as a
  PR with a rationale. Amendments require maintainer approval.
- **Versioning**: The constitution follows semantic versioning:
  - MAJOR: Principle removal, redefinition, or backward-incompatible
    governance change.
  - MINOR: New principle or section added, or existing guidance
    materially expanded.
  - PATCH: Clarifications, wording fixes, non-semantic refinements.
- **Compliance review**: Maintainers SHOULD periodically audit existing
  entries against current principles and remove those that no longer
  qualify.

**Version**: 1.0.2 | **Ratified**: 2026-02-24 | **Last Amended**: 2026-02-24
