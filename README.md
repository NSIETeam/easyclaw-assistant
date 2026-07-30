#  EasyClaw Assistant Pack for Otto

KING's Coder 及完整的 EasyClaw 专家市场，从 EasyClaw 迁移到 Otto。

## 统计数据

| 组件 | 数量 |
|---|---|
|  主 Agent | 1 (kings-coder) |
|  子 Agent | 4 |
|  专家技能 | **57** |

## Agent 清单

| Agent | 类型 | 用途 |
|---|---|---|
|  **kings-coder** | 主 Agent | 国王的专属编程助手 |
|  **ai-engineer** | 子 Agent | AI/ML 模型搭建与部署 |
|  **ppt-master** | 子 Agent | PPT 制作（SVG → PPTX） |
|  **automation-rpa** | 子 Agent | 任务自动化与脚本编写 |
|  **computer-use** | 子 Agent | 桌面控制与浏览器自动化 |

## 技能分类

| 分类 | 数量 | 技能 |
|---|---|---|
|  办公文档 | 4 | docx, pdf, xlsx, powerpoint-editor |
|  代码与工程 | 3 | github-operations, create-skill, full-output-enforcement |
|  浏览器与 Web | 4 | browser-tool, web-extract, multi-search-engine, Deep Research |
|  前端与设计 | 10 | frontend-design-fusion, design-taste-*, gpt-taste, image-to-code, industrial-brutalist-ui, minimalist-ui, etc. |
|  视觉与品牌 | 3 | image-gen, brandkit, video-gen |
|  金融数据 | 1 | stock-data-pro |
|  语音音频 | 1 | TTS-ASR |
|  AI/ML | 1 | self-improving-agent |
|  元技能 | 1 | find-skill |
|  飞书办公 | **29** | lark-* (审批/文档/日历/IM/邮件/会议/OKR/表格/画板/知识库...) |

## 快速开始

```bash
# 1. 克隆
git clone https://github.com/NSIETeam/easyclaw-assistant.git .easyclaw-assistant

# 2. 注册 agent
mkdir -p .otto/agents
cp .easyclaw-assistant/agents/*/agent.json .otto/agents/

# 3. 链接 skills
ln -s .easyclaw-assistant/.otto/skills .otto/skills

# 4. 启动
otto --agent kings-coder
```

## Otto 兼容性

-  AGENTS.md 格式
-  `.otto/settings.json` 项目配置
-  `agent.json` → Otto `AgentDefinition` 
-  57 个 `.otto/skills/*/SKILL.md` — frontmatter 兼容格式

## 许可

Apache-2.0
