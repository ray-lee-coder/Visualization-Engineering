# Kroki

> 统一图表渲染 API — 一条 URL 渲染 20+ 格式

| 属性 | 值 |
|------|-----|
| **仓库** | https://github.com/yuzutech/kroki |
| **类型** | 渲染引擎 / API 服务 |
| **部署** | Docker / SaaS (kroki.io) |

## 支持格式

Mermaid · PlantUML · D2 · Graphviz · Vega-Lite · BlockDiag · BPMN · C4 · Excalidraw · ERD · Nomnoml · Pikchr · Structurizr · SVG · Bytefield · SeqDiag · ActDiag · NwDiag · PacketDiag · RackDiag · Wavedrom · DBML — 20+

## 使用方式

```
GET https://kroki.io/mermaid/svg?diagram=...&output_format=svg
POST https://kroki.io/ — body: {"diagram": "...", "type": "mermaid", "output_format": "svg"}
```

Agent 直接 `curl` 渲染 Mermaid/PlantUML 为 SVG 或 PNG，无需本地安装任何引擎。
