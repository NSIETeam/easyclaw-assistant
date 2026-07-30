# AGENTS.md — EasyClaw Assistant Pack for Otto

## 项目简介

本项目是 **EasyClaw → Otto** 的助手移植包。包含 KING's Coder 的完整助手定义：
agent 人设（SOUL / IDENTITY）、workspace 配置、skills 技能、subagent 定义、以及
Otto 兼容的运行时配置。

**兼容目标**：Otto v1.6+，协议层共享 AGENTS.md / .otto/ SKILL.md / agent 定义
格式。

## 目录结构

```
easyclaw-assistant/
├── AGENTS.md                    # 本文件 — Otto 标准项目入口
├── agents/
│   └── kings-coder/
│       ├── SOUL.md              # Agent 灵魂准则（Otto system prompt 注入）
│       ├── IDENTITY.md          # Agent 身份定义
│       ├── USER.md              # 用户上下文（模板，部署时替换）
│       ├── MEMORY.md            # 持久记忆（模板）
│       └── agent.json           # Otto agent 定义（model / tools / policy）
├── workspace/
│   ├── TOOLS.md                 # 工具配置备忘
│   └── HEARTBEAT.md             # 心跳任务（模板）
├── .otto/
│   ├── settings.json            # Otto 项目级配置
│   └── skills/                  # Otto 兼容的技能
│       └── <skill-name>/
│           └── SKILL.md
└── README.md
```

## Otto 兼容性映射

| EasyClaw 概念 | Otto 对应 | 说明 |
|---|---|---|
| AGENTS.md | `AGENTS.md` | 完全兼容，Otto 原生读取 |
| SOUL.md | agent `systemPrompt` 一部分 | Otto 注入为 system prompt |
| IDENTITY.md | agent `systemPrompt` 一部分 | 同上 |
| MEMORY.md | `memory/` 目录 | Otto 内置记忆管理 |
| TOOLS.md | 本地备忘 | Otto 无直接对应，保留为参考 |
| HEARTBEAT.md | Cron 任务 | Otto 无直接对应，建议用 `.otto/cron/` |
| Skills | `.otto/skills/` SKILL.md | 格式兼容 |
| Subagents | `agent.json` → Otto agent 定义 | 手动转换为 Otto AgentDefinition |

## 使用方式

### 1. 克隆到 Otto 项目

```bash
cd <your-otto-project>
git clone https://github.com/NSIETeam/easyclaw-assistant.git .easyclaw-assistant
```

### 2. 链接 Agent 定义

将 `agents/kings-coder/agent.json` 注册到 Otto 的 agent 系统：

```bash
# Otto 读取 .otto/agents/ 目录下的 agent 定义
cp agents/kings-coder/agent.json .otto/agents/kings-coder.json
```

### 3. 链接 Skills

```bash
# 硬链或复制到 .otto/skills/
cp -r .otto/skills/* .otto/skills/
```

### 4. 注入 Agent 人设

在 Otto 的 `.otto/settings.json` 或 `~/.otto-user/` 中配置 custom system prompt：

```json
{
  "systemPromptAppend": [
    "file://.easyclaw-assistant/agents/kings-coder/SOUL.md",
    "file://.easyclaw-assistant/agents/kings-coder/IDENTITY.md"
  ]
}
```

## 规则

### Otto 开发规范

- 本仓库是纯配置/数据仓库，不包含可执行代码
- SKILL.md 遵循 Otto 的 markdown frontmatter 格式（name / description / version）
- 所有路径使用相对路径，适配 Otto 的 workspace 模型
- 隐私信息（USER.md 中的具体数据）使用模板占位符，部署时替换
