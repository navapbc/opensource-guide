# Nava OSS Guide Plugin Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Add `AGENTS.md`, `.claude-plugin/plugin.json`, and `skills/nava-oss-guide/SKILL.md` to the `navapbc/opensource-guide` repo so it functions as an installable Claude Code plugin that guides users through the Nava open source lifecycle.

**Architecture:** Three new files, no code. `AGENTS.md` is a static AI navigation layer readable by any LLM. `plugin.json` is plugin metadata. `SKILL.md` is the Claude Code skill that runs a diagnostic and guides execution.

**Tech Stack:** Markdown, JSON, Claude Code plugin format

---

## File Map

| File | Purpose |
|------|---------|
| `AGENTS.md` | AI navigation layer — maps repo structure and lifecycle for any LLM |
| `.claude-plugin/plugin.json` | Claude Code plugin metadata |
| `skills/nava-oss-guide/SKILL.md` | Diagnostic skill + lifecycle execution guide |

---

## Task 1: Create AGENTS.md

**Files:**
- Create: `AGENTS.md`

- [ ] **Step 1: Create AGENTS.md**

Create `/AGENTS.md` at the repo root with this exact content:

```markdown
# AGENTS.md — Nava Open Source Guide

This file helps AI agents navigate and use the Nava Open Source Program Office (OSPO) guide effectively.

## What This Repo Is

The `navapbc/opensource-guide` is Nava's internal and public guide for working with open source software. It covers the full lifecycle: evaluating third-party OSS, contributing to external projects, publishing Nava projects, and managing them long-term.

**Primary audience:** Nava engineers and staff
**Secondary audience:** External contributors to Nava open source projects

---

## Repo Structure

| Path | Contents | When to read |
|------|----------|--------------|
| `docs/using/` | How to evaluate and adopt third-party OSS. License considerations, government-specific factors. | User is evaluating a dependency or asking about license compatibility |
| `docs/using/license-types.md` | Reference for OSS license types and compatibility with Apache 2.0 | User asks about a specific license |
| `docs/contributing/` | How Nava staff contribute to external OSS projects. CLAs, representing Nava, contribution best practices. | User wants to contribute to an upstream project |
| `docs/contributing/recordkeeping.md` | How to track and document external contributions | User has made or is making an external contribution |
| `docs/publishing/` | Full lifecycle of releasing Nava code as open source | User is preparing to publish or has a project in any stage of the publishing process |
| `docs/publishing/prepare.md` | Pre-release checklist: required files, sensitive data removal, dependency audit | User is preparing code for public release |
| `docs/publishing/approval.md` | Internal review and stakeholder sign-off process. Government contract considerations. | User is seeking approval to publish |
| `docs/publishing/publish.md` | Practical steps: repo creation, settings, CI, issue templates, announcements | User is ready to make a project public |
| `docs/publishing/release.md` | Ongoing release management: versioning, changelogs, maintenance commitments | User is managing an already-published project |
| `docs/launching/` | Special considerations by project type | User is launching a government tech or infrastructure project |
| `docs/launching/government-projects.md` | Government-specific OSS considerations: ATO, contract IP, agency alignment | User is publishing work done under a government contract |
| `docs/launching/infrastructure.md` | Infrastructure and platform project considerations | User is publishing shared infrastructure |
| `docs/promoting/` | Building community and visibility | User wants to grow adoption or engage contributors |
| `docs/promoting/blog.md` | Writing about a project publicly | User wants to write a post or announcement |
| `docs/promoting/citizenship.md` | Being a good open source citizen | User wants to improve community presence |
| `docs/promoting/support.md` | Supporting and sustaining contributors | User is managing an active community |
| `docs/accepting/` | Managing inbound contributions: setting expectations, reviewing PRs, CLAs, community health | User is receiving external contributions |
| `docs/resources/` | Reference material: license types, copyright, code ownership, branding | User has a specific reference question |
| `docs/resources/licenses.md` | License reference table | User needs to look up a specific license |
| `docs/resources/copyright.md` | Copyright guidance for Nava projects | User has a copyright question |
| `docs/resources/ownership.md` | Code ownership at Nava | User has a question about who owns what |
| `docs/resources/branding.md` | Nava branding guidelines for OSS projects | User has a branding question |
| `docs/projects/` | Nava's active open source portfolio | User wants to know what Nava has published |
| `docs/projects/strata.md` | Strata project details | User asks about Strata |
| `docs/projects/oscer.md` | OSCER project details | User asks about OSCER |
| `docs/superpowers/` | **Internal spec and plan files — ignore, not guide content** | Do not read |

**Key files at repo root:**

| File | Purpose |
|------|---------|
| `README.md` | Guide overview and navigation — start here |
| `CONTRIBUTING.md` | How to contribute to the guide itself |
| `CODE_OF_CONDUCT.md` | Community behavioral expectations |
| `SECURITY.md` | How to report security issues in the guide |
| `code.json` | Federal open source metadata (OMB policy compliance) |

---

## How to Use This Guide as an Agent

1. **Read the relevant section** for the user's lifecycle stage — don't synthesize from memory
2. **Do not hallucinate policy** — Nava's OSS policies are documented here; if you're unsure, say so and link to the relevant page
3. **Link to specific pages** when making recommendations (e.g., `docs/publishing/approval.md`)
4. **Government context matters** — many sections have government-specific guidance; apply it when the user is working on a government contract project
5. **The guide is the authority** — if something in your training conflicts with this guide, defer to this guide for Nava-specific practices

---

## Lifecycle Stage Quick Reference

| User's situation | Primary docs |
|-----------------|-------------|
| "Should I use this open source library?" | `docs/using/` |
| "I want to contribute to an upstream project" | `docs/contributing/` |
| "I want to open source this Nava project" | `docs/publishing/prepare.md` → `approval.md` → `publish.md` |
| "This is a government contract project" | `docs/launching/government-projects.md` + `docs/publishing/approval.md` |
| "How do I manage releases?" | `docs/publishing/release.md` |
| "How do I grow our community?" | `docs/promoting/` |
| "Someone submitted a PR to our OSS project" | `docs/accepting/` |
| "What license should I use?" | `docs/resources/licenses.md` + `docs/using/license-types.md` |
| "What has Nava published?" | `docs/projects/` |
```

