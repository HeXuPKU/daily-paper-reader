---
title: "Modeling cis-regulatory variation in human brain enhancers across a large Parkinson's Disease cohort"
title_zh: 在大型帕金森病队列中对人脑增强子的顺式调节变异进行建模
authors: "Sigalova, O. M., Pancikova, A., De Man, J., Theunis, K., Hulselmans, G. J., Konstantakos, V., Stuyven, B., De Brabandere, A., Geurts, J., Mikorska, A., Mukherjee, S., Abouelasrar Salama, S., Vandereyken, K., Davie, K., Mahieu, L., Adler, C. H., Beach, T. G., Serrano, G. E., Voet, T., Demeulemeester, J., Aerts, S."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.15.711881v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 将功能多组学与 GWAS 位点整合以破译帕金森病风险
tldr: "该研究通过对190名帕金森病患者及对照者的脑样本进行大规模单细胞多组学和长读长全基因组测序，构建了顺式调控变异图谱。研究识别出53,841个调节细胞类型特异性增强子可及性的遗传变异，并利用序列到功能的深度学习模型预测其影响，揭示了变异如何通过破坏转录因子结合位点影响基因表达。该成果为解释PD非编码区风险位点提供了重要资源和建模策略。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-15-711881-v2/fig-001.webp\", \"caption\": \"Figure 2: Single-cell multiomic atlases of substantia nigra and cingulate cortex. A,B. UMAPs of substantia nigra single nuclei gene expression (A) and chromatin accessibility (B) colored by cell type. C,D. UMAPs of cingulate cortex single nuclei gene expression (C) and chromatin accessibility (D) colored by cell type. E. Average gene expression of select marker genes in substantia nigra cell types. F. Pseudobulk\", \"page\": 6, \"index\": 1, \"width\": 993, \"height\": 1197}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-15-711881-v2/fig-002.webp\", \"caption\": \"Figure 5. CREsted models increase power of variant discovery. A. Number of cells per cell type vs. the number of variants with absolute crested prediction logFC > 0.2. B. CREsted absolute logFC for all peaks stratified by whether or not the peak contained the caQTL-ASCA variant. C-D. Rank plot of average allelic imbalances (C) and caQTL slopes (D) for top peaks ranked by CREsted logFC (dark blue) vs. same number of randomly selected peaks (light blue).\", \"page\": 13, \"index\": 2, \"width\": 1040, \"height\": 296}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-15-711881-v2/fig-003.webp\", \"caption\": \"Figure 1: Long-read whole-genome sequencing of 180 post-mortem brains. A. Overview of donor cohort and experimental set-up. B. Donor age distribution stratified by PD status and sex. C,D. Wholegenome coverage (C) and mean aligned read length (D) stratified by sequencing chemistry and method. E.\", \"page\": 4, \"index\": 3, \"width\": 952, \"height\": 1252}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-15-711881-v2/fig-004.webp\", \"caption\": \"Figure 7. Regulatory variation at PD GWAS loci. A. Barplot of the number of PD GWAS loci (n=150) containing caQTL-ASCA variants; also predicted by CREsted; also an eQTL; or all of the above. B. Genes\", \"page\": 19, \"index\": 4, \"width\": 1104, \"height\": 1287}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-15-711881-v2/fig-005.webp\", \"caption\": \"Figure 6. Linking regulatory variation to gene expression changes. A. Agreement between eQTL and caQTL slope for the overlap of the caQTL-ASCA variant call set with eQTLs with FDR < 0.05. B. Share of concordant (eQTL vs. caQTL slope) ASCA-caQTL callset variants overlapping with eQTL variants at different eQTL FDR adjusted p-values. C. Spearman correlation between the caQTL and eQTL slopes of ASCA/caQTL call set variants overlapping with eQTL variants thresholded at different FDR-adjusted pvalues. D. Table with Crested logFC, allelic imbalance, caQTL slope, and eQTL slope for KCNMA1 in all cell types tested for variant chr10:78,424,792 (T/A). Effect sizes in Micro-PVM in SN and CC are highlighted.\", \"page\": 16, \"index\": 5, \"width\": 1038, \"height\": 1116}]"
motivation: 旨在解析帕金森病相关非编码基因组变异如何通过影响细胞类型特异性增强子功能来调节基因表达。
method: 整合190名受试者脑组织的单细胞多组学数据与长读长测序，结合QTL分析及序列到功能的深度学习建模。
result: 鉴定了5万余个调节增强子可及性的顺式变异，并发现其主要通过在特定细胞类型中破坏转录因子结合位点发挥作用。
conclusion: 该研究建立了理解人脑功能性非编码变异的独特资源，并为优先筛选帕金森病风险位点提供了有效的计算建模策略。
---

