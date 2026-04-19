---
title: "ORION: An agentic reasoning construct for the analysis of complex human immune profiling"
title_zh: ORION：一种用于复杂人类免疫图谱分析的智能体推理架构
authors: "Dayao, M. T., Kim, K., Khor, B., Jaech, A., van Opheusden, B., Bodansky, A., DeRisi, J."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.13.718286v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用大语言模型的复杂免疫分析多智能体框架
tldr: ORION是一个基于大语言模型的多智能体框架，旨在解决高维免疫分析数据（如PhIP-seq）解释难、耗时长的瓶颈。它集成了统计分析、机器学习和自动文献综述，能将原本需要数月的复杂免疫组学分析缩短至数小时。通过在APS-1和唐氏综合征数据集上的验证，ORION展示了卓越的自动化分析、假设生成及生物学解释能力，显著提升了科研效率。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-13-718286-v1/fig-001.webp\", \"caption\": \"Figure 1. ORION multi-agent workflow architecture. ORION orchestrates end-to-end PhIP-82 seq analysis through three specialized agents (a Main Analysis Agent, a Literature Agent, and a 83 Supervisor Agent/orchestrator) operating in a constrained Plan → Execute → Verify loop that 84 enforces reproducibility and auditability through persisted, machine-readable intermediate 85\", \"page\": 3, \"index\": 1, \"width\": 1039, \"height\": 581}]"
motivation: 高维生物数据集的快速增长使得依赖专家经验的手动数据解释成为制约科研效率的瓶颈。
method: 提出ORION框架，利用多智能体大语言模型整合统计分析、机器学习和自动文献检索，实现端到端的免疫组学分析。
result: ORION将APS-1数据集的分析时间从数月缩短至2小时，并成功在唐氏综合征新数据中识别出具有生物学意义的候选自身抗体靶点。
conclusion: 智能体AI系统能够显著压缩复杂免疫数据的分析周期，使研究人员能够更专注于核心生物学问题的探索。
---

## 摘要
生成高维生物数据集的能力已经超过了对其进行解释的能力。诸如噬菌体免疫沉淀测序（PhIP-seq）等技术能够实现抗体库的蛋白质组级图谱分析，但将数千个富集肽段解释为机制性假设仍然是一个劳动密集型的瓶颈，需要专家综合统计学、文献和领域知识。在此，我们描述了 ORION（组学推理与解释编排器），这是一个多智能体框架，利用具备推理能力的大语言模型对复杂的免疫图谱数据进行端到端分析。ORION 将统计分析、机器学习和自动化文献综述整合到一个结构化的工作流中，产生的结果具有可重复性和完全可追溯性。应用于已发表的 1 型自身免疫性多内分泌腺病综合征（APS-1）PhIP-seq 数据集时，ORION 在约两小时内恢复了经典的自身抗体特征，高度重现了最初需要一到两个月人工努力才能完成的分析。为了测试在先前未见数据上的假设生成能力，我们将 ORION 应用于来自唐氏综合征患者的新型 PhIP-seq 数据集，该领域目前尚不存在蛋白质组范围的自身抗体参考。ORION 以高准确度区分了疾病样本与对照样本，确定了候选自身抗体靶点的优先级，并将其组织成涵盖免疫、肠道和神经程序的生物学连贯组，为后续实验生成了可测试的假设。这些结果表明，智能体 AI 系统可以将复杂免疫图谱数据的分析时间从数周压缩至数小时，使科学家能够将时间重新投入到基础生物学研究中。

## Abstract
The capacity to generate high-dimensional biological datasets has outpaced the ability to interpret them. Technologies such as phage immunoprecipitation and sequencing (PhIP-seq) enable proteome-scale profiling of antibody repertoires, but interpreting thousands of enriched peptides into mechanistic hypotheses remains a labor-intensive bottleneck requiring expert synthesis of statistics, literature, and domain knowledge. Here we describe ORION (Omics Reasoning & Interpretation Orchestrator), a multi-agent framework that uses reasoning-capable large language models to perform end-to-end analysis of complex immune profiling data. ORION integrates statistical analysis, machine learning, and automated literature review into a single structured workflow, producing results that are reproducible and fully traceable. Applied to a published PhIP-seq dataset from autoimmune polyendocrine syndrome type 1 (APS-1), ORION recovered the canonical autoantibody signature in approximately two hours, closely recapitulating an analysis that originally required one to two months of manual effort. To test hypothesis-generation capacity on previously unseen data, we applied ORION to a novel PhIP-seq dataset from individuals with Down syndrome, for which no proteome-wide autoantibody reference exists. ORION distinguished disease from control samples with high accuracy, prioritized candidate autoantibody targets, and organized them into biologically coherent groups spanning immune, gut, and neuronal programs, generating testable hypotheses for experimental follow-up. These results demonstrate that agentic AI systems can compress the analysis of complex immune profiling data from weeks to hours, allowing scientists to redirect their time toward the fundamental biology.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **ORION**（Omics Reasoning & Interpretation Orchestrator）的多智能体推理框架，旨在利用大语言模型（LLM）的推理能力自动化分析复杂的高维免疫组学数据。

