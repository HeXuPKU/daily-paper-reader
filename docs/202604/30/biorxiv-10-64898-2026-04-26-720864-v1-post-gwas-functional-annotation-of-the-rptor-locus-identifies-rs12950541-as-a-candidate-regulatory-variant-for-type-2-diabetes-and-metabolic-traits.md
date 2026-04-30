---
title: Post-GWAS functional annotation of the RPTOR locus identifies rs12950541 as a candidate regulatory variant for type 2 diabetes and metabolic traits
title_zh: RPTOR位点的GWAS后功能注释鉴定出rs12950541为2型糖尿病及代谢性状的候选调控变异
authors: "Gallardo-Blanco, H. L."
date: 2026-04-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.26.720864v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: GWAS后功能注释与共定位分析
tldr: 本研究针对2型糖尿病相关的RPTOR位点，通过整合Open Targets、GTEx、VEP及RNA-蛋白相互作用预测等多种后GWAS功能注释方法，识别出rs12950541为关键候选调控变异。研究发现该变异通过影响剪接和染色质重塑发挥作用，并首次揭示了RPTOR转录本与磺脲类受体ABCC8/ABCC9之间的潜在分子联系，为理解mTORC1信号通路与胰岛素分泌的交互机制提供了新视角。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在通过系统性的后GWAS功能注释，阐明RPTOR位点在2型糖尿病及代谢性状中的生物学机制及关键调控变异。
method: 综合运用L2G评分、共定位分析、QTL映射、变异效应预测及RNA-蛋白相互作用网络分析等多种生物信息学手段。
result: 确定rs12950541为非编码调控变异，并发现RPTOR-208转录本与ABCC8/ABCC9存在此前未被报道的相互作用。
conclusion: 研究证实了rs12950541的调控潜力，并提出了连接mTORC1信号与KATP通道介导的胰岛素分泌的新分子桥梁。
---

## 摘要
背景：2型糖尿病（T2D）是全球主要的健康负担，已鉴定出超过700个GWAS位点。将其转化为生物学机制仍具挑战性。本研究采用系统的GWAS后功能注释来表征RPTOR位点，该位点编码Raptor，一种对mTORC1信号传导和β细胞功能至关重要的支架蛋白。方法：我们利用Open Targets Platform v24.12分析了包含rs12950541（chr17:80760693 G>A）的31个GWAS可信集，涵盖20种代谢性状。进行了L2G评分、共定位分析以及GTEx v8中的QTL映射。对连锁不平衡（LD）块（D' >= 0.7）进行了独立的变异效应预测器（VEP）分析，以表征与rs12950541处于LD的所有变异。使用RNAct/catRAPID预测了关键RPTOR转录本的RNA-蛋白质相互作用网络，并使用ToppGene进行了功能富集。利用ChEMBL、PubMed和ClinicalTrials.gov数据库进行了药物靶点和新颖性分析。从T2D知识门户网站获取了全表型组关联研究（PheWAS）和调控注释。结果：在所有31个可信集中，RPTOR始终被评为排名第一的L2G基因（平均得分0.428，范围0.383-0.503）。T2D与肥胖相关性状表现出强烈的GWAS-GWAS共定位（H4>0.8）。骨骼肌显示出最强的QTL证据，sQTL P=1.21x10-16，以及多个eQTL/tuQTL。关键的是，胰岛、脂肪或肝脏中GWAS-QTL共定位为零且QTL为零，突显了“eQTL缺口”。对140个LD伙伴的VEP分析显示，全部为非编码变异（100% MODIFIER影响），包括24个调控区变异和2个转录因子结合位点变异。RNAct分析显示，无义介导的mRNA降解（NMD）转录本RPTOR-208比经典转录本表现出更强的RNA-蛋白质相互作用，预测的结合伙伴包括磺脲类受体（ABCC8/ABCC9）、IGF1R和染色质重塑因子，富集于葡萄糖介导的信号传导和SWI/SNF复合物通路。ABCC8被证实为磺脲类药物的分子靶点（ChEMBL: CHEMBL2071），文献分析证实RPTOR-ABCC8的RNA-蛋白质相互作用是完全新颖的，此前尚无研究将RPTOR转录本生物学与磺脲类受体功能联系起来。T2DKP PheWAS确认了跨18个表型组的78个显著关联，揭示了对急性胰岛素反应、胰岛素敏感性、高密度脂蛋白胆固醇、肝酶和睡眠性状的影响；转录因子结合分析显示rs12950541直接增强p300增强子标记，同时减少CTCF绝缘子结合。结论：七条汇聚证据支持rs12950541是RPTOR位点的一个强有力候选调控变异。GWAS后注释、VEP表征、RNA-蛋白质相互作用网络和转化药物靶点分析的整合，汇聚成一个涉及剪接、染色质重塑和代谢信号通路的调控机制。RPTOR-208与ABCC8/ABCC9之间新预测的相互作用提示了mTORC1信号传导与KATP通道介导的胰岛素分泌之间此前未被认识的分子桥梁，对于理解T2D中磺脲类-mTOR通路的交叉对话具有潜在意义。

