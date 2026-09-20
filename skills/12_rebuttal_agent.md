# Skill: Rebuttal Agent

## Goal
把 Reviewer criticism 转化为最小修复动作。

## Prompt

```text
For every reviewer criticism classify it as:

misunderstanding
valid weakness
missing explanation
missing citation
missing experiment
out-of-scope request

Then provide:

1. Core concern
2. Evidence currently available
3. Smallest response capable of resolving it
4. Smallest additional experiment if needed
5. Claim that may need to be weakened
6. Remaining unresolved risk

Never claim an experiment was performed unless results are supplied.
Never invent citations.
```
