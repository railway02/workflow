# AI / CS Research Projects & Tools

> 面向计算机科学 / 人工智能研究的项目目录。重点不是“收藏链接”，而是明确：**它解决科研流程中的哪一个问题、什么时候值得用、怎么组合。**

更新时间：2026-09

---

## 快速入口

| 研究任务 | 建议先看 |
|---|---|
| 找论文 / Prior Art | Semantic Scholar, OpenAlex, OpenReview, Scite |
| 系统综述 | Elicit, ResearchRabbit, Connected Papers |
| PDF → 可供 Agent 使用的数据 | MinerU, Docling, Marker, GROBID |
| 私有论文库 QA / Scientific RAG | PaperQA2 |
| Deep Research | STORM, GPT Researcher |
| Idea 新颖性 / 质量检查 | InnoEval, ResearchStudio, Supervisor-Skills, RINoBench |
| 科研 Skills / MCP | Tashan Research Skills, academic-research-skills, paper-search-mcp, Zotero MCP |
| Repo 级科研 Coding | OpenHands, SWE-agent, Aider |
| 可复现实验 | Hydra, MLflow, W&B, DVC, Optuna |
| LLM / Agent Eval | lm-evaluation-harness, Inspect AI, Promptfoo, DeepEval, Ragas |
| LLM Training / Post-training | TRL, LLaMA-Factory, Axolotl, Unsloth, verl, OpenRLHF |
| Inference / Rollout | vLLM, SGLang |

---

# 1. Literature Discovery & Prior Art

这些工具适合回答：

- 最接近的工作是什么？
- 一个想法是不是已经被做过？
- 哪些论文构成某方向的核心 citation graph？
- 后续工作究竟支持、质疑，还是仅仅引用了某论文？

### Semantic Scholar

- 官网：https://www.semanticscholar.org/
- API：https://api.semanticscholar.org/
- 用途：论文搜索、引用关系、相关推荐、作者与论文图谱。
- 推荐场景：AI/CS 日常检索、自动 prior-art search。

### OpenAlex

- 官网：https://openalex.org/
- API：https://docs.openalex.org/
- 用途：论文、作者、机构、主题、引用关系的开放学术图谱。
- 推荐场景：自己写 Research Agent、批量领域分析、citation graph。

### arXiv

- https://arxiv.org/
- 用途：AI/CS 前沿预印本。
- 注意：预印本不等于已经过同行评审。

### OpenReview

- https://openreview.net/
- 用途：论文、review、author response、discussion。
- 特别适合：ICLR / NeurIPS workshop 等公开评审生态。

### Scite

- https://scite.ai/
- 用途：查看 citation context，辅助判断后续文献是在 supporting / contrasting / mentioning。
- 推荐场景：claim verification、citation audit。

### Elicit

- https://elicit.com/
- 用途：literature review、筛选、结构化抽取、evidence table。

### ResearchRabbit

- https://www.researchrabbit.ai/
- 用途：从 seed papers 扩展作者、论文和引用网络。

### Connected Papers

- https://www.connectedpapers.com/
- 用途：快速查看一篇核心论文周围的研究邻域。

### Litmaps

- https://www.litmaps.com/
- 用途：citation map 与长期主题跟踪。

### Zotero

- https://www.zotero.org/
- 用途：长期论文库、PDF、标注、笔记、引用管理。

---

# 2. Scientific RAG / Personal Research Knowledge Base

## PaperQA2

- GitHub：https://github.com/Future-House/paper-qa
- 定位：面向 scientific literature 的 agentic RAG / evidence QA。
- 适合：
  - 自己的论文 corpus
  - citation-aware QA
  - 多论文证据比较
  - contradictory evidence 搜索
  - 建立长期 Research DB

典型问题：

```text
What evidence contradicts hypothesis X?

Which papers use the same benchmark but report
substantially different results?

Compare how these papers define agent memory.
```

**为什么值得研究代码：** 它比最简单的 embedding → top-k → LLM 更接近真正科研检索，需要处理 metadata、检索、上下文压缩、证据组织和引用。

---

# 3. Deep Research / Research Agents

