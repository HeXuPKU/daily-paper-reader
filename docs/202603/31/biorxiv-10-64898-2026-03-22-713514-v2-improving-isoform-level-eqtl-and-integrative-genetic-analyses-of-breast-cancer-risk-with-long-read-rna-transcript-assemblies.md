---
title: Improving isoform-level eQTL and integrative genetic analyses of breast cancer risk with long-read RNA transcript assemblies
title_zh: 利用长读段 RNA 转录本组装改进乳腺癌风险的异构体级 eQTL 和综合遗传分析
authors: "Head, S. T., Nemani, A., Chang, Y.-H., Harrison, T. A., Bresnahan, S. T., Rothstein, J. H., Sieh, W., Lindstroem, S., Bhattacharya, A."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.22.713514v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 癌症风险的综合遗传分析和eQTL映射
tldr: 本研究针对传统eQTL和TWAS分析中忽略异构体水平调节的问题，利用长读长RNA-seq数据构建了乳腺组织特异性的转录本组装。通过对比GENCODE与组织特异性注释，研究揭示了大量仅在特定注释下可见的遗传调控关联。结果表明，长读长技术能识别出如NUP107等位点处此前未被发现的候选致病异构体，显著提升了乳腺癌遗传风险分析的特异性和准确性，证明了组织特异性注释在解析复杂疾病机制中的关键作用。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713514-v2/fig-001.webp\", \"caption\": \"\", \"page\": 17, \"index\": 1, \"width\": 2184, \"height\": 2123}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713514-v2/fig-002.webp\", \"caption\": \"\", \"page\": 17, \"index\": 2, \"width\": 2933, \"height\": 728}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713514-v2/fig-003.webp\", \"caption\": \"\", \"page\": 18, \"index\": 3, \"width\": 2021, \"height\": 697}]"
motivation: 传统的eQTL分析通常使用组织无关的转录本注释，容易忽略异构体水平的调控机制，从而限制了对乳腺癌遗传风险的解析。
method: 利用长读长RNA-seq数据构建乳腺肿瘤、健康组织及成纤维细胞的特异性转录本组装，并开展eQTL映射、精细映射及TWAS整合分析。
result: 发现约1/3的cis-eQTL在不同注释间存在差异，且长读长注释识别出多个GENCODE漏掉的候选致病异构体（如MARK1和NUP107位点）。
conclusion: 整合长读长测序衍生的组织特异性异构体注释能显著增强遗传调控推断的特异性，是识别GWAS位点候选致病异构体的关键。
---

## 摘要
大多数 eQTL 和 TWAS 分析使用聚合的、与组织无关的转录本注释来量化表达，并忽略了异构体层面的调控，这可能会掩盖或错误归因调控机制。在本研究中，我们开发了一个框架，利用公开的长读段 RNA-seq 数据进行组织知情的遗传调控推断，并优先排序乳腺癌风险的候选因果异构体。我们使用三种转录组注释量化了乳腺肿瘤 (TCGA)、非癌性乳腺组织和培养的成纤维细胞 (GTEx) 中的基因和异构体级表达：标准 GENCODE、组织特异性长读段衍生组装，以及结合了两者的转录本异构体的组合注释。虽然 GENCODE 编目了超过 250,000 个泛组织异构体，但组织特异性长读段组装在肿瘤中捕获了较少的 74,717 个异构体，在成纤维细胞中捕获了 48,057 个，在健康乳腺中捕获了 22,941 个。我们进行了 eQTL 映射和精细映射，随后与总体和亚型特异性乳腺癌 GWAS 以及异构体级 TWAS 进行了共定位。虽然大多数 eGenes 在不同注释之间是一致的，但共享 eGenes 的主要顺式 eQTL (cis-eQTLs) 中约有 1/3 在长读段组装和 GENCODE 之间存在差异。此外，eIsoform 的发现具有高度的注释特异性。在健康乳腺组织（构建乳腺癌 TWAS 基因表达预测模型的金标准组织）中，长读段注释识别出的 eIsoform 中有 46% 是该注释特有的，尽管其中 93.7% 存在于 GENCODE 中。尽管组合注释仅根据组织来源将 GENCODE 目录扩展了 0.6-7.6%，但 69% 的独特显著异构体-性状关联是特定于单一注释的。长读段知情的注释揭示了 GENCODE 完全遗漏的调控关联，包括仅在成纤维细胞中捕获的 MARK1 位点的候选调控异构体，以及在 NUP107 处被优先排序为可能效应转录本的先前未注释的剪接变体。这些发现表明，转录本注释不仅是一个技术考虑因素，而且关键地定义了调控机制的生物学假设空间并塑造了发现。结合来自长读段 RNA-seq 的组织解析异构体注释提高了调控推断的特异性，并增强了对 GWAS 位点候选因果异构体的识别。

