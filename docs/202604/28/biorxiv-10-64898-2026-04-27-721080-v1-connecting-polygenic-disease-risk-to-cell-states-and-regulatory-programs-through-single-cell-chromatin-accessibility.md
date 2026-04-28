---
title: Connecting polygenic disease risk to cell states and regulatory programs through single-cell chromatin accessibility
title_zh: 通过单细胞染色质开放性将多基因疾病风险与细胞状态和调控程序联系起来
authors: "Yu, L., Deary, L. T., Liu, Q., Zhang, Q., Zhao, S."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.27.721080v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 将GWAS摘要统计数据与单细胞染色质可及性数据整合
tldr: 本研究开发了SCADS计算框架，旨在通过整合单细胞染色质可及性数据（scATAC-seq）与全基因组关联分析（GWAS）数据，精准识别与多基因疾病相关的细胞状态。SCADS利用主题模型识别共调控区域并量化其遗传富集程度，从而计算细胞层面的疾病评分。该方法在模拟和实际应用中均优于现有工具，揭示了自身免疫性疾病中免疫细胞和上皮细胞的异质性，为理解非编码调控变异如何影响细胞功能提供了有力工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决如何将复杂的遗传风险信号精准映射到特定的细胞状态及其背后的非编码调控程序这一难题。
method: 开发了SCADS框架，通过主题模型识别染色质共调控区域，并结合GWAS富集分析计算细胞特异性疾病评分。
result: SCADS在性能上超越了现有方法，并成功揭示了炎症性肠病在CD8+ T细胞和结肠上皮细胞中的细胞异质性及关键基因程序。
conclusion: SCADS是一个可扩展且可解释的模块化框架，为连接非编码遗传变异与细胞身份及功能提供了通用方案。
---

## 摘要
单细胞 ATAC 测序能够实现细胞状态及其推断的调控元件的高分辨率映射。全基因组关联研究 (GWAS) 信号在特定背景调控区域内的富集可以揭示与疾病相关的细胞群体。我们提出了单细胞 ATAC-seq 疾病评分 (SCADS)，这是一个整合了 GWAS 汇总统计数据与 scATAC-seq 数据以优先排序疾病相关细胞的计算框架。SCADS 通过以下方式生成经过校准的、在数据集和性状之间具有可比性的细胞级评分：(i) 通过主题建模识别染色质共调控区域，(ii) 量化其多基因 GWAS 富集程度，以及 (iii) 根据主题权重和富集水平计算细胞特异性疾病评分。在广泛的模拟实验中，SCADS 在控制假阳性的同时，在效能上优于现有方法。应用于多种自身免疫性状时，SCADS 揭示了经典免疫细胞类型内部在疾病相关性方面存在的显著异质性。我们专门研究了炎症性肠病在 CD8+ T 细胞和结肠上皮细胞内部的差异化疾病相关性，并精准定位了潜在的基因程序和变异。SCADS 具有可扩展性、可解释性和模块化特点，为将非编码调控变异与细胞身份及功能联系起来提供了一个通用框架。

## Abstract
Single-cell ATAC-sequencing enables high-resolution mapping of cell states and their putative regulatory elements. The enrichment of genome-wide association study (GWAS) signals within context-specific regulatory regions can reveal disease-relevant cell populations. We present Single-Cell ATAC-seq Disease Score (SCADS), a computational framework that integrates GWAS summary statistics with scATAC-seq data to prioritize disease-relevant cells. SCADS produces calibrated, cell-level scores that are comparable across datasets and traits by: (i) identifying chromatin co-regulatory regions via topic modeling, (ii) quantifying their polygenic GWAS enrichment, and (iii) calculating cell-specific disease scores from topic weights and enrichment levels. Across extensive simulations, SCADS outperforms existing methods in power while controlling false positives. Applied to multiple autoimmune traits, SCADS reveals marked heterogeneity in disease relevance within canonical immune cell types. We specifically studied the differential disease relevance within CD8+ T and colon epithelial cells for inflammatory bowel disease, and pinpointed underlying gene programs and variants. SCADS is scalable, interpretable, and modular, providing a general framework to connect noncoding regulatory variation to cellular identity and function.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **SCADS**（Single-Cell ATAC-seq Disease Score）的计算框架，旨在通过整合单细胞染色质开放性数据（scATAC-seq）与全基因组关联分析（GWAS）汇总统计数据，在单细胞分辨率下评估疾病的遗传风险。

以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：大多数复杂疾病的风险变异位于非编码调控区域，且具有高度的细胞类型特异性。虽然 scATAC-seq 提供了高分辨率的调控图谱，但其数据极其**稀疏**（单个细胞仅能捕获 1%-10% 的开放区域），导致难以直接在单细胞层面准确评估 GWAS 信号的富集程度。
*   **研究动机**：现有的方法（如 SCAVENGE 或 g-chromVAR）要么依赖于少数精细映射的变异，要么无法充分利用复杂性状的多基因架构，且缺乏标准化的不确定性度量。SCADS 旨在克服稀疏性，提供可校准、可解释且跨数据集可比的单细胞疾病评分。

