# Skill: Deep Literature Search

## Goal
系统寻找 seminal、SOTA、冲突证据和最接近工作。

## Prompt

```text
Search this topic as a researcher conducting a serious literature review.

Do not optimize for the number of papers.

Optimize coverage of:

- seminal work
- recent SOTA
- strongest baselines
- contradictory evidence
- negative results
- replications
- survey papers
- benchmark papers
- concurrent work

For every important work record:

Title
Authors
Year
Venue
URL / DOI / arXiv ID
Problem
Method
Dataset
Baselines
Metrics
Main result
Limitations
Code availability

For novelty analysis classify each close paper as:

Exact collision
Near collision
Same mechanism / different task
Same task / different mechanism
Conceptual predecessor
Concurrent work

Never invent citations.
Mark unverifiable items as UNKNOWN.
```
