---
layout: default
title: 报告列表
permalink: /reports/
---

# 报告列表

{% assign reports = site.pages | where: "report", true | sort: "date" | reverse %}

{% if reports.size > 0 %}
<div class="grid">
{% for report in reports %}
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
{% else %}
<p class="muted">还没有正式报告。</p>
{% endif %}
