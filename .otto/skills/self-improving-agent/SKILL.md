---
name: self-improving-agent
description: 通用自我改进 Agent。多记忆架构（语义+情节+工作），从所有技能经验中持续学习。
category: ai-ml
otto_tools: []
---

# self-improving-agent

通用自我改进 Agent。多记忆架构（语义+情节+工作），从所有技能经验中持续学习。

## English

Universal self-improving agent. Multi-memory architecture (semantic + episodic + working), learns from all skill experiences.

## 分类

AI/ML (EasyClaw 专家市场迁移)

## Otto 兼容性

### 依赖工具
（无特定工具依赖，由 Agent 运行时决定）

### 使用方式

此技能从 EasyClaw 专家市场迁移，在 Otto 中通过 AGENTS.md 协议的 skill 路由机制激活。
当用户请求匹配 `description` 中描述的任务时，Agent 应加载并遵循本技能的工作流。

### 运行环境

- EasyClaw 原实现: 通过 `easyclaw` 代理调用远程 API 或本地工具
- Otto 迁移: 由 Otto Agent 直接调用对应的本地/远程工具执行

## 迁移状态

- 来源: EasyClaw 专家市场
- 格式: Otto SKILL.md (frontmatter 兼容)
- 状态: ✅ 已迁移（配置/文档层）
