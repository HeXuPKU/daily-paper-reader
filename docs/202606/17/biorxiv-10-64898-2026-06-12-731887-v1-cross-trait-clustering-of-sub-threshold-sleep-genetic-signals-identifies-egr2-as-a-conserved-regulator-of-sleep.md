---
title: Cross-trait clustering of sub-threshold sleep genetic signals identifies EGR2 as a conserved regulator of sleep
title_zh: 跨性状聚类亚阈值睡眠遗传信号揭示EGR2为保守的睡眠调节因子
authors: "Mace, K. D., Trang, K. B., Zimmerman, A. J., Almeraya del Valle, E., Lottes, E. N., Parker, R. E., Choudhury, J., Chesi, A., Grant, S. F., Kayser, M. S."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.731887v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 多特征聚类亚阈值GWAS信号进行遗传发现
tldr: 针对特发性嗜睡症等睡眠障碍遗传机制不清的问题，本文采用多性状聚类分析整合低于显著性阈值的睡眠相关遗传变异，通过细胞类型特异性映射筛选候选基因。在果蝇和斑马鱼中验证发现EGR2（其直系同源基因stripe）在神经元中敲低或突变均增加睡眠，表明EGR2是跨物种保守的睡眠调节因子。该研究证明了从亚阈值遗传信号中发现睡眠调控通路的可行性。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有睡眠遗传研究仅关注基因组显著位点，大量亚阈值信号被忽略，导致嗜睡症等疾病遗传通路不明。
method: 对睡眠相关亚阈值遗传变异进行多性状聚类，结合细胞类型特异性变异-基因映射，再通过果蝇和斑马鱼跨物种功能筛选。
result: 鉴定EGR2为保守睡眠调节因子，其神经元敲低或突变显著增加睡眠时长和巩固性。
conclusion: 证实从低于常规阈值的遗传信号可识别睡眠调节通路，EGR2是跨物种保守的睡眠调控关键基因。
---

## 摘要
特发性嗜睡症（IH）是一种高度遗传的睡眠障碍，表现为日间过度嗜睡，但目前仅有少数与嗜睡相关的遗传通路被鉴定出来。为了在有限的与嗜睡相关性状的全基因组显著位点之外拓展遗传发现，我们应用多性状聚类方法分析了未达到常规显著性阈值的睡眠相关遗传变异。结合我们的细胞类型特异性变异到基因的映射，优先确定了用于跨物种功能筛选的候选效应基因。其中最强的候选基因为EGR2，它在神经元中作为ADO-EGR2位点的远端效应基因出现。敲低果蝇中EGR2的同源基因stripe可增加睡眠时长和睡眠巩固，而斑马鱼egr2同源基因的突变同样增加睡眠。综上，这些发现表明，可以从低于常规显著性阈值的遗传信号中鉴定睡眠调控通路，并确立了EGR2作为跨物种的保守睡眠调节因子。

## Abstract
Idiopathic hypersomnia (IH) is a highly heritable sleep disorder characterized by excessive daytime sleepiness, yet few genetic pathways contributing to hypersomnolence have been identified. To expand genetic discovery beyond the limited number of genome-wide significant loci associated with sleepiness-related traits, we applied multi-trait clustering to sleep-associated genetic variation that did not reach conventional significance thresholds. Integration with our cell-type-specific variant-to-gene mapping prioritized candidate effector genes for cross-species functional screening. Among the strongest candidates was EGR2, which emerged as a distal effector gene at the ADO-EGR2 locus in neurons. Neuronal knockdown of the Drosophila EGR2 ortholog stripe increased sleep duration and sleep consolidation, while mutation of zebrafish egr2 orthologs similarly increased sleep. Together, these findings demonstrate that sleep-regulatory pathways can be identified from genetic signals below conventional significance thresholds and establish EGR2 as a conserved regulator of sleep across species.

---

## 论文详细总结（自动生成）

### 论文详细总结

#### 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：特发性嗜睡症（Idiopathic Hypersomnia, IH）是一种高度遗传但遗传机制不明的睡眠障碍，其特点是日间过度嗜睡、睡眠时间长、觉醒困难。已有的全基因组关联研究（GWAS）由于样本量小和表型异质性，仅鉴定出极少数达到全基因组显著性（genome-wide significance）的位点，大量潜在的遗传信号因阈值限制被忽略。
- **整体含义**：本文提出，睡眠相关性状（如日间嗜睡、睡眠时长、午睡）具有高度多基因性，许多低于显著性阈值的遗传变异可能共同反映嗜睡相关的生物学通路。通过跨性状聚类分析整合这些亚阈值信号，并结合细胞类型特异性染色质构象进行变异-基因映射，再利用果蝇和斑马鱼跨物种功能验证，可以从中发现新的保守睡眠调控因子。本研究成功鉴定了转录因子 **EGR2**（其果蝇同源基因为 *stripe*）为跨物种保守的睡眠调节因子，证明了亚阈值遗传信号中蕴含可发掘的生物学信息。

