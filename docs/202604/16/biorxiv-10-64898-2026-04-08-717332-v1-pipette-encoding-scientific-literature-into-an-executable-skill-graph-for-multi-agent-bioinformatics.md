---
title: "Pipette: Encoding scientific literature into an executable Skill Graph for multi-agent bioinformatics"
title_zh: Pipette：将科学文献编码为可执行的技能图谱，用于多智能体生物信息学
authors: "Gupta, C., Sharma, A."
date: 2026-04-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.08.717332v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 基于大语言模型的多智能体生物信息学工作流框架
tldr: 针对生物信息学分析中LLM生成工作流不连贯的问题，本文提出Pipette框架。该框架利用从2万多篇文献中提取的“技能图谱”来约束多智能体AI的分析路径，确保生物学逻辑的有效性。在单细胞、转录组、药物设计及临床基因组等任务中，Pipette显著提升了工作流的完整性和准确性，降低了非专业研究人员的数据分析门槛。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-001.webp\", \"caption\": \"Figure 8. ACMG Secondary Findings v3.2 variant filtering and classification in HG002. A) Variant filtering pipeline showing progressive reduction from 9,924 PASS variants in ACMG gene regions (chr1-22) to 101 HIGH/MODERATE impact and splice region candidates, 9 variants remaining after common variant filtering (BA1: allele frequency > 5%), and 0 confirmed Pathogenic or Likely Pathogenic variants. B) ACMG/AMP classification of the 101 candidate variants: 92 (91%) classified as Benign/Likely Benign and 9 (9%) as Variants of Uncertain Significance (VUS). C) Classification breakdown by ACMG disease category, showing Cardiovascular genes contribute the most variants (Benign and VUS), followed by Cancer and Miscellaneous categories. D) Seven known pathogenic variants spanning six ACMG SF\", \"page\": 21, \"index\": 1, \"width\": 979, \"height\": 974}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-002.webp\", \"caption\": \"Figure 2. Skill Graph: automated construction of a bioinformatics workflow knowledge graph from scientific literature. A) Overview of the Skill Graph construction pipeline. Starting from ~20,000 open-access PMC papers and 800 structured notes across 9 domains, Named Entity Recognition (NER) and Relation Extraction (RE) models were trained on PubMedBERT with IOB2 tags and cross-entropy loss, respectively. Dictionary-based tool detection using EDAM ontology and bio.tools API identified 215 tool regex patterns. Tool mentions and positions were aggregated into skill-skill edges weighted by paper count, yielding 628 raw pipeline edges. Data type validation retained edges where source outputs matched target inputs, producing 258 literature-backed edges. An additional 225 edges were inferred from type compatibility alone. B) Model performance on held-out test set. Grouped bar chart showing Precision (blue), Recall (teal), and F1 (red) for NER (overall entity recognition), RE (USES relation type), and RE (FOLLOWED_BY relation type). C) Pipeline extraction accuracy expressed as percentage\", \"page\": 7, \"index\": 2, \"width\": 979, \"height\": 966}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-003.webp\", \"caption\": \"Figure 5: Evaluation of Pipette’s differential expression analysis workflows. A) Diverging bar charts comparing DEG counts (up = positive, down = negative) at matched FDR < 0.01 between Robertson et al. 2025 (left) and the AI agent recalculated at the same threshold (right). The agent consistently over-estimates DEG counts by ~11–24%, attributable to the absence of LFC shrinkage. Colours: red = up-regulated, blue = down-regulated. B) Four-panel scatter plot showing gene-level log₂FC concordance between the AI agent's DESeq2 output and Robertson et al. 2025 (Table S2) across all four contrasts. Only paper-significant genes (FDR < 0.01, |LFC| ≥ 1) are shown. Points coloured red (up-regulated in paper) or blue (down-regulated). Dashed line = identity (y = x). Pearson r ≥ 0.976 for all contrasts, confirming near-identical fold-change estimates.\", \"page\": 14, \"index\": 3, \"width\": 979, \"height\": 475}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-004.webp\", \"caption\": \"Figure 7. De novo cyclic peptide design targeting the p53-MDM2 interaction. (A) Docking scores for 10 cyclic peptides (6-8 residues) designed to mimic the p53 Phe19-Trp23-Leu26 hotspot triad, docked into the MDM2 hydrophobic cleft (PDB 1YCR). Bars are coloured by\", \"page\": 18, \"index\": 4, \"width\": 979, \"height\": 948}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-005.webp\", \"caption\": \"Figure 4: Evaluation of Pipette to execute scRNA-seq workflows using the PBMC 68K dataset. A)\", \"page\": 13, \"index\": 5, \"width\": 971, \"height\": 498}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-006.webp\", \"caption\": \"Figure 1. Architecture of Pipette.bio, a multi-agent AI framework for autonomous bioinformatics analysis. The system comprises three layers. (Top) A conversational interface where the Copilot Agent classifies user intent – responding directly to conceptual questions or dispatching analysis requests to the pipeline with domain-aware queue routing. (Middle) A six-stage orchestrated analysis pipeline coordinated by a deterministic orchestrator. Stage 1 initializes an ephemeral workspace and restores outputs from prior conversation turns for multi-turn continuity. Stage 2 houses the Executor Agent, which operates in an iterative tool-use loop (Plan, Write Code, Execute, Observe) across bash, Python, and R, with access to a library of 91+ injectable domain knowledge modules (skills) covering RNA-seq alignment,\", \"page\": 4, \"index\": 6, \"width\": 979, \"height\": 552}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-007.webp\", \"caption\": \"Figure 3. Pipette behavioural metrics and system validation across production deployments. A) Distribution of autonomous pipeline queries across four computational domains during a two-month deployment period. Percentages reflect proportion of total query volume. B) Skill usage distribution showing the 20 most frequently invoked skills (of 48 active), coloured by analytical domain. Differential\", \"page\": 9, \"index\": 7, \"width\": 775, \"height\": 1202}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-008.webp\", \"caption\": \"Figure 6. Molecular docking validation of imatinib into ABL1 kinase (PDB: 2HYY). A) Binding affinity rankings for the top 10 docking modes at pH 7.4 protonation state. The best-scoring pose achieved -11.8 kcal/mol (red), within the expected range from published crystal structure data. The dashed green line indicates the expected threshold (-8 kcal/mol) and the orange line marks the strong binder cutoff (-12\", \"page\": 16, \"index\": 8, \"width\": 979, \"height\": 1033}]"
motivation: 生物信息学分析的高门槛限制了基因组数据的转化，且现有大语言模型在处理复杂多步工作流时常因缺乏领域约束而产生错误。
method: 提出一种多智能体AI框架，通过从两万余篇同行评审文献中提取的有向加权“技能图谱”来引导和约束分析流程的生成。
result: 在单细胞测序、转录组分析及药物设计等多个基准测试中，Pipette的表现均优于传统LLM，并能生成完全可重复的分析记录。
conclusion: Pipette通过将科学文献转化为可执行的知识图谱，有效降低了生物信息学分析的技术门槛，加速了从测序数据到生物学见解的转化。
---

