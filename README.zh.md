# People Node Intake

[English](./README.md) | [中文](./README.zh.md)

People Node Intake 用来把零散的人物相关输入，收成安全的人物节点录入决策和任务衔接结果。

## 最适合的场景

- 基于 Obsidian 的人物关系记忆
- 创始人或运营者的个人知识系统
- 带人工复核的商务人物追踪
- 需要人物到事项映射的项目与复盘系统

## 什么时候用

- 用户提到某个具体人物
- 用户粘贴聊天记录、截图、会议纪要或人物笔记
- 用户想记住、跟踪、补背景某个人
- 用户在见人前想快速回忆“这人是谁”
- 用户同时提到人物和后续动作

## 不适合的场景

- 全自动 CRM 灌库
- 法律、欺诈、拉黑类高风险定性判断
- 没有人审的高频批量建档

## 前置依赖

- 有可用的 Obsidian Vault
- Vault 中存在 `Library/People/`
- 有任务协议承接后续动作
- 有 [Synaptic Link](https://github.com/dlxeva/synaptic-link) 或同类检索能力做人物召回

## 安装方式

把这个文件夹复制到你的 skill 目录中。

示例路径：

- `~/.claude/skills/people-node-intake`
- `~/.openclaw/workspace/skills/people-node-intake`

## 快速开始

1. 把 skill 放进你的 skill 目录。
2. 确认 Vault 中已有 `Library/People/`。
3. 用类似 `记一下这个人，某合作方的商务负责人` 的输入触发它。
4. 检查结果应该是新建、追加、候选还是待确认。

## 输出约定

每次执行都会返回：

- 处理对象
- 操作类型
- 新增事实
- 新增待观察
- 待验证假设
- 关联事项
- 是否转任务
- 落盘路径

## 当前限制

- 社交动态碎片不能直接变成 confirmed 事实
- 去重仍主要依赖 alias 和上下文
- 敏感判断必须人工确认
- v1 不包含图谱可视化、提醒自动化和自主 CRM 流程

## 兼容结构

- 核心 skill 入口：`SKILL.md`
- 详细参考资料：`references/`
- 虚构示例节点：`examples/`
- 许可证：`LICENSE.txt`

## License

见 `LICENSE.txt`
