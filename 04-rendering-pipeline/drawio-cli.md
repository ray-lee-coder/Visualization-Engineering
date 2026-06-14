# draw.io Desktop CLI

> draw.io 桌面版命令行导出工具

| 属性 | 值 |
|------|-----|
| **仓库** | jgraph/drawio-desktop (内置 CLI) |
| **安装** | `brew install drawio` |
| **类型** | 本地渲染引擎 |

## 导出命令

```bash
# .drawio → PNG/SVG/PDF/JPG
drawio input.drawio --export --output output.png
drawio input.drawio --export --format svg --output output.svg

# 保留所有嵌入数据（样式、元数据）
drawio input.drawio --export --embed-diagram --output output.png
```

## Agent 场景

drawio-skill 底层调用此 CLI 将 `.drawio` XML 渲染为可预览图片。支持多页文档 (`--page-index`) 和缩放 (`--scale`)。