## 摘要
全基因组关联研究 (GWAS) 已将一百多个非编码基因组位点与帕金森病 (PD) 风险联系起来。破译这些位点对基因调控的功能影响，需要具备细胞类型感知能力的建模方法，以评估序列变异对增强子功能和靶基因表达的影响。为应对这一挑战，我们生成了一个来自 190 名人类捐赠者（115 名对照组和 75 名 PD 患者）的综合匹配数据集，包括长读长全基因组测序以及前扣带回皮层和黑质的单核多组学图谱（分别包含 310 万和 110 万个细胞核的 snATAC-seq 和 snRNA-seq）。通过整合染色质可及性数量性状位点 (caQTL)、DNA 甲基化 QTL (meQTL) 和等位基因特异性染色质可及性 (ASCA)，我们鉴定了 53,841 个高置信度顺式作用遗传变异，这些变异在一个或两个脑区中调节细胞类型特异性的增强子可及性。随后，我们证明了“序列到功能”模型可以直接从基因组序列中准确预测这些变异的影响。新型可解释性方法允许根据调节功能对这些变异进行分层，其中大多数变异以细胞类型特异性的方式破坏了特定的转录因子结合位点。将这些“增强子变异” (EV) 与 eQTL 映射和基因位点建模相结合，将一部分 EV 与其靶基因联系起来。最后，我们将这些模型应用于已知 PD GWAS 位点的调节变异优先级排序，从而绕过了多巴胺能神经元等稀有疾病相关细胞群体中的统计局限性。总之，我们建立了一个独特的资源和新的序列建模策略，用于解释人脑中的功能性非编码变异。

## Abstract
Genome-wide association studies (GWAS) have linked more than hundred non-coding genomic loci to Parkinson's disease (PD) risk. Deciphering their functional impact on gene regulation requires cell type-aware modeling approaches to assess the effects of sequence variation on enhancer function and target gene expression. To address this challenge, we generated a comprehensive matched dataset from 190 human donors (115 controls and 75 PD), comprising long-read whole-genome sequencing alongside single nucleus multiome atlases (snATAC-seq and snRNA-seq for 3.1 and 1.1 million nuclei respectively) of the anterior cingulate cortex and substantia nigra. By integrating chromatin accessibility quantitative trait loci (caQTL), DNA methylation QTL (meQTL), and allele-specific chromatin accessibility (ASCA), we identified 53,841 high-confidence cis-acting genetic variants that modulate cell type-specific enhancer accessibility in one or both brain regions. We then demonstrate that sequence-to-function models can accurately predict the impact of these variants directly from the genomic sequence. Novel explainability approaches allowed stratifying these variants according to their regulatory function, with the majority disrupting specific transcription factor binding sites in a cell type specific manner. Integrating these "enhancer variants" (EV) with eQTL mapping and gene locus modeling linked a subset of EVs to their target genes. Finally, we applied these models to prioritize regulatory variants at known PD GWAS loci, bypassing statistical limitations in rare disease-relevant populations like dopaminergic neurons. All together, we establish a unique resource and new sequence modeling strategies to interpret functional non-coding variation in the human brain.

---

## 论文详细总结（自动生成）

这篇论文题为《在大型帕金森病队列中对人脑增强子的顺式调节变异进行建模》，是一项结合了大规模人群队列、单细胞多组学和深度学习建模的系统性研究。以下是对该论文的深度总结：

### 1. 核心问题与整体含义
*   **研究背景**：全基因组关联研究（GWAS）识别了大量与帕金森病（PD）相关的风险位点，但约 93% 位于非编码区。这些变异如何通过调节增强子功能影响特定细胞类型的基因表达，一直是该领域的“黑匣子”。
*   **核心问题**：如何系统性地识别并解释这些非编码变异的功能？特别是如何在样本量有限的稀有细胞类型（如多巴胺能神经元）中评估变异的影响？
*   **整体含义**：研究通过整合长读长全基因组测序（WGS）与单细胞多组学数据，构建了一个高分辨率的人脑顺式调控变异图谱，并证明了深度学习模型可以准确预测并解释这些遗传变异的生物学效应。

