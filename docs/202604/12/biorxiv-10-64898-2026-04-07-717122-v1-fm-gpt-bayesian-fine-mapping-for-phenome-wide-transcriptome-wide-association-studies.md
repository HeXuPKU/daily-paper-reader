---
title: "FM-GPT: Bayesian fine mapping for phenome-wide transcriptome-wide association studies"
title_zh: FM-GPT：全表型组全转录组关联研究的贝叶斯精细映射
authors: "Canida, T., Ye, Z., Wang, S.-H., Huang, H.-H., Pan, Y., Liang, M., Chen, S., Ma, T."
date: 2026-04-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.07.717122v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 全表型组转录组关联研究的贝叶斯精细映射
tldr: FM-GPT 是一种新型贝叶斯精细映射方法，旨在解决全表型组转录组关联研究（Phe-TWAS）中因连锁不平衡导致的伪信号问题。该方法支持多种类型的关联表型，通过基因引导的降维技术识别具有多效性或表型特异性的因果基因。在 UK Biobank 的脑部 MRI 和临床表型数据应用中，FM-GPT 成功缩小了候选基因范围，揭示了免疫与代谢功能之间的基因调节权衡，为理解复杂基因-表型关系提供了强有力的工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-07-717122-v1/fig-001.webp\", \"caption\": \"Figure 3. Simulation results for scenario 2 with heterogeneous causality. (A) AUCs of all methods with varying number of factors for both continuous phenotypes only and phenotypes of mixed data types. (B) AUCs of all methods with varying heritability levels for both continuous phenotypes only and phenotypes of mixed data types. (C) Number of true positives vs false positives detected by all methods at same FDR cutoff (0.1) with varying number of factors for both continuous phenotypes only and phenotypes of mixed data types. (D) Number of true positives vs false positives detected by all methods at same FDR cutoff (0.1) with varying heritability levels for both continuous phenotypes only and phenotypes of mixed data types. *mvSuSIE is removed from mixed outcome plots as they cannot handle mixed data types.\", \"page\": 21, \"index\": 1, \"width\": 1037, \"height\": 593}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-07-717122-v1/fig-002.webp\", \"caption\": \"Fig 4. TWAS and fine mapping results for genetic study of 66 regional cortical thickness (CT) measures from UKB. (A) The Phenotypic correlation of the 66 regional CT measures; (B) 3D Manhattan plot of TWAS p-values (most significant genomic regions highlighted); (C) Proportion of regions that harbor different number of causal genes by different methods; (D) Manhattan plot of meta-TWAS Fisher’s method p-values and the putative causal genes identified by each fine mapping method; (E) Brain regions with the largest factor loadings; (F) Pathway enrichment analysis on FM-GPT selected genes results (p<0.05).\", \"page\": 22, \"index\": 2, \"width\": 1062, \"height\": 1056}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-07-717122-v1/fig-003.webp\", \"caption\": \"Figure 1. (A) A schematic overview of the FM-GPT method. (B) A directed acyclic graph (DAG) of the FM-GPT method. (C) Demonstration of phenome-wide TWAS results, highlighted regions are where we will apply fine mapping. (D-E) Main outputs from the FM-GPT method: the putatively causal genes for the phenotype factors (D); the loadings of phenotypes on each phenotype factor (E).\", \"page\": 18, \"index\": 3, \"width\": 1041, \"height\": 579}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-07-717122-v1/fig-004.webp\", \"caption\": \"Table 2. Summary of fine mapping results for the 355 regions by different methods in the cortical thickness example\", \"page\": 23, \"index\": 4, \"width\": 980, \"height\": 1302}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-07-717122-v1/fig-005.webp\", \"caption\": \"Table 1. A comparison of main characteristics of representative GWAS/TWAS fine mapping methods/tools\", \"page\": 19, \"index\": 5, \"width\": 978, \"height\": 1348}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-07-717122-v1/fig-006.webp\", \"caption\": \"Fig 5. TWAS and fine mapping results for genetic study of EHR-derived phenotypes from UKB. (A) 3D Manhattan plot of TWAS p-values (most significant genomic regions highlighted); (B) The Phenotypic correlation of the 39 EHR-derived medical conditions; (C) Manhattan plot of meta-TWAS Fisher’s pvalues and the putative causal genes identified by each fine mapping method; (D) Pathway enrichment analysis on FM-GPT selected genes results (p<0.05); (E) Heatmap of identified putative causal genes and the loadings of phenotypes they target at.\", \"page\": 24, \"index\": 6, \"width\": 1087, \"height\": 1031}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-07-717122-v1/fig-007.webp\", \"caption\": \"Figure 2. Simulation results for scenario 1 with homogeneous causality. (A) AUCs of all methods with varying number of factors for both continuous phenotypes only and phenotypes of mixed data types. (B) AUCs of all methods with varying heritability levels for both continuous phenotypes only and phenotypes of mixed data types. (C) Number of true positives vs false positives detected by all methods at same FDR cutoff (0.1) with varying number of factors for both continuous phenotypes only and phenotypes of mixed data types. (D) Number of true positives vs false positives detected by all methods at same FDR cutoff (0.1) with varying heritability levels for both continuous phenotypes only and phenotypes of mixed data types. *mvSuSIE is removed from mixed outcome plots as they cannot handle mixed data types.\", \"page\": 20, \"index\": 7, \"width\": 1026, \"height\": 587}]"
motivation: 传统的 TWAS 易受连锁不平衡干扰产生伪信号，且现有方法难以处理大规模表型组研究中多表型间的复杂相关性。
method: 提出 FM-GPT 贝叶斯框架，利用基因引导的降维技术对多种混合类型的相关表型进行联合精细映射。
result: 模拟实验证明 FM-GPT 在识别因果基因的准确性上优于现有方法，并在 UK Biobank 数据中定位了影响皮层厚度和多系统疾病的关键多效性基因。
conclusion: FM-GPT 有效揭示了跨表型的共享生物学机制，为大规模表型组研究中的因果基因识别和共病研究提供了新途径。
---

