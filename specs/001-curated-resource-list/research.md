# Research: Initial Curated Resource List

**Branch**: `001-curated-resource-list` | **Date**: 2026-02-24

## R-001: Scope Narrowing

**Decision**: Focus exclusively on GitHub's spec-kit and the spec-driven development (SDD) methodology it implements. Exclude generic specification tools (OpenAPI, AsyncAPI, ADR, Protocol Buffers, JSON Schema).
**Rationale**: User feedback indicated the original broad scope diluted the list's value. Sharp focus on spec-kit makes this the definitive resource hub for the spec-kit ecosystem.
**Alternatives considered**: Broad "spec-driven development" (rejected — too generic), spec-kit repos only with no methodology articles (rejected — too narrow).

## R-002: Awesome-Lint Compliance Requirements

**Decision**: The README must conform to awesome-lint rules, which override general Markdown conventions where they conflict.
**Rationale**: SC-006 in the spec requires awesome-lint compliance. Key constraints:
- Badge must be inside the `h1` heading using `https://awesome.re/badge.svg`
- Heading must be title case: `# Awesome Spec-Kit`
- TOC section must be named exactly `## Contents` and appear first
- List items require ` - ` (space, hyphen, space) separator
- `contributing.md` must exist at root or `.github/`
- A "License" heading in the README is forbidden
- GitHub repo must have "awesome" and "awesome-list" topics and a description

## R-003: Category Structure

**Decision**: Four categories: **Spec-Kit Ecosystem**, **Guides**, **Articles**, **Community Projects**.
**Rationale**: Maps to how a spec-kit practitioner discovers resources — core tools first, then learning materials, then thought leadership, then community work.
**Alternatives considered**: Original generic categories (Tools, Tutorials, Articles, Example Projects) — rejected as they don't reflect the spec-kit ecosystem.

## R-004: Entry Minimums

**Decision**: No minimum entry count. Living document updated on daily cadence.
**Rationale**: Spec-kit is a growing ecosystem. Imposing minimums would force padding or delay launch. Categories can start empty and grow organically.

## R-005: Out of Scope Boundary

**Decision**: Exclude generic ADR/RFC tools, OpenAPI/AsyncAPI/Protocol Buffer tools, and general "specification-first" resources not tied to spec-kit.
**Rationale**: These are precursor or parallel methodologies. Including them blurs the spec-kit focus. User explicitly chose strict exclusion.

## R-006: License

**Decision**: Keep the existing MIT license. Do not add a "License" heading in README.
**Rationale**: awesome-lint forbids "License" headings. The LICENSE file at repo root is sufficient. awesome-lint only checks that a license exists, not the type.

## R-007: Curated Resource Inventory

Research identified 60+ candidate resources. Below is the consolidated inventory.

### Spec-Kit Ecosystem

| # | Name | URL | Description | Stars | Notes |
|---|------|-----|-------------|-------|-------|
| 1 | Spec Kit | https://github.com/github/spec-kit | Open-source toolkit for spec-driven development providing templates, a CLI, and structured workflows for AI-assisted engineering. | 71.5k | Core repo |
| 2 | Spec Kit Documentation | https://github.github.com/spec-kit/ | Official documentation portal covering installation, quickstart, development phases, and the full SDD methodology. | — | Official docs |
| 3 | speckit.org | https://speckit.org/ | Official landing page with overview, features, getting started instructions, and community links. | — | Official site |
| 4 | Spec Kit Discussions | https://github.com/github/spec-kit/discussions | Official community forum for methodology discussion, workflow sharing, and maintainer support. | — | Community hub |
| 5 | spec-kit Topic | https://github.com/topics/spec-kit | Discovery hub aggregating 75+ public repositories tagged with the spec-kit topic. | — | Discovery |
| 6 | SpecLang | https://githubnext.com/projects/speclang/ | GitHub Next research prototype treating natural-language specifications as primary source of truth, conceptual predecessor to Spec Kit (no longer maintained). | — | Historical |
| 7 | spec-kitty | https://github.com/Priivacy-ai/spec-kitty | Enhanced SDD adding a Kanban dashboard, git worktrees, auto-merge, and multi-agent support. | 780 | Extension |
| 8 | spec-kit-plus | https://github.com/panaversity/spec-kit-plus | Fork with patterns and templates for building scalable multi-agent AI systems. | 184 | Extended fork |
| 9 | spec-kit-command-cursor | https://github.com/madebyaris/spec-kit-command-cursor | SDD toolkit ported for Cursor IDE with /specify, /plan, /tasks commands. | 147 | IDE port |
| 10 | spec-kit-extensions | https://github.com/MartyBonacci/spec-kit-extensions | Five workflows extending spec-kit to cover bugfix, modification, refactor, hotfix, and deprecation. | 58 | SDLC extension |
| 11 | iac-spec-kit | https://github.com/IBM/iac-spec-kit | AI-assisted workflows for translating business requirements into infrastructure code using SDD. | 38 | IBM, domain-specific |
| 12 | spec-kit-mcp | https://github.com/lsendel/spec-kit-mcp | MCP server enabling AI assistants to use spec-kit methodology via the Model Context Protocol. | 23 | MCP integration |
| 13 | speckit-agent-skills | https://github.com/dceoy/speckit-agent-skills | Agent skills extension pack providing additional capabilities for AI coding assistants. | 26 | Skills |
| 14 | spec-kit-v-model | https://github.com/leocamello/spec-kit-v-model | V-Model extension enforcing paired development and test specifications with regulatory traceability. | 3 | Regulatory |
| 15 | spec-kit-brownfield-extensions | https://github.com/wcpaxx/spec-kit-brownfield-extensions | Bootstrap extension that brings existing codebases into the SDD workflow. | 12 | Brownfield |
| 16 | spec-kit-jira | https://github.com/mbachorik/spec-kit-jira | Jira extension bridging SDD workflows with Jira project management. | 5 | PM integration |
| 17 | sdd-skill | https://github.com/SpillwaveSolutions/sdd-skill | Claude Code skill for guiding users through Spec Kit and the SDD methodology. | 25 | Claude skill |
| 18 | claude-code-spec-kit-subagent-plugin | https://github.com/jcmrs/claude-code-spec-kit-subagent-plugin | Claude Code plugin providing a conversational subagent for co-creating specs with dynamic memory graphs. | 16 | Claude plugin |
| 19 | cline-spec-kit-workflows | https://github.com/JRedeker/cline-spec-kit-workflows | Cline workflow files for comprehensive SDD in the Cline agent. | 11 | Cline workflows |
| 20 | piv-speckit | https://github.com/galando/piv-speckit | PIV (Prime-Implement-Validate) combined with Spec-Kit for structured specs and strict TDD. | 22 | TDD extension |
| 21 | spec-kit-antigravity | https://github.com/waveupHQ/spec-kit-antigravity | Agent-first specification and orchestration kit adapting spec-kit for Google Antigravity (Gemini 3). | 27 | Gemini integration |
| 22 | lite-kits | https://github.com/tmorgan181/lite-kits | Lightweight add-ons for Spec-Kit including project orientation, git commands, and multi-agent collaboration. | 4 | Lightweight |

