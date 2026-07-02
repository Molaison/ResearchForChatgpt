---
layout: default
title: 首页
---

<section class="hero">
  <p class="eyebrow">Agent Research Archive</p>
  <h1>ResearchForChatgpt</h1>
  <p class="lead">这里用于沉淀由 ChatGPT / Agent 生成的研究报告。报告以 Markdown 为主，可以混合 HTML 组件；每次报告写入仓库后，GitHub Pages 会重新构建站点。</p>
</section>

<section class="grid">
  <div class="card">
    <h2>目录约定</h2>
    <p>正式报告放在 <code>research/YYYY/MM/DD/&lt;slug&gt;/report.md</code>。辅助文件可以包括 <code>prompt.md</code>、<code>plan.md</code>、<code>sources.md</code>、<code>runlog.md</code> 和 <code>artifacts/</code>。</p>
  </div>
  <div class="card">
    <h2>报告格式</h2>
    <p>报告文件使用 YAML front matter 标记元信息，并设置 <code>report: true</code>，正文可以自由混合 Markdown 与 HTML。</p>
  </div>
  <div class="card">
    <h2>更新方式</h2>
    <p>新增或修改报告后，站点会通过 GitHub Pages / GitHub Actions 自动重新发布。若 Pages 未启用，需要先在仓库 Settings → Pages 中配置一次。</p>
  </div>
</section>

## 最新报告

{% assign reports = site.pages | where: "report", true | sort: "date" | reverse %}
{% if reports.size > 0 %}
<div class="grid">
{% for report in reports limit: 6 %}
  <article class="report-card">
    <p class="date">{{ report.date | date: "%Y-%m-%d" }}{% if report.status %} · {{ report.status }}{% endif %}</p>
    <h3><a href="{{ report.url | relative_url }}">{{ report.title }}</a></h3>
    {% if report.summary %}<p>{{ report.summary }}</p>{% endif %}
    {% if report.tags %}
    <div class="tags">
      {% for tag in report.tags %}<span class="tag">{{ tag }}</span>{% endfor %}
    </div>
    {% endif %}
  </article>
{% endfor %}
</div>
<p><a href="{{ '/reports/' | relative_url }}">查看全部报告 →</a></p>
{% else %}
<p class="muted">还没有正式报告。请参考 <a href="{{ '/reports/template/' | relative_url }}">报告模板</a> 创建第一篇报告。</p>
{% endif %}
