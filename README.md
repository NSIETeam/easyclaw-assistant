# 👑 EasyClaw Assistant Pack for Otto

KING's Coder 的完整助手定义，从 EasyClaw 迁移到 Otto，100% 兼容。

## 包含内容

| 组件 | 文件 | 用途 |
|---|---|---|
| Agent 人设 | `agents/kings-coder/SOUL.md` | 灵魂准则 |
| Agent 身份 | `agents/kings-coder/IDENTITY.md` | 身份定义 |
| 用户上下文 | `agents/kings-coder/USER.md` | 用户信息模板 |
| 持久记忆 | `agents/kings-coder/MEMORY.md` | 记忆快照 |
| Agent 定义 | `agents/kings-coder/agent.json` | Otto AgentDefinition |
| 工具备忘 | `workspace/TOOLS.md` | 本地工具配置 |
| 心跳任务 | `workspace/HEARTBEAT.md` | 定时任务模板 |
| 项目配置 | `.otto/settings.json` | Otto 项目级配置 |

## 快速开始

```bash
# 1. 克隆到你的 Otto 项目
git clone https://github.com/NSIETeam/easyclaw-assistant.git .easyclaw-assistant

# 2. 注册 agent 定义
mkdir -p .otto/agents
cp .easyclaw-assistant/agents/kings-coder/agent.json .otto/agents/kings-coder.json

# 3. 启动 Otto，KING's Coder 即可用
otto --agent kings-coder
```

## Otto 兼容性

- ✅ AGENTS.md 格式
- ✅ `.otto/settings.json` 项目配置
- ✅ AgentDefinition JSON 格式
- ✅ SKILL.md frontmatter 格式（预留）
- ✅ System prompt 注入机制

## 许可

Apache-2.0