## STORM / Co-STORM

- GitHub：https://github.com/stanford-oval/storm
- 定位：多视角搜索、问题生成、outline 与 long-form synthesis。
- 最值得学习：Research Agent 的“先构建视角和问题，再搜索和综合”的 architecture。

## GPT Researcher

- GitHub：https://github.com/assafelovic/gpt-researcher
- 定位：通用 Deep Research Agent。
- 适合：自己改造 retrieval、source selection、report generation、多 Agent workflow。

## local-deep-research

- GitHub：https://github.com/LearningCircuit/local-deep-research
- 定位：偏本地 / privacy 的 deep research。
- 适合：未发表论文、内部研究、敏感 corpus。

## AI Scientist v2

- GitHub：https://github.com/SakanaAI/AI-Scientist-v2
- 定位：自动化 idea → experiment → analysis → paper 的研究系统。
- 推荐用途：**研究 autonomous scientist architecture**，而不是把输出直接视为可信科研结论。

## Agent Laboratory

- GitHub：https://github.com/SamuelSchmidgall/AgentLaboratory
- 定位：多 Agent 科研流程。
- 推荐用途：理解科研任务如何拆给不同 agent。

---

# 4. PDF / Scientific Document Parsing

很多“LLM 读论文失败”实际上首先是 PDF parsing 失败。

## MinerU

- GitHub：https://github.com/opendatalab/MinerU
- 用途：PDF → Markdown / JSON，并处理 layout、公式、表格、图片等。
- 推荐：科研 PDF ingestion pipeline。

## Docling

- GitHub：https://github.com/docling-project/docling
- 用途：结构化文档处理，适合 RAG / Agent 数据层。
- 推荐：需要统一 PDF、Office 等文档 pipeline 时。

## Marker

- GitHub：https://github.com/datalab-to/marker
- 用途：快速 PDF → Markdown / JSON。
- 推荐：和 MinerU / Docling 用同一批论文做实际 benchmark 后再决定。

## GROBID

- GitHub：https://github.com/kermitt2/grobid
- 用途：scholarly PDF → structured TEI/XML、metadata、references。
- 推荐：大规模论文 metadata / reference pipeline。

---

# 5. Idea Evaluation / Idea Improvement

不要只让一个 LLM 给 Idea 打 1–10 分。更值得使用的是：

```text
Literature grounding
→ collision checking
→ fatal-flaw analysis
→ strongest baseline attack
→ falsification experiment
→ multi-reviewer simulation
```

## InnoEval

- GitHub：https://github.com/zjunlp/InnoEval
- 方向：knowledge-grounded、multi-perspective research idea evaluation。
- 可借鉴：Extraction → Research → Grounding → Evaluation → Report。

## Microsoft ResearchStudio

- GitHub：https://github.com/microsoft/ResearchStudio
- 重点：ResearchStudio-Idea / idea quality 相关 workflow。
- 适合：还没有完整实验结果时，对 Motivation、Method、Problem–Method match 做结构化检查。

## HKUST Supervisor-Skills

- GitHub：https://github.com/HKUSTDial/Supervisor-Skills
- 重点：idea evaluator / supervisor-style research skills。
- 可借鉴：fatal-flaw audit，以及 Higher / Faster / Stronger / Cheaper / Broader 的 idea mutation。

## RINoBench

- GitHub：https://github.com/TimSchopf/RINoBench
- 方向：research-idea novelty evaluation。
- 值得关注：如何把“这个 Idea 是否 novel”从感觉问题转化为 benchmark 问题。

### 本仓库对应模板

- [Idea Audit Pipeline](IDEA_AUDIT_PIPELINE.md)
- [Idea Card](../templates/IDEA_CARD.md)
- [Idea Scorecard](../templates/IDEA_SCORECARD.md)
- [Multi Reviewer](../templates/MULTI_REVIEWER.md)

---

# 6. Research Skills / Prompt Libraries

## academic-research-skills

- GitHub：https://github.com/Imbad0202/academic-research-skills
- 方向：research → write → review → revise 的科研 Skill workflow。
- 推荐：学习 citation verification、source integrity、adversarial review 的 Skill 设计。

