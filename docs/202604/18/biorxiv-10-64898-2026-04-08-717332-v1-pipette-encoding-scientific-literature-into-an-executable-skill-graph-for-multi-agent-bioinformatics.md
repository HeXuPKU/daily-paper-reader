---
title: "Pipette: Encoding scientific literature into an executable Skill Graph for multi-agent bioinformatics"
title_zh: Pipette：将科学文献编码为用于多智能体生物信息学的可执行技能图谱
authors: "Gupta, C., Sharma, A."
date: 2026-04-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.08.717332v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 利用大语言模型和技能图谱构建的多智能体生物信息学工作流框架
tldr: Pipette是一个多智能体AI框架，旨在解决生物信息学分析中LLM生成工作流不连贯的问题。它通过从2万多篇论文中提取知识构建“技能图谱”，引导AI生成符合生物学逻辑的分析步骤。在单细胞、转录组、药物设计和临床基因组学等任务中，Pipette不仅超越了基准模型，还实现了高度可重复的自动化分析，显著降低了实验科学家的技术门槛。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-001.webp\", \"caption\": \"Figure 8. ACMG Secondary Findings v3.2 variant filtering and classification in HG002. A) Variant filtering pipeline showing progressive reduction from 9,924 PASS variants in ACMG gene regions (chr1-22) to 101 HIGH/MODERATE impact and splice region candidates, 9 variants remaining after common variant filtering (BA1: allele frequency > 5%), and 0 confirmed Pathogenic or Likely Pathogenic variants. B) ACMG/AMP classification of the 101 candidate variants: 92 (91%) classified as Benign/Likely Benign and 9 (9%) as Variants of Uncertain Significance (VUS). C) Classification breakdown by ACMG disease category, showing Cardiovascular genes contribute the most variants (Benign and VUS), followed by Cancer and Miscellaneous categories. D) Seven known pathogenic variants spanning six ACMG SF\", \"page\": 21, \"index\": 1, \"width\": 979, \"height\": 974}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-002.webp\", \"caption\": \"Figure 2. Skill Graph: automated construction of a bioinformatics workflow knowledge graph from scientific literature. A) Overview of the Skill Graph construction pipeline. Starting from ~20,000 open-access PMC papers and 800 structured notes across 9 domains, Named Entity Recognition (NER) and Relation Extraction (RE) models were trained on PubMedBERT with IOB2 tags and cross-entropy loss, respectively. Dictionary-based tool detection using EDAM ontology and bio.tools API identified 215 tool regex patterns. Tool mentions and positions were aggregated into skill-skill edges weighted by paper count, yielding 628 raw pipeline edges. Data type validation retained edges where source outputs matched target inputs, producing 258 literature-backed edges. An additional 225 edges were inferred from type compatibility alone. B) Model performance on held-out test set. Grouped bar chart showing Precision (blue), Recall (teal), and F1 (red) for NER (overall entity recognition), RE (USES relation type), and RE (FOLLOWED_BY relation type). C) Pipeline extraction accuracy expressed as percentage\", \"page\": 7, \"index\": 2, \"width\": 979, \"height\": 966}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-003.webp\", \"caption\": \"Figure 5: Evaluation of Pipette’s differential expression analysis workflows. A) Diverging bar charts comparing DEG counts (up = positive, down = negative) at matched FDR < 0.01 between Robertson et al. 2025 (left) and the AI agent recalculated at the same threshold (right). The agent consistently over-estimates DEG counts by ~11–24%, attributable to the absence of LFC shrinkage. Colours: red = up-regulated, blue = down-regulated. B) Four-panel scatter plot showing gene-level log₂FC concordance between the AI agent's DESeq2 output and Robertson et al. 2025 (Table S2) across all four contrasts. Only paper-significant genes (FDR < 0.01, |LFC| ≥ 1) are shown. Points coloured red (up-regulated in paper) or blue (down-regulated). Dashed line = identity (y = x). Pearson r ≥ 0.976 for all contrasts, confirming near-identical fold-change estimates.\", \"page\": 14, \"index\": 3, \"width\": 979, \"height\": 475}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-004.webp\", \"caption\": \"Figure 7. De novo cyclic peptide design targeting the p53-MDM2 interaction. (A) Docking scores for 10 cyclic peptides (6-8 residues) designed to mimic the p53 Phe19-Trp23-Leu26 hotspot triad, docked into the MDM2 hydrophobic cleft (PDB 1YCR). Bars are coloured by\", \"page\": 18, \"index\": 4, \"width\": 979, \"height\": 948}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-005.webp\", \"caption\": \"Figure 4: Evaluation of Pipette to execute scRNA-seq workflows using the PBMC 68K dataset. A)\", \"page\": 13, \"index\": 5, \"width\": 971, \"height\": 498}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-006.webp\", \"caption\": \"Figure 1. Architecture of Pipette.bio, a multi-agent AI framework for autonomous bioinformatics analysis. The system comprises three layers. (Top) A conversational interface where the Copilot Agent classifies user intent – responding directly to conceptual questions or dispatching analysis requests to the pipeline with domain-aware queue routing. (Middle) A six-stage orchestrated analysis pipeline coordinated by a deterministic orchestrator. Stage 1 initializes an ephemeral workspace and restores outputs from prior conversation turns for multi-turn continuity. Stage 2 houses the Executor Agent, which operates in an iterative tool-use loop (Plan, Write Code, Execute, Observe) across bash, Python, and R, with access to a library of 91+ injectable domain knowledge modules (skills) covering RNA-seq alignment,\", \"page\": 4, \"index\": 6, \"width\": 979, \"height\": 552}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-007.webp\", \"caption\": \"Figure 3. Pipette behavioural metrics and system validation across production deployments. A) Distribution of autonomous pipeline queries across four computational domains during a two-month deployment period. Percentages reflect proportion of total query volume. B) Skill usage distribution showing the 20 most frequently invoked skills (of 48 active), coloured by analytical domain. Differential\", \"page\": 9, \"index\": 7, \"width\": 775, \"height\": 1202}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-08-717332-v1/fig-008.webp\", \"caption\": \"Figure 6. Molecular docking validation of imatinib into ABL1 kinase (PDB: 2HYY). A) Binding affinity rankings for the top 10 docking modes at pH 7.4 protonation state. The best-scoring pose achieved -11.8 kcal/mol (red), within the expected range from published crystal structure data. The dashed green line indicates the expected threshold (-8 kcal/mol) and the orange line marks the strong binder cutoff (-12\", \"page\": 16, \"index\": 8, \"width\": 979, \"height\": 1033}]"
motivation: 尽管测序成本下降，但生物信息学分析仍受限于专业计算技能，且现有大模型在处理复杂工作流时常因缺乏领域约束而产生错误。
method: 提出一种由文献驱动的技能图谱（Skill Graph）引导的多智能体框架，利用从两万余篇论文中提取的知识图谱来约束和优化分析流程。
result: 在多项生物学和临床基因组学任务中，Pipette的表现均优于无约束的LLM基准，能够准确复现生物学发现并生成完整的可重复记录。
conclusion: Pipette通过将科学文献转化为可执行的技能图谱，有效降低了生物信息学分析的门槛，加速了从原始数据到生物学洞察的转化过程。
---

