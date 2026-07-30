---
name: TTS-ASR
description: 文本转语音(TTS)和语音转文字(ASR)。Doubao TTS v2，40+ 海外专业音色，支持多语言。
category: audio
otto_tools: ["shell"]
---

# TTS-ASR

文本转语音(TTS)和语音转文字(ASR)。Doubao TTS v2，40+ 海外专业音色，支持多语言。

## English

Text-to-speech and speech-to-text. Doubao TTS v2 with 40+ professional overseas voices, multi-language support.

## 分类

语音音频 (EasyClaw 专家市场迁移)

## Otto 兼容性

### 依赖工具
shell

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