## 摘要
全转录组关联研究 (TWAS) 将全基因组关联研究与表达定量性状位点参考面板相结合，以识别与感兴趣性状相关的基因。然而，连锁不平衡和相关的基因表达可能诱发伪 TWAS 信号，这促使精细映射方法在相关位点内优先排序推定的致病基因。大规模表型组资源（如电子健康档案 (EHR)）的快速增长，已将遗传研究从单性状分析转向联合评估许多密切相关表型的全表型组调查。我们介绍了 FM-GPT（全表型组全转录组关联研究致病基因精细映射），这是一种新型贝叶斯精细映射方法，用于在全表型组 TWAS 中，针对具有潜在混合结局类型（如二元、计数或连续型）的多个相关表型，对致病基因进行优先排序。FM-GPT 对表型进行基因引导的降维，并揭示所识别基因的多效性或表型特异性效应。在模拟实验中，FM-GPT 在控制假阳性的同时，比其他精细映射方法更准确地识别了真实的致病基因。我们将 FM-GPT 应用于使用英国生物样本库 (UK Biobank) 数据的两个案例：一项针对 MRI 衍生的区域皮层厚度测量的全脑遗传分析，以及一项针对 EHR 数据衍生的临床表型的全表型组遗传分析。FM-GPT 大大缩小了推定致病基因的集合规模，并识别出：1. 对整个大脑皮层的区域皮层厚度具有多效性影响的基因，包括 17 号染色体上调节神经元形态和皮层组织的五个基因 BCAS3、LRRC37A、NOS2P3、ARL17B 和 UBB；2. 影响循环、代谢、消化、呼吸和泌尿生殖系统多种疾病的基因，揭示了这些疾病之间两个主要的变异轴，指向免疫和代谢功能之间基因调节的潜在权衡。这些结果突显了 FM-GPT 在大规模全表型组研究中解开复杂基因-表型关系的能力，揭示了不同人类性状之间共享的生物学机制，并推进了转化医学和共病研究。

## Abstract
Transcriptome-wide association studies (TWAS) integrate genome wide association studies with expression quantitative trait locus reference panels to identify genes associated with traits of interest. However, linkage disequilibrium and correlated gene expression can induce spurious TWAS signals, motivating fine mapping methods to prioritize putatively causal genes within associated loci. The rapid growth of large-scale phenomic resources (e.g. electronic health records (EHRs)) has shifted genetic studies from single-trait analyses to phenome-wide investigations that jointly evaluate many closely related phenotypes. We introduce FM-GPT (Fine-mapping of causal Genes for Phenome-wide Transcriptome-wide association studies), a novel Bayesian fine mapping method for prioritizing causal genes across multiple correlated phenotypes with potentially mixed outcome types (e.g., binary, count or continuous) in phenome-wide TWAS. FM-GPT performs gene-guided dimension reduction of the phenotypes and reveals pleiotropic or phenotype-specific effects of the identified genes. In simulations, FM-GPT identified true causal genes more accurately than other fine mapping methods while controlling false positives. We applied FM-GPT to two applications using data from UK Biobank: a brain-wide genetic analysis of MRI data derived regional cortical thickness measures and a phenome-wide genetic analysis of clinical phenotypes derived from EHR data. FM-GPT greatly narrowed down the set size of putatively causal genes and identified: 1. genes with pleiotropic effects on regional cortical thickness across the cerebral cortex, including five genes BCAS3, LRRC37A, NOS2P3, ARL17B and UBB on chromosome 17 regulating neuronal morphology and cortical organization; and 2. genes that influence multiple medical conditions across the circulatory, metabolic, digestive, respiratory and genitourinary systems, revealing two major axes of variation among these conditions that point to a potential trade-off in gene regulation between immune and metabolic functions. These results highlight FM-GPT's power to disentangle complex gene-phenotype relationships in large-scale phenome-wide studies, uncovering shared biological mechanisms across diverse human traits and advancing translational and comorbidity research.

---

## 论文详细总结（自动生成）

以下是对论文《FM-GPT: Bayesian fine mapping for phenome-wide transcriptome-wide association studies》的深度结构化总结：