### 2. 方法论
*   **核心思想**：利用自然遗传变异作为“体内诱变系统”，通过统计学关联（QTL）和深度学习预测（S2F）双重验证变异的功能。
*   **关键技术细节**：
    *   **数据采集**：对 190 名捐赠者的前扣带回皮层（CC）和黑质（SN）进行长读长 ONT 测序（获取相位信息和结构变异）及单核多组学（snATAC-seq 和 snRNA-seq）。
    *   **统计框架**：结合 **caQTL**（群体水平关联）和 **ASCA**（个体内的等位基因特异性分析）来鉴定顺式作用变异。
    *   **CREsted 模型**：开发了基于扩张卷积神经网络（Dilated CNN）的局部峰值回归模型，输入 2114bp 序列，预测细胞类型特异性的染色质可及性。
    *   **scooby 模型**：基于 Borzoi 架构进行微调，利用单细胞嵌入（Poisson-MultiVI）预测大范围（约 196kb）序列对基因表达的影响。
    *   **解释性分析**：使用 **TF-MINDI** 识别变异破坏的具体转录因子（TF）结合位点（如 SPI1, SOX 家族）。

### 3. 实验设计
*   **数据集**：190 名人类捐赠者（115 对照，75 PD），涵盖 310 万个 ATAC 核和 110 万个 RNA 核。
*   **Benchmark**：
    *   以实测的 **caQTL 斜率**和 **ASCA 等位基因失衡值**作为地面真值（Ground Truth）。
    *   对比了 **DeepHumanBrain**（基于外部脑数据训练）和 **DeepBICCN2**（基于小鼠数据训练）模型。
*   **验证场景**：在 22 种脑细胞类型中进行 eQTL 映射，并将增强子变异（EV）与靶基因表达联系起来。

### 4. 资源与算力
*   **算力使用**：文中明确提到使用 **NVIDIA H100 GPU** 进行 scooby 模型的微调训练（采用 batch size 1）。
*   **计算平台**：计算资源由弗拉芒超级计算机中心（VSC）和 VIB 数据核心提供。
*   **训练细节**：CREsted 模型在 CC 和 SN 数据集上分别训练了 35 和 21 个 epoch。具体的总训练时长未详细列出，但强调了使用了高性能计算集群。

### 5. 实验数量与充分性
*   **实验规模**：分析了约 700 万个 SNP 和 80 万个小片段插入缺失（Indels），鉴定了 53,841 个高置信度顺式变异。
*   **充分性**：
    *   **多维度验证**：通过 caQTL、ASCA、meQTL（甲基化）和 eQTL 四个维度交叉验证，实验设计非常严密。
    *   **消融与对比**：模型不仅在测试集上表现良好（相关性 0.76-0.82），还通过了跨物种（小鼠 vs 人）和跨模型（CREsted vs Borzoi）的对比验证。
    *   **客观性**：模型训练仅基于参考基因组，预测变异效应时未接触过捐赠者的基因型数据，保证了预测的无偏性。

### 6. 主要结论与发现
*   **顺式变异图谱**：识别了超过 5 万个调节细胞类型特异性增强子的变异，发现可及性增加与 DNA 甲基化降低强相关。
*   **模型预测力**：深度学习模型能以高准确度（Spearman ρ = 0.71-0.81）预测变异对染色质可及性的影响。
*   **GWAS 解释**：成功解释了多个 PD GWAS 位点。例如，识别出 rs4698412 变异通过破坏星形胶质细胞中的增强子来调节 *CD38* 基因，而非此前认为的 *BST1*。
*   **稀有细胞突破**：模型能够预测在统计学上因细胞数量不足而无法通过 QTL 检测到的变异效应（如在多巴胺能神经元中）。

### 7. 优点
*   **技术整合度高**：首次在大规模 PD 队列中完美整合了长读长测序、单细胞多组学和先进的 AI 序列建模。
*   **解决统计瓶颈**：通过“序列到功能”模型绕过了单细胞 QTL 研究中对稀有细胞类型样本量要求的限制。
*   **可解释性强**：不仅预测变异有无影响，还能具体指出是哪个转录因子结合位点受到了破坏。

### 8. 不足与局限
*   **表达预测尚弱**：虽然对染色质可及性的预测非常精准，但对基因表达（eQTL）的预测敏感性较低（约 25%），反映了从染色质状态到 mRNA 水平的复杂缓冲机制。
*   **静态快照**：研究基于死后组织，可能无法捕捉到疾病早期或特定应激状态下的动态调控变化。
*   **因果验证缺失**：虽然模型预测和统计关联很强，但缺乏大规模的 CRISPR 干扰等实验来最终证实变异与表型之间的直接因果链条。

（完）