- [ ] **Step 2: Verify the file**

Confirm the file exists and is valid markdown:
```bash
cat AGENTS.md | head -5
```
Expected: first lines of the AGENTS.md header

- [ ] **Step 3: Commit**

```bash
git add AGENTS.md
git commit -m "docs: add AGENTS.md for AI agent navigation"
```

---

## Task 2: Create plugin.json

**Files:**
- Create: `.claude-plugin/plugin.json`

- [ ] **Step 1: Create the directory and plugin.json**

```bash
mkdir -p .claude-plugin
```

Create `.claude-plugin/plugin.json`:

```json
{
  "name": "nava-oss-guide",
  "description": "Guides Nava team members and contributors through the full open source lifecycle using the Nava OSPO guide. Runs a diagnostic on your project and gives you a prioritized action plan.",
  "version": "1.0.0",
  "homepage": "https://github.com/navapbc/opensource-guide",
  "skills": ["skills/nava-oss-guide"]
}
```

- [ ] **Step 2: Verify valid JSON**

```bash
python3 -c "import json; json.load(open('.claude-plugin/plugin.json')); print('valid')"
```
Expected: `valid`

- [ ] **Step 3: Commit**

```bash
git add .claude-plugin/plugin.json
git commit -m "feat: add Claude Code plugin metadata"
```

---

## Task 3: Create the SKILL.md

**Files:**
- Create: `skills/nava-oss-guide/SKILL.md`

This is the main deliverable. Write it carefully — it contains the actual diagnostic and lifecycle guidance.

- [ ] **Step 1: Create the directory**

```bash
mkdir -p skills/nava-oss-guide
```

- [ ] **Step 2: Create SKILL.md**

Create `skills/nava-oss-guide/SKILL.md` with this content:

````markdown
---
name: nava-oss-guide
description: Use this skill when a user is working on anything related to Nava's open source processes — publishing a Nava project, getting OSS approval, contributing to an external project on behalf of Nava, managing an existing Nava open source project, reviewing inbound contributions, or asking about Nava's open source policies. Also activates when the user runs /oss-guide. Does NOT activate for generic open source questions unrelated to Nava (e.g., "how do I publish to npm", "what is the MIT license").
argument-hint: [describe your project or question]
version: 1.0.0
---

# Nava OSS Guide

