---
title: AlphaGenome deletion responses complement supervised enhancer-gene relation prediction in primary human astrocytes
title_zh: AlphaGenome删除响应补充了原代人星形胶质细胞中受监督的增强子-基因关系预测
authors: "Huang, Z., Huang, R., Han, J."
date: 2026-08-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.14.744988v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 增强子-基因映射的功能基因组学方法，有助于非编码GWAS变异的功能解读
tldr: 序列到功能模型虽能直接预测分子读数，但识别调控元件不等于确定其调控基因。本文利用K562分析和人类星形胶质细胞CRISPRi数据，评估AlphaGenome缺失响应在增强子-基因关系预测中的价值。对2307个AstroREG关系的冻结评估显示，AlphaGenome删除强度可区分功能与非功能关系（平均精度0.479，AUC 0.726），并提升现有特征和监督模型的表现。结果表明AlphaGenome可作为监督预测的补充证据，但不支持单独用于因果推断。
source: biorxiv
selection_source: fresh_fetch
motivation: 序列到功能模型预测分子读数，但识别调控元件不揭示其调控的基因，需验证AlphaGenome缺失响应能否补充增强子-基因关系的证据。
method: 利用K562分析和人类星形胶质细胞CRISPRi资源，对2307个AstroREG关系进行冻结评估，比较AlphaGenome单独及加入基线特征和EGrf后的增量效果。
result: AlphaGenome区分功能与非功能关系（平均精度0.479，AUC 0.726），加入基线特征将平均精度从0.396升至0.534，叠加于EGrf再提升至0.619。
conclusion: AlphaGenome提供互补的关系级证据，但不等同于EGrf优越、也不能单独用于因果分配或替代CRISPRi验证。
---

## 摘要
序列到功能模型直接从DNA预测分子读数，但识别功能性调控元件并不等同于指定其调控的基因。我们评估了AlphaGenome删除响应是否能识别经实验支持的增强子-基因关系，使用了固定的K562分析以及我们分析外部的原代人星形胶质细胞CRISPR干扰（CRISPRi）资源。K562平均对比度为正值但呈重尾分布，精确连接显示与已发布的Gasperini和ENCODE-rE2G资源直接冲突；因此我们将K562视为支持性证据。在对2,307个AstroREG关系的固定评估中，AlphaGenome删除强度区分了133个功能性关系与2,174个有充分效力的非功能性关系（平均精确度0.479，增强子簇95%置信区间0.394-0.561，患病率0.058；接收者操作特征曲线下面积0.726，0.659-0.786）。将AlphaGenome添加到距离、ABC评分、增强子长度、测量的表达和测定深度背景中，将增强子分组的折外平均精确度从0.396提高到0.534，并将对数损失从0.169改善到0.150。作者交叉拟合的EGrf评分单独更强（平均精确度0.559）；在同时保留基因和增强子折的事后校准中，添加AlphaGenome将平均精确度从0.550提高到0.619（配对的增强子簇增量0.068，区间0.023-0.115），并将对数损失从0.143改善到0.132。该比较具有不对称输入：EGrf在AstroREG标签上受监督并使用局部表观基因组和上下文特征，而AlphaGenome评分在本研究中未拟合到这些标签或该特征面板，而是从预先存在的原发性星形胶质细胞RNA-seq输出轨道读取。事后同增强子分析给出条件AUC 0.741（0.663-0.814）；较小的同基因分析（34个基因，155个关系）给出0.701（0.571-0.823）。AstroREG标签和EGrf输出在AlphaGenome公开发布之前是公开的，因此该评估对我们研究是外部的，但不是发布后或经证明未见的基准。结果支持互补的关系级效用，而非EGrf优越性、仅序列部署、任意位点的因果分配或序列删除与CRISPRi之间的等价性。

## Abstract
Sequence-to-function models predict molecular readouts directly from DNA, but recognizing a functional regulatory element is not equivalent to assigning the gene it regulates. We evaluated whether AlphaGenome deletion responses identify experimentally supported enhancer-gene relations, using a frozen K562 analysis and a primary-human-astrocyte CRISPR interference (CRISPRi) resource external to our analysis. The K562 mean contrast was positive but heavy-tailed, and exact joins showed direct collision with released Gasperini and ENCODE-rE2G resources; we therefore treated K562 as supporting evidence. In a frozen evaluation of 2,307 AstroREG relations, AlphaGenome deletion strength discriminated 133 functional relations from 2,174 well-powered nonfunctional relations (average precision 0.479, enhancer-cluster 95% confidence interval 0.394-0.561, prevalence 0.058; area under the receiver-operating-characteristic curve 0.726, 0.659-0.786). Adding AlphaGenome to distance, ABC score, enhancer length, measured expression and assay-depth context increased enhancer-grouped out-of-fold average precision from 0.396 to 0.534 and improved log loss from 0.169 to 0.150. The authors' cross-fitted EGrf score was stronger alone (average precision 0.559); in a post-hoc calibration that held out both gene and enhancer folds, adding AlphaGenome increased average precision from 0.550 to 0.619 (paired enhancer-cluster increment 0.068, interval 0.023-0.115) and improved log loss from 0.143 to 0.132. This comparison had asymmetric inputs: EGrf was supervised on AstroREG labels and used local epigenomic and context features, whereas the AlphaGenome score was not fitted in this study to those labels or that feature panel but was read from a pre-existing primary-astrocyte RNA-seq output track. A post-hoc same-enhancer analysis gave conditional AUC 0.741 (0.663-0.814); a smaller same-gene analysis (34 genes, 155 relations) gave 0.701 (0.571-0.823). AstroREG labels and EGrf outputs were public before AlphaGenome's public release, so this evaluation is external to our study but not a post-release or proven-unseen benchmark. The results support complementary relation-level utility, not EGrf superiority, sequence-only deployment, causal assignment at arbitrary loci or equivalence between sequence deletion and CRISPRi.