---
title: Mapping kidney trait heritability to individual cells reals disease-specific remodeling of genetic risk architecture
title_zh: 将肾脏性状遗传力映射到单个细胞揭示了遗传风险架构的疾病特异性重塑
authors: "Hu, H."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.12.717976v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 应用单细胞疾病相关性评分来映射GWAS信号
tldr: 该研究构建了肾脏遗传疾病细胞图谱，利用单细胞疾病相关性评分（scDRS）将六种肾脏性状的GWAS信号映射到包含30万个细胞的单核RNA测序数据中，涵盖健康及AKI、DKD等多种病理状态。通过整合空间转录组学，研究揭示了遗传风险在不同疾病环境下发生的细胞类型特异性重塑，并据此确定了PDE4D等潜在治疗靶点，为理解肾脏疾病的遗传机制提供了重要资源。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-717976-v1/fig-001.webp\", \"caption\": \"Figure 3. Cell-type enrichment and cross-platform spatial validation. (a) Heatmap of mean scDRS enrichment scores across 16 cell types and 6 traits from the snRNA-seq atlas. Color intensity reflects mean norm_score; asterisks denote Bonferroni-adjusted P < 0.05. (b) Corresponding enrichment heatmap from Slide-seqV2 spatial transcriptomics data (920,088 beads, 44 pucks, 11 donors), showing concordant cell-type enrichment patterns. (c–h) Paired bar plots comparing the percentage of statistically significant cells (P < 0.05) between snRNA-seq (blue) and Slide-seqV2 (orange) for each of the six traits: (c) eGFR, (d) eGFRcys, (e) BUN, (f) T2D, (g) UACR, (h) IgAN. (i–n) Cross-platform scatter plots of mean scDRS scores per cell type for each trait: (i) eGFR (ρ = 0.89), (j) eGFRcys, (k) BUN, (l) T2D (ρ = 0.72), (m) UACR, (n) IgAN, with Spearman rank correlation coefficients indicated. (o–p) Slide-seqV2 spatial maps showing scDRS enrichment for all six traits in representative cortex (o) and medulla (p) pucks. Each row shows one trait; color scale reflects scDRS norm_score, with warmer colors indicating higher disease relevance. See Extended Data Figs. 3–4 for detailed enrichment statistics, L2 subtype analysis, and per-puck validation.\", \"page\": 15, \"index\": 1, \"width\": 943, \"height\": 950}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-717976-v1/fig-002.webp\", \"caption\": \"Figure 2. UMAP atlas overview and trait-specific scDRS enrichment. (a) UMAP embedding of 304,652 kidney cells colored by 16 major cell types (subclass L1). (b) UMAP colored by clinical condition (Ref, n = 107,701; AKI, n = 65,171; COV-AKI, n = 19,575; DKD, n = 67,628; H-CKD, n = 44,577). (c) UMAP colored by donor identity. (d–i) UMAP embeddings colored by scDRS norm_score for each of the six traits: (d) eGFR, (e) eGFRcys, (f) BUN, (g) T2D, (h) IgAN, (i) UACR, showing trait-specific enrichment patterns across cell types. See Extended Data Fig. 2a–e for detailed atlas views and condition-stratified visualizations.\", \"page\": 14, \"index\": 2, \"width\": 943, \"height\": 773}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-717976-v1/fig-003.webp\", \"caption\": \"Figure 1. Study design and integrative analysis pipeline for the Kidney Genetic Disease Cell Atlas. (a) Schematic overview of the pipeline: GWAS summary statistics for six kidney-related traits (eGFR, eGFRcys, BUN, UACR, T2D, IgAN) are processed through MAGMA v1.10 for gene-level association scoring. The top 1,000 genes per trait are input to scDRS v1.0.2, which computes disease relevance scores for each of the 304,652 cells in the Lake et al. kidney atlas across five clinical conditions (Ref, AKI, COV-AKI, DKD, H-CKD). Results are validated using Slide-seqV2 spatial transcriptomics (920,088 beads, 44 pucks). Downstream analyses include cell-type enrichment, condition-specific remodeling, gene-level correlation, GO enrichment, and druggable target nomination. (b) GWAS Manhattan-style summary plot showing the number of genome-wide significant loci per trait.\", \"page\": 13, \"index\": 3, \"width\": 943, \"height\": 927}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-12-717976-v1/fig-004.webp\", \"caption\": \"Figure 6. Disease-specific druggable target genes nominated by scDRS. (a) Rank shift waterfall plot for three prioritized druggable targets showing the magnitude of rank change from healthy reference to disease condition. Bar length represents the absolute rank shift; annotations show the reference and disease ranks with corresponding drug candidates. (b) Dumbbell plot showing the Spearman ρ correlation change from healthy reference (circle) to disease condition (diamond) for each target gene. Line length represents the magnitude of correlation shift. (c) Expression dot plot for PDE4D across 73 cell subtypes (L2) and five conditions. Dot size = percentage of cells expressing the gene; color = mean expression level. Disease-specific condition highlighted. PDE4D shows DKD-specific upregulation in PT segments and fibroblasts. Drug: PDE4 inhibitor (roflumilast). (d) Expression dot plot for ITGB6. COV-AKI-specific upregulation in proximal tubule and collecting duct cells. Drug: anti-αvβ6 mAb (STX-100/BG00011). (e) Expression dot plot for SPP1 (osteopontin). COV-AKI-specific broad upregulation across tubular, macrophage, and endothelial populations. Drug: anti-OPN antibody (in development). See Extended Data Fig. 13 for the full set of 10 druggable targets.\", \"page\": 20, \"index\": 4, \"width\": 943, \"height\": 965}]"
motivation: 旨在阐明GWAS发现的肾脏疾病遗传变异在特定细胞类型及不同疾病状态下的具体作用机制。
method: 利用scDRS算法将多种肾脏性状的遗传力映射到跨越五种临床条件的单核RNA-seq及空间转录组图谱上。
result: 发现遗传风险分布随疾病状态显著重塑，并识别出PDE4D、ITGB6和SPP1等具有临床潜力的疾病特异性治疗靶点。
conclusion: 该图谱为理解肾脏疾病遗传力的细胞基础提供了系统性框架，并为开发针对特定疾病状态的疗法指明了方向。
---