以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：生物学高维数据集（如 PhIP-seq 噬菌体展示免疫沉淀测序）的生成速度已远超人类专家的解释能力。
*   **研究背景**：PhIP-seq 可以检测全蛋白质组范围的抗体-抗原相互作用，但其数据具有高度稀疏性、个体差异大、非特异性结合多等特点。
*   **瓶颈**：将数千个富集肽段转化为生物学假设通常需要专家花费数月时间，综合统计学分析、大量文献检索和领域知识。ORION 的目标是将这一过程从“月”级压缩至“小时”级。

### 2. 方法论
ORION 是一个多智能体协作框架，核心思想是通过“计划→执行→验证”的闭环逻辑实现端到端分析。
*   **核心架构**：
    *   **主分析智能体 (Main Analysis Agent)**：负责数据清洗、统计分析、机器学习建模及初步解释。
    *   **文献智能体 (Literature Agent)**：负责检索数据库（PubMed, UniProt, Human Protein Atlas 等），提供蛋白质功能、组织表达和疾病关联的背景。
    *   **监督智能体 (Supervisor Agent)**：充当编排者，根据预设的 9 项清单（如数据完整性、归一化合理性等）审核结果，不合格则触发重试。
*   **关键技术细节**：
    *   **数据管理**：使用 SQLite 存储稀疏矩阵，加速特征提取。
    *   **算法流程**：采用逻辑回归（L2 正则化）进行特征归因，利用随机森林进行分类预测，并结合 StratifiedKFold 交叉验证。
    *   **环境安全**：所有代码执行均在沙盒化的 Python 环境中完成，确保可追溯性和安全性。

### 3. 实验设计
论文通过两个主要案例验证了 ORION 的性能：
*   **基准测试 (Benchmark)**：使用已发表的 **APS-1（1 型自身免疫性多内分泌腺病综合征）** 数据集。该病有明确的自身抗体特征，用于验证 ORION 能否准确找回已知信号。
*   **新发现测试**：使用未公开的 **唐氏综合征 (DS)** 数据集（105 名患者，103 名健康对照，17 名珠子对照）。该领域尚无全蛋白质组参考图谱，用于测试 ORION 的假设生成能力。
*   **对比基准**：主要对比对象是人类专家手动分析所需的时间和结论的准确性。

### 4. 资源与算力
*   **模型使用**：论文提到了使用 **GPT-5.2** 和 **GPT-5.2 pro**（注：此处可能为论文预设或特定版本的代号）作为底层推理引擎。
*   **算力细节**：文中**未明确说明**具体的 GPU 型号或数量。
*   **运行耗时**：APS-1 分析耗时 2 小时 16 分钟；唐氏综合征分析耗时 1 小时 41 分钟。

### 5. 实验数量与充分性
*   **实验规模**：涵盖了已知疾病模型和未知疾病探索。在唐氏综合征实验中，使用了超过 200 个样本和 56 万个肽段特征。
*   **充分性评价**：实验设计较为客观。作者对比了“珠子归一化（AG-normalization）”前后的差异，证明了框架处理实验伪影的能力；通过交叉验证（AUC 达 0.911）证明了分类性能的稳健性。但作为 AI 框架，其在更多组学（如转录组、代谢组）上的泛化性仍需更多实验支撑。

### 6. 主要结论与发现
*   **效率极大提升**：ORION 将原本需要 1-2 个月的人工分析缩短至约 2 小时。
*   **准确性验证**：在 APS-1 中成功找回了所有经典的细胞因子和器官特异性自身抗体标志物。
*   **新生物学见解**：在唐氏综合征中识别出与免疫调节（IL17F）、肠道屏障（MGAM）和神经粘附（NTM）相关的候选靶点，并提出了可验证的实验假设。
*   **分类能力**：ORION 构建的模型能以高准确度（AUC 0.911）区分唐氏综合征与健康对照。

### 7. 优点
*   **端到端自动化**：整合了从原始数据到文献综述再到实验设计的全流程。
*   **可追溯与可重复**：通过持久化的执行日志和 SQLite 数据库，每一项结论都可以追溯到具体的计算步骤。
*   ** artifact 意识**：能够自动识别并处理 PhIP-seq 中的非特异性结合伪影。

### 8. 不足与局限
*   **幻觉风险**：尽管有监督智能体，LLM 仍可能产生看似合理但错误的解释，结论必须经过实验验证。
*   **成本问题**：大规模队列的迭代推理可能产生较高的 API 调用成本。
*   **应用限制**：目前主要针对 PhIP-seq 数据优化，扩展到其他组学（如单细胞测序）需要调整输入模式和提示词工程。
*   **依赖性**：高度依赖底层 LLM 的推理能力和外部数据库的实时性。

（完）
