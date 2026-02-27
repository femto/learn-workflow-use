# s07: 工具化运行

> 像工具一样跑。

## 问题

你希望 workflow 像一个可调用工具, 只给自然语言即可运行。

## 解决方案

使用 `run-as-tool` 或 `Workflow.run_as_tool`。

## CLI 方式

```bash
cd workflow-use/workflows
python cli.py run-as-tool examples/workflows/parameterized/github_stars_parameterized.workflow.yaml \
  --prompt "查 browser-use 的 star 数"
```

## Python 方式

```python
from workflow_use.workflow.service import Workflow
from browser_use.llm import ChatBrowserUse

llm = ChatBrowserUse(model='bu-latest')
workflow = Workflow.load_from_file(
    "examples/workflows/parameterized/github_stars_parameterized.workflow.yaml",
    llm=llm,
)

result = await workflow.run_as_tool("查 browser-use 的 star 数")
print(result)
```

## 试一试

1. 给 prompt 增加更多变量
2. 对比 `run_workflow` 的交互式输入
