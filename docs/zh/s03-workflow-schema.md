# s03: 文件结构与步骤

> 工作流是数据。

## 问题

workflow 文件到底包含哪些字段? step 类型有哪些? 如果不了解结构, 就很难维护和扩展。

## 解决方案

理解 workflow 的最小结构:

```
name / description / version
input_schema
steps[]
```

## 示例片段

```yaml
name: Pure Semantic Form Fill
version: '1.0'
input_schema:
  - name: first_name
    type: string
    required: true
steps:
  - type: navigation
    url: https://example.com
  - type: input
    target_text: First Name
    value: '{first_name}'
  - type: click
    target_text: Submit
```

## 常见 step 类型

1. `navigation`
2. `click`
3. `input`
4. `extract_page_content`
5. `keypress`

## 试一试

1. 打开 `examples/workflows/basic/pure_semantic.workflow.yaml`
2. 修改 `target_text`, 观察执行效果
