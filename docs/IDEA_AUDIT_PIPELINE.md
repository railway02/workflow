# Research Idea Audit Pipeline

用于已经有初步 Idea 的 AI / CS 研究项目。

---

# Phase 0 — Normalize the Idea

先禁止提出新方法。

把 Idea 结构化为：

```text
Problem:
Observation:
Hypothesis:
Mechanism:
Method:
Claim:
Setting:
Expected evidence:
Falsification condition:
```

若其中任何一项含糊，先补齐。

---

# Phase 1 — Novelty Collision Test

## Step 1: Decompose

将 Idea 拆成：

```text
Problem
Mechanism
Claim
Setting
```

## Step 2: Search independently

不要只搜索完整句子。

```text
mechanism + problem
mechanism + adjacent task
same problem + alternative mechanism
same mechanism + different task
conceptual predecessor
recent concurrent work
```

## Step 3: Label every close paper

```text
Exact collision
Near collision
Same mechanism / different task
Same task / different mechanism
Conceptual predecessor
Concurrent work
```

## Step 4: Write the Delta

必须能够用一句话说清：

> Existing work does X under Y; we test/propose/discover Z under W.

如果无法清楚写出 delta，不要继续大规模实验。

---

# Phase 2 — Adversarial Kill Test

要求 Reviewer 假设 Idea 是：

```text
wrong
unoriginal
unnecessary
misleading
```

搜索：

1. Prior work already implementing the core idea
2. Simpler baselines
3. False hidden assumptions
4. Failure cases
5. Misleading evaluation settings
6. Confounders
7. Data leakage
8. Benchmark artifacts
9. Compute / scale limitations
10. Alternative explanations

每个 criticism 输出：

```text
Failure mode
Evidence
Severity
Cheapest validating experiment
```

---

# Phase 3 — Strongest Baseline Attack

主动寻找最简单、最危险的 baseline：

```text
more compute
larger model
longer context
better prompt
more samples
retrieval
reranking
majority voting
simple regularization
extra training data
parameter-matched control
randomized control
```

核心问题：

> 如果这个 baseline 达到同样效果，我还剩下什么 scientific contribution？

---

# Phase 4 — Idea Mutation

从五个方向改造：

## Higher

是否提升：

```text
capability
accuracy
scale
upper bound
```

## Faster

是否降低：

```text
latency
training time
search complexity
sample complexity
```

## Stronger

是否让结论：

```text
more robust
more general
better controlled
mechanistically grounded
```

## Cheaper

是否减少：

```text
compute
data
memory
labels
parameters
```

## Broader

是否扩展到：

```text
more datasets
more model families
more modalities
more domains
more task classes
```

---

# Phase 5 — Minimum Falsification Experiment

设计最便宜的实验来证明 Idea 错。

模板：

```text
Hypothesis:

Dataset:
Model:
Baselines:
Seeds:
Primary metric:

Mechanism control:
Compute control:
Parameter control:

Expected result:

Kill condition:
```

目标：

```text
fail fast
```

而不是：

```text
produce pretty benchmark table
```

---

# Phase 6 — Alternative Explanation Test

即使结果上涨，也强制提出其他解释：

```text
more parameters
more FLOPs
longer training
better preprocessing
data leakage
prompt effect
sampling randomness
evaluation artifact
implementation advantage
hyperparameter tuning asymmetry
```

逐个设计 control。

---

# Phase 7 — Multi-Reviewer Simulation

## Theory Reviewer

重点攻击：

```text
assumptions
mechanism
logic
identifiability
causal interpretation
```

## Experimental Reviewer

重点攻击：

```text
baselines
datasets
metrics
ablations
statistics
reproducibility
```

## Area Chair

重点：

```text
novelty
importance
scope
positioning
claim strength
overall evidence
```

---

# Phase 8 — Meta Review

汇总：

```text
Criticisms agreed upon by >=2 reviewers
Fatal flaws
Major weaknesses
Cheap fixes
Expensive fixes
Reviewer disagreement
Missing evidence
```

---

# Phase 9 — Final Go / Pivot / Kill Decision

不要用单一分数。

输出：

```text
GO
What must be true before scaling experiments?

PIVOT
Which assumption/method/setting should change?

KILL
What evidence already makes the project unattractive?
```

最终判断必须引用：

```text
prior work
pilot experiment
controls
reviewer critique
```

而不是语言模型主观感觉。
