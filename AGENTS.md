# AGENTS.md — EasyClaw Assistant Pack for Otto

## 项目简介

本项目是 **EasyClaw → Otto** 的完整助手移植包。包含 1 个主 Agent + 4 个专业子 Agent 的定义，以及 workspace 配置。

**兼容目标**：Otto v1.6+，协议层共享 AGENTS.md / .otto/ agent.json / SKILL.md 格式。

## 目录结构

```
easyclaw-assistant/
├── AGENTS.md                    # 本文件 — Otto 标准项目入口
├── agents/
│   ├── kings-coder/             #  主 Agent — KING's Coder
│   │   ├── SOUL.md              #                                 灵魂准则
│   │   ├── IDENTITY.md          # 身份定义
│   │   ├── USER.md              # 用户上下文（模板）
│   │   ├── MEMORY.md            # 持久记忆（模板）
│   │   └── agent.json           # Otto AgentDefinition
│   ├── ai-engineer/             #  AI系统构建工程师
│   │   └── agent.json
│   ├── ppt-master/              #  PPT Creation Expert
│   │   └── agent.json
│   ├── automation-rpa/          #  自动化任务录制助手
│   │   └── agent.json
│   └── computer-use/            #  Computer Use
│       └── agent.json
├── workspace/
│   ├── TOOLS.md                 # 工具配置备忘
│   └── HEARTBEAT.md             # 心跳任务（模板）
└── .otto/
    └── settings.json            # Otto 项目级配置
```

## Agent 总览

| Agent Type | 角色 | Max Turns | Model |
|---|---|---|---|
| `kings-coder` | 国王的编程助手 | 50 | claude-sonnet-4-20250514 |
| `ai-engineer` | AI/ML 系统工程 | 40 | claude-sonnet-4-20250514 |
| `ppt-master` | PPT 制作专家 | 60 | claude-sonnet-4-20250514 |
| `automation-rpa` | 任务自动化 | 40 | deepseek-v4-pro |
| `computer-use` | 桌面操控 | 50 | claude-sonnet-4-20250514 |

## Otto 兼容性映射

| EasyClaw 概念 | Otto 对应 | 说明 |
|---|---|---|
| AGENTS.md | `AGENTS.md` | 完全兼容 |
| SOUL.md / IDENTITY.md | agent `systemPrompt` | 注入为 system prompt |
| MEMORY.md | `memory/` 目录 | Otto 内置记忆管理 |
| Subagents | `agents/*/agent.json` | 转换为 Otto AgentDefinition |
| Skills | `.otto/skills/` SKILL.md | 格式兼容 |
| HEARTBEAT.md | Cron 任务 | 建议用 `.otto/cron/` |

## 使用方式

### 1. 克隆到 Otto 项目

```bash
cd <your-otto-project>
git clone https://github.com/NSIETeam/easyclaw-assistant.git .easyclaw-assistant
```

### 2. 注册所有 Agent

```bash
mkdir -p .otto/agents
cp .easyclaw-assistant/agents/*/agent.json .otto/agents/
```

### 3. 注入主 Agent 人设

在 `.otto/settings.json` 中配置 custom system prompt：

```json
{
  "systemPromptAppend": [
    "file://.easyclaw-assistant/agents/kings-coder/SOUL.md",
    "file://.easyclaw-assistant/agents/kings-coder/IDENTITY.md"
  ]
}
```

### 4. 调用子 Agent

Otto 中通过 task 工具调用：

```
task(kings-coder, "修复这个 bug")
task(ai-engineer, "设计一个推荐系统的训练流水线")
task(ppt-master, "做一个 Q3 季度汇报的 PPT")
task(automation-rpa, "把每日数据汇总自动化")
task(computer-use, "帮我在浏览器里填这个表单")
```

## 规则

- 本仓库是纯配置/数据仓库，不包含可执行代码
- `agent.json` 遵循 Otto `AgentDefinition` 接口
- 所有路径使用相对路径
- 隐私信息使用模板占位符
