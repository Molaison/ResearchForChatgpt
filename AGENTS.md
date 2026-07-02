# ResearchForChatgpt Agent Instructions

This repository is a GitHub Pages research archive. Agents should write durable research outputs in Markdown with optional embedded HTML.

## Output layout

For every substantial research task, create a dated directory:

```text
research/YYYY/MM/DD/<slug>/
  prompt.md
  plan.md
  report.md
  sources.md
  runlog.md
  artifacts/
```

Use lowercase kebab-case for `<slug>`.

## Required report front matter

`report.md` must start with YAML front matter:

```yaml
---
layout: report
title: Descriptive report title
date: 2026-07-02
status: completed
author: ChatGPT / Agent
summary: One concise sentence shown on the homepage and report index.
tags: [tag-one, tag-two]
report: true
---
```

The `report: true` field is required for automatic listing on the homepage and `/reports/` page.

## Writing format

- Use Markdown as the default format.
- Embedded HTML is allowed for cards, callouts, grids, figures, and other layout components.
- Prefer semantic sections: TL;DR, Scope, Findings, Engineering recommendations, Risks, Sources.
- Distinguish facts, direct code observations, and model/agent inferences.
- Keep generated reports self-contained and readable as standalone web pages.

## Source discipline

- Preserve the original user prompt in `prompt.md`.
- Put search/code/paper/source notes in `sources.md`.
- Put execution notes and limitations in `runlog.md`.
- When reporting GitHub code findings, include repository, path, function/class, and commit/tag when available.

## Update policy

Whenever a report is added or modified:

1. Ensure `report.md` has valid YAML front matter and `report: true`.
2. Do not manually edit `reports/index.md` unless the site structure itself changes; the index is generated from Jekyll/Liquid.
3. Commit all files to `main` or open a PR, depending on the caller's instruction.
4. GitHub Pages will rebuild on pushes to `main` once Pages is enabled for this repository.

## Safety and privacy

GitHub Pages sites may be publicly accessible even when the repository is private. Do not publish credentials, private datasets, unpublished manuscripts, or other sensitive material unless the user explicitly confirms it is safe to make public.