## 摘要
基因组测序成本已下降了几个数量级，但数据分析仍然是集中在具有专业计算背景的研究人员手中的瓶颈。虽然大语言模型可以生成生物信息学代码，但由于缺乏特定领域的分析约束，它们经常产生不连贯的多步工作流。在此，我们介绍了 Pipette，这是一个多智能体 AI 框架，它在源自文献的技能图谱（Skill Graph）引导下，通过自然语言交互编排端到端的生物信息学工作流。该有向、边加权的知识图谱提取自 20,000 多篇同行评审的出版物，它将工作流生成约束在生物学有效的分析转换中，从而防止产生不完整或不连贯的工作流。我们使用已发表的数据集在四个生物学领域对 Pipette 进行了基准测试：外周血单核细胞和人类胰腺图谱的单细胞 RNA-seq 分析、环境压力下水稻的 Bulk RNA-seq 差异表达，以及两个基于结构的计算药物设计工作流。在与两个没有技能图谱约束的大语言模型进行的消融实验中，Pipette 在所有定量指标上都达到或超过了这两个基准，同时独特地完成了多步跨领域转换。我们进一步在临床基因组学任务上评估了 Pipette，它在参考人类基因组上执行了符合 ACMG/AMP 标准的变异分类。在所有案例中，Pipette 在重现已确立的生物学和临床发现的同时，生成了完全可重复、机器可读的溯源记录。通过降低执行标准基因组分析所需的计算专业知识要求，Pipette 为实验科学家降低了从测序数据获取生物学见解的门槛。Pipette 可在 https://pipette.bio 获取。

