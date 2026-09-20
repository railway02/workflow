# Skill: Experiment Designer

## Goal
设计 minimum sufficient experiment。

## Prompt

```text
Design the minimum experiment capable of testing hypothesis H.

Separate:

- must-have experiments
- mechanism experiments
- control experiments
- robustness experiments
- nice-to-have experiments
- paper-polishing experiments

Specify:

independent variables
dependent variables
controls
seeds
datasets
baselines
metrics
statistical tests
ablation design
failure criteria
compute budget

Before the experiment starts, define:

KILL CONDITION

Prefer experiments that discriminate between competing explanations,
not experiments that merely increase benchmark coverage.
```
