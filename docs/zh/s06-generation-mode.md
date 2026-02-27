# s06: 生成模式

> 一句话生成。

## 问题

你希望描述任务就能得到可复用 workflow, 而不是手写或录制。

## 解决方案

使用 CLI 的 `generate-workflow` 命令。
它会先运行一次 browser-use, 然后把执行历史转成 workflow。

## 最小步骤

```bash
cd workflow-use/workflows
python cli.py generate-workflow "Fill out the contact form on example.com"
```

如果需要云浏览器:

```bash
python cli.py generate-workflow "Search for browser-use" --use-cloud
```

## 试一试

1. 用 `--output-file` 保存到指定位置
2. 生成后立即用 `run-workflow-no-ai` 执行
