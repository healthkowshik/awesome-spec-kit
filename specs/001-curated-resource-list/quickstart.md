# Quickstart: Initial Curated Resource List

**Branch**: `001-curated-resource-list` | **Date**: 2026-02-24

## What This Feature Delivers

A fully populated `README.md` at the repository root containing a curated awesome list of spec-driven development resources, organized into four categories (Tools, Tutorials, Articles, Example Projects), plus a `contributing.md` with contribution guidelines.

## Files Modified/Created

| File | Action | Purpose |
|------|--------|---------|
| `README.md` | Rewrite | The awesome list itself — header, badge, TOC, categories, entries. |
| `contributing.md` | Create | Contribution guidelines for adding/editing resources. |

## How to Validate

### 1. Visual check

Open `README.md` in a browser or GitHub preview. Verify:
- Title is in title case with the Awesome badge
- Table of contents links work
- All four categories have 3+ entries each
- Every entry follows the format: `- [Name](URL) - Description.`

### 2. Run awesome-lint

```bash
npx awesome-lint
```

All checks should pass with zero warnings or errors.

### 3. Check links

Click through each resource link to verify it resolves to a live, canonical page. No link should require login or payment.

## Adding a New Resource

1. Choose the correct category (Tools, Tutorials, Articles, or Example Projects).
2. Add an entry in alphabetical order within the category:
   ```markdown
   - [Resource Name](https://canonical-url.example) - One-sentence description ending with a period.
   ```
3. Update `## Contents` if adding a new category (not needed for entries within existing categories).
4. Run `npx awesome-lint` to validate.
5. Submit a pull request with a brief rationale.
