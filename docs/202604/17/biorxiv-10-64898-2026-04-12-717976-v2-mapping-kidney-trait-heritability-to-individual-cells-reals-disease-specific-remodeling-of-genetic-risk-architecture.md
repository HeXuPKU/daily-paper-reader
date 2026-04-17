---
title: Mapping kidney trait heritability to individual cells reals disease-specific remodeling of genetic risk architecture
title_zh: 将肾脏性状遗传力映射到单个细胞揭示了遗传风险架构的疾病特异性重塑
authors: "Hu, H."
date: 2026-04-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.12.717976v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 将单细胞RNA测序与GWAS信号整合以映射疾病相关性
tldr: 该研究构建了肾脏遗传疾病细胞图谱，利用单细胞疾病相关性评分（scDRS）将6种肾脏性状的GWAS信号映射到包含30万个细胞的单细胞转录组中。研究涵盖健康及多种疾病状态，揭示了遗传风险在细胞类型间的动态重塑，并结合空间转录组学验证了结果。最终识别出特定疾病状态下的分子程序，并推荐了PDE4D等高优先级治疗靶点，为理解肾脏疾病的细胞遗传基础提供了重要资源。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-717976-v2/fig-001.webp\", \"caption\": \"Figure 3. Cell-type enrichment and cross-platform spatial validation. (a) Heatmap of mean scDRS enrichment scores across 16 cell types and 6 traits from the snRNA-seq atlas. Color intensity reflects mean norm_score; asterisks denote Bonferroni-adjusted P < 0.05. (b) Corresponding enrichment heatmap from Slide-seqV2 spatial transcriptomics data (920,088 beads, 44 pucks, 11 donors), showing concordant cell-type enrichment patterns. (c–h) Paired bar plots comparing the percentage of statistically significant cells (P < 0.05) between snRNA-seq (blue) and Slide-seqV2 (orange) for each of the six traits: (c) eGFR, (d) eGFRcys, (e) BUN, (f) T2D, (g) UACR, (h) IgAN. (i–n) Cross-platform scatter plots of mean scDRS scores per cell type for each trait: (i) eGFR (ρ = 0.89), (j) eGFRcys, (k) BUN, (l) T2D (ρ = 0.72), (m) UACR, (n) IgAN, with Spearman rank correlation coefficients indicated. (o–p) Slide-seqV2 spatial maps showing scDRS enrichment for all six traits in representative cortex (o) and medulla (p) pucks. Each row shows one trait; color scale reflects scDRS norm_score, with warmer colors indicating higher disease relevance. See Extended Data Figs. 3–4 for detailed enrichment statistics, L2 subtype analysis, and per-puck validation.\", \"page\": 15, \"index\": 1, \"width\": 943, \"height\": 984}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-717976-v2/fig-002.webp\", \"caption\": \"Figure 2. UMAP atlas overview and trait-specific scDRS enrichment. (a) UMAP embedding of 304,652 kidney cells colored by 16 major cell types (subclass L1). (b) UMAP colored by clinical condition (Ref, n = 107,701; AKI, n = 65,171; COV-AKI, n = 19,575; DKD, n = 67,628; H-CKD, n = 44,577). (c) UMAP colored by donor identity. (d–i) UMAP embeddings colored by scDRS norm_score for each of the six traits: (d) eGFR, (e) eGFRcys, (f) BUN, (g) T2D, (h) IgAN, (i) UACR, showing trait-specific enrichment patterns across cell types. See Extended Data Fig. 2a–e for detailed atlas views and condition-stratified visualizations.\", \"page\": 14, \"index\": 2, \"width\": 943, \"height\": 773}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-717976-v2/fig-003.webp\", \"caption\": \"Figure 6. Disease-specific druggable target genes nominated by scDRS. (a) Rank shift waterfall plot for three prioritized druggable targets showing the magnitude of rank change from healthy reference to disease condition. Bar length represents the absolute rank shift; annotations show the reference and disease ranks with corresponding drug candidates. (b) Dumbbell plot showing the Spearman ρ\", \"page\": 18, \"index\": 3, \"width\": 943, \"height\": 1004}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-717976-v2/fig-004.webp\", \"caption\": \"Figure 1. Study design and integrative analysis pipeline for the Kidney Genetic Disease Cell Atlas. (a) Schematic overview of the pipeline: GWAS summary statistics for six kidney-related traits (eGFR, eGFRcys, BUN, UACR, T2D, IgAN) are processed through MAGMA v1.10 for gene-level association scoring. The top 1,000 genes per trait are input to scDRS v1.0.2, which computes disease relevance scores for each of the 304,652 cells in the Lake et al. kidney atlas across five clinical conditions (Ref, AKI, COV-AKI, DKD, H-CKD). Results are validated using Slide-seqV2 spatial transcriptomics (920,088 beads, 44 pucks). Downstream analyses include cell-type enrichment, condition-specific remodeling, gene-level correlation, GO enrichment, and druggable target nomination. (b) GWAS Manhattan-style summary plot showing the number of genome-wide significant loci per trait.\", \"page\": 13, \"index\": 4, \"width\": 906, \"height\": 888}]"
motivation: 旨在阐明肾脏疾病相关遗传变异在特定细胞类型及不同疾病状态下的具体作用机制。
method: 利用scDRS技术将六种肾脏性状的GWAS数据整合到涵盖五种临床条件的单细胞及空间转录组图谱中进行分析。
result: 揭示了遗传风险在疾病状态下的细胞特异性重塑现象，并鉴定出PDE4D、ITGB6和SPP1等受疾病驱动的潜在治疗靶点。
conclusion: 该研究为理解肾脏疾病遗传力的细胞基础提供了系统性资源，并为开发针对特定疾病状态的疗法指明了方向。
---

