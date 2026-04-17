---
title: "ORION: An agentic reasoning construct for the analysis of complex human immune profiling"
title_zh: ORION：一种用于复杂人类免疫图谱分析的智能体推理架构
authors: "Dayao, M. T., Kim, K., Khor, B., Jaech, A., van Opheusden, B., Bodansky, A., DeRisi, J."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.13.718286v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用大语言模型的生物数据分析多智能体框架
tldr: ORION是一个基于大语言模型的多智能体推理框架，旨在解决高维免疫分析数据（如PhIP-seq）解读效率低下的瓶颈。它集成了统计分析、机器学习和自动文献综述，能将原本需要数月的专家分析缩短至数小时。通过在APS-1和唐氏综合征数据集上的验证，ORION展示了卓越的自动化分析、目标识别和生物学假设生成能力，显著加速了复杂免疫组学研究。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-13-718286-v1/fig-001.webp\", \"caption\": \"Figure 1. ORION multi-agent workflow architecture. ORION orchestrates end-to-end PhIP-82 seq analysis through three specialized agents (a Main Analysis Agent, a Literature Agent, and a 83 Supervisor Agent/orchestrator) operating in a constrained Plan → Execute → Verify loop that 84 enforces reproducibility and auditability through persisted, machine-readable intermediate 85\", \"page\": 3, \"index\": 1, \"width\": 1039, \"height\": 581}]"
motivation: 高维生物数据集的快速增长使得依赖专家手动整合统计与文献的传统分析方式成为制约免疫组学研究的效率瓶颈。
method: 开发了名为ORION的多智能体框架，利用具备推理能力的大语言模型，将统计分析、机器学习和自动化文献检索整合进端到端的结构化工作流。
result: ORION在APS-1研究中将数月的分析缩短至两小时并重现了经典特征，并在唐氏综合征研究中准确识别了新的候选自身抗体目标及生物学程序。
conclusion: 智能体AI系统能极大压缩复杂免疫分析的时间成本，使科学家能从繁琐的数据处理中解脱，专注于核心生物学问题的探索。
---

## 摘要
生成高维生物数据集的能力已经超过了对其进行解释的能力。诸如噬菌体免疫沉淀测序（PhIP-seq）等技术能够实现抗体库的蛋白质组级图谱分析，但将数千个富集肽段解释为机制性假设仍然是一个劳动密集型瓶颈，需要专家综合统计学、文献和领域知识。在此，我们介绍了 ORION（组学推理与解释协调器），这是一个多智能体框架，利用具备推理能力的大语言模型对复杂的免疫图谱数据进行端到端分析。ORION 将统计分析、机器学习和自动化文献综述整合到一个结构化的工作流中，产生的结果具有可重复性和完全可追溯性。应用于已发表的 1 型自身免疫性多内分泌腺病综合征（APS-1）PhIP-seq 数据集时，ORION 在约两小时内恢复了经典的自身抗体特征，高度重现了最初需要一到两个月人工努力的分析过程。为了测试在先前未见数据上的假设生成能力，我们将 ORION 应用于来自唐氏综合征患者的新型 PhIP-seq 数据集，该领域尚不存在全蛋白质组范围的自身抗体参考。ORION 以高准确度区分了疾病样本与对照样本，确定了候选自身抗体靶点的优先级，并将其组织成涵盖免疫、肠道和神经程序的生物学连贯组，为后续实验生成了可测试的假设。这些结果表明，智能体 AI 系统可以将复杂免疫图谱数据的分析时间从数周压缩至数小时，使科学家能够将时间重新投入到基础生物学研究中。

## Abstract
The capacity to generate high-dimensional biological datasets has outpaced the ability to interpret them. Technologies such as phage immunoprecipitation and sequencing (PhIP-seq) enable proteome-scale profiling of antibody repertoires, but interpreting thousands of enriched peptides into mechanistic hypotheses remains a labor-intensive bottleneck requiring expert synthesis of statistics, literature, and domain knowledge. Here we describe ORION (Omics Reasoning & Interpretation Orchestrator), a multi-agent framework that uses reasoning-capable large language models to perform end-to-end analysis of complex immune profiling data. ORION integrates statistical analysis, machine learning, and automated literature review into a single structured workflow, producing results that are reproducible and fully traceable. Applied to a published PhIP-seq dataset from autoimmune polyendocrine syndrome type 1 (APS-1), ORION recovered the canonical autoantibody signature in approximately two hours, closely recapitulating an analysis that originally required one to two months of manual effort. To test hypothesis-generation capacity on previously unseen data, we applied ORION to a novel PhIP-seq dataset from individuals with Down syndrome, for which no proteome-wide autoantibody reference exists. ORION distinguished disease from control samples with high accuracy, prioritized candidate autoantibody targets, and organized them into biologically coherent groups spanning immune, gut, and neuronal programs, generating testable hypotheses for experimental follow-up. These results demonstrate that agentic AI systems can compress the analysis of complex immune profiling data from weeks to hours, allowing scientists to redirect their time toward the fundamental biology.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **ORION**（Omics Reasoning & Interpretation Orchestrator）的多智能体推理框架，旨在利用大语言模型（LLM）的推理能力自动化分析复杂的高维免疫组学数据。

