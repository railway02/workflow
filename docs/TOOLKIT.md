# AI / CS Research Toolkit

> 面向已有科研 Idea 的工具优先级，而不是纯“找灵感”。

> 更完整的官方链接、开源项目说明和推荐组合见 **[PROJECTS.md](PROJECTS.md)**。

## 1. Literature & Prior Art

| Tool | Best for |
|---|---|
| Semantic Scholar | 论文检索、引用关系、相关推荐 |
| OpenAlex | 论文/作者/机构/引用图谱的程序化检索 |
| arXiv | AI/CS 前沿预印本 |
| OpenReview | 论文、review、author response、讨论 |
| Scite | 查后续文献如何引用某工作 |
| Elicit | 系统综述、结构化 evidence extraction |
| ResearchRabbit | 从 seed papers 扩展文献图 |
| Connected Papers | 快速查看论文邻域 |
| Litmaps | 长期跟踪研究主题 |

### 推荐组合

```text
Semantic Scholar
+ OpenAlex
+ OpenReview
+ Scite
```

不要只依赖单一搜索引擎。

---

## 2. PDF / Document Parsing

| Tool | Best for |
|---|---|
| MinerU | PDF → Markdown / JSON / equation / table |
| Docling | 文档结构化、RAG/Agent pipeline |
| Marker | 快速 PDF → Markdown / JSON |
| GROBID | 大规模 scholarly metadata / references |

对于复杂科研 PDF，解析质量会直接决定后续 RAG 和 Agent 的质量。

---

## 3. Personal Research Knowledge Base

### PaperQA2

适合：

- 自己的论文 corpus
- evidence retrieval
- citation-aware QA
- 多论文比较

典型问题：

```text
What evidence contradicts hypothesis X?

Which papers use the same benchmark but report
substantially different results?

Compare the definitions of memory used across these papers.
```

---

## 4. Deep Research Agents

| Tool | Best for |
|---|---|
| STORM / Co-STORM | 多视角调研、outline、long-form synthesis |
| GPT Researcher | 通用 deep research workflow |
| local-deep-research | 本地/隐私敏感研究 |
| AI Scientist v2 | 自动科研流程研究、agent architecture |
| Agent Laboratory | 多 Agent 科研流程实验 |

自动科研系统适合做辅助研究和 architecture study，不应替代人工验证。

---

## 5. Research Skills / MCP

值得关注：

```text
academic-research-skills
Tashan Research Skills
paper-search-mcp
arxiv-mcp-server
Zotero MCP
OpenAlex MCP
Docling MCP
```

核心价值：

> 把科研习惯从一次性 prompt 变成可复用 workflow。

---

## 6. Coding Agents

| Tool | Best for |
|---|---|
| OpenHands | repo-level coding agent |
| SWE-agent | software engineering agent research |
| Aider | Git-native coding workflow |

推荐让 Coding Agent 做：

```text
read repository
map paper equations to code
modify experiment
run tests
inspect logs
commit reproducible changes
```

---

## 7. Experiment Reproducibility

| Tool | Purpose |
|---|---|
| Hydra | 实验配置 |
| MLflow | parameters / metrics / artifacts / model / traces |
| Weights & Biases | experiment dashboard / sweeps / reports |
| DVC | data/model versioning |
| Optuna | hyperparameter optimization |
| Ray Tune | distributed tuning |

最低要求：

```text
固定 code
固定 data version
固定 config
固定 seed
记录 environment
记录 metrics
记录 artifacts
```

---

## 8. LLM / Agent Evaluation

| Tool | Best for |
|---|---|
| lm-evaluation-harness | 标准 LLM benchmark |
| Inspect AI | Agent / tool-use / multi-turn eval |
| Promptfoo | Prompt / Model regression testing |
| DeepEval | LLM application tests |
| Ragas | RAG evaluation |
| Lighteval | 开源模型 benchmark |
| HELM | holistic evaluation |

把 prompt 当代码：

```text
change prompt
→ run eval
→ compare
→ regression test
```

不要只用“感觉更好了”。

---

## 9. LLM Training

### Fine-tuning / Post-training

```text
TRL
LLaMA-Factory
Axolotl
Unsloth
```

### RL / RLHF / RLVR

```text
verl
OpenRLHF
```

### Inference

```text
vLLM
SGLang
```

---

# 已有 Idea 后最值得关注的工具

## Idea evaluation

推荐关注的方向：

- InnoEval
- Microsoft ResearchStudio Idea Quality
- HKUST Supervisor-Skills Idea Evaluator
- RINoBench
- AgentIdeaBench

用途不是“自动给分”，而是学习更可靠的：

```text
knowledge-grounded evaluation
multi-perspective review
literature collision checking
structured thought experiments
fatal-flaw analysis
```

---

# 最终原则

工具不是越多越好。

更推荐固定一套：

```text
Search
→ Evidence DB
→ Idea Audit
→ Experiment Tracking
→ Evaluation
→ Reviewer Simulation
```

然后长期积累自己的：

```text
Research DB
Zotero Library
PDF Corpus
Experiment DB
Reusable Skills
Evaluation Suites
Reviewer Checklists
```
