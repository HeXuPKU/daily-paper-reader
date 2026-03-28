---
title: Coupling codon and protein constraints decouples drivers of variant pathogenicity
title_zh: 耦合密码子与蛋白质约束解耦变异致病性的驱动因素
authors: "Chen, R., Palpant, N., Foley, G., Boden, M."
date: 2026-03-20
pdf: "https://www.biorxiv.org/content/10.1101/2025.03.12.642937v3.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 结合密码子和蛋白质语言模型预测变异致病性
tldr: 本研究旨在解决基因变异致病性预测中忽视编码序列调控约束的问题。通过结合密码子语言模型（CaLM）和蛋白质语言模型（ESM-2），研究者揭示了致病性由蛋白质“产物”和翻译“过程”共同驱动。研究发现，功能缺失变异主要受残基特征影响，而功能获得变异则表现出更强的密码子约束，且内源基因组环境会放大密码子信号，为理解变异致病性提供了新视角。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-03-12-642937-v3/fig-001.webp\", \"caption\": \"Fig. 7: Schematic of the proposed mechanism.\", \"page\": 25, \"index\": 1, \"width\": 775, \"height\": 538}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-03-12-642937-v3/fig-002.webp\", \"caption\": \"Fig. 3: Decoupling evolutionary drivers of LoF and GoF mechanisms across DMS and CBGE platforms.\", \"page\": 21, \"index\": 2, \"width\": 775, \"height\": 394}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-03-12-642937-v3/fig-003.webp\", \"caption\": \"Fig. 4: Codon-level constraints reflect nonsense and synonymous variant effects.\", \"page\": 22, \"index\": 3, \"width\": 777, \"height\": 723}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-03-12-642937-v3/fig-004.webp\", \"caption\": \"Fig. 5: Dissecting the biological complementarity of CLM and PLM.\", \"page\": 23, \"index\": 4, \"width\": 775, \"height\": 640}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-03-12-642937-v3/fig-005.webp\", \"caption\": \"Fig. 1: Linguistic duality reveals orthogonal evolutionary constraints across the central dogma.\", \"page\": 19, \"index\": 5, \"width\": 775, \"height\": 519}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-03-12-642937-v3/fig-006.webp\", \"caption\": \"Fig. 6: Cross-platform comparison reveals context-dependent codon constraints in BRCA1 and TP53.\", \"page\": 24, \"index\": 6, \"width\": 777, \"height\": 777}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-03-12-642937-v3/fig-007.webp\", \"caption\": \"Fig. 2: Codon and protein constraints define a composite landscape of variant pathogenicity.\", \"page\": 20, \"index\": 7, \"width\": 777, \"height\": 509}]"
motivation: 现有的变异预测模型主要关注蛋白质内在缺陷，而忽略了嵌入在编码序列中的调控约束。
method: 耦合密码子语言模型 (CaLM) 与蛋白质语言模型 (ESM-2)，从不同维度剖析变异致病性的驱动因素。
result: 密码子和蛋白质模态在区分致病变异方面贡献接近，且功能获得性变异比功能缺失性变异更依赖密码子水平的约束。
conclusion: 变异致病性反映了蛋白质产物与翻译过程的共同作用，且实验平台和基因组上下文会显著影响对这些维度的观测。
---

## 摘要
预测遗传变异的功能影响仍然是基因组学中的一个基本挑战。现有模型侧重于蛋白质内在缺陷，却忽视了嵌入在编码序列中的调控约束。在本研究中，我们将密码子语言模型 (CaLM) 与蛋白质语言模型 (ESM-2) 相结合，以剖析变异致病性的驱动因素。在 ClinVar 数据上，两种模态在区分致病性变异与良性变异方面的贡献几乎相等。在 ClinMAVE 的深度突变扫描和基于 CRISPR 的基因组编辑平台上的评估表明，功能缺失 (loss-of-function) 变异主要受残基水平特征支配，而功能获得 (gain-of-function) 变异则表现出密码子水平约束的更大相对贡献，尽管这具有基因特异性。对 BRCA1 和 TP53 中相同变异的对照比较进一步表明，密码子水平的信号在内源基因组背景下有所增强。总之，这些发现表明致病性既反映了“产物”也反映了“过程”，并且实验平台可能会影响哪个维度是可观察的。

## Abstract
Predicting the functional impact of genetic variants remains a fundamental challenge in genomics. Existing models focus on protein-intrinsic defects yet overlook regulatory constraints embedded within coding sequences. Here, we couple a codon language model (CaLM) with a protein language model (ESM-2) to dissect the drivers of variant pathogenicity. On ClinVar data, both modalities contribute near-equally to distinguishing pathogenic from benign variants. Evaluation across Deep Mutational Scanning and CRISPR-Based Genome Editing platforms in ClinMAVE reveals that loss-of-function variants are governed primarily by residue-level features, whereas gain-of-function variants show a greater relative contribution from codon-level constraints, albeit in a gene-specific manner. A controlled comparison of identical variants in BRCA1 and TP53 further suggests that codon-level signals are elevated in the endogenous genomic context. Together, these findings indicate that pathogenicity reflects both the "product" and the "process," and that the experimental platform may influence which dimension is observable.

---

## 论文详细总结（自动生成）

