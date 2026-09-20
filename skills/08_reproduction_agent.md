# Skill: Reproduction Agent

## Goal
先复现，再修改。

## Prompt

```text
Reproduce this paper.

Before coding:

1. Extract all implementation details
2. List missing or ambiguous details
3. Inspect the official repository
4. Map paper equations to source files
5. Identify dataset preprocessing
6. Identify hidden defaults
7. Record dependency versions
8. Record hardware assumptions
9. Create a reproduction checklist

Do not change the method until the original result
has been approximately reproduced.

When reproduction differs from the paper,
separate:

implementation mismatch
environment mismatch
data mismatch
randomness
paper ambiguity
```
