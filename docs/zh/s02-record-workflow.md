# s02: 录制并生成

> 录制就是结构。

## 问题

手写 workflow 容易漏细节, 也难保证语义选择器的稳定性。
你需要一种低门槛方式把真实操作变成结构化步骤。

## 解决方案

用 CLI 录制浏览器操作, 自动生成 workflow 文件。

## 最小步骤

```bash
cd workflow-use/workflows

# 录制并生成标准 workflow
python cli.py create-workflow

# 或生成语义 workflow (更适合 no-ai 执行)
python cli.py create-workflow-no-ai
```

录制结束后会提示保存路径, 并生成 `.workflow.yaml`。

## 试一试

1. 录制一个搜索流程, 保存为 `my_search.workflow.yaml`
2. 用 `run-workflow-no-ai` 执行, 验证可复现性