### 1. 论文的核心问题与整体含义
*   **核心问题**：全转录组关联研究（TWAS）虽然能识别与性状相关的基因，但由于**连锁不平衡（LD）**和基因表达的相关性，容易产生大量的伪信号（假阳性）。此外，随着生物样本库（如 UK Biobank）的发展，研究已转向**全表型组（Phenome-wide）**分析，如何从成百上千个相关的表型（且包含连续型、二元型等混合类型）中精准定位真正的致病基因，是当前遗传学研究的重大挑战。
*   **整体含义**：FM-GPT 旨在提供一个统一的贝叶斯框架，通过整合多表型信息来提高精细映射（Fine-mapping）的准确性，从而在复杂的基因-表型网络中识别具有多效性（Pleiotropic）或特异性的致病基因。

### 2. 论文提出的方法论
*   **核心思想**：采用**基因引导的降维技术**（Gene-guided dimension reduction）。FM-GPT 不直接建立基因与每个表型的关联，而是假设多个表型受潜在的“表型因子”（Latent Factors）驱动，而基因通过影响这些因子来作用于多个表型。
*   **关键技术细节**：
    *   **贝叶斯潜在因子模型**：将观测到的多种表型分解为潜在因子和负荷矩阵（Loadings）。
    *   **处理混合数据类型**：通过引入潜在变量（Latent Variable）机制，使模型能够同时处理连续型（如身高）、二元型（如患病与否）和计数型数据。
    *   **变量选择**：在基因到因子的映射上使用“刺突与平板”先验（Spike-and-slab priors），实现稀疏性建模，从而识别关键致病基因。
    *   **输出指标**：计算每个基因的后验包含概率（PIP），用于衡量其作为致病基因的可能性。

### 3. 实验设计
*   **数据集与场景**：
    1.  **模拟实验**：设置了同质因果关系（所有表型受相同基因影响）和异质因果关系（不同因子受不同基因影响）两种场景，并测试了纯连续型和混合型数据。
    2.  **脑部 MRI 数据**：分析 UK Biobank 中 66 个区域的皮层厚度（CT）测量值。
    3.  **临床 EHR 数据**：分析 UK Biobank 中由电子健康档案衍生的 39 种临床疾病（PheCodes）。
*   **Benchmark（对比方法）**：
    *   **FOCUS**：经典的单表型 TWAS 精细映射方法。
    *   **SuSiE / mvSuSIE**：基于加性模型的精细映射方法（mvSuSIE 仅限连续型数据）。
    *   **Meta-TWAS (Fisher's method)**：传统的元分析方法。

### 4. 资源与算力
*   **说明**：论文中**未明确指出**具体的 GPU 型号、数量或具体的训练时长。
*   **推断**：由于该方法基于贝叶斯推断（可能涉及 MCMC 或变分推断），其计算复杂度通常高于简单的线性回归，但通过降维技术（因子模型）有效地控制了在大规模表型组数据上的计算负担。

### 5. 实验数量与充分性
*   **实验规模**：
    *   模拟实验涵盖了不同的遗传力（Heritability）水平、因子数量和数据类型组合，进行了多次重复以评估 AUC 和假发现率（FDR）。
    *   真实数据应用涵盖了成像遗传学（MRI）和临床流行病学（EHR）两个完全不同的领域。
*   **充分性评价**：实验设计较为充分且客观。通过与单表型方法和现有的多表型方法对比，证明了 FM-GPT 在处理相关表型时的优越性，尤其是在控制假阳性和处理非连续型数据方面。

### 6. 论文的主要结论与发现
*   **性能优越性**：在所有模拟场景中，FM-GPT 的 AUC 均优于对比方法，且在混合数据类型下表现尤为稳健。
*   **生物学发现（脑部）**：在 17 号染色体上识别出 5 个关键基因（如 *BCAS3*, *LRRC37A* 等），这些基因对全脑皮层厚度具有广泛的多效性影响，涉及神经元形态调节。
*   **生物学发现（临床）**：揭示了免疫功能与代谢功能之间的“基因调节权衡”。例如，某些基因（如 *FADS1/2*）在促进代谢性状的同时可能对循环系统疾病有不同方向的影响。
*   **精简候选基因**：FM-GPT 显著缩小了 TWAS 显著区域内的候选基因范围，提高了定位的精准度。

### 7. 优点
*   **多功能性**：是少数能同时处理**混合结局类型**（连续+二元）的精细映射工具。
*   **降维优势**：通过潜在因子模型捕捉表型间的共性，有效解决了全表型组研究中的高维数和共线性问题。
*   **可解释性强**：不仅能识别基因，还能通过因子负荷解释基因如何影响特定的表型群组。

### 8. 不足与局限
*   **模型假设限制**：该方法依赖于“因子结构”的假设，如果表型之间完全独立或关联极其微弱，该方法的优势可能无法体现。
*   **计算成本**：尽管进行了优化，但贝叶斯框架在处理数万个基因和数千个表型的极大规模组合时，计算资源消耗仍可能高于简单的频率派方法。
*   **参考面板依赖**：与所有 TWAS 方法一样，其准确性高度依赖于外部 eQTL 参考面板（如 GTEx）的质量和组织特异性。

（完）
