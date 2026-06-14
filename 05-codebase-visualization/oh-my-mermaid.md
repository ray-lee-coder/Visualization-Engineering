# Oh My Mermaid

> Claude Code 理解代码库 → 结构化架构图

| 属性 | 值 |
|------|-----|
| **仓库** | https://github.com/oh-my-mermaid/oh-my-mermaid |
| **类型** | Agent Skill / 提示词模板 |
| **工具** | Claude Code + Mermaid CLI |

## 工作流程

1. Claude Code 扫描代码库（文件结构、依赖、类继承）
2. Agent 分析架构关系
3. 输出 Mermaid 架构图（C4 / 组件 / 类图）
4. 通过 Mermaid CLI 渲染为 PNG/SVG

## 亮点

- 结构化输入 → 清晰的分层架构图
- 支持 React / Vue / Python / Java 等多语言
- Agent 自主完成，无需人工标记
