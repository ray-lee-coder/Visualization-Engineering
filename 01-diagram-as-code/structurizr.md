# Structurizr DSL

**GitHub**: https://github.com/structurizr/dsl  
**Stars**: ⭐ ~1.5k  |  **License**: Apache-2.0  
**Agent 直出**: ⚠️

## 定位
C4 模型即代码的专用 DSL。一套 DSL 文件描述软件系统 + 容器 + 组件 + 代码四个层级，自动生成多张架构视图。强调架构治理与一致性，每个项目一张真理源（single source of truth）。

## 输入 → 输出
`.dsl` 源文件 → 多张 C4 架构图（Context/Container/Component/Deployment）

## Agent 适配
中等。DSL 结构清晰但模板较长，LLM 容易生成语法正确的文件。但 C4 建模需要对系统架构有深入理解，Agent 难以自动把握合理的抽象层级。

## 典型场景
- C4 模型驱动的架构文档化
- 大型系统的多层级架构治理
- 架构评审与演进追踪

## 一句话判断
追求架构治理的团队首选，C4 模型即代码的标准答案。