这是一份关于论文《Coupling codon and protein constraints decouples drivers of variant pathogenicity》（耦合密码子与蛋白质约束解耦变异致病性的驱动因素）的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
预测遗传变异（尤其是错义突变）的致病性是基因组学的核心挑战。长期以来，该领域的研究重点主要集中在**蛋白质“产物”**（即氨基酸改变对蛋白质结构和功能的影响）上。然而，编码序列不仅决定氨基酸，还包含调节翻译效率、mRNA 稳定性及剪接的**“过程”约束**。
本研究的动机在于：现有的蛋白质语言模型（PLM）忽略了密码子水平的调控信息。研究者试图通过结合密码子和蛋白质两种维度的约束，探讨致病性是如何由蛋白质功能缺陷和翻译过程干扰共同驱动的。

### 2. 论文提出的方法论
研究提出了一种**双模态耦合分析框架**，旨在从不同生物学层面剖析变异影响：
*   **核心思想**：将变异视为两个层面的扰动：一是氨基酸残基层面的改变（由蛋白质语言模型捕捉），二是密码子序列层面的改变（由密码子语言模型捕捉）。
*   **关键技术细节**：
    *   **CaLM (Codon Language Model)**：使用预训练的密码子语言模型来评估编码序列的进化约束，捕捉翻译效率、mRNA 二级结构等非氨基酸改变的信号。
    *   **ESM-2 (Protein Language Model)**：使用最先进的蛋白质语言模型来评估氨基酸替换对蛋白质适应性的影响。
    *   **耦合评分**：通过计算变异在两个模型下的对数似然比（LLR），并利用逻辑回归或简单的加权组合，将“过程”信号与“产物”信号结合，构建综合致病性预测景观。

### 3. 实验设计
*   **数据集与场景**：
    *   **ClinVar**：用于验证模型区分临床已知的致病（Pathogenic）与良性（Benign）变异的能力。
    *   **ClinMAVE (DMS & CBGE)**：包含深度突变扫描（DMS，通常基于 cDNA 质粒）和基于 CRISPR 的基因组编辑（CBGE，在内源基因组背景下）的数据。
    *   **特定基因案例**：重点分析了 *BRCA1* 和 *TP53*，因为这两个基因在不同实验平台（DMS vs CBGE）下都有丰富的变异数据。
*   **Benchmark 与对比方法**：
    *   对比了单独使用 ESM-2、单独使用 CaLM 以及两者结合的效果。
    *   分析了不同功能类型（LoF 功能缺失 vs GoF 功能获得）变异在两种模型下的表现差异。

### 4. 资源与算力
论文摘要及提供的元数据中**未明确说明**具体的算力消耗（如 GPU 型号、数量或训练时长）。通常此类研究涉及对预训练模型（如 ESM-2）的推理和轻量级下游分类器的训练，对算力的需求主要集中在模型推理阶段。

### 5. 实验数量与充分性
实验设计较为充分且具有多维度视角：
*   **广度**：涵盖了 ClinVar 的大规模临床变异数据。
*   **深度**：通过 ClinMAVE 平台对比了数千个变异在不同实验环境下的表现。
*   **对照严谨性**：特别设计了针对 *BRCA1* 和 *TP53* 的跨平台对比，控制了“相同变异、不同基因组上下文”的变量，增强了结论的可信度。
*   **消融/解耦分析**：通过对比 LoF 和 GoF 变异，成功证明了不同致病机制对密码子/蛋白质约束的依赖程度不同。

### 6. 主要结论与发现
*   **双重驱动**：在 ClinVar 数据中，密码子约束和蛋白质约束对区分致病性的贡献几乎相等，证明了“过程”与“产物”同等重要。
*   **机制解耦**：
    *   **LoF 变异**：主要受残基水平特征（蛋白质结构/功能）支配。
    *   **GoF 变异**：表现出更强的密码子水平约束，暗示其致病性可能更多地涉及翻译调控或表达水平的改变。
*   **上下文依赖**：内源基因组环境（CBGE 平台）会放大密码子水平的信号，而 cDNA 表达系统（DMS 平台）可能会掩盖这些调控约束。
*   **无义/同义变异**：CaLM 能够有效捕捉无义介导的 mRNA 降解（NMD）和同义突变的功能影响，这是传统 PLM 无法做到的。

### 7. 优点
*   **视角新颖**：打破了“蛋白质中心论”，将密码子层面的调控约束引入致病性预测。
*   **生物学解释性强**：通过解耦分析，为 LoF 和 GoF 变异提供了差异化的生物学解释。
*   **跨平台验证**：揭示了实验平台（内源 vs 外源）对观测变异效应的系统性偏差，对未来功能基因组学实验设计有指导意义。

### 8. 不足与局限
*   **基因特异性**：研究指出密码子约束的贡献在不同基因之间存在差异，模型在某些基因上的泛化能力可能受限。
*   **数据偏差风险**：ClinVar 等数据库本身存在报告偏差（Reporting Bias），可能影响模型对“良性”变异的界定。
*   **应用限制**：目前主要针对编码区变异，对于非编码区或复杂的剪接变异，该耦合框架的适用性尚需进一步扩展。
*   **模型复杂性**：虽然结合两个模型提升了性能，但也增加了计算开销和结果解释的复杂性。

（完）
