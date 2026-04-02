---
name: people-node-intake
description: Turn person-related input into safe person-node intake decisions for creation, append-only updates, dedup checks, and task handoff. Use when the user mentions a specific person, asks to remember or track someone, pastes notes or screenshots about a person, or mixes a person with follow-up actions.
---

# People Node Intake

## Role

Turn messy person-related input into one safe decision:

- create
- append
- candidate
- needs confirmation

Keep person information and follow-up actions separate.

## Core Rules

1. Separate confirmed facts, explicit user observations, hypotheses, and task actions.
2. Refuse to create a formal node from weak or incomplete identity data.
3. Keep append-only behavior for existing nodes unless explicit confirmation is required.
4. Rewrite emotional or extreme wording into neutral wording before storage.
5. Escalate instead of guessing when identity, evidence, or user intent is unclear.

## Workflow

1. Decide whether the input is person-related.
2. Split the input into:
   - person information
   - task or action content
3. If two or more distinct people appear, split them first and handle one person at a time.
4. Check the minimum node threshold:
   - a name or stable title
   - plus at least one of organization, role, or matter linkage
5. Search existing nodes by:
   - name
   - aliases
   - organization or role
   - project or matter context
   - linked people
6. Choose one operation:
   - create
   - append
   - candidate
   - needs confirmation
7. Extract only:
   - confirmed facts
   - explicit user-stated observations
   - hypotheses needing verification
   - linked matters, projects, or people
   - follow-up actions that must be handed off
8. Route action content to the task protocol instead of burying it in the person node.

## Clarification Policy

- Ask one minimal question at a time.
- Ask at most two rounds of clarification.
- Downgrade to `candidate` or keep only raw material if identity or intent is still unclear after that.

## Hard Rules

1. Mark every fact line with item-level confidence: `confirmed`, `observed`, or `hearsay`.
2. Reject subjective evaluation words from tags and stored labels, including: `不靠谱`, `靠谱`, `厉害`, `废物`, `忽悠`, `骗子`, `天花乱坠`, `差劲`, `垃圾`, `坑人`.
3. Enforce the minimum node threshold. If it is not met, keep the result as `candidate` and do not create a formal node.
4. Mark contradictions with `⚠️` and require confirmation before merge or overwrite.
5. Do not generate new observations from facts. Store only observations explicitly stated by the user.
6. Do not invent causal explanations or motives. Record conflicting claims separately with source labels.
7. Mark counterparty claims as unverified, for example `(对方口述, 未验证)`.
8. Split multi-person input before node decisions. Do not merge multiple people into one intake result.
9. Rewrite emotional or extreme wording into neutral wording; keep the original wording only when quoted context is necessary.
10. Require active confirmation before formal storage for monetary disputes, legal conflicts, fraud accusations, blacklisting claims, or other high-risk judgments.

## Decision Rules

### Create

Create a person node only when:

- the minimum node threshold is met
- the person is clearly relevant to future work, relationship tracking, project context, or review context

### Append

Append when:

- an existing node is found with enough confidence
- the new material is a new fact, interaction, explicit observation, or alias

### Candidate

Use `candidate` when:

- the identity is incomplete
- the information is mostly weak signal
- the material is too thin to justify a formal node

### Needs Confirmation

Use `needs confirmation` when:

- identity collision is possible
- the input contains sensitive judgment
- the evidence conflicts materially
- the user intent is unclear between archive and task

## Output Format

Always return this structure:

```md
## 人物节点录入结果

- **处理对象**：某联系人
- **操作类型**：新建 / 追加 / 候选 / 待确认
- **新增事实**：
  - 2026-03-17 — 在展会遇到，聊了合作 (confirmed, source: oral)
- **新增待观察**：
  - 合作意向待验证 (observed)
- **待验证假设**：
  - 可能是当前项目的关键影响者 (hearsay)
- **关联事项**：[[当前项目]]
- **是否转任务**：是 — 下周跟进
- **落盘路径**：Library/People/某联系人.md
```

If a section is empty, keep the section label and state `无`.

## What Not To Do

- Do not auto-merge ambiguous duplicates.
- Do not turn a social fragment into a confirmed fact.
- Do not auto-maintain reminders, contact details, or relationship graphs in v1.
- Do not replace human judgment for sensitive business, legal, or fraud-related claims.

## References

- Intake detail: `${CLAUDE_SKILL_DIR}/references/intake-sop-detail.md`
- Examples: `${CLAUDE_SKILL_DIR}/references/examples.md`
- Person node template: `${CLAUDE_SKILL_DIR}/references/person-node-template.md`
- QA checklist: `${CLAUDE_SKILL_DIR}/references/test-checklist.md`