### Guides

| # | Name | URL | Source | Date |
|---|------|-----|--------|------|
| 1 | Microsoft Learn: Greenfield Intro | https://learn.microsoft.com/en-us/training/modules/spec-driven-development-github-spec-kit-greenfield-intro/ | Microsoft Learn | Jan 2026 |
| 2 | Microsoft Learn: Enterprise Developers | https://learn.microsoft.com/en-us/training/modules/spec-driven-development-github-spec-kit-enterprise-developers/ | Microsoft Learn | Jan 2026 |
| 3 | LinkedIn Learning: SDD with GitHub Spec Kit | https://github.com/LinkedInLearning/spec-driven-development-with-github-spec-kit-4641001 | LinkedIn Learning | Sep 2025 |
| 4 | LogRocket: Exploring SDD with Spec Kit | https://blog.logrocket.com/github-spec-kit/ | LogRocket | Oct 2025 |
| 5 | Scalable Path: SDD Tutorial | https://www.scalablepath.com/machine-learning/spec-driven-development-workflow | Scalable Path | Nov 2025 |
| 6 | Mad Devs: 0 to 1 with Spec-kit & Cursor | https://maddevs.io/writeups/project-creation-using-spec-kit-and-cursor/ | Mad Devs | Nov 2025 |
| 7 | Redreamality: Spec Kit Deep Dive | https://redreamality.com/garden/notes/github-spec-kit-guide/ | Redreamality | Jan 2026 |
| 8 | speckit-tutorial (Japanese) | https://github.com/kkawailab/speckit-tutorial | kkawailab | Nov 2025 |
| 9 | DeepWiki: spec-kit | https://deepwiki.com/github/spec-kit | DeepWiki | Auto-gen |
| 10 | Fred Hutch: Spec-Kit Walkthrough | https://matsen.fredhutch.org/general/2026/02/10/spec-kit-walkthrough.html | Erick Matsen | Feb 2026 |
| 11 | Kilo.ai: SDD with Spec Kit + Kilo Code | https://blog.kilo.ai/p/spec-driven-development-what-it-is | Kilo.ai Blog | Oct 2025 |
| 12 | ENESFERA/spec-kit-lab | https://github.com/ENESFERA/spec-kit-lab | ENESFERA | Jan 2026 |

### Articles

