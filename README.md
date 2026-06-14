# Visualization Engineering

> **Agent-native Visualization Stack** — 让 Agent 把自然语言、文档、代码库、业务分析，直接转成可编辑、可渲染、可复用的结构化视觉产物。

本仓库系统梳理 **Agent 直出可视化** 赛道的工具链、项目和方法论。不收录"画图软件"，只收录 Agent 能直接产出结构化视觉产物的工具 / skill / 项目。

---

## 总体地图

| 层级 | 代表项目 | 本质 | Agent 直出 |
|------|---------|------|:----------:|
| **图表 DSL 层** | Mermaid, D2, PlantUML, Structurizr, Graphviz | 文本→图 | ✅ 很适合 |
| **可编辑画布层** | draw.io, Excalidraw, Obsidian Canvas, tldraw | JSON/XML 格式 | ✅ 需 skill |
| **Agent Skill 层** | 8 个 SKILL.md 项目 | 给 Agent 的图表能力包 | ✅ 最贴需求 |
| **MCP Server 层** | 9 个 MCP 协议项目 | 协议层工具调用 | ✅ 实时交互 |
| **渲染管线层** | Kroki, Mermaid CLI, draw.io CLI, cairosvg | DSL→图片 | ✅ 很适合 |
| **端到端方案层** | Azure 架构审查 Agent, Paper2Any | 产品级流水线 | ✅ 完整方案 |

---

## 目录

### [📐 图表 DSL 层](01-diagram-as-code/)
| 项目 | 定位 | 
|------|------|
| [Mermaid](01-diagram-as-code/mermaid.md) | 文档图事实标准，Markdown-like 语法 |
| [D2](01-diagram-as-code/d2.md) | 现代 diagram scripting language |
| [PlantUML](01-diagram-as-code/plantuml.md) | UML 成熟生态 |
| [Structurizr DSL](01-diagram-as-code/structurizr.md) | C4 model-as-code |
| [Graphviz DOT](01-diagram-as-code/graphviz.md) | 图布局底层标准 |
| [mingrammer/diagrams](01-diagram-as-code/mingrammer-diagrams.md) | Python 代码画云架构 |

### [🤖 Agent Skills](02-agent-skills/)
| 项目 | 引擎 | 亮点 |
|------|------|------|
| [⭐ drawio-skill](02-agent-skills/drawio-skill.md) ✅ 已安装 | draw.io | 自检修复 · 10k+ 形状 · 321 AI 图标 · 代码库→图 |
| [excalidraw-diagram-skill](02-agent-skills/excalidraw-diagram-skill.md) | Excalidraw | 手绘风格 Agent 直出 · Playwright 渲染 |
| [diagram-design](02-agent-skills/diagram-design.md) | HTML/SVG | 14 种编辑级 · 品牌颜色匹配 |
| [fireworks-tech-graph](02-agent-skills/fireworks-tech-graph.md) | SVG | 8 种视觉风格 · 14 UML · AI 领域模式 |
| [visual-explainer](02-agent-skills/visual-explainer.md) | HTML/Mermaid | 7 子命令 · 幻灯片 · Vercel 部署 |
| [architecture-diagram-generator](02-agent-skills/architecture-diagram-generator.md) | HTML | 深色主题 · 自包含 · Claude 自定义技能 |
| [tikz-diagrams-skill](02-agent-skills/tikz-diagrams-skill.md) | LaTeX TikZ | 学术论文级矢量图 |
| [softaworks/agent-toolkit](02-agent-skills/softaworks-agent-toolkit.md) | 合集包 | c4/draw-io/excalidraw/mermaid 技能包 |