## Abstract
The cost of genomic sequencing has fallen by several orders of magnitude, yet data analysis remains a bottleneck concentrated among researchers with specialized computational expertise. While Large Language Models can generate bioinformatics code, they frequently produce incoherent multi-step workflows due to the absence of domain-specific analytical constraints. Here, we present Pipette, a multi-agent AI framework that orchestrates end-to-end bioinformatics workflows through natural language interaction, guided by a literature-derived Skill Graph. This directed, edge-weighted knowledge graph, extracted from over 20,000 peer-reviewed publications, constrains workflow generation to biologically valid analytical transitions, preventing incomplete or incoherent workflows. We benchmarked Pipette across four biological domains using published datasets: single-cell RNA-seq analysis of peripheral blood mononuclear cells and a human pancreas atlas, bulk RNA-seq differential expression in rice under environmental stress, and two structure-based computational drug design workflows. In ablation against two LLMs operating without Skill Graph constraints, Pipette matched or exceeded both baselines across all quantitative metrics while uniquely completing multi-step cross-domain transitions. We further evaluated Pipette on a clinical genomics task, where it executed an ACMG/AMP-compliant variant classification on a reference human genome. In all cases, Pipette recapitulated established biological and clinical findings while generating a fully reproducible, machine-readable provenance record. By reducing the computational expertise required to execute standard genomic analyses, Pipette lowers the barrier between sequencing data and biological insight for bench scientists. Pipette is available at https://pipette.bio.

---

## 论文详细总结（自动生成）

以下是对论文《Pipette: Encoding scientific literature into an executable Skill Graph for multi-agent bioinformatics》的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **研究背景**：随着测序成本大幅下降，基因组学的数据生成已不再是瓶颈，真正的挑战转向了**数据分析**。目前的分析高度依赖具有专业计算背景的人员，导致研究周期长、沟通成本高。
*   **核心问题**：虽然大语言模型（LLM）具备生成生物信息学代码的能力，但由于缺乏领域特定的分析约束，它们在处理复杂的多步工作流时经常产生**不连贯、不符合生物学逻辑或错误的转换**（即“幻觉”）。
*   **整体含义**：本文提出了 Pipette 框架，旨在通过从海量文献中提取的“技能图谱”（Skill Graph）来约束 AI 智能体的规划行为，使非计算专业的实验科学家也能通过自然语言完成严谨、可重复的生物信息学分析。

### 2. 核心方法论
*   **多智能体架构**：Pipette 包含 Copilot（交互）、Orchestrator（编排）、Executor（执行）、Reviewer（审计）、Reporter（报告）和 Hypothesis（假设生成）等多个智能体。
*   **技能图谱（Skill Graph）**：
    *   **构建**：从 20,000 多篇 PubMed 全文和 800 份手动标注笔记中提取。
    *   **技术细节**：使用微调后的 PubMedBERT 模型进行命名实体识别（NER）和关系抽取（RE），识别工具、操作和数据类型。
    *   **约束机制**：图谱中的节点代表离散技能（如序列比对），有向边代表有效的分析转换。通过**数据类型验证**（输入/输出匹配）和**文献共现频率**加权，确保工作流的逻辑严密性。
