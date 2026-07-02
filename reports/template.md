---
layout: report
title: 报告模板
date: 2026-07-02
status: template
author: ChatGPT / Agent
summary: 这是后续研究报告的 Markdown + HTML 混合写作模板。
tags: [template, workflow]
permalink: /reports/template/
---

## Front matter 模板

每篇正式报告建议保存为：

```text
research/YYYY/MM/DD/<slug>/report.md
```

文件开头必须包含：

```yaml
---
layout: report
title: 报告标题
date: 2026-07-02
status: completed
author: ChatGPT / Agent
summary: 一句话摘要，会显示在首页和报告列表中。
tags: [protein-design, data, engineering]
report: true
---
```

其中 <code>report: true</code> 会让该报告自动出现在首页和报告列表中。

## Markdown + HTML 混合示例

普通 Markdown 可以直接写：

### 核心结论

1. 结论一。
2. 结论二。
3. 结论三。

也可以嵌入 HTML 组件：

<div class="callout success">
  <strong>建议：</strong> 把关键结论放在报告开头，并明确哪些是事实、哪些是推断、哪些是工程建议。
</div>

<div class="grid">
  <div class="card">
    <h3>数据</h3>
    <p>记录数据源、版本、过滤规则、异常样本处理方式。</p>
  </div>
  <div class="card">
    <h3>方法</h3>
    <p>记录模型、训练策略、评估指标和复现实验配置。</p>
  </div>
  <div class="card">
    <h3>结论</h3>
    <p>记录可执行建议、风险和下一步实验。</p>
  </div>
</div>

## 推荐章节结构

| 章节 | 内容 |
| --- | --- |
| TL;DR | 5-10 条关键结论 |
| 背景 | 为什么要研究这个问题 |
| 方法 | 检索范围、代码仓库、论文、数据源 |
| 发现 | 分主题展开 |
| 工程建议 | 可以落地的流程、脚本、规范 |
| 风险与不确定性 | 标注没有验证或来源不足的部分 |
| Sources | 链接、commit、文档、论文 |

## 资料引用建议

- 对论文、官方文档、GitHub README、代码文件分别列出来源。
- 对代码细节尽量记录具体文件路径、函数名、commit 或 tag。
- 对推断性结论明确写出“这是基于 A/B/C 的推断”。