| # | Name | URL | Author/Source | Date |
|---|------|-----|---------------|------|
| 1 | Spec-Driven Development with AI | https://github.blog/ai-and-ml/generative-ai/spec-driven-development-with-ai-get-started-with-a-new-open-source-toolkit/ | Den Delimarsky / GitHub Blog | Sep 2025 |
| 2 | Diving Into SDD With GitHub Spec Kit | https://developer.microsoft.com/blog/spec-driven-development-spec-kit | Den Delimarsky / Microsoft Blog | Sep 2025 |
| 3 | What's The Deal With GitHub Spec Kit | https://den.dev/blog/github-spec-kit/ | Den Delimarsky | Oct 2025 |
| 4 | Understanding SDD Tools | https://martinfowler.com/articles/exploring-gen-ai/sdd-3-tools.html | Birgitta Boeckeler / martinfowler.com | Oct 2025 |
| 5 | Spec-Driven Development (Technology Radar) | https://www.thoughtworks.com/en-us/radar/techniques/spec-driven-development | ThoughtWorks | Nov 2025 |
| 6 | Unpacking SDD: 2025's Key New Practice | https://www.thoughtworks.com/en-us/insights/blog/agile-engineering-practices/spec-driven-development-unpacking-2025-new-engineering-practices | Liu Shangqi / ThoughtWorks | Dec 2025 |
| 7 | A Look at Spec Kit | https://tessl.io/blog/a-look-at-spec-kit-githubs-spec-driven-software-development-toolkit/ | Paul Sawers / Tessl | Oct 2025 |
| 8 | Putting Spec Kit Through Its Paces | https://blog.scottlogic.com/2025/11/26/putting-spec-kit-through-its-paces-radical-idea-or-reinvented-waterfall.html | Colin Eberhardt / Scott Logic | Nov 2025 |
| 9 | SDD: The Waterfall Strikes Back | https://marmelab.com/blog/2025/11/12/spec-driven-development-waterfall-strikes-back.html | Francois Zaninotto / Marmelab | Nov 2025 |
| 10 | Spec-driven AI Coding with Spec Kit | https://www.infoworld.com/article/4062524/spec-driven-ai-coding-with-githubs-spec-kit.html | Martin Heller / InfoWorld | Dec 2025 |
| 11 | GitHub Open Sources Kit for Spec-Driven AI Development | https://visualstudiomagazine.com/articles/2025/09/03/github-open-sources-kit-for-spec-driven-ai-development.aspx | David Ramel / Visual Studio Magazine | Sep 2025 |
| 12 | Inside SDD: What Spec Kit Makes Possible | https://www.epam.com/insights/ai/blogs/inside-spec-driven-development-what-githubspec-kit-makes-possible-for-ai-engineering | EPAM | Oct 2025 |
| 13 | SDD for Brownfield Code Exploration | https://www.epam.com/insights/ai/blogs/using-spec-kit-for-brownfield-codebase | EPAM | Nov 2025 |
| 14 | SDD: A First Review | https://dev.to/danielsogl/spec-driven-development-sdd-a-initial-review-2llp | Daniel Sogl / DEV | Sep 2025 |
| 15 | SDD from Code to Contract (Academic) | https://arxiv.org/abs/2602.00180 | Deepak Babu Piskala / arXiv | Jan 2026 |
| 16 | Beyond Vibe-Coding: Scaling AI with Spec Kit | https://www.markbeacom.com/blog/architecture/genai/github-spec-kit | Mark Beacom | 2025 |
| 17 | VirtusLab: Spec-Kit Taming AI-Coding Chaos | https://virtuslab.com/blog/ai/spec-kit-tames-ai-coding-chaos/ | VirtusLab | 2025 |

### Community Projects

| # | Name | URL | Stars | Notes |
|---|------|-----|-------|-------|
| 1 | spec-kit-cn | https://github.com/Linfee/spec-kit-cn | 494 | Chinese (zh-CN) localization |
| 2 | spec-kit (zh-TW) | https://github.com/doggy8088/spec-kit | 244 | Traditional Chinese localization |
| 3 | spec-kit-chinese | https://github.com/888888888881/spec-kit-chinese | 172 | Chinese localization |
| 4 | novel-writer | https://github.com/wordflowlab/novel-writer | 630 | Built with spec-kit methodology |
| 5 | sdd-pilot | https://github.com/attilaszasz/sdd-pilot | 8 | Copilot SDD template |
| 6 | copilot-spec-driven-template | https://github.com/GregorBiswanger/copilot-spec-driven-template | 7 | Copilot SDD template |
| 7 | RooCode_SpecKit_StarterKit | https://github.com/Dazlarus/RooCode_SpecKit_StarterKit | 16 | Roo Code integration |
| 8 | sdd_vibe_converter | https://github.com/TrolljanO/sdd_vibe_converter | 9 | Ideas → specs converter |
| 9 | Awesome-Spec-Driven-Development | https://github.com/zhimin-z/Awesome-Spec-Driven-Development | 32 | Related awesome-list |
| 10 | pmf-kit | https://github.com/agentii-ai/pmf-kit | 7 | Product-market fit toolkit on spec-kit |
| 11 | palestra-sdd | https://github.com/glaucia86/palestra-sdd | 3 | Talk materials (Portuguese) |

## R-008: Key People

- **Den Delimarsky** (@localden) — Principal Product Manager at GitHub, primary public advocate
- **John Lam** (@jflam) — GitHub engineer, SpecLang researcher, origin of spec-kit methodology
