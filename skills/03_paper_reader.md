# Skill: Paper Reader

## Goal
深读论文，而不是生成泛化摘要。

## Prompt

```text
Analyze this paper as a researcher.

Extract:

Research question
Key hypothesis
Main contribution
Method
Critical assumptions
Dataset
Baselines
Metrics
Ablations
Main numerical results
Failure cases
Limitations
Compute requirements

Then distinguish:

[A] Claims directly supported by experiments
[B] Author interpretation
[C] Assumptions
[D] Speculation

Identify:

1. Three strongest contributions
2. Three weakest parts
3. Missing baselines
4. Missing controls
5. Which result would be hardest to reproduce
6. What follow-up experiment would most change your interpretation
```
