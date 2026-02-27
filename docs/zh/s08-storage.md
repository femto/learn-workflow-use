# s08: 存储与复用

> 存储即资产。

## 问题

workflow 生成之后如何长期保存、检索、复用?

## 解决方案

用内置的 storage 服务。CLI 提供 list / run / info / delete。

## 最小步骤

```bash
cd workflow-use/workflows

python cli.py list-workflows
python cli.py workflow-info <workflow-id>
python cli.py run-stored-workflow <workflow-id> --prompt "Fill the form with test data"
python cli.py delete-workflow <workflow-id>
```

## 试一试

1. 用 `generate-workflow` 生成后再 `list-workflows`
2. 试试 `--generation-mode` 过滤