以下是对该论文的结构化总结：

### 1. 核心问题与研究动机
*   **核心问题**：生物组学数据（如 PhIP-seq 噬菌体展示免疫沉淀测序）的生成速度远超人类的解释能力。
*   **研究动机**：分析此类数据是一个“劳动密集型”瓶颈。专家需要手动整合复杂的统计结果、海量生物医学文献和领域知识，将数千个富集的肽段转化为可验证的生物学假设。这一过程通常需要耗费资深科学家数周甚至数月的时间。

### 2. 方法论
ORION 是一个基于 **Plan → Execute → Verify（计划-执行-验证）** 闭环的多智能体协作框架：
*   **核心思想**：通过专门化的 AI 智能体分工协作，在受限的沙盒环境中运行代码并检索知识，实现端到端的自动化分析。
*   **关键智能体角色**：
    *   **主分析智能体 (Main Analysis Agent)**：负责数据清洗、统计建模（如逻辑回归、随机森林）和初步解释。
    *   **文献智能体 (Literature Agent)**：负责检索蛋白质数据库（UniProt、PubMed、Human Protein Atlas 等），提供功能注释和疾病关联。
    *   **监督智能体 (Supervisor Agent)**：充当协调员，根据 9 项清单（如数据完整性、归一化合理性等）审核分析步骤，不合格则触发重试。
*   **技术细节**：
    *   使用 **GPT-5.2** 系列模型作为推理引擎。
    *   **数据处理**：将原始矩阵转化为 SQLite 数据库以提高查询效率。
    *   **统计模块**：集成 Scikit-learn，利用 L2 正则化逻辑回归进行特征归因，并通过交叉验证评估模型性能。
    *   **可追溯性**：所有中间步骤、执行日志和代码均持久化存储，确保分析过程可审计。

### 3. 实验设计
论文通过两个主要场景验证了 ORION 的能力：
*   **基准测试（APS-1 数据集）**：使用已发表的 1 型自身免疫性多内分泌腺病综合征数据。
    *   **目标**：验证 ORION 能否重现已知的经典自身抗体特征。
    *   **对比**：将 ORION 的分析结果与原始论文中耗时数月的人工分析进行对比。
*   **新假设生成（唐氏综合征数据集）**：使用 105 名唐氏综合征（DS）患者和 103 名健康对照（HC）的全新 PhIP-seq 数据。
    *   **目标**：在没有先验参考的情况下，测试 ORION 发现新生物学程序的能力。
    *   **Benchmark**：评估其分类准确度（AUC）及生成的假设是否具有生物学连贯性。

### 4. 资源与算力
*   **模型**：使用了 GPT-5.2 和 GPT-5.2 pro。
*   **算力说明**：文中**未明确提及**具体的 GPU 型号或数量。
*   **时间成本**：APS-1 分析耗时 **2 小时 16 分钟**；唐氏综合征分析耗时 **1 小时 41 分钟**。相比之下，人工分析通常需要 1-2 个月。

### 5. 实验数量与充分性
*   **实验规模**：主要针对两个大型疾病队列进行了深度端到端测试。
*   **充分性评价**：
    *   **客观性**：通过引入“珠子对照（AG-beads）”归一化步骤，展示了 AI 处理实验噪声的能力。
    *   **公平性**：在唐氏综合征分析中，使用了严格的交叉验证（StratifiedKFold）来评估分类器性能，避免了过拟合导致的虚假关联。
    *   **局限性**：虽然样本量（>200）在免疫组学中具有代表性，但目前仅展示了 PhIP-seq 这一种模态，跨组学（如转录组+蛋白质组）的泛化性仍需更多实验支撑。

### 6. 主要结论与发现
*   **效率飞跃**：ORION 将原本需要数月的分析周期压缩至 **2 小时左右**。
*   **准确性**：在 APS-1 中完美找回了所有关键自身抗体靶点（如 IL-17F, IFN-α 等）。
*   **新发现**：在唐氏综合征研究中，ORION 识别出了一套分布式的自身抗体特征（AUC=0.911），并将其归纳为免疫调节、肠道屏障和神经粘附三个生物学程序，提出了 IL17F 和 MUC20 等潜在靶点。

### 7. 优点
*   **端到端整合**：打破了统计分析与文献综述之间的壁垒。
*   **高可追溯性**：Plan-Execute-Verify 循环提供了透明的决策链，减少了“黑箱”感。
*   **假设导向**：不仅给出排名，还能生成具体的、可实验验证的后续方案。

### 8. 不足与局限
*   **幻觉风险**：尽管有验证机制，推理系统仍可能产生看似合理但错误的解释，必须经过实验验证。
*   **成本问题**：大规模队列的迭代推理和长上下文处理可能产生较高的 API 调用成本。
*   **应用限制**：目前高度依赖于结构化的输入和特定的 Prompt 模板，对于非标准或极度异构的数据可能需要重新调整架构。

（完）
