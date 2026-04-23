---
title: "ORION: An agentic reasoning construct for the analysis of complex human immune profiling"
title_zh: ORION：一种用于复杂人类免疫图谱分析的智能体推理架构
authors: "Dayao, M. T., Kim, K., Khor, B., Jaech, A., van Opheusden, B., Bodansky, A., DeRisi, J."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.13.718286v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用大语言模型的生物数据解释多智能体框架
tldr: ORION是一个基于大语言模型的多智能体框架，旨在解决高维免疫分析数据（如PhIP-seq）解读效率低下的瓶颈。它集成了统计分析、机器学习和自动文献综述，能将原本需要数月的复杂数据分析缩短至数小时。通过在APS-1和唐氏综合征数据集上的验证，证明了其在自动化发现生物标志物和生成科学假设方面的卓越能力，显著提升了免疫组学研究的效率。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-13-718286-v1/fig-001.webp\", \"caption\": \"Figure 1. ORION multi-agent workflow architecture. ORION orchestrates end-to-end PhIP-82 seq analysis through three specialized agents (a Main Analysis Agent, a Literature Agent, and a 83 Supervisor Agent/orchestrator) operating in a constrained Plan → Execute → Verify loop that 84 enforces reproducibility and auditability through persisted, machine-readable intermediate 85\", \"page\": 3, \"index\": 1, \"width\": 1039, \"height\": 581}]"
motivation: 高维生物数据生成能力的飞速提升与传统依赖专家手动整合统计、文献进行数据解读的低效现状之间存在矛盾。
method: 开发了名为ORION的多智能体推理框架，利用具备推理能力的LLM协同执行端到端的统计分析、机器学习建模及自动化文献调研。
result: ORION在两小时内重现了APS-1的经典抗体特征，并成功在唐氏综合征数据中识别出具有生物学意义的候选自身抗体靶点。
conclusion: 智能体AI系统能将复杂免疫数据的分析周期从数周缩短至数小时，使科学家能够更专注于基础生物学问题的探索。
---

## 摘要
生成高维生物数据集的能力已经超过了对其进行解释的能力。诸如噬菌体免疫沉淀测序（PhIP-seq）等技术能够实现抗体库的蛋白质组级图谱分析，但将数千个富集肽段解释为机制性假设仍然是一个劳动密集型的瓶颈，需要专家综合统计学、文献和领域知识。在此，我们描述了 ORION（组学推理与解释编排器），这是一个多智能体框架，利用具备推理能力的大语言模型对复杂的免疫图谱数据进行端到端分析。ORION 将统计分析、机器学习和自动化文献综述整合到一个结构化的工作流中，产生的结果具有可重复性和完全可追溯性。应用于已发表的 1 型自身免疫性多内分泌腺病综合征（APS-1）PhIP-seq 数据集时，ORION 在约两小时内恢复了经典的自身抗体特征，高度重现了最初需要一到两个月人工努力才能完成的分析。为了测试在先前未见数据上的假设生成能力，我们将 ORION 应用于来自唐氏综合征患者的新型 PhIP-seq 数据集，该领域目前尚不存在蛋白质组范围的自身抗体参考。ORION 以高准确度区分了疾病样本与对照样本，确定了候选自身抗体靶点的优先级，并将其组织成涵盖免疫、肠道和神经程序的生物学连贯组，为后续实验生成了可测试的假设。这些结果表明，智能体 AI 系统可以将复杂免疫图谱数据的分析时间从数周压缩至数小时，使科学家能够将时间重新投入到基础生物学研究中。

## Abstract
The capacity to generate high-dimensional biological datasets has outpaced the ability to interpret them. Technologies such as phage immunoprecipitation and sequencing (PhIP-seq) enable proteome-scale profiling of antibody repertoires, but interpreting thousands of enriched peptides into mechanistic hypotheses remains a labor-intensive bottleneck requiring expert synthesis of statistics, literature, and domain knowledge. Here we describe ORION (Omics Reasoning & Interpretation Orchestrator), a multi-agent framework that uses reasoning-capable large language models to perform end-to-end analysis of complex immune profiling data. ORION integrates statistical analysis, machine learning, and automated literature review into a single structured workflow, producing results that are reproducible and fully traceable. Applied to a published PhIP-seq dataset from autoimmune polyendocrine syndrome type 1 (APS-1), ORION recovered the canonical autoantibody signature in approximately two hours, closely recapitulating an analysis that originally required one to two months of manual effort. To test hypothesis-generation capacity on previously unseen data, we applied ORION to a novel PhIP-seq dataset from individuals with Down syndrome, for which no proteome-wide autoantibody reference exists. ORION distinguished disease from control samples with high accuracy, prioritized candidate autoantibody targets, and organized them into biologically coherent groups spanning immune, gut, and neuronal programs, generating testable hypotheses for experimental follow-up. These results demonstrate that agentic AI systems can compress the analysis of complex immune profiling data from weeks to hours, allowing scientists to redirect their time toward the fundamental biology.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **ORION**（Omics Reasoning & Interpretation Orchestrator）的多智能体推理框架，旨在利用大语言模型（LLM）自动化处理和解释复杂的生物组学数据。

