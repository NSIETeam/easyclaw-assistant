---
name: lark-openapi-explorer
description: 飞书/Lark 原生 OpenAPI 探索：挖掘未经 CLI 封装的原生 API 接口。
category: lark
otto_tools: ["shell", "web_search"]
---

# lark-openapi-explorer

飞书/Lark 原生 OpenAPI 探索：挖掘未经 CLI 封装的原生 API 接口。

## English

Lark OpenAPI Explorer: discover native OpenAPI endpoints not yet wrapped by CLI.

## 分类

飞书办公套件 (EasyClaw 专家市场迁移)

## Otto 兼容性

### 依赖工具
shell, web_search

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
