# Diamond Build Skill

`diamond-build-skill` 是 Diamond 系列里的第二个核心 Skill。

它不负责判断一个需求值不值得做，这件事交给 `Diamondneed-skill`。它负责在需求已经通过初步验证之后，把需求、SKU、竞品观察和商业判断，快速整理成一份可以交给 Codex / Claude Code / Cursor / Gemini CLI 执行的产品开发蓝图。

一句话：

> Diamondneed-skill 判断“要不要做”，Diamond Build Skill 判断“怎么做、做多大、用什么技术栈、怎么交给 AI 编程工具开发”。

---

## 核心目标

这个 Skill 的目标不是写一份漂亮但不能落地的 PRD，而是减少从需求洞察到开发执行之间最耗时间的反复沟通。

它应该帮助你快速输出：

- 产品一句话定义
- 目标用户与核心痛点
- MVP 功能边界
- 明确不做什么
- 用户流程
- 页面结构
- UI / UX 风格
- 技术栈选择
- 前端架构
- 后端架构
- 数据库模型
- API 设计
- 权限与商业化设计
- AI 调用方案
- 风险和成本控制
- Codex 分批开发任务
- 验收标准
- 上线检查清单

---

## 与 Diamondneed-skill 的关系

```text
真实案例 / know-how / 竞品观察 / 用户反馈
        ↓
Diamondneed-skill
需求洞察、市场验证、SKU判断、Go / No-Go
        ↓
Demand-to-Build Handoff
需求到开发交接单
        ↓
Diamond Build Skill
产品开发蓝图、技术框架、UI、数据库、API、Codex任务
        ↓
Codex / Claude Code / Cursor / Gemini CLI
快速开发 MVP
        ↓
上线测试 / 销售 / 数据反馈
        ↓
反哺两个 Skill
```

---

## 什么时候使用

当你已经通过 Diamondneed-skill 或自己的判断确认一个需求可以进入开发阶段时，使用这个 Skill。

典型触发语：

```text
进入 DiamondBuildSpec-skill，生成开发蓝图。
```

```text
这个需求确认要做，帮我生成完整开发方案。
```

```text
根据前面的需求分析，整理一份能交给 Codex 开发的项目方案。
```

```text
把这个 SKU 变成一个轻量级工具，给我产品结构、技术栈、数据库、API 和 Codex 任务。
```

---

## 不适合做什么

这个 Skill 不负责：

- 重新做市场调研
- 判断需求有没有人买
- 写营销文案
- 写小红书笔记
- 深度法律合规审查
- 直接替代 Codex 写完整项目代码

它的核心职责是把“商业需求”翻译成“开发蓝图”。

---

## 推荐使用方式

1. 先用 `Diamondneed-skill` 分析需求。
2. 从 Diamondneed 输出里拿到 `Demand-to-Build Handoff`。
3. 把交接单丢给本 Skill。
4. 本 Skill 输出 `Product Build Spec`。
5. 把 `Product Build Spec` 交给 Codex 分批开发。
6. 开发、上线、销售后，把实际问题反哺到本 Skill。

---

## 仓库结构

```text
.
├── SKILL.md
├── README.md
├── references/
│   ├── build-principles.md
│   ├── codex-execution-rules.md
│   ├── database-api-design-rules.md
│   ├── default-tech-stacks.md
│   ├── diamondneed-handoff.md
│   ├── product-pattern-library.md
│   ├── risk-scope-rules.md
│   └── ui-style-defaults.md
├── templates/
│   ├── acceptance-checklist-template.md
│   ├── case-update-template.md
│   ├── codex-batch-plan-template.md
│   ├── input-template.md
│   └── product-build-spec-template.md
├── examples/
│   ├── example-ai-xiaohongshu-cover-tool.md
│   └── example-teacher-resource-tool.md
└── CHANGELOG.md
```

---

## 迭代原则

每次看到新的真实案例、开发返工、Codex 卡点、用户反馈、支付/交付/售后问题，都不要只停留在聊天记录里。

要沉淀成：

```text
1. 原始案例
2. 需求洞察
3. 开发方案判断
4. 适用边界
5. 反例提醒
6. 应该更新到哪个文件
```

这个 Skill 最终要成为一个“需求到产品开发”的流水线，而不是一份静态文档。
