# Contribution Guidelines

Thank you for your interest in contributing to Awesome Spec-Kit! This list curates high-quality resources specifically for GitHub's [Spec Kit](https://github.com/github/spec-kit) and the spec-driven development (SDD) methodology it implements.

## Scope

This list is **strictly focused** on GitHub's Spec Kit and its spec-driven development methodology. Resources must be directly about or for Spec Kit to be included.

### In Scope

- Spec Kit itself, its documentation, and official resources
- Extensions, plugins, and integrations built for Spec Kit
- Tutorials and guides teaching Spec Kit or its SDD workflow
- Articles analyzing, reviewing, or discussing Spec Kit
- Community projects built with or for Spec Kit (templates, localizations, tools)

### Out of Scope

- Generic API specification tools (OpenAPI, AsyncAPI, Protocol Buffers, JSON Schema, GraphQL)
- Architecture Decision Records (ADR) tools, templates, and guides
- RFC processes and templates
- General "specification-first" or "design-first" resources not tied to Spec Kit
- AI coding tools and agents that don't specifically relate to spec-driven development methodology

## Quality Criteria

Every resource must meet these criteria before inclusion:

- **Relevant** - Directly related to Spec Kit or the spec-driven development methodology it implements.
- **Maintained** - Actively maintained or, if no longer maintained, still substantively useful (noted in description).
- **Documented** - Sufficient documentation or context for a reader to understand its purpose.
- **Accessible** - Freely and publicly accessible. Paywalled or login-required resources are not accepted.
- **Non-promotional** - Entries exist to serve readers, not promote authors.

## Entry Format

Each entry must follow this exact format:

```text
- [Resource Name](https://canonical-url) - One-sentence description starting with a capital letter and ending with a period.
```

For resources no longer maintained:

```text
- [Resource Name](https://canonical-url) - One-sentence description (no longer maintained).
```

Key rules:

- Use the resource's official name.
- Link to the primary/canonical source (official repo, not a mirror or fork).
- The separator between the link and description is ` - ` (space, hyphen, space).
- The description must be exactly one sentence ending with a period.
- The description must not start by repeating the resource name.

## How to Submit

1. Fork this repository.
2. Add your resource to the appropriate category in alphabetical order.
3. Ensure your entry follows the format above.
4. Verify the link works and points to the canonical source.
5. Confirm the resource is within scope (Spec Kit and SDD methodology only).
6. Run `npx awesome-lint` to validate formatting.
7. Submit a pull request with a brief rationale for why this resource belongs in the list.

## Categories

Place each resource in exactly one category:

- **Spec-Kit Ecosystem** - Core tools, extensions, integrations, and official resources for Spec Kit.
- **Guides** - Tutorials, courses, walkthroughs, and learning resources for Spec Kit and SDD.
- **Articles** - Blog posts, analyses, thought pieces, and news coverage about Spec Kit and SDD.
- **Community Projects** - Third-party projects, localizations, templates, and tools built with or for Spec Kit.

If a resource spans multiple categories, place it in the most specific one.

## Review Process

All submissions are reviewed by a maintainer. We check for:

- Compliance with the scope and quality criteria above.
- Correct entry formatting.
- Link validity and canonical source.
- Direct relevance to Spec Kit or its SDD methodology.