### [🔌 MCP Servers](03-mcp-servers/)
| 项目 | 引擎 | 能力 |
|------|------|------|
| [excalidraw-mcp (官方)](03-mcp-servers/excalidraw-mcp.md) | Excalidraw | 流式手绘 · 无需 Key · MCP App |
| [drawio-mcp-server](03-mcp-servers/drawio-mcp-server.md) | draw.io | 控制编辑器 · 多文档/页 · Mermaid 兼容 |
| [diagram-ai-generator](03-mcp-servers/diagram-ai-generator.md) | diagrams | 多云架构 · 5 工具 · pip 安装 |
| [maaker-excalidraw-mcp](03-mcp-servers/maaker-excalidraw-mcp.md) | Excalidraw | 25+ 图类型 · CJK · Sugiyama 布局 |
| [mcp-mermaid](03-mcp-servers/mcp-mermaid.md) | Mermaid | Agent 动态生成 Mermaid |
| [claude-mermaid](03-mcp-servers/claude-mermaid.md) | Mermaid | Claude Code 实时预览 |
| [awsdac](03-mcp-servers/awsdac.md) | AWS | YAML→图 · MCP + CLI |
| [ai-diagram-maker-mcp](03-mcp-servers/ai-diagram-maker-mcp.md) | SaaS | 远程 MCP 服务 |
| [AgentDoc](03-mcp-servers/agent-doc.md) | Mermaid C4 | 代码库→C4 文档 |

### [🖼 渲染管线层](04-rendering-pipeline/)
| 项目 | 定位 |
|------|------|
| [Kroki](04-rendering-pipeline/kroki.md) | 统一图表渲染 API，支持 20+ 格式 |
| [draw.io CLI](04-rendering-pipeline/drawio-cli.md) | draw.io 命令行导出引擎 |

### [🔍 代码库可视化](05-codebase-visualization/)
| 项目 | 定位 |
|------|------|
| [GitDiagram](05-codebase-visualization/gitdiagram.md) | 任意 GitHub 仓库→交互式架构图 |
| [oh-my-mermaid](05-codebase-visualization/oh-my-mermaid.md) | Claude Code 理解代码库→架构图 |
| [drawio-skill 代码库→图](05-codebase-visualization/drawio-skill-codebase.md) | drawio-skill 内置代码库可视化 |

### [📊 数据可视化](06-data-visualization/)
| 项目 | 定位 |
|------|------|
| [Vega-Lite](06-data-visualization/vega-lite.md) | JSON 语法数据交互图 |

### [🎨 画布 / 节点图 SDK](07-canvas-node-graph/)
| 项目 | 定位 |
|------|------|
| [React Flow](07-canvas-node-graph/react-flow.md) | 节点式工作流 UI 底座 |
| [tldraw](07-canvas-node-graph/tldraw.md) | 无限画布 SDK |
| [Obsidian Canvas](07-canvas-node-graph/obsidian-canvas.md) | 知识库可视化落点 |

### [🏗 端到端方案](08-end-to-end/)
| 项目 | 定位 |
|------|------|
| [Azure 架构审查 Agent](08-end-to-end/azure-architecture-review-agent.md) | 全自动架构审查 + Excalidraw 图 |
| [Paper2Any](08-end-to-end/paper2any.md) | 论文→draw.io 图/PPT/海报/视频 |
| [learn-architecture-drawing-with-ai](08-end-to-end/learn-architecture-drawing.md) | 提示词模板 + SOP 指南 |

---

## 4 条产品路线

| 路线 | 格式 | 适合场景 | 代表项目 |
|------|------|---------|---------|
| Agent → Mermaid | Markdown | 文档图、README、PRD | Mermaid + mcp-mermaid |
| Agent → draw.io XML | .drawio | 正式架构交付、企业图 | drawio-skill + drawio-mcp-server |
| Agent → SVG/HTML | HTML | 内容表达图、商业框架 | diagram-design + visual-explainer |
| Agent → Canvas/JSON | JSON | 知识库、交互图、产品化 | excalidraw-mcp + React Flow |

---

## 选型参考：你的场景

| 目标 | 首选 | 备选 |
|------|------|------|
| Agent 生成正式图表文件 | **drawio-skill** ✅ 已装 | fireworks-tech-graph |
| Agent 生成文档内图表 | **Mermaid + mcp-mermaid** | Kroki |
| Agent 生成内容表达图 | **diagram-design** | visual-explainer |
| Agent 生成 AI/Agent 技术图 | **fireworks-tech-graph** | drawio-skill |
| Agent 帮你理解开源项目 | **GitDiagram** | oh-my-mermaid |

---

> 收录标准：开源 · Agent 可直出 · 结构化视觉产物 · 有维护活性
>
> 维护：@ray-lee-coder | 贡献：PR welcome