## 摘要
全基因组关联研究 (GWAS) 已鉴定出数百个与肾功能和疾病相关的遗传位点，但这些变异发挥作用的细胞类型特异性机制在很大程度上仍不清楚。在此，我们通过应用单细胞疾病相关性评分 (scDRS)，将六种肾脏相关性状——估算肾小球滤过率 (eGFR)、基于胱抑素 C 的 eGFR (eGFRcys)、血尿素氮 (BUN)、尿白蛋白/肌酐比值 (UACR)、2 型糖尿病 (T2D) 和 IgA 肾病 (IgAN)——的 GWAS 信号映射到包含 304,652 个肾脏细胞的综合单核 RNA-seq 图谱中，该图谱涵盖五种临床状况（健康对照、急性肾损伤 [AKI]、COVID-19 相关 AKI [COV-AKI]、糖尿病肾病 [DKD] 和高血压慢性肾脏病 [H-CKD]），从而构建了肾脏遗传疾病细胞图谱 (Kidney Genetic Disease Cell Atlas)。我们利用来自 44 个 puck 的 920,088 个珠子的 Slide-seqV2 空间转录组学数据验证了富集模式，证明了强大的跨平台一致性 (Spearman rho = 0.72-0.89)。疾病状况特异性分析揭示了跨细胞类型的遗传风险分布发生了剧烈重塑，其中成纤维细胞在 DKD 中获得了 T2D 富集 (Delta = +1.07)，而免疫细胞在所有状况下都主导了 IgAN 风险 (Cohen's d = 1.40)。基因水平的相关性分析识别出了特定状况下的分子程序，包括 eGFRcys 的线粒体基因主导地位以及 T2D/UACR 中 PDE4D 的出现。通过将 scDRS 排名变化与药物靶点数据库相结合，我们提名了三个高优先级治疗靶点：PDE4D（罗氟司特）、ITGB6 (STX-100) 和 SPP1（抗 OPN 抗体），每个靶点在不同的细胞群体中均显示出疾病特异性的上调。肾脏遗传疾病细胞图谱为理解肾脏疾病遗传力的细胞基础和识别特定状况下的治疗机会提供了资源。

## Abstract
Genome-wide association studies (GWAS) have identified hundreds of genetic loci associated with kidney function and disease, yet the cell-type-specific mechanisms through which these variants act remain largely unknown. Here, we construct the Kidney Genetic Disease Cell Atlas by applying single-cell disease relevance scoring (scDRS) to map GWAS signals for six kidney-related traits-estimated glomerular filtration rate (eGFR), cystatin C-based eGFR (eGFRcys), blood urea nitrogen (BUN), urinary albumin-to-creatinine ratio (UACR), type 2 diabetes (T2D), and IgA nephropathy (IgAN) onto a comprehensive single-nucleus RNA-seq atlas of 304,652 kidney cells spanning five clinical conditions (healthy reference, acute kidney injury [AKI], COVID-19-associated AKI [COV-AKI], diabetic kidney disease [DKD], and hypertensive chronic kidney disease [H-CKD]). We validate enrichment patterns using Slide-seqV2 spatial transcriptomics from 920,088 beads across 44 pucks, demonstrating strong cross-platform concordance (Spearman rho = 0.72-0.89). Disease-condition-specific analysis reveals dramatic remodeling of genetic risk distribution across cell types, with fibroblasts gaining T2D enrichment in DKD (Delta = +1.07) and immune cells dominating IgAN risk across all conditions (Cohens d = 1.40). Gene-level correlation analysis identifies condition-specific molecular programs, including mitochondrial gene dominance for eGFRcys and PDE4D emergence for T2D/UACR. By integrating scDRS rank shifts with druggability databases, we nominate three high-priority therapeutic targets-PDE4D (roflumilast), ITGB6 (STX-100), and SPP1 (anti-OPN antibody)-each showing disease-specific upregulation in distinct cell populations. The Kidney Genetic Disease Cell Atlas provides a resource for understanding the cellular basis of kidney disease heritability and identifying condition-specific therapeutic opportunities.

---

## 论文详细总结（自动生成）

这是一份关于论文《Mapping kidney trait heritability to individual cells reveals disease-specific remodeling of genetic risk architecture》的结构化分析报告：

### 1. 核心问题与整体含义
*   **核心问题**：全基因组关联研究（GWAS）虽然识别了大量与肾脏功能和疾病相关的遗传位点，但这些变异如何在**特定细胞类型**以及**不同疾病状态**（如糖尿病肾病、急性肾损伤）下发挥作用的机制尚不明确。
*   **整体含义**：本研究构建了“肾脏遗传疾病细胞图谱”（Kidney Genetic Disease Cell Atlas），旨在通过单细胞层面的遗传力映射，阐明遗传风险在疾病进程中如何发生“细胞重塑”，并据此发现新的治疗靶点。

### 2. 方法论
*   **核心思想**：利用**单细胞疾病相关性评分（scDRS）**算法，将群体水平的 GWAS 信号转化为单个细胞的疾病关联评分。
*   **关键技术流程**：
    1.  **GWAS 数据处理**：选取 6 种肾脏相关性状（eGFR, eGFRcys, BUN, UACR, T2D, IgAN），利用 MAGMA 软件将 SNP 关联转化为基因水平的关联评分。
    2.  **scDRS 评分**：选取每个性状关联度最高的前 1000 个基因，在单细胞转录组数据中计算每个细胞的疾病相关性得分。
    3.  **多维映射**：将评分映射到包含 30 万个细胞的单核 RNA 测序（snRNA-seq）图谱中，涵盖 5 种临床状态。
    4.  **空间验证**：利用 Slide-seqV2 空间转录组技术验证这些遗传信号在组织空间中的分布。
    5.  **靶点筛选**：结合药物数据库，通过分析疾病状态下 scDRS 排名显著变化的基因，提名潜在的治疗靶点。

### 3. 实验设计
*   **数据集**：
    *   **snRNA-seq**：来自 Lake 等人的肾脏图谱，包含 304,652 个细胞。
    *   **空间转录组**：Slide-seqV2 数据，包含 920,088 个珠子（beads），分布于 44 个切片（pucks）。
*   **临床场景**：涵盖健康对照（Ref）、急性肾损伤（AKI）、新冠相关 AKI（COV-AKI）、糖尿病肾病（DKD）和高血压慢性肾脏病（H-CKD）。
*   **对比方法**：
    *   **跨平台对比**：对比 snRNA-seq 与 Slide-seqV2 的富集一致性。
    *   **跨疾病对比**：对比同一细胞类型在健康与不同疾病状态下的遗传风险分布差异。

### 4. 资源与算力
*   论文中未明确说明具体的 GPU 型号、数量或训练时长。
*   **软件工具**：明确提到了使用 MAGMA v1.10 进行基因关联分析，以及 scDRS v1.0.2 进行单细胞评分计算。

### 5. 实验数量与充分性
*   **实验规模**：分析了超过 30 万个单细胞和 92 万个空间位点，涵盖 6 种性状和 5 种病理状态，数据量庞大。
*   **充分性**：
    *   **验证充分**：通过空间转录组学进行了独立的跨平台验证，Spearman 相关系数达到 0.72-0.89，证明了结果的稳健性。
    *   **维度全面**：不仅分析了细胞类型，还深入到了细胞亚型（L2 subtype）以及基因水平的贡献分析。
    *   **客观性**：通过 Bonferroni 校正等统计手段严格控制了假阳性。

### 6. 主要结论与发现
*   **遗传风险的细胞特异性**：如 eGFR 风险主要富集在近端小管（PT），而 IgAN 风险在所有状态下均由免疫细胞主导。
*   **疾病导致的风险重塑**：发现遗传风险分布并非固定。例如，在 DKD 状态下，成纤维细胞显著获得了 T2D 的遗传风险富集，暗示了间质细胞在糖尿病损伤中的遗传易感性。
*   **分子程序差异**：eGFRcys 的遗传力主要由线粒体基因驱动，而 T2D/UACR 则与 PDE4D 等基因密切相关。
*   **治疗靶点提名**：识别出 **PDE4D**（针对 DKD）、**ITGB6** 和 **SPP1**（针对 COV-AKI）作为高优先级药物靶点，并观察到它们在特定疾病细胞中的表达上调。

### 7. 优点
*   **动态视角**：突破了以往只研究健康组织遗传力的局限，揭示了疾病状态下遗传风险的动态重塑。
*   **多组学整合**：成功整合了 GWAS、单细胞转录组和空间转录组，提供了极高的空间分辨率和生物学解释力。
*   **临床转化潜力**：直接将遗传评分与药物靶点数据库挂钩，为精准医疗提供了具体候选药物（如罗氟司特）。

### 8. 不足与局限
*   **GWAS 偏差**：分析结果高度依赖于现有 GWAS 研究的质量和样本量，某些性状的信号可能不够强。
*   **转录组代理偏差**：scDRS 假设基因表达水平可以代表遗传效应，但忽略了蛋白质水平、翻译后修饰或非编码区的复杂调控机制。
*   **功能验证缺失**：研究主要基于计算推断和空间相关性，尚未在体外或动物模型中对提名的靶点（如 PDE4D 在 DKD 中的作用）进行功能性实验验证。

（完）
