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
| `docs/accepting/index.md` | How to set up for contributions, review PRs, handle CLAs, measure community health | User is setting up a project to receive contributions |
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