*   **六阶段分析流程**：环境初始化、智能执行（Plan-Code-Execute-Observe 循环）、方法论审查（独立审计代码和统计假设）、溯源追踪（生成 DAG 记录环境和参数）、报告生成、文献综合。

### 3. 实验设计
*   **实验场景与数据集**：
    *   **单细胞 RNA-seq**：使用 68,000 个 PBMC 数据集和人类胰腺图谱（GSE85241）。
    *   **Bulk RNA-seq**：分析环境压力下的水稻叶片数据（GSE295637）。
    *   **药物设计**：伊马替尼与 ABL1 激酶的分子对接，以及针对 p53-MDM2 的环肽设计。
    *   **临床基因组学**：对 GIAB HG002 参考样本进行 ACMG/AMP 标准的变异分类。
*   **Benchmark 与对比方法**：
    *   **消融实验**：对比了在没有技能图谱约束下的 Claude 4.5 和 GPT 5.4（文中使用的代号，指代当时最先进的模型版本）。
    *   **验证标准**：与已发表的原始论文结果（如细胞比例、差异表达基因 log2FC、晶体结构 RMSD 等）进行定量对比。

### 4. 资源与算力
*   **算力配置**：系统运行在可扩展的云基础设施上，提供五种领域特定的弹性计算队列。
    *   **标准型**：4 vCPU, 16 GB 内存。
    *   **高内存型**：最高 32 vCPU, 128 GB 内存, 500 GB 磁盘（用于 Bulk RNA-seq 比对等任务）。
*   **模型训练**：PubMedBERT 的微调在文中提到使用了 10-20 个 epoch，但未详细说明具体的 GPU 型号和总训练时长。

### 5. 实验数量与充分性
*   **实验规模**：涵盖了 4 个大类领域、6 个核心数据集，并分析了生产环境两个月内的 125 份报告和 899 个质量检查项。
*   **充分性评价**：实验设计较为充分，不仅涵盖了常见的组学分析，还挑战了复杂的药物分子设计和严苛的临床变异诊断。通过消融实验证明了技能图谱在减少错误和提高相关性方面的关键作用。实验对比采用了 Pearson 相关系数、RMSD、敏感性/特异性等客观指标，具有较高的说服力。

### 6. 主要结论与发现
*   **高准确性**：在单细胞和转录组任务中，Pipette 与原始论文结果的相关性极高（r > 0.95）。
*   **鲁棒性**：在药物对接实验中，智能体能自动诊断并修复工具链中的 Bug（如处理 PDBQT 转换错误），实现亚埃级（0.89 Å）的精度。
*   **临床可靠性**：在临床变异分析中，Pipette 实现了 100% 的敏感性，并能正确识别复杂的复合杂合变异。
*   **图谱价值**：相比无约束的 LLM，技能图谱显著提升了多步跨领域任务的完成率，并能有效避免统计学方法（如多重假设检验校正）的缺失。

### 7. 优点（亮点）
*   **知识驱动的约束**：将非结构化的科学文献转化为结构化的可执行图谱，解决了 LLM 在专业领域“乱写代码”的问题。
*   **自动化审计**：引入独立的 Reviewer 智能体，模拟人类同行评审过程，捕捉 QC 阈值和统计假设错误。
*   **完全可重复性**：自动生成机器可读的溯源记录（Provenance），符合科研诚信和临床监管要求。
*   **动态自修复**：Executor 智能体具备在执行失败时根据观察结果调整策略的能力。

### 8. 不足与局限
*   **图谱时效性**：技能图谱基于静态语料库构建，对于最新出现的算法或工具可能存在滞后，需要定期更新。
*   **供应商依赖**：核心推理依赖商业 LLM（如 Claude、GPT），存在成本、延迟及隐私合规的潜在风险。
*   **临床应用限制**：尽管表现优异，但 AI 生成的临床报告仍需专业遗传学家签字确认，不能直接用于临床决策。
*   **文献检索偏差**：Hypothesis 智能体在检索时倾向于近期文献，可能忽略奠基性的经典研究。

（完）
