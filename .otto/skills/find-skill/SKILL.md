---
name: find-skill
description: 帮助用户发现并安装代理技能。当用户问"如何做X"或"有什么技能可以"时使用。
category: meta
otto_tools: ["web_search"]
---

# find-skill

帮助用户发现并安装代理技能。当用户问"如何做X"或"有什么技能可以"时使用。

## English

Help users discover and install agent skills. Use when users ask 'how to do X' or 'is there a skill for'.

## 分类

元技能 (EasyClaw 专家市场迁移)

## Otto 兼容性

### 依赖工具
web_search

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