## 摘要
基因组测序成本已下降了几个数量级，但数据分析仍然是一个瓶颈，主要集中在具有专业计算背景的研究人员手中。虽然大语言模型可以生成生物信息学代码，但由于缺乏特定领域的分析约束，它们经常产生不连贯的多步工作流。在此，我们提出了 Pipette，这是一个多智能体 AI 框架，它在源自文献的技能图谱指导下，通过自然语言交互编排端到端的生物信息学工作流。该有向、边加权的知识图谱提取自 20,000 多篇同行评审的出版物，它将工作流生成约束在生物学有效的分析转换中，从而防止产生不完整或不连贯的工作流。我们利用已发表的数据集在四个生物学领域对 Pipette 进行了基准测试：外周血单核细胞和人类胰腺图谱的单细胞 RNA-seq 分析、环境压力下水稻的大体 RNA-seq 差异表达分析，以及两个基于结构的计算药物设计工作流。在与两个没有技能图谱约束的大语言模型进行的消融实验中，Pipette 在所有定量指标上均达到或超过了两个基准模型，同时能够独特地完成多步跨领域转换。我们进一步在临床基因组学任务上评估了 Pipette，它在参考人类基因组上执行了符合 ACMG/AMP 标准的变异分类。在所有案例中，Pipette 都在重现已确立的生物学和临床发现的同时，生成了完全可重现、机器可读的出处记录。通过降低执行标准基因组分析所需的计算专业知识门槛，Pipette 为实验科学家降低了从测序数据到生物学洞察之间的障碍。Pipette 可在 https://pipette.bio 获取。

