# drawio-skill 代码库可视化

> drawio-skill 内置的代码库→架构图能力

| 属性 | 值 |
|------|-----|
| **所在 skill** | drawio-skill (Hermes Agent) |
| **类型** | 代码分析 + 图生成 |
| **引擎** | Graphviz / draw.io |

## 支持语言

- **Python**: import 图, 类继承
- **JavaScript**: module 依赖, 组件树
- **Go**: package 依赖, struct 关系
- **Rust**: module 图, trait 继承

## 流程

1. 扫描源码 AST / 依赖分析
2. 生成 Graphviz DOT 布局
3. 输出为 `.drawio` XML → CLI 渲染为 PNG

Agent 一句指令即可将任意代码库导出为可编辑的 draw.io 架构图。
