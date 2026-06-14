
╔══════════════════════════════════════════════════════════════╗
║            Visualization Engineering                         ║
║     Agent-native Visualization Stack · 赛道全景图 · 选型手册   ║
╚══════════════════════════════════════════════════════════════╝

**你不是在找"画图软件"，你是在找 Agent 能直接产出可视化交付物的工具链。**

这个仓库就是那张地图。收录标准只有一条：**Agent 能不能直接吐结构化视觉产物**。不能的，再火也不收。

---

## 先讲清楚一个判断

> Agent 直出可视化这件事，底层逻辑不是"AI 画图"，是 **"结构化视觉产物生成"**。

本质区别：
- AI 画图 → 你描述，AI 帮你操作一个画图软件（慢、贵、不可复用）
- 结构化视觉产物 → Agent 直接输出 Mermaid / .drawio XML / Excalidraw JSON / Vega-Lite JSON / SVG / HTML（快、可编辑、可版本管理、可继续改）

这个仓库赌的是**第二条路**。

---

## 赛道地图：6 层结构

```
┌─────────────────────────────────────────────────────────────┐
│  ① 图表 DSL 层     Mermaid · D2 · PlantUML · Structurizr    │
│                    文本 → 图，Agent 最适合的输出目标           │
├─────────────────────────────────────────────────────────────┤
│  ② Agent Skill 层  drawio-skill · diagram-design ·          │
│                    fireworks-tech-graph · visual-explainer   │
│                    SKILL.md 格式，Agent 直接加载使用            │
├─────────────────────────────────────────────────────────────┤
│  ③ MCP Server 层   excalidraw-mcp · drawio-mcp-server ·     │
│                    diagram-ai-generator · mcp-mermaid        │
│                    协议层，Agent 实时调用                      │
├─────────────────────────────────────────────────────────────┤
│  ④ 渲染管线层      Kroki · draw.io CLI · cairosvg           │
│                    DSL → PNG/SVG/PDF，中台化渲染               │
├─────────────────────────────────────────────────────────────┤
│  ⑤ 代码库可视化     GitDiagram · oh-my-mermaid                │
│                    GitHub repo → 架构图，理解代码不用读代码      │
├─────────────────────────────────────────────────────────────┤
│  ⑥ 端到端方案       Azure 架构审查 Agent · Paper2Any          │
│                    产品级流水线，开箱即用（但重）               │
└─────────────────────────────────────────────────────────────┘
```

---

## 你大概会怎么用这个仓库

### 场景 1：给老板 / 客户画架构图

```text
你：帮我画一个微服务架构图，前端 React，后端 Go，
    PostgreSQL，Kafka，K8s 编排

Agent 用 drawio-skill → .drawio XML → PNG/SVG/PDF

结果：正式交付级，可编辑，可继续改
```

→ 去 `02-agent-skills/drawio-skill.md`

### 场景 2：写 README / 文档需要插图

```text
你：帮我画一个流程图，用户登录流程

Agent 用 Mermaid → Markdown fenced code block → 嵌进文档

结果：GitHub 原生渲染，零维护
```

→ 去 `01-diagram-as-code/mermaid.md` + `03-mcp-servers/mcp-mermaid.md`

### 场景 3：理解一个开源项目

```text
你：帮我看看这个 repo 的结构

你打开 https://github.com/xxx/yyy 改成 https://github.diagram/xxx/yyy
或者让 Agent 用 oh-my-mermaid

结果：秒出架构图，不用读一行代码
```

→ 去 `05-codebase-visualization/gitdiagram.md`

### 场景 4：写文章 / 做内容需要配图

```text
你：帮我把这篇分析做成一张框架图

Agent 用 diagram-design → 自包含 HTML+SVG → 截图/导出

结果：编辑级质量，品牌色自动匹配
```

→ 去 `02-agent-skills/diagram-design.md`

---

## 项目一览（按层分）

### 📐 图表 DSL 层 — Agent 最舒服的输出格式