## Abstract
The cost of genomic sequencing has fallen by several orders of magnitude, yet data analysis remains a bottleneck concentrated among researchers with specialized computational expertise. While Large Language Models can generate bioinformatics code, they frequently produce incoherent multi-step workflows due to the absence of domain-specific analytical constraints. Here, we present Pipette, a multi-agent AI framework that orchestrates end-to-end bioinformatics workflows through natural language interaction, guided by a literature-derived Skill Graph. This directed, edge-weighted knowledge graph, extracted from over 20,000 peer-reviewed publications, constrains workflow generation to biologically valid analytical transitions, preventing incomplete or incoherent workflows. We benchmarked Pipette across four biological domains using published datasets: single-cell RNA-seq analysis of peripheral blood mononuclear cells and a human pancreas atlas, bulk RNA-seq differential expression in rice under environmental stress, and two structure-based computational drug design workflows. In ablation against two LLMs operating without Skill Graph constraints, Pipette matched or exceeded both baselines across all quantitative metrics while uniquely completing multi-step cross-domain transitions. We further evaluated Pipette on a clinical genomics task, where it executed an ACMG/AMP-compliant variant classification on a reference human genome. In all cases, Pipette recapitulated established biological and clinical findings while generating a fully reproducible, machine-readable provenance record. By reducing the computational expertise required to execute standard genomic analyses, Pipette lowers the barrier between sequencing data and biological insight for bench scientists. Pipette is available at https://pipette.bio.

---

## 论文详细总结（自动生成）

### 论文总结：Pipette —— 基于文献驱动技能图谱的多智能体生物信息学框架

#### 1. 核心问题与整体含义（研究动机和背景）
随着测序技术的发展，基因组数据的生成成本大幅下降，但**数据分析**成为了新的瓶颈。生物信息学分析通常需要熟练掌握命令行、多种软件工具及统计方法。虽然大语言模型（LLM）具备生成代码的能力，但在处理复杂的多步生物信息学工作流时，由于缺乏领域特定的逻辑约束，LLM 容易产生“幻觉”，导致步骤不连贯、工具不兼容或统计方法错误。Pipette 的提出旨在通过构建一个从科学文献中提取的“技能图谱”（Skill Graph），为 AI 智能体提供领域知识约束，从而实现自动化、高可靠且可重复的生物信息学分析。

#### 2. 论文提出的方法论
Pipette 采用了一种多智能体协同架构，其核心思想是将自由的代码生成转变为受约束的图谱导航。

*   **核心组件：技能图谱 (Skill Graph)**
    *   **构建过程**：从 PubMed Central 提取了约 20,000 篇全文论文，利用微调后的 PubMedBERT 模型进行命名实体识别（NER）和关系抽取（RE）。
    *   **拓扑结构**：包含 78 个离散技能节点（如序列比对、差异表达分析）和 483 条有向边。边权重基于文献中的共现频率，并经过数据类型兼容性（基于 EDAM 本体）的严格过滤。
*   **多智能体架构**：
    *   **Copilot Agent**：负责自然语言交互和意图分类。
    *   **Executor Agent**：根据技能图谱规划路径，编写并执行 Python/R/Bash 代码。
    *   **Reviewer Agent**：独立审计代码和结果，检查统计严谨性（如多重假设检验校正）和 QC 阈值，不合格则触发修复循环。
    *   **Provenance Tracking**：自动生成机器可读的 DAG（有向无环图），记录软件版本、参数和随机种子，确保 100% 可重复性。

