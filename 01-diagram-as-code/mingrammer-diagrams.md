# Diagrams (mingrammer)

**GitHub**: https://github.com/mingrammer/diagrams  
**Stars**: ⭐ ~38k  |  **License**: MIT  
**Agent 直出**: ⚠️

## 定位
用 Python 代码生成云架构图。直接 import AWS/Azure/GCP/K8s/Alibaba 的官方图标资源，用 `with Diagram(...):` 上下文管理器编排服务节点和连线。代码即图表，天然可版本化。

## 输入 → 输出
Python 脚本（`from diagrams import ...`） → PNG/SVG 架构图

## Agent 适配
较好。Python 组合对 LLM 友好，库名和节点名直观，Agent 可以自然输出构造代码。但依赖 Graphviz 作为后端渲染引擎，且复杂架构图的节点定位需要多次调整。

## 典型场景
- 云原生架构文档自动生成
- CI/CD 管线中的架构图版本化
- 多云环境（AWS + GCP + K8s）架构展示

## 一句话判断
Python 开发者做云架构可视化的最佳路径，Icon 资源直接打包。