You are a guide for Nava's open source program. Your job is to run a quick diagnostic on the user's situation, determine where they are in the open source lifecycle, and give them a clear, prioritized action plan drawn from the [Nava Open Source Guide](https://github.com/navapbc/opensource-guide).

**You never make up policy.** Every recommendation must come from the guide. When in doubt, say so and link to the relevant section.

---

## Step 1: Diagnostic

Read the following files if they exist in the current working directory (use the Read and Glob tools):

- `LICENSE` or `LICENSE.md`
- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`
- `SECURITY.md`
- `.github/ISSUE_TEMPLATE/` (check if directory exists)
- `code.json`
- `README.md` (just the first 30 lines — look for public URL, description, status)

Note what's present and what's missing. Do not report findings yet.

Then ask the user **at most 2 of these questions** (pick the ones most relevant to what you observed — skip any that are already answered by the files you read):

1. "Has this project been through Nava's open source approval process?" (yes / no / not sure)
2. "Is this project already publicly visible on GitHub?" (yes / no / it's private)
3. "Is this project built under a government contract?" (yes / no / not sure)
4. "What are you trying to do today?" (open-ended fallback if context is unclear)

If the user invoked `/oss-guide` with an argument, use that as context and skip questions you can answer from it.

---

## Step 2: Determine Lifecycle Stage

Based on the diagnostic, identify the user's stage:

| Stage | Signals |
|-------|---------|
| **Evaluating OSS** | User is asking about adopting a third-party dependency |
| **Contributing externally** | User wants to contribute to an upstream project |
| **Pre-OSS (starting from scratch)** | No OSS files found, not yet approved |
| **Preparing to publish** | Some files present, not yet approved or published |
| **Getting approval** | Files in place, needs sign-off |
| **Publishing** | Approved, making the repo public |
| **Post-launch: releases** | Already public, managing versions/releases |
| **Post-launch: community** | Already public, growing contributors/promotion |
| **Accepting contributions** | Receiving external PRs or issues |

A user may be in multiple stages simultaneously — address the most immediate one first.

---

## Step 3: Action Plan

Present a prioritized checklist. Lead with what's most urgent or blocking. Format:

```
## Your Open Source Action Plan

**Stage:** [stage name]

### Must do first
- [ ] [action] — [why] ([guide link])

### Next steps
- [ ] [action] — [guide link]

### Already done ✓
- [thing that looks good]
```

Use these guide URLs for links (always link to the specific page, not just the repo root):

- Preparing code: `https://github.com/navapbc/opensource-guide/blob/main/docs/publishing/prepare.md`
- Getting approval: `https://github.com/navapbc/opensource-guide/blob/main/docs/publishing/approval.md`
- Publishing: `https://github.com/navapbc/opensource-guide/blob/main/docs/publishing/publish.md`
- Managing releases: `https://github.com/navapbc/opensource-guide/blob/main/docs/publishing/release.md`
- Government projects: `https://github.com/navapbc/opensource-guide/blob/main/docs/launching/government-projects.md`
- Using OSS: `https://github.com/navapbc/opensource-guide/blob/main/docs/using/index.md`
- Contributing externally: `https://github.com/navapbc/opensource-guide/blob/main/docs/contributing/index.md`
- Accepting contributions: `https://github.com/navapbc/opensource-guide/blob/main/docs/accepting/index.md`
- Promoting: `https://github.com/navapbc/opensource-guide/blob/main/docs/promoting/index.md`
- License reference: `https://github.com/navapbc/opensource-guide/blob/main/docs/resources/licenses.md`

---

## Step 4: Guided Execution

After presenting the action plan, ask: **"Want me to walk through any of these with you, or generate a specific file?"**

If the user says yes, work through items one at a time.

### Generating artifacts

Output all generated content as fenced code blocks in chat. Tell the user to review before applying. Do not write files directly.

#### CONTRIBUTING.md template

When asked, generate a CONTRIBUTING.md appropriate for a Nava project. It must include:
- How to report bugs (link to issue tracker)
- How to suggest features
- How to submit a pull request (branch naming, PR description, review process)
- Code style and standards note
- Reference to the CODE_OF_CONDUCT.md
- CLA/DCO statement (default: no CLA required, Apache 2.0 terms apply)

Base the content on the project's README and any context the user has provided. See guide requirements: `docs/publishing/prepare.md` and `docs/accepting/index.md`.

#### code.json template

`code.json` is required for government projects (OMB M-16-21 compliance). Generate it when the project is government-related:

```json
{
  "version": "2.0.0",
  "measurementType": {
    "method": "modules"
  },
  "releases": [
    {
      "name": "[project name]",
      "version": "[version]",
      "organization": "Nava PBC",
      "description": "[one sentence description]",
      "status": "Production",
      "vcs": "git",
      "repositoryURL": "https://github.com/navapbc/[repo-name]",
      "homepageURL": "https://github.com/navapbc/[repo-name]",
      "downloadURL": "https://github.com/navapbc/[repo-name]/archive/main.zip",
      "languages": ["[primary language]"],
      "tags": ["government", "open-source"],
      "contact": {
        "email": "opensource@navapbc.com"
      },
      "license": "https://spdx.org/licenses/Apache-2.0.html",
      "openSourceProject": 1,
      "governmentWideReuseProject": 0,
      "exemptionText": null,
      "date": {
        "created": "[YYYY-MM-DD]",
        "lastModified": "[YYYY-MM-DD]",
        "metadataLastUpdated": "[YYYY-MM-DD]"
      }
    }
  ]
}
```

Fill in all `[bracketed]` fields with real values from the project context.

#### GitHub issue templates

When asked, generate two templates in `.github/ISSUE_TEMPLATE/`:

**bug_report.md:**
```markdown
---
name: Bug report
about: Report a problem with the project
labels: bug
---

**Describe the bug**
A clear description of what the bug is.

**To reproduce**
Steps to reproduce the behavior.

**Expected behavior**
What you expected to happen.

**Environment**
- OS:
- Version:
- Other relevant details:

**Additional context**
Any other context or screenshots.
```

**feature_request.md:**
```markdown
---
name: Feature request
about: Suggest an idea or improvement
labels: enhancement
---

**Problem statement**
What problem does this solve? Who is affected?

**Proposed solution**
Describe what you'd like to happen.

**Alternatives considered**
Other approaches you've thought about.

**Additional context**
Any other context or mockups.
```

---

## Scope limits

This skill covers Nava's open source practices as documented in the guide. For questions outside that scope:

- Generic OSS licensing questions → answer from general knowledge but note it's not Nava-specific
- Questions about specific Nava projects → refer to `docs/projects/`
- Contract or legal questions → refer to an engineering lead or Nava's legal team
- Questions about this guide itself → refer to `CONTRIBUTING.md` in the guide repo
````

- [ ] **Step 3: Verify frontmatter parses**

Check the frontmatter is valid YAML by confirming the `---` delimiters are correct and the fields match expected format:
```bash
head -10 skills/nava-oss-guide/SKILL.md
```
Expected: frontmatter block with `name`, `description`, `argument-hint`, `version` fields

- [ ] **Step 4: Commit**

```bash
git add skills/nava-oss-guide/SKILL.md
git commit -m "feat: add nava-oss-guide Claude Code skill"
```

---

## Task 4: Smoke Test the Plugin Structure

- [ ] **Step 1: Verify all three files exist**

```bash
ls AGENTS.md .claude-plugin/plugin.json skills/nava-oss-guide/SKILL.md
```
Expected: all three paths listed with no errors

- [ ] **Step 2: Verify plugin.json is valid JSON**

```bash
python3 -c "import json; d=json.load(open('.claude-plugin/plugin.json')); print(d['name'], d['version'])"
```
Expected: `nava-oss-guide 1.0.0`

- [ ] **Step 3: Verify SKILL.md has required frontmatter fields**

```bash
python3 -c "
content = open('skills/nava-oss-guide/SKILL.md').read()
assert content.startswith('---'), 'Missing opening frontmatter'
end = content.index('---', 3)
fm = content[3:end]
for field in ['name:', 'description:', 'version:']:
    assert field in fm, f'Missing {field}'
print('Frontmatter OK')
"
```
Expected: `Frontmatter OK`

- [ ] **Step 4: Final commit if anything was missed**

```bash
git status
# If clean, you're done. If there are uncommitted changes, stage and commit them.
```

---

## Done

All three files are committed. To install the plugin in Claude Code:

```
/plugin install navapbc/opensource-guide
```

(Verify this command format against current Claude Code documentation — the exact syntax may vary.)
