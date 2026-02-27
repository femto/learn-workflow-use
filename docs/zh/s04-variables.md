# s04: 变量与复用

> 变量让它复用。

## 问题

workflow 如果写死输入, 就无法复用。你需要一种显式参数机制。

## 解决方案

用 `input_schema` 声明变量, 在步骤里用 `{var}` 占位。

## 最小示例

```yaml
input_schema:
  - name: repo_name
    type: string
    required: true

steps:
  - type: navigation
    url: https://github.com/search?q={repo_name}&type=repositories
  - type: click
    target_text: '{repo_name}'
```

CLI 会自动提示输入:

```bash
python cli.py run-workflow-no-ai examples/workflows/parameterized/github_stars_parameterized.workflow.yaml
```

## 试一试

1. 给变量加 `default`
2. 用不同输入跑同一个 workflow, 对比结果
