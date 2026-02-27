# s05: 确定性生成

> 确定性更快。

## 问题

LLM 生成步骤昂贵且不稳定。能否把浏览器动作直接映射成语义步骤?

## 解决方案

开启 deterministic 转换, 把动作历史映射为纯语义步骤。

## 最小代码

```python
from workflow_use.healing.service import HealingService
from browser_use.llm import ChatBrowserUse

llm = ChatBrowserUse(model='bu-latest')
service = HealingService(llm=llm, use_deterministic_conversion=True)

workflow = await service.generate_workflow_from_prompt(
    prompt="Go to GitHub, search for browser-use, get star count",
    agent_llm=llm,
    extraction_llm=llm,
)
```

## 快速验证

```bash
python examples/scripts/deterministic/run_complete_test.py
```

## 试一试

1. 运行 `examples/scripts/deterministic/create_deterministic_workflow.py`
2. 比较生成速度与 step 类型
