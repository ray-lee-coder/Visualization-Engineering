# Vega-Lite

> 高频交互图形 JSON 语法

| 属性 | 值 |
|------|-----|
| **官网** | https://vega.github.io/vega-lite/ |
| **类型** | 声明式可视化语法 |
| **渲染** | Vega (底层) → SVG / Canvas / WebGL |

## 核心概念

- **Data**: 数据源（JSON / CSV / URL）
- **Mark**: 图形类型 (bar/line/point/area/text/geoshape...)
- **Encoding**: x/y/color/size/shape 等通道映射
- **Transform**: 聚合/过滤/计算字段

## Agent 场景

```json
{
  "$schema": "https://vega.github.io/schema/vega-lite/v5.json",
  "data": {"url": "data.csv"},
  "mark": "bar",
  "encoding": {"x": {"field": "category"}, "y": {"field": "value"}}
}
```

Agent 生成 JSON 即可渲染交互式图表，适合数据驱动的可视化管线。