### 2. 方法论
*   **核心思想**：利用**主题模型（Topic Modeling）**将稀疏的单细胞数据投影到低维的“共调控程序”空间，在主题层面评估遗传富集，再重构回细胞层面的评分。
*   **关键流程**：
    1.  **主题建模**：使用 `fastTopics` 对 scATAC-seq 计数矩阵进行分解，识别出代表共调控基因组区域的“主题”（Topics）以及每个细胞在这些主题上的权重（Loadings）。
    2.  **主题富集分析**：将每个主题识别出的开放区域作为功能注释，利用分层连锁不平衡得分回归（**S-LDSC**）计算该主题对特定 GWAS 性状的遗传力富集程度（$e_k$）。
    3.  **细胞评分重构**：结合细胞的主题权重和各主题的富集水平，计算细胞级疾病评分（$c_i$），并推导其方差和 p 值。
    4.  **下游分析**：利用主题注释进行功能知情的变异精细映射（Fine-mapping），并分析变异可及性与疾病评分的相关性。

### 3. 实验设计
*   **数据集**：
    *   **模拟数据**：基于 5 种血细胞类型的真实 scATAC-seq 谱图和 UK Biobank（45K 样本）的基因型数据模拟复杂性状。
    *   **真实数据**：人类造血系统（23 种细胞类型）、结肠上皮细胞数据。
*   **Benchmark 与对比方法**：
    *   对比了 **SCAVENGE**（基于网络传播的方法）和 **g-chromVAR**（基于变异加权的方法）。
    *   评估指标包括：与真实富集值的相关性（Spearman $r$）、识别目标细胞的准确率（AUROC）、假阳性控制（Null simulations）。

### 4. 资源与算力
*   论文中**未明确说明**具体的硬件型号（如 GPU 数量）或具体的训练时长。
*   但文中强调了 SCADS 的**可扩展性（Scalable）**，提到使用了 `fastTopics` 这一高效算法，能够处理大规模单细胞数据集。

### 5. 实验数量与充分性
*   **实验设置**：
    *   **模拟实验**：涵盖了不同的遗传架构（高多基因性 vs. 低多基因性）、不同的富集倍数（10x, 20x）以及空假设模拟（Null simulations）。
    *   **真实应用**：应用于 8 种自身免疫性疾病（如 IBD、RA、SLE 等）和单核细胞计数性状。
*   **充分性评价**：实验设计较为充分。通过模拟实验验证了方法在处理多基因信号时的鲁棒性，通过真实数据展示了其在发现细胞异质性（如 CD8+ T 细胞内部梯度）和识别关键调控变异（如 *RNF186* 相关的 rs7553638）方面的能力。

### 6. 主要结论与发现
*   **性能优越**：在模拟实验中，SCADS 在捕捉多基因信号方面显著优于 SCAVENGE，尤其是在高多基因性场景下。
*   **揭示异质性**：在自身免疫性疾病中，SCADS 发现即使在同一种免疫细胞（如 CD8+ T 细胞）内部，疾病相关性也存在显著梯度。
*   **生物学发现**：
    *   在 **IBD** 研究中，识别出 *ETS1* 和 *TCF7* 调控网络是 CD8+ T 细胞参与疾病的关键。
    *   在结肠上皮中，发现成熟肠细胞（Enterocytes）比干细胞对 IBD 更具遗传敏感性，并实验验证了变异 **rs7553638** 通过调节 ***RNF186*** 表达影响肠道屏障功能。

### 7. 优点
*   **克服稀疏性**：通过主题模型聚合信号，有效解决了单细胞数据的噪声和稀疏问题。
*   **统计严谨**：提供了校准的 p 值和方差，使得评分在不同性状和数据集之间具有统计学上的可比性。
*   **可解释性强**：将疾病风险直接联系到具体的调控程序（主题）和转录因子基序（Motifs）。
*   **模块化**：可以灵活更换底层的主题模型或富集分析工具。

### 8. 不足与局限
*   **批次效应**：目前的模型尚未直接整合批次效应校正，在处理跨实验的大规模整合数据时可能存在偏差。
*   **依赖 GWAS 效能**：作为基于 S-LDSC 的方法，其准确性高度依赖于 GWAS 汇总统计数据的质量和样本量。
*   **计算复杂性**：虽然使用了快速算法，但相比于简单的加权评分，主题建模和 S-LDSC 的组合流程在计算步骤上更为复杂。
*   **物种限制**：目前主要针对人类数据，虽然提到未来可能利用小鼠数据，但跨物种调控景观的差异仍是挑战。

（完）
