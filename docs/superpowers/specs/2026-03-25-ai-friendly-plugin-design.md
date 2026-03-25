---
title: AI-Friendly Plugin Design
date: 2026-03-25
status: approved
---

# AI-Friendly Plugin Design

## Overview

Make the `navapbc/opensource-guide` repo navigable by any AI agent and installable as a Claude Code plugin that helps Nava team members and external contributors execute the full open source lifecycle — from evaluating third-party OSS through publishing, promoting, and managing contributions.

**Primary audience:** Nava engineers and staff preparing to publish or manage open source projects. Secondary audience: external contributors coming to an already-published Nava project.

## Goals

- Any AI tool (Claude, Gemini, Codex, etc.) can navigate the guide via `AGENTS.md` and give advice grounded in the actual guide content — not hallucinated policy
- Nava developers install the plugin once and get the skill available in every repo they work in, with no per-repo setup
- Given a project repo, the skill correctly identifies the user's lifecycle stage and surfaces a relevant, prioritized action plan
- The skill generates common artifacts (CONTRIBUTING.md, issue templates, code.json) as output in chat — the user reviews and pastes/applies them
- The skill does not activate in unrelated contexts (e.g., publishing an npm package)

## Approach

The repo itself becomes an installable Claude Code plugin. No separate repo is needed — plugin metadata and skill files live alongside the guide content in `navapbc/opensource-guide`.

Two complementary layers:
1. **`AGENTS.md`** — a static navigation file any AI tool can read to understand the repo structure and know which docs to consult for a given task
2. **`skills/nava-oss-guide/SKILL.md`** — a Claude Code skill that runs a diagnostic workflow and guides users through execution

This was chosen over alternatives:
- A monolithic skill with all content inline would become unwieldy and wouldn't serve non-Claude AI tools
- Separate per-stage skill files add routing complexity without clear benefit at this scale

## Deliverables

### 1. `AGENTS.md` (repo root)

An AI navigation layer readable by any LLM tool. Contains:

- **Repo purpose** — what this guide is, who it's for
- **Structure map** — table of all `docs/` sections, what each contains, and when an agent should read it. Must cover all nine directories: `using/`, `contributing/`, `publishing/`, `launching/`, `promoting/`, `accepting/`, `projects/`, `resources/`, `superpowers/` (note: `superpowers/` contains internal spec files, not guide content — agents should ignore it)
- **Key files** — what `code.json`, `CONTRIBUTING.md`, `SECURITY.md`, etc. are for
- **Agent usage instructions** — read relevant sections, do not hallucinate policy, link to specific guide pages when making recommendations
- **Lifecycle stage map** — given a user's situation, which docs apply

### 2. `.claude-plugin/plugin.json`

Plugin metadata following the Claude Code plugin schema. Required fields:

```json
{
  "name": "nava-oss-guide",
  "description": "Guides Nava team members through the full open source lifecycle using the Nava OSPO guide",
  "version": "1.0.0",
  "homepage": "https://github.com/navapbc/opensource-guide",
  "skills": ["skills/nava-oss-guide"]
}
```

Exact schema to be verified against the Claude Code plugin documentation during implementation.

### 3. `skills/nava-oss-guide/SKILL.md`

The main skill file with two entry points:

- **Model-invoked**: triggers when a user asks about open source processes specifically in a Nava/government context — publishing a Nava project, contributing on behalf of Nava, open source approval, Nava OSS policy, etc. Does NOT trigger for generic OSS questions unrelated to Nava (e.g., "how do I publish to npm")
- **User-invoked**: `/oss-guide` slash command for explicit activation from any context

**Skill flow:**

1. **Diagnostic** — attempt to read key project files: `LICENSE`, `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md`, `.github/ISSUE_TEMPLATE/`, `code.json`. If none exist, treat the project as pre-OSS (starting from scratch). If some exist, note what's present vs. missing. Ask 2-3 targeted questions to confirm lifecycle stage (e.g., "Has this project been through Nava's approval process?", "Is this already publicly visible on GitHub?")

2. **Stage determination** — map to one or more lifecycle stages based on diagnostic findings

3. **Action plan** — present a prioritized checklist: what's present, what's missing, what to do next. Each item links to the relevant guide section by URL

4. **Guided execution** — walk through checklist items one at a time. For generatable artifacts, output the content directly in chat with instructions for the user to review and apply

**Lifecycle stages covered:**

| Stage | Guide Sections |
|-------|---------------|
| Evaluating/using third-party OSS | `docs/using/` |
| Contributing to external projects | `docs/contributing/` |
| Preparing to publish | `docs/publishing/prepare.md` |
| Getting approval | `docs/publishing/approval.md` |
| Publishing | `docs/publishing/publish.md`, `docs/launching/` |
| Managing releases | `docs/publishing/release.md` |
| Promoting | `docs/promoting/` |
| Accepting contributions | `docs/accepting/` |
| Looking up reference info (licenses, copyright, branding, code ownership) | `docs/resources/` |
| Exploring Nava's existing OSS portfolio | `docs/projects/` |

**Artifact generation:** The skill outputs artifact content in chat (fenced code blocks) with a note to review before applying. It does not write files to the repo directly. The user copies or applies the content themselves.

## Installation

Once the plugin files are committed to `navapbc/opensource-guide`, Nava developers install with:

```
/plugin install navapbc/opensource-guide
```

This is the expected Claude Code plugin installation format for GitHub-hosted plugins. Exact command syntax to be confirmed against current Claude Code documentation during implementation.

## Acceptance Criteria

- `AGENTS.md` accurately reflects current repo structure and all `docs/` sections
- Given a repo with no OSS files, the skill identifies "pre-OSS / preparing to publish" and surfaces the approval + preparation checklist
- Given a fully published repo, the skill identifies post-launch stage and surfaces promotion/contribution management guidance
- The skill does not activate when a user asks about unrelated OSS topics (npm publishing, pip packaging, etc.)
- Artifact output (CONTRIBUTING.md, issue templates, code.json) is consistent with the requirements described in `docs/publishing/prepare.md` and `docs/accepting/index.md` — verified by an OSPO member before merging

## Non-Goals

- No Q&A chatbot over guide content (no RAG/search)
- No MCP servers or external integrations in v1
- No per-repo CLAUDE.md changes required
- No automated file writing — all artifact output is in chat for user review

## Future Considerations

- Submit to `anthropics/claude-plugins-official` external plugins directory for broader discoverability
- Modularize skill into per-stage files if SKILL.md grows too large
- Add Gemini extension support (`GEMINI.md`) for non-Claude AI tools
- Define version bump policy once plugin is in active use
