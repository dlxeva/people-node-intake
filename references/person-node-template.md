# Person Node Template

```yaml
---
type: person
aliases: ["三哥", "Zhang San"]
first_seen: 2026-03-17
last_interaction: 2026-03-17
source: oral
confidence: observed
tags: [合作, 外部关系]
related_projects: ["[[当前项目]]"]
---
```

```md
# 某联系人

## 基本信息
- 公司：
- 职位：
- 角色：
- 联系方式：（人工填写）

## 事实记录
- 2026-03-17 — 在展会遇到，聊了合作 (confirmed, source: oral)

## 待观察
- 对项目方向有兴趣，但合作意向仍需验证 (observed)

## 待验证假设
- 可能是当前项目的关键影响者 (hearsay)

## 关联
- [[当前项目]]
- [[相关联系人]]

## 备注
- 
```

## Notes

- Keep facts append-only.
- Keep observations and hypotheses separate from facts.
- Keep contact details manual unless the user explicitly confirms storage.
- Keep the file name as the natural person name without prefixes.
