# s09: GUI 与进度

> 可视化与进度。

## 问题

当 workflow 变长, 你需要可视化管理与实时进度, 否则很难调试。

## 解决方案

1. 使用 CLI 启动 GUI
2. 在生成流程里使用进度回调

## 启动 GUI

```bash
cd workflow-use/workflows
python cli.py launch-gui
```

默认会打开本地 UI, 用于查看和运行 workflow。

## 进度回调示例

```python
workflow = await service.generate_workflow_from_prompt(
    prompt="Search for Python docs",
    agent_llm=llm,
    extraction_llm=llm,
    on_step_recorded=lambda s: print(f"Step {s['step_number']}: {s['description']}"),
    on_status_update=lambda msg: print(f"Status: {msg}"),
)
```

完整示例见:

```bash
python examples/progress_tracking_example.py
```

## 试一试

1. 在回调里把日志写入文件
2. 用 GUI 运行你自己的 workflow