#### 2. 方法论：核心思想、关键技术细节
- **核心思想**：利用多性状贝叶斯非负矩阵分解（Bayesian Non-negative Matrix Factorization, bNMF）对**未达到基因组显著性的睡眠相关GWAS变异**进行软聚类，根据它们与18种睡眠表型的关联模式分组，从而识别出与嗜睡倾向相关的变异簇。再结合三维染色质互作数据（Capture-C/Hi-C）和开放染色质（ATAC-seq）进行细胞类型特异性变异-基因（V2G）映射，筛选候选效应基因。最后，在果蝇和斑马鱼中进行RNAi和CRISPR介导的跨物种功能验证。
- **关键技术细节**：
  - **变异选择与LD修剪**：从三个大型UK Biobank GWAS（日间午睡、日间嗜睡、睡眠时长）中提取P ≤ 5×10⁻⁶的亚阈值变异（共4,254个独立变异）；经LD修剪（r²=0.05）。
  - **bNMF聚类**：对每个变异提取在18个睡眠表型上的z-score，转化为非负矩阵（正负分量分离），使用BayesNMF.L2EU算法运行1,000次，通过负对数证据（negative log-evidence）选择最优簇数K。虽然K=5在统计上最优，但考虑到生物学解释和基因覆盖度，最终选择K=4（因为K=5将嗜睡相关信号分散到多个簇，而K=4的簇2更完整）。
  - **V2G映射**：使用iPSC来源的神经元、神经祖细胞（NPCs）和星形胶质细胞的ATAC-seq和Capture-C/Hi-C数据，将位于开放染色质区域且与目标基因启动子有染色质环相互作用的变异连接到候选基因。本研究最终从簇2的213个变异中映射到93个候选基因（其中53个蛋白编码基因）。
  - **果蝇功能筛选**：对V2G候选基因的果蝇同源物进行神经元（elav-GAL4）和胶质细胞（repo-GAL4）特异性RNAi敲低，使用DAMS系统量化睡眠指标，并通过PCA和k-means聚类识别显著表型。
  - **斑马鱼验证**：利用CRISPR-Cas9同时敲除egr2a和egr2b，在6-7天龄幼虫中进行视频追踪睡眠行为。

#### 3. 实验设计：数据集、基准、对比方法
- **数据集**：
  - **GWAS数据**：三个大型UK Biobank GWAS（N分别为452,633、452,071、446,118）的亚阈值变异，以及从同一数据集提取的18个睡眠相关表型（9个自报告、8个加速度计导出、1个临床OSA）。
  - **表型数据**：包括日间嗜睡、睡眠时长、午睡、睡眠效率、睡眠碎片化、昼夜节律等。簇2（嗜睡相关簇）的特征是正向关联于日间嗜睡、日间午睡、长睡眠时长和加速度计测量的日间不活动。
  - **染色体构象数据**：iPSC衍生神经元（Capture-C）、NPCs（Capture-C）、星形胶质细胞（Hi-C）的开放染色质和3D互作图谱。
- **基准**：论文将已知的嗜睡效应基因**CADM2**（先前在基因组显著位点中鉴定）作为内部阳性对照。所有6个已报道的"睡眠倾向"位点均被分配到簇2，验证了聚类方法的有效性。
- **对比方法**：论文未直接对比其他聚类或V2G方法，而是通过自身K=4与K=5的比较来证明模型选择的合理性。功能筛选部分未对比其他筛选策略，而是直接对V2G候选基因进行系统性RNAi。

#### 4. 资源与算力
- 文中未明确说明使用了哪些GPU型号、数量及训练时长。bNMF聚类运行在CPU上（1,000次运行），未提及具体硬件。果蝇和斑马鱼行为实验未涉及大规模计算资源。因此，**资源与算力信息缺失**。

