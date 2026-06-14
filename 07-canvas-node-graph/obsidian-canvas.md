# Obsidian Canvas

> Obsidian 知识图谱画布

| 属性 | 值 |
|------|-----|
| **文档** | https://obsidian.md/canvas |
| **类型** | 本地知识库画布 |
| **格式** | JSON (.canvas) |

## 文件结构

```json
{
  "nodes": [
    {"id": "node1", "type": "text", "text": "核心概念", "x": 100, "y": 100},
    {"id": "node2", "type": "file", "file": "note.md", "x": 400, "y": 100}
  ],
  "edges": [
    {"id": "edge1", "fromNode": "node1", "toNode": "node2"}
  ]
}
```

## Agent 场景

Agent 直接生成 `.canvas` JSON 文件。在 Obsidian 中打开即得可视化知识图谱，节点可链接到库内笔记。