### 1. 论文的核心问题与整体含义
*   **研究动机**：高维生物数据（如 PhIP-seq 蛋白质组级抗体谱分析）的生成速度已远超人类的解释能力。
*   **核心问题**：传统的 PhIP-seq 数据分析是一个“劳动密集型”瓶颈。它不仅需要复杂的统计建模，还需要专家查阅海量文献并结合领域知识来构建生物学假设。这一过程通常耗时数月。
*   **整体含义**：ORION 旨在通过智能体（Agentic）推理架构，将统计分析、机器学习建模和自动化文献综述整合进一个闭环工作流，将分析周期从“月”缩短至“小时”。

### 2. 论文提出的方法论
ORION 是一个基于 **Plan → Execute → Verify（计划 → 执行 → 验证）** 循环的多智能体框架，核心组件包括：
*   **核心思想**：通过分工明确的智能体协作，在沙盒环境中运行代码并检索知识，确保分析的可追溯性和可重复性。
*   **关键智能体角色**：
    *   **主分析智能体 (Main Analysis Agent)**：负责数据清洗、统计分析（如逻辑回归、随机森林）和初步解释。
    *   **文献智能体 (Literature Agent)**：负责检索 PubMed、UniProt、Human Protein Atlas 等数据库，提供蛋白质功能、组织表达和疾病关联的背景。
    *   **监督智能体 (Supervisor Agent)**：充当编排者，根据预设的 9 项清单（如数据完整性、归一化合理性等）审核任务进度，不合格则触发重试。
*   **算法流程**：
    1.  **数据物化**：将原始矩阵转换为 SQLite 数据库以提高处理效率。
    2.  **候选优先级排序**：利用逻辑回归（L2 正则化）和随机森林进行特征归因，识别疾病组与对照组差异显著的肽段/蛋白质。
    3.  **伪影处理**：自动进行 AG-bead（珠子背景）归一化，剔除由于非特异性结合产生的假阳性信号。

### 3. 实验设计
论文通过两个主要场景验证了 ORION 的效能：
*   **基准测试（APS-1 数据集）**：使用已发表的 1 型自身免疫性多内分泌腺病综合征数据。该病有明确的自身抗体特征（如抗细胞因子抗体）。
    *   **Benchmark**：原始的人工分析结果（耗时 1-2 个月）。
*   **新发现测试（唐氏综合征数据集）**：使用 105 名唐氏综合征患者和 103 名健康对照的全新 PhIP-seq 数据（模型训练阶段未见过此数据）。
    *   **对比方法**：对比了有无 AG 归一化的结果差异，并使用随机森林和逻辑回归进行分类性能评估。

### 4. 资源与算力
*   **模型使用**：文中提到了使用 **GPT-5.2** 和 **GPT-5.2 pro**（注：这可能是论文撰写时的内部版本或预研代号）。
*   **环境**：所有计算步骤在沙盒化的 Python 环境中执行，元数据存储于 SQLite。
*   **算力细节**：文中**未明确说明**具体的 GPU 型号、数量或训练时长。但提到了运行时间：APS-1 分析耗时 **2 小时 16 分钟**，唐氏综合征分析耗时 **1 小时 41 分钟**。

### 5. 实验数量与充分性
*   **实验规模**：主要针对两个大型队列（APS-1 和唐氏综合征）进行了端到端的深度分析。
*   **充分性评估**：
    *   **客观性**：通过“盲测”未公开的唐氏综合征数据，证明了框架的假设生成能力而非仅仅是记忆已知知识。
    *   **公平性**：采用了交叉验证（StratifiedKFold）来评估分类器的鲁棒性。
    *   **局限性**：实验主要集中在 PhIP-seq 这一种模态上，虽然作者声称其具有通用性，但尚未在转录组或单细胞测序等其他组学上进行大规模验证。

### 6. 论文的主要结论与发现
*   **效率飞跃**：ORION 将原本需要 1-2 个月的人工分析压缩至约 2 小时。
*   **准确性**：在 APS-1 中完美复现了已知的经典抗体特征；在唐氏综合征中，随机森林分类器的平均 **AUC 达到 0.911**。
*   **生物学发现**：在唐氏综合征中识别出与免疫调节（IL17F）、肠道屏障（MGAM、MUC20）和神经粘附（NTM）相关的自身抗体程序，为后续实验提供了明确的、可测试的假设。

### 7. 优点
*   **端到端集成**：首次将代码执行、统计建模与实时文献检索深度耦合。
*   **可追溯性**：通过 Plan-Execute-Verify 循环和持久化的执行日志，解决了 AI 分析“黑盒化”的问题，所有结论均可追溯至具体的统计输出。
*   **伪影感知**：能够自动识别并处理生物实验中的系统性偏差（如非特异性结合）。

### 8. 不足与局限
*   **幻觉风险**：尽管有验证机制，推理系统仍可能产生看似合理但错误的解释，必须经过实验验证。
*   **成本问题**：大规模队列的迭代探索可能产生较高的 API 调用成本。
*   **应用限制**：目前主要针对蛋白质/肽段层面的分析，对于更复杂的非编码区或结构变异等组学数据的适配性尚待观察。
*   **依赖性**：系统高度依赖底层 LLM 的推理能力和外部数据库的质量。

（完）
