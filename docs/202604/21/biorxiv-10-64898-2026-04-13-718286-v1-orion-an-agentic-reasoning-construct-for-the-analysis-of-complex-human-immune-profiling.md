---
title: "ORION: An agentic reasoning construct for the analysis of complex human immune profiling"
title_zh: ORION：一种用于复杂人类免疫图谱分析的智能体推理架构
authors: "Dayao, M. T., Kim, K., Khor, B., Jaech, A., van Opheusden, B., Bodansky, A., DeRisi, J."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.13.718286v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 用于复杂免疫分析的智能体推理和大语言模型
tldr: ORION是一个基于大语言模型的多智能体框架，旨在解决高维免疫分析数据（如PhIP-seq）解释难、耗时长的瓶颈。它集成了统计分析、机器学习和自动文献综述，能将原本需要数月的复杂免疫组学分析缩短至数小时。通过在APS-1和唐氏综合征数据集上的验证，ORION展示了卓越的自动化分析、假设生成及生物学解释能力，显著提升了科研效率。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-13-718286-v1/fig-001.webp\", \"caption\": \"Figure 1. ORION multi-agent workflow architecture. ORION orchestrates end-to-end PhIP-82 seq analysis through three specialized agents (a Main Analysis Agent, a Literature Agent, and a 83 Supervisor Agent/orchestrator) operating in a constrained Plan → Execute → Verify loop that 84 enforces reproducibility and auditability through persisted, machine-readable intermediate 85\", \"page\": 3, \"index\": 1, \"width\": 1039, \"height\": 581}]"
motivation: 高维生物数据集的快速增长使得依赖专家手动整合统计与文献的传统分析方式成为制约免疫组学研究的效率瓶颈。
method: 开发了名为ORION的多智能体框架，利用具备推理能力的大语言模型，将统计分析、机器学习和自动化文献检索整合进端到端的结构化工作流中。
result: ORION在APS-1数据集中仅用2小时便重现了需数月完成的经典抗体特征，并在唐氏综合征新数据中准确识别并分类了具有生物学意义的候选自身抗体靶点。
conclusion: 智能体AI系统能极大压缩复杂免疫分析的时间成本，使科学家能从繁琐的数据处理中解脱，专注于核心生物学问题的探索。
---

## 摘要
生成高维生物数据集的能力已经超过了对其进行解释的能力。诸如噬菌体免疫沉淀测序（PhIP-seq）等技术能够实现抗体库的蛋白质组级图谱分析，但将数千个富集肽段解释为机制性假设仍然是一个劳动密集型的瓶颈，需要专家综合统计学、文献和领域知识。在此，我们介绍了 ORION（组学推理与解释编排器），这是一个多智能体框架，利用具备推理能力的大语言模型对复杂的免疫图谱数据进行端到端分析。ORION 将统计分析、机器学习和自动化文献综述整合到一个结构化的工作流中，产生的结果具有可重复性和完全可追溯性。应用于已发表的 1 型自身免疫性多内分泌腺病综合征（APS-1）PhIP-seq 数据集时，ORION 在约两小时内恢复了经典的自身抗体特征，高度重现了最初需要一到两个月人工努力才能完成的分析。为了测试在先前未见数据上的假设生成能力，我们将 ORION 应用于来自唐氏综合征患者的新型 PhIP-seq 数据集，该领域目前尚不存在蛋白质组范围的自身抗体参考。ORION 以高准确度区分了疾病样本与对照样本，确定了候选自身抗体靶点的优先级，并将其组织成涵盖免疫、肠道和神经程序的生物学连贯组，为后续实验生成了可测试的假设。这些结果表明，智能体 AI 系统可以将复杂免疫图谱数据的分析时间从数周压缩至数小时，使科学家能够将时间重新投入到基础生物学研究中。

## Abstract
The capacity to generate high-dimensional biological datasets has outpaced the ability to interpret them. Technologies such as phage immunoprecipitation and sequencing (PhIP-seq) enable proteome-scale profiling of antibody repertoires, but interpreting thousands of enriched peptides into mechanistic hypotheses remains a labor-intensive bottleneck requiring expert synthesis of statistics, literature, and domain knowledge. Here we describe ORION (Omics Reasoning & Interpretation Orchestrator), a multi-agent framework that uses reasoning-capable large language models to perform end-to-end analysis of complex immune profiling data. ORION integrates statistical analysis, machine learning, and automated literature review into a single structured workflow, producing results that are reproducible and fully traceable. Applied to a published PhIP-seq dataset from autoimmune polyendocrine syndrome type 1 (APS-1), ORION recovered the canonical autoantibody signature in approximately two hours, closely recapitulating an analysis that originally required one to two months of manual effort. To test hypothesis-generation capacity on previously unseen data, we applied ORION to a novel PhIP-seq dataset from individuals with Down syndrome, for which no proteome-wide autoantibody reference exists. ORION distinguished disease from control samples with high accuracy, prioritized candidate autoantibody targets, and organized them into biologically coherent groups spanning immune, gut, and neuronal programs, generating testable hypotheses for experimental follow-up. These results demonstrate that agentic AI systems can compress the analysis of complex immune profiling data from weeks to hours, allowing scientists to redirect their time toward the fundamental biology.

---

## 论文详细总结（自动生成）

以下是对论文《ORION: An agentic reasoning construct for the analysis of complex human immune profiling》的结构化总结：

