# 👑 EasyClaw Assistant Pack for Otto

KING's Coder 及 4 个专业子 Agent 的完整定义，从 EasyClaw 迁移到 Otto，100% 兼容。

## Agent 清单

| Agent | 类型 | 用途 |
|---|---|---|
| 👑 **kings-coder** | 主 Agent | 国王的专属编程助手 |
| 🤖 **ai-engineer** | 子 Agent | AI/ML 模型搭建与部署 |
| 📊 **ppt-master** | 子 Agent | PPT 制作（SVG → PPTX） |
| 🤖 **automation-rpa** | 子 Agent | 任务自动化与脚本编写 |
| 🖥️ **computer-use** | 子 Agent | 桌面控制与浏览器自动化 |

## 包含内容

```
easyclaw-assistant/
├── agents/
│   ├── kings-coder/       # 主 Agent（SOUL + IDENTITY + 完整定义）
│   ├── ai-engineer/       # AI 系统构建工程师
│   ├── ppt-master/        # PPT 制作专家
│   ├── automation-rpa/    # 自动化任务录制助手
│   └── computer-use/      # 桌面操控专家
├── workspace/             # 工具备忘 + 心跳模板
├── .otto/                 # Otto 项目配置
└── AGENTS.md              # Otto 协议入口
```

每个 agent 目录包含：
- `agent.json` — Otto `AgentDefinition` 格式（systemPrompt / tools / maxTurns / model）
- 人设文件（主 Agent 有 SOUL.md / IDENTITY.md / USER.md / MEMORY.md）

## 快速开始

```bash
# 1. 克隆
git clone https://github.com/NSIETeam/easyclaw-assistant.git .easyclaw-assistant

# 2. 注册所有 agent
mkdir -p .otto/agents
cp .easyclaw-assistant/agents/*/agent.json .otto/agents/

# 3. 启动 Otto
otto --agent kings-coder         # 主 Agent
otto --agent ai-engineer         # AI 工程师
otto --agent ppt-master          # PPT 专家
otto --agent automation-rpa      # 自动化助手
otto --agent computer-use        # 桌面控制
```

## Otto 兼容性

- ✅ AGENTS.md 格式
- ✅ `.otto/settings.json` 项目配置
- ✅ `agent.json` → Otto `AgentDefinition` 格式
- ✅ systemPrompt / tools / disallowedTools / maxTurns / model
- ✅ SKILL.md 预留

## 许可

Apache-2.0
