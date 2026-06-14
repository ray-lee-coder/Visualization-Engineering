# Azure 架构审查 Agent

> 全自动架构审查 + Excalidraw 架构图

| 属性 | 值 |
|------|-----|
| **仓库** | https://github.com/Azure-Samples/agent-architecture-review-sample |
| **类型** | 端到端 Agent 方案 |
| **部署** | Python / Docker |

## 核心流程

1. 读取架构描述或基础设施代码
2. 调用 LLM 审查架构合理性（安全/成本/性能/可靠性）
3. 自动生成 Excalidraw 架构图（手绘风格）
4. 输出审查报告 + 架构图

## Agent 场景

输入：Terraform / Bicep / 文字描述。输出：结构化审查报告 + 可直接编辑的 Excalidraw 图。企业级架构交付流水线。