## Tashan Research Skills

- GitHub：https://github.com/TashanGKD/tashan-research-skills
- 方向：Paper Search、Deep Research、Baseline Builder、Experiment Design、Statistical Analysis、PaperCheck 等。
- 推荐：把科研习惯从一次性 prompt 变成可复用 Skill。

## Awesome Scientific AI Tools

- GitHub：https://github.com/Harsh9005/awesome-scientific-ai-tools
- 定位：科研 AI 工具、MCP、Agent Skills 总目录。
- 推荐：发现新项目。

## Literature Review Agent Tools

- GitHub：https://github.com/brycewang-stanford/lit-review-agent-tools
- 定位：literature-review agent / tools / MCP 资源索引。

## DAIR.AI Prompt Engineering Guide

- GitHub：https://github.com/dair-ai/Prompt-Engineering-Guide
- 定位：prompting、RAG、agents、context engineering 学习资料。
- 推荐：学方法，不要把它当“万能 Prompt 收藏夹”。

## University of Basel RISE Prompt Library

- GitHub：https://github.com/RISE-UNIBAS/prompt-library
- 定位：大学科研场景 prompt library。
- 推荐：structured extraction、research / programming 类 prompt 设计参考。

---

# 7. Research MCP

科研 Agent 至少需要“可检索真实来源”的工具层。

## paper-search-mcp

- GitHub：https://github.com/openags/paper-search-mcp
- 用途：多来源学术论文搜索。
- 适合：构建 novelty search / literature collision agent。

## arxiv-mcp-server

- GitHub：https://github.com/blazickjp/arxiv-mcp-server
- 用途：arXiv 搜索、获取论文等。

## Zotero MCP

- GitHub：https://github.com/54yyyu/zotero-mcp
- 用途：让 Agent 访问个人 Zotero papers / notes / annotations。
- 很适合作为长期科研记忆层。

## OpenAlex Research MCP

- GitHub：https://github.com/oksure/openalex-research-mcp
- 用途：citation / author / institution / trend analysis。

---

# 8. Coding Agents for Research

## OpenHands

- GitHub：https://github.com/OpenHands/OpenHands
- 用途：repo-level coding、修改代码、跑实验、检查日志。
- 推荐：实验 repo 已经较复杂时。

## SWE-agent

- GitHub：https://github.com/SWE-agent/SWE-agent
- 用途：真实 repository 上的软件工程 Agent。
- 推荐：研究 coding-agent design，或自动修复实验代码。

## Aider

- GitHub：https://github.com/Aider-AI/aider
- 用途：Git-native AI coding。
- 推荐：科研 repo 中需要人保持较强控制权的 coding workflow。

---

# 9. Experiment Reproducibility & Tracking

## Hydra

- GitHub：https://github.com/facebookresearch/hydra
- 用途：结构化实验配置。
- 解决：`train_final2_really_final.py` 式实验管理。

## MLflow

- GitHub：https://github.com/mlflow/mlflow
- 用途：parameters、metrics、artifacts、model、LLM/Agent traces 与 evaluation。

## Weights & Biases

- 官网：https://wandb.ai/
- 用途：实验 dashboard、sweeps、artifacts、tables、reports。

## DVC

- GitHub：https://github.com/iterative/dvc
- 用途：data / model versioning。

## Optuna

- GitHub：https://github.com/optuna/optuna
- 用途：hyperparameter optimization。

## Ray / Ray Tune

- GitHub：https://github.com/ray-project/ray
- 用途：distributed tuning / distributed workloads。

最低推荐记录：

```text
code commit
data version
config
seed
environment
hardware
metrics
artifacts
```

---

# 10. LLM / Agent Evaluation

不要用“感觉这个 prompt 更聪明”作为实验结论。

## lm-evaluation-harness

- GitHub：https://github.com/EleutherAI/lm-evaluation-harness
- 用途：标准 LLM benchmarks。

## Inspect AI

- GitHub：https://github.com/UKGovernmentBEIS/inspect_ai
- 用途：LLM / Agent / tool-use / multi-turn eval。
- 推荐：Agent 研究尤其值得看。

