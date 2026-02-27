<picture>
  <img alt="Workflow Use logo - a product by Browser Use." src="./static/workflow-use.png"  width="full">
</picture>

<br />

<h1 align="center">Learn Workflow Use —— 从 0 到 1 写出可复用的语义工作流</h1>

[English](./README.md) | [中文](./README-zh.md)

```
                 WORKFLOW USE 核心路径
                 =====================

录制/执行 -> 行为历史 -> 语义步骤 -> workflow.yaml
                              |
                              v
                     run-workflow(-no-ai)
                              |
                              v
                         结果 + 变量
```

**9 个递进式教程, 从第一个 workflow 到生成、复用与可视化。**
**每一节只加一个机制, 保持心智模型清晰。**

> **s01** &nbsp; *"先跑通一次"* &mdash; 运行一个现成 workflow
>
> **s02** &nbsp; *"录制就是结构"* &mdash; 录制并生成语义 workflow
>
> **s03** &nbsp; *"工作流是数据"* &mdash; 文件结构与 step 类型
>
> **s04** &nbsp; *"变量让它复用"* &mdash; input_schema 与占位符
>
> **s05** &nbsp; *"确定性更快"* &mdash; deterministic 生成
>
> **s06** &nbsp; *"一句话生成"* &mdash; generation mode
>
> **s07** &nbsp; *"像工具一样跑"* &mdash; run-as-tool
>
> **s08** &nbsp; *"存储即资产"* &mdash; list/run/delete
>
> **s09** &nbsp; *"可视化与进度"* &mdash; GUI 与进度回调

---

## 快速开始

```bash
git clone https://github.com/browser-use/workflow-use
cd workflow-use/workflows

uv sync
source .venv/bin/activate
playwright install chromium
cp .env.example .env
```

运行一个示例 workflow:

```bash
python cli.py run-workflow-no-ai examples/workflows/basic/pure_semantic.workflow.yaml
```

## 学习路径

```
Phase 1: 起步与结构                 Phase 2: 生成与复用
======================              ============================
s01  运行现成 workflow     [1]      s05  确定性生成       [3]
     run-workflow-no-ai             use_deterministic_conversion
     |
     +-> s02  录制与生成      [2]    s06  generation mode  [3]
             create-workflow          generate-workflow
     |
     +-> s03  文件结构        [2]    s07  run-as-tool       [2]
     |
     +-> s04  变量复用        [2]    s08  存储与复用        [3]

Phase 3: 可视化与调试
====================
s09  GUI 与进度回调        [2]

[N] = 关键 API 数量
```

## 项目结构

```
workflow-use/
|
|-- extension/           # 浏览器录制插件
|-- workflows/           # Python 包与 CLI (主教程关注点)
|-- ui/                  # 可视化界面
|-- static/              # 资源
+-- README.md            # English 介绍
```

## 文档

| 课程 | 主题 | 格言 |
|------|------|------|
| [s01](./docs/zh/s01-run-workflow.md) | 运行第一个 workflow | *先跑通一次* |
| [s02](./docs/zh/s02-record-workflow.md) | 录制并生成 | *录制就是结构* |
| [s03](./docs/zh/s03-workflow-schema.md) | 文件结构与步骤 | *工作流是数据* |
| [s04](./docs/zh/s04-variables.md) | 变量与复用 | *变量让它复用* |
| [s05](./docs/zh/s05-deterministic.md) | 确定性生成 | *确定性更快* |
| [s06](./docs/zh/s06-generation-mode.md) | 生成模式 | *一句话生成* |
| [s07](./docs/zh/s07-run-as-tool.md) | 工具化运行 | *像工具一样跑* |
| [s08](./docs/zh/s08-storage.md) | 存储与复用 | *存储即资产* |
| [s09](./docs/zh/s09-gui-progress.md) | GUI 与进度 | *可视化与进度* |

## 许可证

MIT