## 摘要
全基因组关联研究 (GWAS) 已鉴定出数百个与肾功能和疾病相关的遗传位点，但这些变异发挥作用的细胞类型特异性机制在很大程度上仍不清楚。在此，我们通过应用单细胞疾病相关性评分 (scDRS)，将六种肾脏相关性状——估算肾小球滤过率 (eGFR)、基于胱抑素 C 的 eGFR (eGFRcys)、血尿素氮 (BUN)、尿白蛋白/肌酐比值 (UACR)、2 型糖尿病 (T2D) 和 IgA 肾病 (IgAN)——的 GWAS 信号映射到包含 304,652 个肾脏细胞的综合单核 RNA-seq 图谱中，从而构建了肾脏遗传疾病细胞图谱 (Kidney Genetic Disease Cell Atlas)。该图谱涵盖五种临床状况（健康对照、急性肾损伤 [AKI]、COVID-19 相关 AKI [COV-AKI]、糖尿病肾病 [DKD] 和高血压慢性肾脏病 [H-CKD]）。我们利用来自 44 个 puck 的 920,088 个珠子的 Slide-seqV2 空间转录组学数据验证了富集模式，证明了强大的跨平台一致性 (Spearman rho = 0.72-0.89)。疾病状况特异性分析揭示了跨细胞类型的遗传风险分布发生了剧烈重塑，其中成纤维细胞在 DKD 中获得了 T2D 富集 (Delta = +1.07)，而免疫细胞在所有状况下都主导了 IgAN 风险 (Cohen's d = 1.40)。基因水平的相关性分析识别出了特定状况下的分子程序，包括 eGFRcys 的线粒体基因主导地位以及 T2D/UACR 中 PDE4D 的出现。通过将 scDRS 排名变化与药物靶点数据库相结合，我们提名了三个高优先级治疗靶点：PDE4D（罗氟司特）、ITGB6 (STX-100) 和 SPP1（抗 OPN 抗体），每个靶点在不同的细胞群体中均显示出疾病特异性的上调。肾脏遗传疾病细胞图谱为理解肾脏疾病遗传力的细胞基础和识别特定状况下的治疗机会提供了资源。

## Abstract
Genome-wide association studies (GWAS) have identified hundreds of genetic loci associated with kidney function and disease, yet the cell-type-specific mechanisms through which these variants act remain largely unknown. Here, we construct the Kidney Genetic Disease Cell Atlas by applying single-cell disease relevance scoring (scDRS) to map GWAS signals for six kidney-related traits-estimated glomerular filtration rate (eGFR), cystatin C-based eGFR (eGFRcys), blood urea nitrogen (BUN), urinary albumin-to-creatinine ratio (UACR), type 2 diabetes (T2D), and IgA nephropathy (IgAN) onto a comprehensive single-nucleus RNA-seq atlas of 304,652 kidney cells spanning five clinical conditions (healthy reference, acute kidney injury [AKI], COVID-19-associated AKI [COV-AKI], diabetic kidney disease [DKD], and hypertensive chronic kidney disease [H-CKD]). We validate enrichment patterns using Slide-seqV2 spatial transcriptomics from 920,088 beads across 44 pucks, demonstrating strong cross-platform concordance (Spearman rho = 0.72-0.89). Disease-condition-specific analysis reveals dramatic remodeling of genetic risk distribution across cell types, with fibroblasts gaining T2D enrichment in DKD (Delta = +1.07) and immune cells dominating IgAN risk across all conditions (Cohens d = 1.40). Gene-level correlation analysis identifies condition-specific molecular programs, including mitochondrial gene dominance for eGFRcys and PDE4D emergence for T2D/UACR. By integrating scDRS rank shifts with druggability databases, we nominate three high-priority therapeutic targets-PDE4D (roflumilast), ITGB6 (STX-100), and SPP1 (anti-OPN antibody)-each showing disease-specific upregulation in distinct cell populations. The Kidney Genetic Disease Cell Atlas provides a resource for understanding the cellular basis of kidney disease heritability and identifying condition-specific therapeutic opportunities.

---

## 论文详细总结（自动生成）

### 论文结构化深度总结：将肾脏性状遗传力映射到单个细胞

#### 1. 核心问题与整体含义
全基因组关联研究（GWAS）虽然识别了大量与肾功能和疾病相关的遗传位点，但这些变异如何通过特定的**细胞类型**和**分子机制**影响疾病易感性，尤其是在不同疾病状态（如糖尿病、急性损伤）下这些遗传风险如何动态变化，仍是该领域的重大挑战。本研究旨在构建“肾脏遗传疾病细胞图谱”，通过整合大规模单细胞转录组、空间转录组与 GWAS 数据，系统性地解析肾脏性状遗传力的细胞基础及其在疾病中的重塑规律。

#### 2. 方法论
*   **核心思想**：利用单细胞疾病相关性评分（scDRS）框架，将群体水平的 GWAS 信号转化为单个细胞水平的疾病相关性度量。
*   **关键流程**：
    1.  **基因评分**：使用 MAGMA v1.10 对 6 种肾脏性状（eGFR, eGFRcys, BUN, UACR, T2D, IgAN）的 GWAS 摘要统计量进行处理，提取每种性状关联度最高的前 1000 个基因。
    2.  **单细胞评分**：应用 scDRS v1.0.2，通过评估这 1000 个基因在 30.4 万个单细胞中的聚合表达水平（相对于匹配的对照基因集），计算每个细胞的归一化疾病相关性分数（norm_score）。
    3.  **空间验证**：将 snRNA-seq 得到的富集模式与 Slide-seqV2 空间转录组数据进行交叉验证，确保细胞类型富集的解剖学准确性。
    4.  **靶点提名**：通过比较健康与疾病状态下基因-scDRS 相关性的排名变化（Rank Shift），结合药物数据库提名潜在治疗靶点。

#### 3. 实验设计
*   **数据集**：
    *   **单细胞图谱**：Lake et al. 提供的 304,652 个单核 RNA-seq 数据，涵盖 16 种主要细胞类型和 73 种亚型。
    *   **临床条件**：健康参考（Ref）、急性肾损伤（AKI）、COVID-19 相关 AKI、糖尿病肾病（DKD）、高血压慢性肾脏病（H-CKD）。
    *   **空间数据**：Slide-seqV2 数据，包含来自 11 个供体的 920,088 个珠子（44 个 pucks）。
*   **Benchmark 与对比**：
    *   对比了 snRNA-seq 与 Slide-seqV2 两个平台的一致性（Spearman ρ 达 0.72-0.89）。
    *   对比了不同肾脏性状（如肌酐基础的 eGFR vs 胱抑素 C 基础的 eGFRcys）的遗传架构差异。
    *   对比了健康状态与四种疾病状态下的遗传风险分布差异。

#### 4. 资源与算力
*   论文中**未明确说明**具体的硬件配置（如 GPU 型号、数量）及训练/计算的总时长。
*   软件层面使用了 Python 环境下的 Scanpy、scDRS、MAGMA 和 gseapy 等标准生物信息学工具。考虑到处理 30 万+细胞及 90 万+空间位点，该研究通常需要高性能计算集群（HPC）及大内存（256GB+ RAM）支持。

#### 5. 实验数量与充分性
*   **实验规模**：分析了 6 种性状、5 种临床条件、16 种大类细胞及 73 种亚型，实验维度非常全面。
*   **充分性**：研究不仅停留在细胞富集分析，还深入到了基因水平的相关性重组、GO 功能通路富集以及临床药物靶点的筛选。
*   **客观性**：通过独立的空间转录组数据集进行验证，极大地增强了结果的可信度；使用了 Bonferroni 校正等严格的统计手段处理多重比较问题。

#### 6. 主要结论与发现
*   **细胞特异性**：eGFR 遗传力主要富集在近端小管（PT），而 IgAN 风险由免疫细胞主导。
*   **疾病重塑**：疾病状态会显著改变遗传风险的细胞分布。例如，在 DKD 中，成纤维细胞获得了显著的 T2D 遗传风险富集；在 AKI 中，线粒体基因对 eGFRcys 的主导作用消失。
*   **分子程序重组**：识别出 PDE4D 是 T2D 和 UACR 共同的顶端相关基因，且在 DKD 状态下其相关性排名剧烈上升。
*   **治疗靶点**：提名了 **PDE4D**（罗氟司特）、**ITGB6**（STX-100）和 **SPP1**（抗 OPN 抗体）作为具有疾病特异性潜力的治疗靶点。

#### 7. 优点
*   **高分辨率**：将遗传风险从“组织/细胞类型”提升到了“单个细胞”和“空间位点”级别。
*   **动态视角**：打破了以往只研究健康组织的局限，揭示了疾病微环境如何“激活”或“放大”特定的遗传风险。
*   **转化价值**：通过 Rank Shift 分析直接对接现有药物数据库，为老药新用和新药研发提供了精准的细胞靶向建议。

#### 8. 不足与局限
*   **空间数据局限**：空间验证仅使用了健康组织，缺乏疾病状态下的空间转录组对比。
*   **样本量偏差**：某些疾病条件（如 COV-AKI）的细胞数量远少于健康对照，可能影响统计效能。
*   **模型假设**：scDRS 主要捕捉线性表达相关性，可能忽略非线性相互作用或表观遗传调控的影响。
*   **验证缺失**：提名的药物靶点仅基于计算推断，尚未在动物模型或类器官中进行功能性实验验证。

（完）