## Abstract
Most eQTL and TWAS analyses quantify expression using aggregate, tissue-agnostic transcript annotations and ignore isoform-level regulation, potentially obscuring or misattributing regulatory mechanisms. Here, we developed a framework leveraging publicly available long-read RNA-seq data to perform tissue-informed inference of genetic regulation and prioritize candidate causal isoforms for breast cancer risk. We quantified gene- and isoform-level expression in breast tumor (TCGA), non-cancerous mammary tissue, and cultured fibroblasts (GTEx) using three transcriptome annotations: standard GENCODE, tissue-specific long-read-derived assemblies, and combined annotations incorporating transcript-isoforms from both. While GENCODE cataloged over 250,000 pan-tissue isoforms, the tissue-specific long-read assemblies captured reduced sets of 74,717 isoforms in tumor, 48,057 in fibroblasts, and 22,941 in healthy breast. We performed eQTL mapping and fine-mapping, followed by colocalization with overall and subtype-specific breast cancer GWAS and isoform-level TWAS. While most eGenes were concordant across annotations, approximately 1/3 of lead cis-eQTLs for shared eGenes differed between long-read assemblies and GENCODE. Further, eIsoform discovery was highly annotation-specific. In healthy breast tissue, the gold standard tissue for building gene expression prediction models for TWAS of breast cancer, 46% of eIsoforms identified by the long-read annotation were unique to that annotation even though 93.7% of them are present in GENCODE. Despite combined annotations expanding the GENCODE catalog by only 0.6-7.6% depending on tissue source, 69% of unique significant isoform-trait associations were specific to a single annotation. Long-read-informed annotations uncovered regulatory associations entirely missed by GENCODE, including a candidate regulatory isoform at the MARK1 locus captured only in fibroblasts and a previously unannotated splice variant prioritized as the likely effector transcript at NUP107. These findings demonstrate that transcript annotation is not merely a technical consideration but critically defines the biological hypothesis space for regulatory mechanisms and shapes discovery. Incorporating tissue-resolved isoform annotations from long-read RNA-seq improves the specificity of regulatory inference and enhances identification of candidate causal isoforms at GWAS loci.

---

## 论文详细总结（自动生成）

这篇论文深入探讨了转录本注释对乳腺癌遗传调控分析的影响，以下是对该研究的结构化总结：

### 1. 核心问题与研究背景
*   **研究动机**：尽管已有超过 200 个遗传变异被证实与乳腺癌风险相关，但其背后的转录组机制仍不明确。
*   **核心痛点**：
    *   **基因级聚合的局限**：传统的 eQTL 和 TWAS 分析通常将表达量聚合在基因水平，掩盖了具有不同甚至拮抗功能的异构体（isoform）特有的调控效应。
    *   **短读长测序的歧义**：短读长 RNA-seq 在区分结构相似的异构体时存在映射歧义，导致定量不准。
    *   **注释滞后**：常用的 GENCODE 等参考注释是泛组织的，包含了大量在乳腺组织中不表达的“噪音”转录本，干扰了统计推断。
*   **整体含义**：研究旨在证明，利用长读长（Long-read）测序构建组织特异性的转录本组装，能显著提升识别乳腺癌因果异构体的特异性和准确性。