#### 3. 实验设计
论文在四个关键生物学领域进行了验证，并与主流 LLM 进行了对比：

*   **实验场景与数据集**：
    1.  **单细胞 RNA-seq**：使用 PBMC 68K 数据集和人类胰腺图谱，验证聚类、注释和细胞比例的一致性。
    2.  **Bulk RNA-seq**：使用水稻叶片受压力的转录组数据（GSE295637），验证差异表达基因（DEG）识别的准确性。
    3.  **药物设计**：执行伊马替尼与 ABL1 激酶的分子对接，以及针对 p53-MDM2 相互作用的从头环肽设计。
    4.  **临床基因组学**：对 GIAB HG002 参考样本进行符合 ACMG/AMP 标准的变异分类。
*   **Benchmark 与对比方法**：
    *   **基准**：已发表的原始论文结果。
    *   **对比模型**：在没有技能图谱约束的情况下，直接使用 Claude 4.5 和 GPT 5.4 执行相同任务。

#### 4. 资源与算力
*   **算力说明**：论文提到 Pipette 运行在可扩展的云基础设施上，根据任务需求动态分配资源。
*   **具体配置**：提供了五种领域特定的弹性计算队列，从标准型（4 vCPU, 16 GB RAM）到高内存型（32 vCPU, 128 GB RAM, 500 GB 磁盘）。
*   **训练细节**：PubMedBERT 的微调在 800 份标注文档上进行（10-20 个 epoch），但未明确说明具体的 GPU 型号（如 A100/H100）或总训练时长。

#### 5. 实验数量与充分性
*   **实验规模**：涵盖了 6 个真实世界数据集，跨越转录组学、结构生物学和临床医学。
*   **消融实验**：通过移除技能图谱的对比实验，量化了图谱在减少逻辑错误和提高相关性方面的贡献。
*   **充分性评价**：实验设计较为全面，不仅关注定量指标（如 Pearson 相关系数、RMSD），还关注定性的方法论正确性（如 Reviewer Agent 拦截的错误类型）。对比实验使用了目前最顶尖的 LLM，具有较高的参考价值。

#### 6. 主要结论与发现
*   **高准确性**：Pipette 在单细胞和 Bulk RNA-seq 任务中与原始论文结果高度一致（相关系数 r > 0.95）。
*   **超越基准 LLM**：在无约束对比中，Claude 和 GPT 经常出现忽略批次效应校正、使用错误的统计模型或无法完成跨领域 API 调用等问题，而 Pipette 均能正确处理。
*   **自我修复能力**：在药物对接实验中，Pipette 能够自动识别并修复软件环境中的 bug（如 PDBQT 转换错误），展现了极强的鲁棒性。
*   **临床合规性**：在临床变异分析中实现了 100% 的敏感性和特异性（针对注入的致病变异）。

#### 7. 优点
*   **知识驱动的约束**：通过文献图谱解决了 LLM 在专业领域“胡言乱语”的问题，确保了分析流程的生物学合理性。
*   **闭环审计机制**：Reviewer Agent 的引入模拟了人类同行评审过程，显著提升了结果的严谨性。
*   **透明度与可重复性**：自动记录完整的出处信息，解决了生物信息学中长期存在的“黑箱”分析问题。

#### 8. 不足与局限
*   **图谱时效性**：技能图谱基于静态语料库构建，对于最新发表的算法或工具可能存在滞后，需要定期更新。
*   **依赖商业模型**：系统核心依赖于 Claude/GPT 等闭源模型，存在供应商锁定风险及隐私/成本考量。
*   **临床风险**：尽管表现优异，但 AI 生成的临床报告仍需专业医生审核，不能完全替代人工诊断。
*   **文献偏差**：图谱构建依赖于文献共现，可能导致系统倾向于推荐“流行”但非“最优”的方法。

（完）
