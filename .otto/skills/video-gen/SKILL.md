---
name: video-gen
description: AI 视频生成：文生视频、图生视频、漫剧全流程（剧本→角色→分镜→视频→配音→合成）。
category: visual
otto_tools: ["write_file", "shell", "image_generation"]
---

# video-gen

AI 视频生成：文生视频、图生视频、漫剧全流程（剧本→角色→分镜→视频→配音→合成）。

## English

AI video generation: text-to-video, image-to-video, full comic/animation pipeline (script→character→storyboard→video→dub→composite).

## 分类

视觉与品牌 (EasyClaw 专家市场迁移)

## Otto 兼容性

### 依赖工具
write_file, shell, image_generation

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
