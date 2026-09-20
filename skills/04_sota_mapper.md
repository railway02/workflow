# Skill: SOTA Mapper

## Goal
建立可比较的证据矩阵，避免“不同 setting 下乱比 SOTA”。

## Prompt

```text
Build an evidence matrix.

Rows = papers.

Columns:

problem
method
model
dataset
training data
compute
baseline
metric
result
code availability
limitations

Normalize metrics and evaluation settings whenever possible.

Explicitly mark incomparable settings.

Do not call a method SOTA unless:
- evaluation settings are genuinely comparable
- metrics are the same
- data assumptions are comparable
- model/compute advantages are accounted for
```