| 项目 | 一句话 | 适合 |
|------|--------|------|
| **[Mermaid](01-diagram-as-code/mermaid.md)** | 文档图事实标准，Markdown 里直接写 | README、PRD、流程图 |
| **[D2](01-diagram-as-code/d2.md)** | 比 Mermaid 更现代的 DSL，布局引擎可换 | 严肃架构图 |
| **[PlantUML](01-diagram-as-code/plantuml.md)** | UML 老大哥，生态最成熟 | UML、时序、部署图 |
| **[Structurizr](01-diagram-as-code/structurizr.md)** | C4 model-as-code，一份 DSL 出多张图 | 企业架构文档 |
| **[Graphviz](01-diagram-as-code/graphviz.md)** | 图布局的底层标准，万物之源 | 依赖图、关系图 |
| **[mingrammer/diagrams](01-diagram-as-code/mingrammer-diagrams.md)** | Python 代码画云架构 | AWS/Azure/GCP 架构 |

### 🤖 Agent Skills — 这个仓库的核心

| 项目 | 引擎 | 凭什么上榜 |
|------|------|-----------|
| **[⭐ drawio-skill](02-agent-skills/drawio-skill.md) ✅ 已装** | draw.io | 自检修复 · 10k+ 形状 · 321 AI 图标 · 代码库→图 |
| **[excalidraw-diagram-skill](02-agent-skills/excalidraw-diagram-skill.md)** | Excalidraw | 手绘风 Agent 直出，Playwright 渲染 |
| **[diagram-design](02-agent-skills/diagram-design.md)** | HTML/SVG | 编辑级 · 品牌色匹配 · 14 种类型 |
| **[fireworks-tech-graph](02-agent-skills/fireworks-tech-graph.md)** | SVG | 8 种视觉风格 · AI 领域模式 (RAG/Agent) |
| **[visual-explainer](02-agent-skills/visual-explainer.md)** | HTML/Mermaid | 7 个命令 · 幻灯片 · Diff Review |
| **[architecture-diagram-generator](02-agent-skills/architecture-diagram-generator.md)** | HTML | 深色主题 · 自包含 · Claude 技能 |
| **[tikz-diagrams-skill](02-agent-skills/tikz-diagrams-skill.md)** | LaTeX | 学术论文级，数学/算法图 |
| **[softaworks/agent-toolkit](02-agent-skills/softaworks-agent-toolkit.md)** | 合集 | 40+ 技能包，c4/draw-io/excalidraw/mermaid 都有 |

### 🔌 MCP Servers — 让 Agent 直接操控画布

| 项目 | 引擎 | 值钱的地方 |
|------|------|-----------|
| **[excalidraw-mcp (官方)](03-mcp-servers/excalidraw-mcp.md)** | Excalidraw | 流式手绘 · 无需 Key · MCP App |
| **[drawio-mcp-server](03-mcp-servers/drawio-mcp-server.md)** | draw.io | 控制编辑器 · 多文档 · Mermaid 兼容 |
| **[diagram-ai-generator](03-mcp-servers/diagram-ai-generator.md)** | diagrams | 多云架构 · 5 工具 · pip install |
| **[maaker-excalidraw-mcp](03-mcp-servers/maaker-excalidraw-mcp.md)** | Excalidraw | 25+ 图类型 · CJK · 自动布局 |
| **[mcp-mermaid](03-mcp-servers/mcp-mermaid.md)** | Mermaid | Agent 动态生成+校验 |
| **[claude-mermaid](03-mcp-servers/claude-mermaid.md)** | Mermaid | Claude Code 实时预览+live reload |
| **[awsdac](03-mcp-servers/awsdac.md)** | AWS | YAML→架构图，AWS 官方 |
| **[ai-diagram-maker-mcp](03-mcp-servers/ai-diagram-maker-mcp.md)** | SaaS | 远程 MCP，需要 API Key |
| **[AgentDoc](03-mcp-servers/agent-doc.md)** | Mermaid C4 | 代码库→C4 文档 |


### 🖼 渲染管线层 — DSL 转图片的最后一公里

| 项目 | 一句话 |
|------|--------|
| **[Kroki](04-rendering-pipeline/kroki.md)** | 统一 API 渲染 20+ 格式，Agent 不用关心具体渲染器 |
| **[draw.io CLI](04-rendering-pipeline/drawio-cli.md)** | .drawio → PNG/SVG/PDF/JPG，支持可编辑嵌入 |

### 🔍 代码库可视化 — 理解代码不用读代码

