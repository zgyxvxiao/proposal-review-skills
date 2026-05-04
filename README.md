# proposal-review-skills

一组用于评审飞书提案、PRD、方案文档的轻量 skill。

## 目录结构

```text
proposal-review-skills/
├── codex-proposal-review/
│   ├── SKILL.md
│   └── references/
│       ├── good-review-examples.md
│       ├── review-patterns.md
│       ├── domain-checklists.md
│       └── anti-patterns.md
└── claude-proposal-review/
    └── CLAUDE.md
```

## 适用场景

- Review 飞书提案、PRD、需求评审文档
- 比较正文、comments 和已有评审建议
- 输出飞书可直接粘贴的评审意见、整改要求、复审意见
- 识别支付、出款、渠道接入、商户影响等场景中的典型评审问题

## Codex 用法

把 `codex-proposal-review` 放到 Codex skills 目录下：

```bash
mkdir -p ~/.codex/skills/proposal-review-feishu
cp -R codex-proposal-review/* ~/.codex/skills/proposal-review-feishu/
```

触发后，skill 会优先做三件事：

1. 判断提案是在评审短期机会方案、长期能力方案，还是两者混写
2. 用 comments 校正正文和原有评审建议
3. 输出可直接进入飞书的评审意见或整改要求

按需读取的 reference：

- `good-review-examples.md`
- `review-patterns.md`
- `domain-checklists.md`
- `anti-patterns.md`

## Claude 用法

把 `claude-proposal-review/CLAUDE.md` 放到 Claude Code 项目根目录，或合并到你现有的 `CLAUDE.md` 中。

它适合：

- 统一评审语气
- 先判断问题模式，再出结论
- 避免把“止血动作”误判成“长期方案”

## 设计原则

- 轻量：主逻辑放在 `SKILL.md` / `CLAUDE.md`
- 可扩展：模式、checklist、例子拆到 `references/`
- 偏产品评审：聚焦目标、范围、收益口径、定价、渠道差异、商户影响
- 不评技术实现正确性

## 当前更适合的文档类型

- 支付 / 出款 / 渠道接入提案
- 本地银行 / wallet / bank transfer 相关需求
- 需要把“问题定义 + 根因分析 + 方案建议”讲清楚的文档

## 后续可继续扩展

- 输出模板库
- 反例库
- 分业务域 checklist
- 更细的飞书评审意见短版模板