## Abstract
Background: Type 2 diabetes (T2D) represents a major global health burden, with over 700 GWAS loci identified. Translation to biological mechanisms remains challenging. This study employs systematic post-GWAS functional annotation to characterize the RPTOR locus, encoding Raptor, a scaffold protein critical for mTORC1 signaling and beta-cell function. Methods: We analyzed 31 GWAS credible sets containing rs12950541 (chr17:80760693 G>A) using Open Targets Platform v24.12, encompassing 20 metabolic traits. L2G scoring, colocalization analysis, and QTL mapping in GTEx v8 were performed. Independent Variant Effect Predictor (VEP) analysis of the linkage disequilibrium (LD) block was conducted to characterize all variants in LD (D' >= 0.7) with rs12950541. RNA-protein interaction networks were predicted using RNAct/catRAPID for key RPTOR transcripts and functionally enriched using ToppGene. Drug target and novelty analyses were performed using ChEMBL, PubMed, and ClinicalTrials.gov databases. Phenome-wide associations and regulatory annotations were obtained from the T2D Knowledge Portal. Results: RPTOR was consistently ranked #1 L2G gene across all 31 credible sets (mean score 0.428, range 0.383-0.503). T2D showed strong GWAS-GWAS colocalizations (H4>0.8) with adiposity traits. Skeletal muscle demonstrated strongest QTL evidence with sQTL at P=1.21x10-16 and multiple eQTLs/tuQTLs. Critically, zero GWAS-QTL colocalizations and zero QTL in pancreatic islets, adipose, or liver highlight an "eQTL gap." VEP analysis of 140 LD partners revealed exclusively non-coding variants (100% MODIFIER impact), including 24 regulatory region variants and 2 transcription factor binding site variants. RNAct analysis revealed that the NMD transcript RPTOR-208 shows stronger RNA-protein interactions than the canonical transcript, with predicted binding partners including sulfonylurea receptors (ABCC8/ABCC9), IGF1R, and chromatin remodelers, enriched for glucose-mediated signaling and SWI/SNF complex pathways. ABCC8 is confirmed as the molecular target of sulfonylurea drugs (ChEMBL: CHEMBL2071), and literature analysis confirms that the RPTOR-ABCC8 RNA-protein interaction is completely novel, with no prior publications linking RPTOR transcript biology to sulfonylurea receptor function. T2DKP PheWAS confirmed 78 significant associations across 18 phenotype groups, revealing effects on acute insulin response, insulin sensitivity, HDL cholesterol, hepatic enzymes, and sleep traits, with transcription factor binding analysis showing that rs12950541 directly enhances p300 enhancer marking while reducing CTCF insulator binding. Conclusions: Seven convergent lines of evidence support rs12950541 as a strong candidate regulatory variant at RPTOR. Integration of post-GWAS annotation, VEP characterization, RNA-protein interaction networks, and translational drug target analysis converges on a regulatory mechanism involving splicing, chromatin remodeling, and metabolic signaling pathways. The novel predicted interaction between RPTOR-208 and ABCC8/ABCC9 suggests a previously unrecognized molecular bridge between mTORC1 signaling and KATP channel-mediated insulin secretion, with potential implications for understanding sulfonylurea-mTOR pathway crosstalk in T2D.

---

## 论文详细总结（自动生成）

这是一份关于论文《Post-GWAS functional annotation of the RPTOR locus identifies rs12950541 as a candidate regulatory variant for type 2 diabetes and metabolic traits》的结构化总结：

### 1. 核心问题与整体含义
*   **研究动机**：尽管全基因组关联研究（GWAS）已鉴定出超过 700 个与 2 型糖尿病（T2D）相关的位点，但如何将这些统计学关联转化为具体的生物学机制仍是巨大挑战。
*   **核心问题**：本研究聚焦于 *RPTOR* 基因位点（编码 mTORC1 复合体的关键支架蛋白 Raptor），旨在通过系统的 GWAS 后功能注释，识别并表征该位点的因果变异及其调控机制。
*   **整体含义**：研究确定了 **rs12950541** 为关键的候选调控变异，并揭示了其通过影响剪接、染色质重塑以及与磺脲类药物靶点（ABCC8/ABCC9）相互作用来影响代谢性状的潜在路径。

### 2. 方法论
*   **核心思想**：采用“收敛性证据”策略，整合遗传学、调控组学、蛋白质组学和药理学等多维度公共数据进行交叉验证。
*   **关键技术细节**：
    *   **L2G (Locus-to-Gene) 评分**：利用机器学习模型整合距离、QTL 和染色质交互数据，预测因果基因。
    *   **共定位分析 (Colocalization)**：使用 COLOC 和 eCAVIAR 算法评估 GWAS 信号与分子 QTL 信号是否共享同一个因果变异。
    *   **VEP (Variant Effect Predictor) 分析**：对连锁不平衡（LD）块（D' ≥ 0.7）内的 140 个变异进行精细的功能预测，包括转录因子结合位点（TFBS）分析。
    *   **RNA-蛋白互作预测**：利用 **RNAct/catRAPID** 算法预测 *RPTOR* 不同转录本（特别是 NMD 转录本 RPTOR-208）与蛋白质的物理相互作用。
    *   **PheWAS (全表型组关联分析)**：在 T2D 知识门户（T2DKP）中检索该变异与数百种代谢、心血管及睡眠性状的关联。

### 3. 实验设计
*   **数据集**：Open Targets Platform v24.12、GTEx v8、Ensembl VEP、RNAct、ChEMBL、T2D Knowledge Portal。
*   **分析场景**：
    *   分析了 31 个包含 rs12950541 的 GWAS 可信集（涵盖 T2D、BMI、体脂率等 20 种性状）。
    *   评估了 16 个 QTL 可信集，重点关注骨骼肌、胰岛、脂肪和肝脏组织。
*   **对比对象**：
    *   基因层面：对比了 *RPTOR* 与邻近基因（如 *NPTX1*, *CHMP6*）的 L2G 得分。
    *   转录本层面：对比了经典蛋白编码转录本（RPTOR-201）与无义介导降解转录本（RPTOR-208）的互作网络。

### 4. 资源与算力
*   **算力说明**：论文**未明确说明**具体的硬件算力（如 GPU/CPU 型号或训练时长）。
*   **资源性质**：该研究属于干实验（In silico）分析，主要依赖于公共数据库的 API 调用、在线生物信息学分析平台及已有的机器学习模型输出。

### 5. 实验数量与充分性
*   **实验规模**：
    *   涵盖 31 个 GWAS 研究的元分析数据。
    *   对 140 个 LD 伙伴变异进行了详尽的 VEP 注释。
    *   PheWAS 分析涉及 703 个表型-数据集组合。
*   **充分性与公平性**：研究通过七条独立的证据链（遗传优先级、共定位、组织特异性 QTL、LD 块表征、RNA 互作、表型谱、药物靶点）进行论证，实验设计较为全面。使用标准化公共流水线（如 Open Targets），保证了分析的客观性和可重复性。

### 6. 主要结论与发现
*   **因果基因确认**：*RPTOR* 在所有 31 个 GWAS 可信集中均被评为排名第一的因果基因。
*   **eQTL 缺口**：在骨骼肌中发现强烈的剪接 QTL（sQTL），但在胰岛、脂肪和肝脏中未发现显著 QTL，提示该变异可能通过组织特异性剪接或在特定应激条件下发挥作用。
*   **调控机制**：rs12950541 直接增强 p300 增强子标记并减少 CTCF 绝缘子结合；其 LD 变异 rs12601089 破坏了 ATF4/CEBP 结合位点。
*   **新型分子桥梁**：首次预测 **RPTOR-208 (NMD 转录本) 与 ABCC8/ABCC9 (KATP 通道组件)** 存在相互作用。这建立了 mTORC1 信号与胰岛素分泌（磺脲类药物靶点）之间此前未知的分子联系。

### 7. 优点
*   **视角新颖**：不仅关注总表达量（eQTL），还深入分析了剪接（sQTL）和非编码/NMD 转录本的功能。
*   **转化医学价值**：将遗传变异直接与临床常用药物（磺脲类）的分子靶点联系起来，为精准医疗提供了理论依据。
*   **证据链闭环**：从群体遗传学统计量到分子层面的 RNA-蛋白互作预测，逻辑严密。

### 8. 不足与局限
*   **缺乏湿实验验证**：所有的 RNA-蛋白互作和转录因子结合预测均基于计算模型，尚未通过 RIP-seq、EMSA 或 CRISPR 基因编辑进行生物学实验证实。
*   **组织覆盖偏差**：现有的 QTL 数据库（如 GTEx）多基于健康或静态组织，可能遗漏了 T2D 病理状态下或特定细胞类型（如极少数的 β 细胞亚群）中的调控信号。
*   **预测工具局限**：catRAPID 等预测工具存在一定的假阳性率，且 VEP 注释中的 CADD 得分在非编码区敏感度有限。

（完）