| 项目 | 一句话 |
|------|--------|
| **[GitDiagram](05-codebase-visualization/gitdiagram.md)** | 把 GitHub URL 的 hub 改成 diagram，秒出交互式架构图 |
| **[oh-my-mermaid](05-codebase-visualization/oh-my-mermaid.md)** | Claude Code 理解代码库 → 结构清晰的架构图 |
| **[drawio-skill 代码库→图](05-codebase-visualization/drawio-skill-codebase.md)** | Python/JS/Go/Rust import 图 + 类继承 |

### 📊 数据可视化 — 不是流程图，但有图

| 项目 | 一句话 |
|------|--------|
| **[Vega-Lite](06-data-visualization/vega-lite.md)** | JSON 语法定义交互式图表，Agent 输出最稳定 |

### 🎨 画布 / 节点图 SDK — 以后做产品用的

| 项目 | 一句话 |
|------|--------|
| **[React Flow](07-canvas-node-graph/react-flow.md)** | 工作流编辑器/Agent 流程 builder 的 UI 底座 |
| **[tldraw](07-canvas-node-graph/tldraw.md)** | 无限画布，Make Real 把手绘变 HTML |
| **[Obsidian Canvas](07-canvas-node-graph/obsidian-canvas.md)** | 知识库可视化落点 |

### 🏗 端到端方案 — 完整的，但重

| 项目 | 一句话 |
|------|--------|
| **[Azure 架构审查 Agent](08-end-to-end/azure-architecture-review-agent.md)** | 输入架构描述 → 风险分析 + Excalidraw 图 |
| **[Paper2Any](08-end-to-end/paper2any.md)** | 论文 → draw.io 图 / PPT / 海报 / 视频 |
| **[learn-architecture-drawing](08-end-to-end/learn-architecture-drawing.md)** | 提示词模板 + 多工具 SOP 指南 |

---

## 4 条产品路线（你怎么选）

```
路线 1: Agent → Mermaid
  最轻、最快、文档标配
  适合: README · PRD · 技术文档 · 知识库
  缺点: 复杂布局难控、正式交付感不够
  代表: Mermaid + mcp-mermaid

路线 2: Agent → draw.io XML  ← 推荐主力
  最适合正式交付
  适合: 企业架构图 · 客户方案 · 系统拓扑 · UML/ER
  缺点: XML 长，需要 skill 和校验
  代表: drawio-skill + drawio-mcp-server

路线 3: Agent → SVG / HTML+SVG
  最适合内容表达
  适合: 商业框架图 · 文章配图 · 课程图 · 产品机制
  缺点: 后续编辑不如 draw.io 方便
  代表: diagram-design + visual-explainer

路线 4: Agent → Canvas / Node Graph
  最适合知识库和产品化
  适合: Obsidian Canvas · Excalidraw · React Flow
  缺点: 需要前端承载
  代表: excalidraw-mcp + React Flow
```

---

## 按你的场景选

```
你是什么角色/要干什么                          → 先看哪个
─────────────────────────────────────────────────
非程序员，想用 Agent 直出正式图表文件            → drawio-skill（已装）
写 README/文档要插图                           → Mermaid + mcp-mermaid
做内容/文章需要配图                            → diagram-design
研究 AI Agent/RAG 相关技术，需要画技术图         → fireworks-tech-graph
经常 fork 开源项目，想快速理解代码结构            → GitDiagram
用 Obsidian 做知识库，要可视化                    → Obsidian Canvas + excalidraw-diagram-skill
想给团队搭一个自动出图服务                       → Kroki 渲染中台 + drawio-skill
以后想做 Agent workflow builder 产品             → React Flow + tldraw
```

---

## 最后说几句

这个领域正在快速成型。目前的状态是：

- **Mermaid** 是文档图的标准答案，但不是所有场景的答案
- **draw.io XML** 正在成为 Agent 正式图表交付的核心格式（drawio-skill + drawio-mcp-server 两个方向都在押）
- **Agent Skills 生态** 刚起步，2025-2026 年集中爆发，现在是入场好时机
- **MCP 协议** 让 Agent 从"生成文件"进化到"直接操控画布编辑器"
- **最大的空白**：缺一个"文档/代码/业务分析 → 选引擎 → 出图"的端到端 Agent 工作流

这个仓库会持续更新，PR welcome。

---

> 收录标准：开源 · Agent 可直出 · 结构化视觉产物 · 有维护活性
>
> 维护：@ray-lee-coder
