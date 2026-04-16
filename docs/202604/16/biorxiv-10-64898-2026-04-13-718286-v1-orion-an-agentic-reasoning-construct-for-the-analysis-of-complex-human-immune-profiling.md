---
title: "ORION: An agentic reasoning construct for the analysis of complex human immune profiling"
title_zh: ORION：一种用于复杂人类免疫图谱分析的智能体推理架构
authors: "Dayao, M. T., Kim, K., Khor, B., Jaech, A., van Opheusden, B., Bodansky, A., DeRisi, J."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.13.718286v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用具备推理能力的大语言模型的免疫分析多智能体框架
tldr: ORION是一个基于大语言模型的多智能体框架，旨在自动化分析高维免疫分析数据（如PhIP-seq）。它集成了统计分析、机器学习和文献综述，将原本需要数月的专家分析缩短至数小时。通过在APS-1和唐氏综合征数据集上的应用，ORION证明了其在重现已知结果和生成新生物学假设方面的卓越能力，显著提升了科研效率。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-13-718286-v1/fig-001.webp\", \"caption\": \"Figure 1. ORION multi-agent workflow architecture. ORION orchestrates end-to-end PhIP-82 seq analysis through three specialized agents (a Main Analysis Agent, a Literature Agent, and a 83 Supervisor Agent/orchestrator) operating in a constrained Plan → Execute → Verify loop that 84 enforces reproducibility and auditability through persisted, machine-readable intermediate 85\", \"page\": 3, \"index\": 1, \"width\": 1039, \"height\": 581}]"
motivation: 高维生物数据的快速增长与人工解读效率低下之间的矛盾，使得从复杂免疫谱中提取机制性假设成为科研瓶颈。
method: 开发了名为ORION的多智能体推理框架，利用具备推理能力的LLM整合统计工具、机器学习和自动化文献检索。
result: 在APS-1研究中仅用2小时便重现了数月的分析成果，并在唐氏综合征数据中发现了涵盖免疫、肠道和神经系统的潜在自身抗体靶点。
conclusion: 智能体AI系统能极大压缩复杂组学数据的分析周期，使科学家能够从繁琐的数据处理中解脱，专注于核心生物学问题的研究。
---

## 摘要
生成高维生物数据集的能力已经超过了对其进行解释的能力。诸如噬菌体免疫沉淀测序（PhIP-seq）等技术能够实现抗体库的蛋白质组级图谱分析，但将数千个富集肽段解释为机制性假设仍然是一个劳动密集型瓶颈，需要专家综合统计学、文献和领域知识。在此，我们描述了 ORION（组学推理与解释协调器），这是一个多智能体框架，利用具备推理能力的大语言模型对复杂的免疫图谱数据进行端到端分析。ORION 将统计分析、机器学习和自动化文献综述整合到一个结构化的工作流中，产生的结果具有可重复性和完全可追溯性。应用于已发表的 1 型自身免疫性多内分泌腺病综合征（APS-1）PhIP-seq 数据集时，ORION 在约两小时内恢复了经典的自身抗体特征，高度重现了最初需要一到两个月人工努力的分析过程。为了测试在先前未见数据上的假设生成能力，我们将 ORION 应用于来自唐氏综合征患者的新型 PhIP-seq 数据集，该领域尚不存在全蛋白质组范围的自身抗体参考。ORION 以高准确度区分了疾病样本与对照样本，确定了候选自身抗体靶点的优先级，并将其组织成涵盖免疫、肠道和神经程序的生物学连贯组，为后续实验生成了可测试的假设。这些结果表明，智能体 AI 系统可以将复杂免疫图谱数据的分析时间从数周压缩至数小时，使科学家能够将时间重新投入到基础生物学研究中。

## Abstract
The capacity to generate high-dimensional biological datasets has outpaced the ability to interpret them. Technologies such as phage immunoprecipitation and sequencing (PhIP-seq) enable proteome-scale profiling of antibody repertoires, but interpreting thousands of enriched peptides into mechanistic hypotheses remains a labor-intensive bottleneck requiring expert synthesis of statistics, literature, and domain knowledge. Here we describe ORION (Omics Reasoning & Interpretation Orchestrator), a multi-agent framework that uses reasoning-capable large language models to perform end-to-end analysis of complex immune profiling data. ORION integrates statistical analysis, machine learning, and automated literature review into a single structured workflow, producing results that are reproducible and fully traceable. Applied to a published PhIP-seq dataset from autoimmune polyendocrine syndrome type 1 (APS-1), ORION recovered the canonical autoantibody signature in approximately two hours, closely recapitulating an analysis that originally required one to two months of manual effort. To test hypothesis-generation capacity on previously unseen data, we applied ORION to a novel PhIP-seq dataset from individuals with Down syndrome, for which no proteome-wide autoantibody reference exists. ORION distinguished disease from control samples with high accuracy, prioritized candidate autoantibody targets, and organized them into biologically coherent groups spanning immune, gut, and neuronal programs, generating testable hypotheses for experimental follow-up. These results demonstrate that agentic AI systems can compress the analysis of complex immune profiling data from weeks to hours, allowing scientists to redirect their time toward the fundamental biology.

---

## 论文详细总结（自动生成）

### 论文结构化总结：ORION 多智能体免疫图谱分析架构

