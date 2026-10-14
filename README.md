<h1 align="center">ResearchForChatgpt</h1>

<p align="center">
  <strong>把 ChatGPT / Agent 研究成果整理成可检索、可追溯的报告档案。</strong><br>
  Markdown 写作 · Jekyll 索引 · GitHub Pages 发布
</p>

<p align="center">
  <a href="https://github.com/Molaison/ResearchForChatgpt/stargazers"><img src="https://img.shields.io/github/stars/Molaison/ResearchForChatgpt" alt="GitHub stars"></a>
  <a href=".github/workflows/pages.yml"><img src="https://img.shields.io/badge/deploy-GitHub%20Pages-blue" alt="GitHub Pages workflow"></a>
</p>

<p align="center">
  <a href="https://molaison.github.io/ResearchForChatgpt/">站点地址</a> ·
  <a href="https://molaison.github.io/ResearchForChatgpt/reports/">报告目录</a> ·
  <a href="reports/template.md">报告模板</a> ·
  <a href="#发布到-github-pages">发布指南</a>
</p>

---

## 项目简介

本仓库用 Git 保存研究报告以及支撑报告的 Prompt、计划、来源和执行记录，再由 Jekyll 将 Markdown 渲染成可浏览的网站。

| 组成 | 用途 |
| --- | --- |
| **报告档案** | 按日期和主题存放，便于回溯与引用。 |
| **自动索引** | 标注 `report: true` 的页面会进入首页及 [报告列表](reports/index.md)。 |
| **报告模板** | 统一标题、摘要、结论、来源与不确定性，支持 Markdown 与 HTML。 |
| **自动发布** | `main` 分支更新后，由 GitHub Actions 构建并部署 Pages。 |

## 创建一篇报告

在 `research/` 下按 **年 / 月 / 日 / 主题** 建立目录；主题使用小写 kebab-case：

```text
research/
  2026/10/14/example-topic/
    report.md      # 正式报告
    prompt.md      # 原始需求
    plan.md        # 研究计划
    sources.md     # 引用、检索与代码来源
    runlog.md      # 执行过程及限制
    artifacts/     # 图表、数据与其他产物
```

正式报告 `report.md` 的文件开头至少包含以下 YAML front matter，并按实际内容更新字段：

```yaml
---
layout: report
title: 示例研究标题
date: 2026-10-14
status: completed
author: ChatGPT / Agent
summary: 用一句话说明报告结论。
tags: [research, example]
report: true
---
```

**`report: true` 是自动收录的关键字段。** 新增页面后，无需手动编辑首页或报告列表；Liquid 会在构建时汇总报告并按日期排序。

写作请参考 [完整报告模板](reports/template.md)，研究代理的目录、引用及归档要求见 [AGENTS.md](AGENTS.md)。正式报告应区分**事实、代码观察与推断**，并保留来源与复现信息。

## 发布到 GitHub Pages

本仓库已经提供 [Pages Workflow](.github/workflows/pages.yml)。首次部署需要在 GitHub 仓库设置中：

1. 进入 **Settings → Pages**。
2. 将 **Build and deployment → Source** 设为 **GitHub Actions**。
3. 将报告提交到 `main`，或手动触发 **Deploy GitHub Pages** 工作流。

站点预期地址：**[molaison.github.io/ResearchForChatgpt](https://molaison.github.io/ResearchForChatgpt/)**。实际访问取决于 Pages 是否已启用且部署成功。

## 目录导航

| 路径 | 作用 |
| --- | --- |
| [`index.md`](index.md) | 网站首页和最新报告卡片。 |
| [`reports/index.md`](reports/index.md) | 自动生成的报告索引页面。 |
| [`reports/template.md`](reports/template.md) | Front matter 与写作组件示例。 |
| [`_layouts/`](_layouts/) · [`assets/css/`](assets/css/) | 站点模板与样式。 |
| [`_config.yml`](_config.yml) | Jekyll 配置与站点路径。 |

> **公开发布提醒：** GitHub Pages 的站点内容可能公开访问。推送前请检查并移除密钥、个人数据、未公开手稿及其他不适合公开的研究材料。