## Promptfoo

- GitHub：https://github.com/promptfoo/promptfoo
- 用途：Prompt A/B、Model A/B、regression testing、CI。

## DeepEval

- GitHub：https://github.com/confident-ai/deepeval
- 用途：LLM application evaluation / tests。

## Ragas

- GitHub：https://github.com/explodinggradients/ragas
- 用途：RAG retrieval / context / faithfulness / answer evaluation。

## Lighteval

- GitHub：https://github.com/huggingface/lighteval
- 用途：开源模型 benchmark。

## HELM

- GitHub：https://github.com/stanford-crfm/helm
- 用途：holistic model evaluation。

推荐 workflow：

```text
change method / prompt
→ run fixed eval suite
→ compare
→ inspect failures
→ regression test
```

---

# 11. LLM Training / Post-training / Inference

## Fine-tuning

### TRL
https://github.com/huggingface/trl

### LLaMA-Factory
https://github.com/hiyouga/LLaMA-Factory

### Axolotl
https://github.com/axolotl-ai-cloud/axolotl

### Unsloth
https://github.com/unslothai/unsloth

---

## RL / RLHF / RLVR

### verl
https://github.com/volcengine/verl

### OpenRLHF
https://github.com/OpenRLHF/OpenRLHF

---

## Inference / Rollout

### vLLM
https://github.com/vllm-project/vllm

### SGLang
https://github.com/sgl-project/sglang

---

# 12. Recommended Stacks

## A. 已经有 Idea，先判断值不值得做

```text
Semantic Scholar + OpenAlex + OpenReview
                    ↓
         Literature Collision Test
                    ↓
      InnoEval / ResearchStudio 思路
                    ↓
           Adversarial Reviewer
                    ↓
         Strongest Baseline Attack
                    ↓
      Minimum Falsification Experiment
```

## B. 深读一个领域

```text
Semantic Scholar / OpenAlex
          ↓
   ResearchRabbit
          ↓
 Zotero + PDF corpus
          ↓
 MinerU / Docling
          ↓
      PaperQA2
          ↓
  SOTA / Gap Mapper
```

## C. 做 LLM / Agent 实验

```text
Hydra
  ↓
Training / Agent Code
  ↓
MLflow / W&B
  ↓
DVC
  ↓
Inspect AI / lm-eval / Promptfoo
  ↓
Result Analyst
  ↓
Adversarial Reviewer
```

## D. 个人 AI Research OS

```text
                   LLM / Coding Agent
                          │
                    Research Skills
                          │
       ┌──────────────────┼──────────────────┐
       │                  │                  │
 Literature Layer     Coding Layer     Experiment Layer
       │                  │                  │
Semantic Scholar      OpenHands           Hydra
OpenAlex              Aider               MLflow
OpenReview                                DVC
Scite                                     Optuna
       │                                      │
       └──── Zotero / PaperQA2 / Evidence DB ─┘
                          │
                    Evaluation
                          │
             Inspect / lm-eval / Promptfoo
                          │
                   Reviewer Simulation
```

---

# 13. 选择工具时的原则

1. **优先真实 evidence，而不是 LLM confidence。**
2. **优先 API / MCP / structured data，而不是只能手工复制粘贴的 UI。**
3. **优先能留下长期资产的工具：论文库、实验库、eval suite、Skills。**
4. **同类工具先用自己的数据 benchmark，再决定长期绑定。**
5. **自动科研系统的输出必须经过人工 source verification 与实验验证。**
6. **第三方项目的许可证、数据政策、API 条款可能变化，正式使用前自行检查。**

---

# 14. 下一步可以继续建设的内容

本仓库后续适合继续加入：

- 自动 OpenAlex / Semantic Scholar Novelty Search
- Zotero / paper-search MCP integration
- PDF ingestion CLI
- `idea.yaml → IDEA_AUDIT_REPORT.md`
- experiment manifest
- automatic strongest-baseline checklist
- reviewer ensemble
- eval regression suite
- paper claim ↔ evidence traceability