### 1. 核心问题与整体含义
*   **研究背景**：随着噬菌体免疫沉淀测序（PhIP-seq）等高维生物技术的普及，人类产生免疫组学数据的速度已远超解释数据的能力。
*   **核心问题**：从数万个富集的肽段信号中提取出具有生物学意义的机制假设，通常需要领域专家花费数周甚至数月时间，手动整合统计学结果、查阅海量文献并结合领域知识。这种“专家瓶颈”严重制约了免疫学研究的效率。
*   **整体含义**：本文提出了 **ORION**（组学推理与解释编排器），这是一个基于大语言模型（LLM）的多智能体推理框架。它旨在通过自动化统计分析、机器学习建模和文献综述，将复杂的免疫图谱分析周期从“月”级压缩至“小时”级。

### 2. 方法论
*   **核心思想**：采用多智能体协作架构，通过“计划→执行→验证”的闭环逻辑，在沙盒环境中实现端到端的自动化分析。
*   **关键技术细节**：
    *   **多智能体架构**：
        *   **主分析智能体 (Main Analysis Agent)**：负责数据清洗、统计分析（如 RPK 归一化）、运行机器学习模型。
        *   **文献智能体 (Literature Agent)**：专门负责检索 PubMed、UniProt、Human Protein Atlas 等数据库，为候选靶点提供生物学背景。
        *   **监督智能体 (Supervisor Agent)**：充当编排器，根据预设的 9 项清单（如数据完整性、归一化合理性等）审核分析结果，不合格则触发重试。
    *   **算法流程**：
        1.  **数据物化**：将原始矩阵转换为 SQLite 数据库以提高查询效率。
        2.  **候选优先级排序**：利用逻辑回归（L2 正则化）和随机森林进行特征归因，识别区分疾病与对照组的关键肽段/蛋白质。
        3.  **伪影处理**：自动进行 AG-bead（非特异性结合）归一化。
        4.  **知识合成**：将统计显著的靶点与文献证据结合，生成可测试的生物学假设。

### 3. 实验设计
*   **数据集与场景**：
    1.  **APS-1（已知基准）**：使用已发表的 1 型自身免疫性多内分泌腺病综合征数据。**Benchmark** 是原始论文中专家手动分析的结果。
    2.  **唐氏综合征（DS，未知探索）**：使用全新的、未公开的 PhIP-seq 数据集（105 名 DS 患者 vs 103 名健康对照）。该领域尚无蛋白质组范围的参考标准。
*   **对比方法**：主要对比“人工专家分析”与“ORION 自动化分析”在耗时、发现的准确性及假设的连贯性上的差异。

### 4. 资源与算力
*   **模型使用**：论文提到了使用 **GPT-5.2** 和 **GPT-5.2 pro**（注：这反映了该研究的前瞻性或使用了特定版本的推理模型）。
*   **运行时长**：
    *   APS-1 分析耗时：**2 小时 16 分钟**（人工需 1-2 个月）。
    *   唐氏综合征分析耗时：**1 小时 41 分钟**。
*   **算力细节**：文中未明确提及具体的 GPU 数量或型号，但指出所有计算步骤均在受限的 Python 沙盒环境中执行。

### 5. 实验数量与充分性
*   **实验规模**：涵盖了从已知验证到未知发现的两个大型案例研究。
*   **充分性评价**：
    *   **客观性**：通过交叉验证（StratifiedKFold）评估分类器性能（DS 任务 AUC 达 0.911），并对比了归一化前后的结果差异，显示了严谨的统计态度。
    *   **公平性**：在 DS 实验中使用了模型从未接触过的新数据，证明了其并非单纯依赖训练数据中的记忆，而是具备真正的推理和假设生成能力。

### 6. 主要结论与发现
*   **效率飞跃**：ORION 将分析时间缩短了数百倍，同时保持了极高的准确性。
*   **APS-1 验证**：成功找回了所有经典的自身抗体特征（如 IL-17F, IFN-α, NLRP5 等）。
*   **DS 新发现**：识别出唐氏综合征中存在分布式的免疫信号，并将其归类为免疫调节（IL17F）、肠道屏障（MGAM, MUC20）和神经粘附（NTM）三大程序，为后续实验提供了明确方向。
*   **临床潜力**：展示了 AI 在识别罕见免疫程序和辅助儿科免疫疾病诊断方面的巨大潜力。

### 7. 优点
*   **可追溯性与透明度**：通过 Plan-Execute-Verify 循环和持久化日志，解决了 AI 分析常被诟病的“黑箱”问题。
*   **多模态整合**：成功将干实验代码执行与湿实验背景知识（文献）深度缝合。
*   **通用性强**：框架设计不限于 PhIP-seq，理论上可扩展至转录组、蛋白质组等其他组学领域。

### 8. 不足与局限
*   **幻觉风险**：尽管有监督智能体，LLM 仍可能生成看似合理但错误的生物学解释，结论必须经过湿实验验证。
*   **成本问题**：大规模队列的深度推理可能产生较高的 API 调用成本。
*   **应用限制**：目前主要针对抗体库分析优化，对于需要复杂空间信息或单细胞轨迹推断的任务，可能需要额外的模块适配。
*   **验证依赖**：ORION 缩短了“数据到假设”的过程，但“假设到真理”仍受限于实验验证的速度。

（完）