#### 5. 实验数量与充分性
- **实验数量**：
  - **bNMF聚类**：在K=3~7范围内各运行1,000次，最终选定K=4（共4,254个变异分配到4个簇）。
  - **V2G映射**：针对簇2的213个变异，结合三种细胞类型（神经元、NPC、星形胶质细胞）的染色质数据，得到93个候选基因。
  - **果蝇RNAi筛选**：使用神经元和胶质细胞两种驱动，每种驱动下测试了数十个RNAi品系（具体数量未明确，但图2显示约40多个品系）。多重独立RNAi线对关键候选（如*stripe*）进行了3次独立验证。
  - **斑马鱼验证**：进行了两个生物重复（不同批次胚胎），每组样本量为65（突变体）和96（对照）。
  - **空间筛选**：使用11种不同GAL4驱动在特定神经元亚型中敲低*stripe*，并重复实验。
- **充分性与公平性**：
  - **充分**：跨物种验证（果蝇+斑马鱼）增加了因果推断的可靠性。多重独立RNAi线以及对照（如Luciferase RNAi、空载体对照）排除了脱靶效应。斑马鱼实验中剔除了形态异常个体，并检测了运动活性，以排除非特异性影响。
  - **客观**：睡眠数据通过自动监测系统（DAM、Zebrabox）客观采集；PCA和k-means聚类为无监督分类；统计方法正确（ANOVA、Mann-Whitney等）。
  - **局限**：果蝇RNAi筛选未对所有候选基因进行多轮独立验证（仅对前几位做了）；星形胶质细胞的V2G仅支持10个额外基因，但后续验证重点在神经元；未对星形胶质细胞候选进行功能筛选。

#### 6. 主要结论与发现
- **主要结论**：跨性状聚类亚阈值睡眠遗传信号可以有效发现隐藏的睡眠调控通路。**EGR2（stripe）** 在物种间保守地调节睡眠：果蝇中神经元特异敲低*stripe*增加睡眠时长、巩固性和深度，且不影响运动活性和昼夜节律；斑马鱼中敲除egr2a/b同样增加日间睡眠。
- **其他发现**：
  - 果蝇*stripe*通过嗅觉神经元介导其睡眠调控作用（利用orco-GAL4和peb-GAL4敲低可复现全神经元表型）。
  - rs10995311变异位于ADO基因编码区，但功能数据（染色质互作、预测的良性和蛋白结构）强烈支持该变异通过调控远端EGR2表达发挥作用，而非通过ADO本身。
  - 聚类方法成功恢复了已知的嗜睡基因CADM2，证明了方法的有效性。

#### 7. 优点
- **创新性**：首次系统性地挖掘低于基因组显著性阈值的睡眠GWAS变异，通过多性状聚类整合微弱信号，突破了传统GWAS的阈值限制。
- **跨物种验证**：从人类遗传学出发，经细胞特异性V2G映射，再到果蝇RNAi筛选和斑马鱼突变验证，形成完整的因果推理链条。
- **技术融合**：结合贝叶斯聚类、三维基因组学、CRISPR和自动行为分析，方法前沿。
- **生物学深度**：不仅发现EGR2，还通过空间筛选定位到嗅觉环路，将基因与特定神经回路联系，加深了对睡眠调控机制的理解。
- **保守性**：在果蝇和斑马鱼两个远缘物种中验证了同一基因的作用，提示其功能的重要性。

#### 8. 不足与局限
- **亚阈值信号的噪声问题**：聚类中不可避免地包含假阳性信号，尽管用了保守的95百分位阈值，但部分候选可能为统计噪声。
- **表型特异性有限**：簇2反映的是广义的“睡眠倾向”，而非特发性嗜睡症的独有特征，可能混杂了其他睡眠障碍（如OSA）的表型成分。
- **V2G映射的覆盖度**：仅使用了三种神经细胞类型的染色质数据，可能忽略了其他重要细胞类型（如下丘脑神经元、松果体细胞等）的调控信息。
- **果蝇筛选的局限性**：RNAi可能部分脱靶，且筛选仅覆盖了V2G候选基因的一小部分（共93个候选，但图2仅显示约40余个品系，说明非全部筛选）；未对所有候选进行独立验证。
- **斑马鱼模型**：egr2ab crispants中出现了个别鱼的运动异常和疑似癫痫样活动，可能干扰睡眠表型；虽然剔除了严重畸形个体，但不能排除亚临床运动缺陷对睡眠的影响。
- **缺乏人类直接证据**：研究未在人源细胞或患者中验证EGR2的表达变化与嗜睡的关系，因果关系仅依赖模式生物。
- **可重复性**：由于是预印本，尚未经过同行评审；数据可用性声明中的代码和数据集需进一步检查。

（完）
