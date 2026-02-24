# Quickstart: Initial Curated Resource List

**Branch**: `001-curated-resource-list` | **Date**: 2026-02-24

## What This Feature Delivers

A curated `README.md` at the repository root containing an awesome list of GitHub spec-kit resources, organized into four categories (Spec-Kit Ecosystem, Guides, Articles, Community Projects), plus a `contributing.md` with contribution guidelines.

## Scope

This list focuses exclusively on GitHub's spec-kit and the spec-driven development (SDD) methodology it implements. Generic specification tools (OpenAPI, AsyncAPI, ADR tools, etc.) are out of scope.

## Files Modified/Created

| File | Action | Purpose |
|------|--------|---------|
| `README.md` | Rewrite | The awesome list — header, badge, TOC, four categories, entries. |
| `contributing.md` | Update | Contribution guidelines reflecting narrowed scope. |

## How to Validate

### 1. Visual check

Open `README.md` in a browser or GitHub preview. Verify:
- Title is in title case with the Awesome badge
- Table of contents links work
- All four categories are present (Spec-Kit Ecosystem, Guides, Articles, Community Projects)
- Every entry follows the format: `- [Name](URL) - Description.`
- Every entry is about spec-kit or SDD (not generic spec tools)

### 2. Run awesome-lint

```bash
npx awesome-lint
```

All checks should pass with zero warnings or errors.

### 3. Check links

Click through each resource link to verify it resolves to a live, canonical page. No link should require login or payment.

## Adding a New Resource

1. Verify the resource is about spec-kit or its SDD methodology (see spec.md Out of Scope).
2. Choose the correct category (Spec-Kit Ecosystem, Guides, Articles, or Community Projects).
3. Add an entry in alphabetical order within the category:
   ```markdown
   - [Resource Name](https://canonical-url.example) - One-sentence description ending with a period.
   ```
4. Run `npx awesome-lint` to validate.
5. Submit a pull request with a brief rationale.