#### 1. 核心问题与整体含义（研究动机和背景）
随着生物技术的发展，高维生物数据集（如 PhIP-seq 噬菌体展示库测序）的生成速度已远超人类的解释能力。PhIP-seq 能够扫描全蛋白质组范围的抗体-抗原相互作用，但其数据具有高度稀疏性、个体差异大且存在非特异性结合等挑战。传统上，从数千个富集肽段中提取出具有生物学意义的机制性假设，需要领域专家花费数周甚至数月的时间进行统计建模、查阅海量文献并进行逻辑综合。
**研究动机：** 开发一种能够自动化处理统计分析、机器学习建模及文献综述的智能系统，将复杂的免疫组学分析周期从“月”缩短至“小时”。

#### 2. 方法论：核心思想与关键技术细节
论文提出了 **ORION (Omics Reasoning & Interpretation Orchestrator)**，这是一个基于具备推理能力的大语言模型（如 GPT-5.2 系列）的多智能体框架。其核心思想是通过“计划→执行→验证”的闭环逻辑实现端到端分析。

*   **核心架构（三智能体协作）：**
    *   **主分析智能体 (Main Analysis Agent)：** 负责数据清洗、统计分析（如 AG 珠标准化）、运行机器学习模型并提出初步解释。
    *   **文献智能体 (Literature Agent)：** 专门负责检索和总结蛋白质功能、亚细胞定位、组织表达及疾病关联，为候选靶点提供生物学背景。
    *   **监督智能体 (Supervisor Agent)：** 充当协调员，根据预设的 9 项清单（如数据完整性、模型合理性等）审核其他智能体的输出，不合格则触发重试。
*   **技术流程：**
    1.  **数据物化：** 将原始矩阵转换为 SQLite 数据库以提高查询效率。
    2.  **候选优先级排序：** 结合队列分析和**逻辑回归 (Logistic Regression)**。使用 L2 正则化和分层 K 折交叉验证来识别区分疾病与对照组的关键肽段/蛋白。
    3.  **自动化推理：** 智能体在沙盒 Python 环境中执行代码，并将结果与文献证据整合，生成可测试的实验假设。

#### 3. 实验设计
论文通过两个主要案例验证了 ORION 的性能：
*   **基准测试 (Benchmark)：APS-1 数据集。**
    *   **背景：** 1 型自身免疫性多内分泌腺病综合征，其自身抗体特征已明确。
    *   **目的：** 验证 ORION 是否能重现已知的科学结论。
*   **假设生成测试：唐氏综合征 (DS) 数据集。**
    *   **背景：** 包含 105 名 DS 患者和 103 名健康对照的新型 PhIP-seq 数据，此前无全蛋白质组参考。
    *   **对比方法：** 将 ORION 的自动化分析与传统的人工专家分析（耗时 1-2 个月）进行对比。

#### 4. 资源与算力
*   **模型：** 使用了 OpenAI 的推理模型（文中提及 GPT-5.2 及 GPT-5.2 pro）。
*   **算力硬件：** 论文未明确指出具体的 GPU 型号或数量，因为该框架是基于 API 调用和云端沙盒环境运行的。
*   **耗时：** APS-1 分析耗时 **2 小时 16 分钟**；唐氏综合征分析耗时 **1 小时 41 分钟**。

#### 5. 实验数量与充分性
*   **实验规模：** 论文重点展示了两个深度案例研究。APS-1 实验证明了系统的**准确性**（重现了所有关键自身抗体，如 IL-17F, IFN-α 等）；唐氏综合征实验证明了系统的**发现能力**（识别出 AUC 为 0.911 的分类特征）。
*   **充分性与客观性：** 实验设计较为客观。作者特意选择了模型未曾“见过”的新数据集（唐氏综合征）来排除训练数据污染的风险。通过交叉验证（StratifiedKFold）和对比标准化（AG-normalized vs Unnormalized）确保了统计结果的稳健性。

#### 6. 主要结论与发现
*   **效率飞跃：** ORION 将原本需要 1-2 个月的人工分析压缩至约 2 小时，效率提升了数百倍。
*   **生物学发现：** 在唐氏综合征研究中，ORION 发现其自身抗体特征并非由单一高频抗原驱动，而是由涵盖免疫调节（IL17F）、肠道屏障（MGAM, MUC20）和神经粘附（NTM, PCDHGA11）的多个分布式程序组成。
*   **可解释性：** 系统不仅给出了排名，还提供了完整的推理日志和文献支持，生成的假设具有高度的实验可操作性。

#### 7. 优点
*   **端到端集成：** 首次将代码执行、统计建模与实时文献检索整合进一个自动化的推理循环。
*   **可追溯性：** 所有的中间步骤、执行日志和决策依据均可审计，克服了传统 AI “黑盒”分析的弊端。
*   **通用性：** 框架设计不限于 PhIP-seq，理论上可扩展至转录组、蛋白质组等其他组学数据。

#### 8. 不足与局限
*   **幻觉风险：** 尽管有监督智能体，但 LLM 仍可能产生看似合理但错误的生物学解释，最终结论必须经过实验验证。
*   **成本问题：** 大规模调用高性能推理模型 API 的计算成本和 Token 消耗可能较高。
*   **依赖性：** 系统的表现高度依赖于底层 LLM 的推理能力和外部数据库（如 UniProt, PubMed）的完备性。
*   **样本量限制：** 虽然在百人规模队列中表现良好，但在超大规模或极小样本下的表现尚需进一步验证。

（完）
