# Graphviz DOT

**GitHub**: https://gitlab.com/graphviz/graphviz  
**Stars**: ⭐ ~12k (GitLab)  |  **License**: EPL  
**Agent 直出**: ⚠️

## 定位
图布局的事实标准与基础设施。DOT 语言描述有向图/无向图，内置层次式（dot）和弹簧式（neato/fdp）布局引擎。40 年历史，几乎被所有图表工具引用或依赖。

## 输入 → 输出
`.dot`/`.gv` 源文件 → SVG/PNG/PDF 矢量图表

## Agent 适配
中等。语法古老且布局粒度难以精确控制（node/edge 属性繁多），LLM 对简单图输出可靠，但复杂图需要反复调参。

## 典型场景
- 依赖关系图、调用链可视化
- 树状结构、家族谱、流程图
- 作为后端引擎被其他工具调用

## 一句话判断
最老牌、生态最广泛的图布局引擎，但不是上手最快的。