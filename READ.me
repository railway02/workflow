# AI/CS Research Idea Toolkit

一套面向 **计算机科学 / 人工智能研究** 的科研 Idea 评估、改进、实验设计与论文自审工具箱。

目标不是让 LLM 替你“判断一个 Idea 好不好”，而是把科研 Idea 变成一个可验证、可证伪、可复现、能经受 Reviewer 攻击的研究项目。

---

## 核心理念

不要这样：

```text
Idea
→ 问 LLM “这个 idea 几分？”
→ 得到 8.7/10
→ 开始投入几个月
```

推荐这样：

```text
Idea v0
  ↓
结构化问题
  ↓
搜索 closest work
  ↓
Novelty collision test
  ↓
Adversarial attack
  ↓
Strongest baseline attack
  ↓
Minimum falsification experiment
  ↓
Multi-reviewer simulation
  ↓
Idea v1
  ↓
Repeat
```

---

## Repository Structure

```text
ai-cs-research-idea-toolkit/
├── README.md
├── docs/
│   ├── TOOLKIT.md
│   └── IDEA_AUDIT_PIPELINE.md
├── skills/
│   ├── 01_problem_formulation.md
│   ├── 02_deep_literature_search.md
│   ├── 03_paper_reader.md
│   ├── 04_sota_mapper.md
│   ├── 05_gap_finder.md
│   ├── 06_hypothesis_generator.md
│   ├── 07_experiment_designer.md
│   ├── 08_reproduction_agent.md
│   ├── 09_result_analyst.md
│   ├── 10_paper_writer.md
│   ├── 11_adversarial_reviewer.md
│   └── 12_rebuttal_agent.md
└── templates/
    ├── IDEA_CARD.md
    ├── IDEA_SCORECARD.md
    └── MULTI_REVIEWER.md
```

---

# 最重要的 5 个判断

一个 Idea 在投入大量时间前，至少回答清楚：

1. **Novelty**  
   最接近的工作是什么？你的 delta 是什么？

2. **Falsifiability**  
   什么结果会证明你的假设是错的？

3. **Strongest Baseline**  
   最简单的 baseline 能不能把你的贡献打掉？

4. **Mechanism**  
   如果实验有效，为什么有效？是否存在更简单解释？

5. **Minimum Experiment**  
   能否在数小时到数天内先做一个“杀死这个 Idea”的小实验？

---

# 推荐工作流

## Stage 1 — Problem Formulation

先把模糊 Idea 改写为：

```text
Problem
Observation
Hypothesis
Mechanism
Method
Expected Evidence
Falsification Condition
```

使用：

`skills/01_problem_formulation.md`

---

## Stage 2 — Literature Collision Test

不是只搜索完整 Idea，而是拆成：

```text
Problem
Mechanism
Claim
Setting
```

分别搜索：

```text
mechanism + problem
mechanism + related task
same problem + alternative mechanism
conceptual predecessor
recent/concurrent work
```

对论文分类：

```text
Exact collision
Near collision
Same mechanism / different task
Same task / different mechanism
Conceptual predecessor
Concurrent work
```

---

## Stage 3 — Kill the Idea

在优化之前，先尝试证明它：

- 已经被做过
- 逻辑不成立
- 可以被简单 baseline 替代
- 实验设计存在 confounder
- improvement 只是 compute / data / parameter 增加
- benchmark 不支持真正 claim
- 规模化后失效

---

## Stage 4 — Improve the Idea

从五个方向 mutation：

```text
Higher
Faster
Stronger
Cheaper
Broader
```

目标不是单纯增加 module，而是尽可能把贡献从：

> “我提出了一个模块”

提升到：

> “我发现并验证了一个可推广的现象、机制或规律。”

---

## Stage 5 — Minimum Falsification Experiment

先问：

> 最便宜的什么实验可以证明我错？

一个典型设计：

```text
1 dataset
1 small/medium model
2 strongest baselines
3 seeds
1 primary metric
1 mechanism-control experiment
```

提前写好：

```text
Kill condition
```

如果失败，就停止或重新设计，不要为了 sunk cost 继续扩大实验。

---

## Stage 6 — Multi-Reviewer Simulation

至少三个独立角色：

```text
Theory Reviewer
Experimental Reviewer
Area Chair
```

最后由 Meta Reviewer 汇总：

```text
Consensus criticisms
Fatal flaws
Cheap fixes
Expensive fixes
Reviewer disagreements
Missing evidence
```

---

# 推荐科研工具栈

完整清单见：

[`docs/TOOLKIT.md`](docs/TOOLKIT.md)

核心组合：

```text
Semantic Scholar / OpenAlex / OpenReview
                ↓
          Zotero + PDFs
                ↓
       MinerU / Docling
                ↓
            PaperQA2
                ↓
        Research Skills
                ↓
 Hydra / MLflow / W&B / DVC
                ↓
 Inspect AI / lm-eval / Promptfoo / Ragas
```

---

# 12 个 Research Skills

| Skill | 作用 |
|---|---|
| Problem Formulation | 把模糊 Idea 变成研究问题 |
| Deep Literature Search | 系统检索文献 |
| Paper Reader | 深读单篇论文 |
| SOTA Mapper | 建证据矩阵 |
| Gap Finder | 找真正 gap |
| Hypothesis Generator | 生成可证伪假设 |
| Experiment Designer | 设计最小有效实验 |
| Reproduction Agent | 复现已有工作 |
| Result Analyst | 优先寻找反例和 confounder |
| Paper Writer | 控制 claim / evidence 边界 |
| Adversarial Reviewer | 主动尝试拒稿 |
| Rebuttal Agent | 分类并解决 reviewer criticism |

进入 [`skills/`](skills/) 即可直接复制使用。

---

# Idea Card

开始投入大量 GPU / 时间之前，建议先完整填写：

[`templates/IDEA_CARD.md`](templates/IDEA_CARD.md)

特别关注：

```text
CORE INSIGHT
DELTA
STRONGEST BASELINE
FALSIFICATION
FATAL RISK
```

如果其中几项仍然说不清楚，通常说明 Idea 还没收敛。

---

# 使用建议

这套 Toolkit 更适合作为：

- ChatGPT / Claude / Codex / Coding Agent 的 system skill
- Research Agent prompt library
- Lab 内部 Idea Review 模板
- 论文开题检查表
- NeurIPS / ICML / ICLR / ACL / CVPR 等投稿前自审流程

建议把自己的研究方向、算力、数据、目标 venue 和时间预算补进这些 Skills，使其成为个人科研 OS。

---

## License

本仓库中的原创模板与 Prompt 可自由修改和二次使用。第三方工具与项目遵循其各自许可证。