### 2. 核心方法论
*   **核心思想**：通过长读长数据定义“组织知情”的搜索空间，减少不相关转录本的干扰，并发现新的剪接变体。
*   **关键技术流程**：
    1.  **转录本组装**：利用 ESPRESSO 算法处理 PacBio 和 Oxford Nanopore 长读长数据，构建乳腺肿瘤、健康乳腺和成纤维细胞的去中心化组装。
    2.  **质量控制与分类**：使用 SQANTI3 结合正交证据（如 CAGE-seq 启动子、PolyA 位点）对异构体进行分类（如 FSM, NIC, NNC 等）和严格过滤。
    3.  **重定量**：使用 Salmon 软件，分别基于三种注释（GENCODE v45、LR 组装、Combined 组合注释）对大规模短读长样本进行表达量定量。
    4.  **遗传分析框架**：
        *   **eQTL 映射**：使用 QTLtools 进行顺式 eQTL 映射。
        *   **精细映射**：使用 SuSiE 识别 95% 置信变异集。
        *   **整合分析**：通过 coloc 进行共定位分析，利用 isoTWAS 框架进行异构体级转录组关联研究。

### 3. 实验设计
*   **数据集**：
    *   **长读长源**：26 个乳腺肿瘤样本、5 个健康乳腺样本、22 个成纤维细胞样本。
    *   **短读长定量样本**：TCGA（1,085 个乳腺肿瘤）、GTEx（363 个健康乳腺、483 个成纤维细胞）。
    *   **GWAS 数据**：来自 BCAC 联盟的总体乳腺癌及 5 种亚型（如 Luminal A, Triple-negative 等）的汇总统计数据。
*   **Benchmark（基准）**：以广泛使用的 **GENCODE v45** 作为标准参考注释。
*   **对比方案**：对比了“仅 GENCODE”、“仅长读长组装（LR）”以及“组合注释（Combined）”在 eQTL 发现率、GWAS 位点覆盖度及 TWAS 关联结果上的差异。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号、数量或总训练时长。
*   **软件环境**：提到了使用 R 语言环境及多种生物信息学工具（Salmon, QTLtools, SuSiE, isoTWAS 等），这些工具通常在高性能计算集群（HPC）的 CPU 节点上运行。

### 5. 实验数量与充分性
*   **实验规模**：
    *   涵盖了 3 种组织类型、3 种注释策略、6 种癌症表型。
    *   对数千个基因和数万个异构体进行了 eQTL 映射和精细映射。
    *   进行了 10,000 次置换检验（Permutation test）以验证 TWAS 结果的可靠性。
*   **充分性评价**：实验设计非常**充分且客观**。研究不仅对比了发现数量，还深入分析了不同注释下 lead eQTL 的一致性（LD 关系）以及预测模型的交叉验证 R²，确保了结论不是由统计偏差驱动的。

### 6. 主要结论与发现
*   **注释决定发现**：69% 的显著异构体-性状关联是特定于单一注释的。即使组合注释仅比 GENCODE 多出极少比例的新异构体，结果也会发生剧烈变化。
*   **精简即是力量**：长读长组装虽然异构体数量比 GENCODE 少 70-90%，但在捕捉 GWAS 风险位点方面的能力与之持平，且能提供更清晰的因果解释。
*   **识别新机制**：
    *   在 *MARK1* 位点，仅长读长注释识别出了与乳腺癌风险相关的特定异构体。
    *   在 *NUP107* 位点，优先排序出了一个此前未被注释的、受增强子调控的新剪接变体。
*   **定量敏感性**：异构体级别的定量对注释极其敏感，错误的注释会导致读段（reads）被错误分配，从而产生伪信号或掩盖真信号。

### 7. 优点与亮点
*   **视角独特**：首次系统性地证明了“转录本注释”本身就是一种关键的生物学假设，而不仅仅是技术参数。
*   **组织特异性强**：通过长读长技术解决了乳腺组织中特定剪接模式的识别问题。
*   **实用性高**：提供了一套改进异构体级 TWAS 的完整流程，并发布了乳腺癌相关的异构体调控目录。

### 8. 不足与局限
*   **长读长样本量较小**：尤其是健康乳腺组织的长读长样本较少，可能导致低丰度异构体的漏检。
*   **组织替代风险**：研究中使用成纤维细胞作为非恶性组织的补充，虽然有其生物学意义，但不能完全代表乳腺上皮细胞的调控环境。
*   **计算成本**：对大规模短读长数据集（如 TCGA）进行多种注释下的重定量和 eQTL 映射，计算资源消耗巨大，难以在所有实验室普及。
*   **应用限制**：目前仅针对乳腺癌进行了验证，其结论在其他复杂疾病中的普适性尚需进一步研究。

（完）
