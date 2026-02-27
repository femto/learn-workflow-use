# s01: 运行第一个 workflow

> 先跑通一次。

## 问题

你需要确认 workflow 引擎能在你的环境里正常跑起来。
在你写或生成 workflow 之前, 先跑通一个现成的例子, 才有确定性。

## 解决方案

使用 CLI 直接运行示例 workflow, 走一遍完整执行链路。

## 最小步骤

```bash
cd workflow-use/workflows
python cli.py run-workflow-no-ai examples/workflows/basic/pure_semantic.workflow.yaml
```

这个例子是纯语义步骤, 不依赖 LLM, 运行最快、成本最低。

## 你会看到什么

1. CLI 加载 workflow 文件
2. 按顺序执行 navigation / click / input / extract
3. 输出执行结果或报错

## 试一试

1. 换成 `examples/workflows/basic/example_workflow.yaml`
2. 用 `run-workflow` (非 no-ai) 比较行为差异
