---
title: Leveraging multiplicity in biologically informed neural networks to uncover disease heterogeneity
title_zh: 利用生物信息神经网络中的多重性揭示疾病异质性
authors: "Gankin, D., Beltrao, P."
date: 2026-07-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.15.738681v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 利用基因型数据的生物信息神经网络疾病预测
tldr: 生物启发神经网络（BINN）将生物通路结构嵌入神经网络，但在大规模生物样本库中训练困难且解释不可靠。本文在UK Biobank 50万人的基因和蛋白质组数据上训练BINN，发现归因分数受网络拓扑偏差影响，且模型存在预测多重性，不同训练实例优先不同基因和通路。然而，分析多个BINN的解释空间能揭示疾病异质性，例如2型糖尿病中炎症与肝脏代谢通路的不同解决方案聚类，将多重性转化为研究复杂疾病机制的工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738681-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1505, \"height\": 1105, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738681-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1692, \"height\": 819, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738681-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1548, \"height\": 1089, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738681-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1477, \"height\": 1815, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738681-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 550, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738681-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1247, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738681-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 747, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738681-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1561, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738681-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 885, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738681-v1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1668, \"height\": 1660, \"label\": \"Figure\"}]"
motivation: 现有BINN在生物样本库规模训练困难，且其解释可靠性未经过系统测试，需要评估并挖掘其潜在价值。
method: 在UK Biobank约50万人6种常见疾病的基因型和蛋白质组数据上训练快速BINN，并分析100个复现模型对2型糖尿病的解释。
result: BINN预测性能良好，但归因分数受图拓扑偏差影响；预测多重性导致不同模型优先不同基因/通路，但解释空间揭示了炎症和肝脏代谢两簇机制。
conclusion: 分析BINN解释的多重性可以揭示疾病异质性，将不稳定性转化为研究复杂疾病机制的新方法。
---

## 摘要
生物启发神经网络（BINNs）将通路、本体或蛋白质-相互作用结构直接嵌入神经网络，有望实现可解释的疾病预测，其中隐藏节点映射到命名的生物实体。然而，BINNs在生物银行规模上难以训练，其解释的可靠性也基本未经检验。在此，我们提出一种快速BINN实现，基于英国生物银行约50万个体在六种常见疾病中的基因型和血浆蛋白质组学数据进行训练。BINNs达到了具有竞争力的预测性能，但我们发现了其可解释性的两个主要限制。首先，归因分数受到图拓扑结构的强烈偏倚，因为节点度和层位置影响分数。归一化可减少这种偏倚，但可能削弱已知疾病基因的富集。其次，BINNs表现出显著的预测多重性，即独立训练的、具有相同架构和数据的模型能达到同样准确的解，但优先考虑不同的基因和通路。尽管这种多重性使得单一模型的解释不稳定，但解释范围本身可以揭示疾病生物学。针对2型糖尿病的100个重复BINNs，我们发现了不同的解簇，分别优先考虑炎症或肝代谢通路，反映了已知的疾病异质性。因此，分析BINN解释的空间可以将多重性转化为研究复杂疾病机制的工具。

## Abstract
Biologically inspired neural networks (BINNs) embed pathway, ontology, or protein-interaction structure directly into neural networks, promising interpretable disease prediction where hidden nodes map to named biological entities. Yet BINNs have been hard to train at biobank scale, and the reliability of their interpretations remains largely untested. Here we present a fast BINN implementation trained on UK Biobank genotype and plasma proteomics data from about 500,000 individuals across six common diseases. BINNs achieve competitive predictive performance, but we uncover two major limits to their interpretability. First, attribution scores are strongly biased by graph topology, because node degree and layer position influence the scores. Normalization reduces this bias but can weaken enrichment for known disease genes. Second, BINNs show substantial predictive multiplicity, that is, independently trained models with identical architecture and data reach similarly accurate solutions while prioritizing different genes and pathways. Although this multiplicity makes single-model explanations unstable, the range of interpretations can itself reveal disease biology. Across 100 replicate BINNs for type 2 diabetes, we find distinct solution clusters prioritizing either inflammatory or hepatic-metabolic pathways, mirroring known disease heterogeneity. Thus, analyzing the space of BINN explanations can turn multiplicity into a tool for studying complex disease mechanisms.

---

## 论文详细总结（自动生成）

# 基于论文《Leveraging multiplicity in biologically informed neural networks to uncover disease heterogeneity》的详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **背景**：生物启发神经网络（Biologically Inspired Neural Networks, BINNs）通过将生物通路、基因本体（Gene Ontology）或蛋白质相互作用图直接嵌入神经网络结构，使隐藏节点对应可命名的生物实体，从而实现“可解释性设计”。这类模型在癌症药物反应、单细胞分析等任务中显示出潜力，但存在两个关键问题：① 在生物样本库（如UK Biobank）大规模基因型数据上训练困难，因为高维输入导致内存和计算资源需求过高；② 模型解释的可靠性未经系统检验——已有研究表明初始化和训练选择可能影响解释，但解释的变异（即“预测多重性”）及其生物学意义未被充分研究。
- **核心问题**：BINNs在大规模数据上的可扩展性及其解释的稳定性、偏差和多重性如何影响生物学发现？能否将多重性转化为理解疾病异质性的工具？
- **整体含义**：论文通过开发快速BINN实现（FastBINN），在约50万人的UK Biobank基因型和血浆蛋白质组数据上训练六种常见疾病模型，系统表征了归因分数的网络拓扑偏差和模型间的解释多重性，并首次展示了解释空间的结构化性质可以揭示疾病亚型机制（如2型糖尿病中的炎症 vs 肝脏代谢通路）。

## 2. 方法论：核心思想、关键技术细节与算法流程

- **核心思想**：将已知的生物知识图（如Gene Ontology）作为神经网络的连接结构，输入特征（SNP或蛋白丰度）通过基因节点传播到更高层次的本体节点（如生物学过程、细胞组分），最终输出疾病风险。训练后通过归因方法（Integrated Gradients）将预测信号归因到每个生物单元（基因/GO术语），从而获得可解释的疾病关联。
- **关键技术细节**：
  - **FastBINN实现**：基于Nest-VNN（Park et al. 2024）改进，主要优化包括：
    - 全模型使用稀疏张量（sparse tensors）；
    - SNP到基因输入层的向量化操作；
    - 逐层更新的隐藏模型状态，减少顺序计算次数（相比于逐节点传播）。
    - 这些改进使模型内存占用从>128 GB（无法加载）降至0.38 GB，训练时间减少>100倍。
  - **网络架构**：
    - 基因型模型：约70万SNP输入 → 映射到基因 → 连接至Gene Ontology（生物学过程BP或细胞组分CC），每个基因/GO术语用5个神经元表示，分为两层。
    - 蛋白质组模型：2707个蛋白丰度输入 → 直接映射到对应基因 → 通过GO图传播。
  - **归因分数计算**：使用Integrated Gradients，以非突变等位基因（基因型模型）或零基线（蛋白质组模型）作为参考，对每个个体计算后平均得到全局归因。
  - **偏差校正**：针对网络拓扑偏差（节点层数和中心性影响归因），训练100个标签随机打乱的“空模型”作为零分布，对归因分数进行z-score归一化和百分位归一化。
  - **预测多重性分析**：对同一架构、同一数据、不同随机种子独立训练101个2型糖尿病蛋白质组模型，计算归因谱的Spearman相关矩阵，层次聚类识别解释簇。

## 3. 实验设计

- **数据集**：
  - UK Biobank（约50万无关个体），使用ICD-10编码定义六种疾病：阿尔茨海默病、2型糖尿病、房颤、甲亢、高血压、痛风（另包括急性心肌梗死，但因疾病基因数量过少被排除）。
  - 基因型数据：PLINK过滤后约70万SNP（MAF>0.001, 基因型缺失<0.03, 个体缺失<0.1），进行one-hot编码。
  - 蛋白质组数据：52,634人的血浆蛋白测量（2,707种蛋白），经对数变换和批次归一化。
  - 额外处理：对蛋白质组模型还构建了“冗余缩减”版本（仅保留10%信号方差最高的蛋白）和“深度缩减”版本（将GO深度≥5的节点折叠至第4层父节点）。
- **基准对比**：基因型模型预测性能与Genome Local Net（GLN，一种当前最先进的黑箱深度学习模型，Sigurdsson et al., 2023）比较。
- **对比方法**：
  - 归因分数验证：与已知疾病基因集（来自Open Targets和GWAS Catalog）的富集分析。
  - 系统级验证：使用独立的外部嵌入空间（Trip et al., 2026），该空间通过GWAS和ClinVar证据构建疾病/基因/术语的共享嵌入，比较FastBINN优先化的GO术语与疾病嵌入的距离。
  - 多重性分析：对比不同模型架构（基因型vs蛋白质组）、不同输入维度、不同网络深度、不同输入冗余下的归因一致性。
- **消融/变体实验**：训练了冗余缩减（6个模型）、深度缩减（9个模型）的蛋白质组模型，比较归因一致性变化。

## 4. 资源与算力

- **计算平台**：UK Biobank Research Analysis Platform。
- **基因型模型**：NVIDIA A10G GPU（22GB显存）、250GB RAM，训练10个epoch约6小时。
- **蛋白质组模型**：NVIDIA A10G GPU（22GB显存）、64GB RAM，训练10个epoch约15分钟。
- **空模型训练**：基因型模型使用合成基因型+随机标签训练100个空模型（本地集群）；蛋白质组模型使用相同输入但随机标签训练100个空模型。
- **总体计算量**：约1个基因型模型（×6种疾病×少量种子） + 101个蛋白质组模型 + 约100个空模型（蛋白）+ 多个变体模型，总计算开销合理但未给出精确GPU小时数。

## 5. 实验数量与充分性

- **实验数量**：
  - 基因型模型：七种疾病各训练至少1个模型（可能含少量重复），共约7+。
  - 蛋白质组模型：2型糖尿病101个重复模型，另加冗余缩减（6个）、深度缩减（9个）共约116个模型。
  - 空模型：每种疾病/输入类型各100个，总数百个。
  - 归因验证：每个疾病进行富集分析和嵌入距离检验（图2、图4、图S4、图S5）。
- **充分性评估**：
  - **优点**：重复实验数量充足（101个蛋白模型），足以系统分析解释空间结构。外部验证使用了独立数据源（ClinVar、Open Targets嵌入），增加了可信度。
  - **局限性**：
    - 基因型模型由于计算成本高，仅训练了少量重复，无法像蛋白质组那样分析解释空间结构。
    - 仅对2型糖尿病进行了深入的多重性分析，其他疾病未验证解释空间的可推广性。
    - 除了网络深度和输入冗余，其他影响多重性的因素（如正则化、学习率、优化器、归因方法）未系统探索。
    - 基因型模型中空模型使用合成基因型而非真实基因型，可能引入额外偏差（作者提及但未详细论证影响）。
- **公平性**：基准对比GLN使用已发表数值，但GLN与FastBINN架构差异大（GO图vs更稀疏但无本体约束的网络），对比有一定参考价值但非严格公平。

## 6. 主要结论与发现

- **FastBINN可扩展性**：成功将BINNs扩展到全基因组SNP输入（约70万特征），内存降至0.38GB，训练时间较前代实现减少>100倍，在六种疾病中预测性能接近Genome Local Net（某些疾病如痛风、房颤性能匹配，2型糖尿病差距较大）。
- **归因分数存在网络拓扑偏差**：原始归因分数与节点层数（Spearman ρ≈-0.9）、度中心性强相关，反映了梯度随深度衰减和连接性偏差。归一化可降低偏差，但会削弱已知疾病基因富集（如甲亢从15倍降至5倍），表明部分生物信号可能被移除。
- **预测多重性与解释多重性广泛存在**：相同架构、不同种子的模型性能相似但个体预测不一致（两模型Spearman ρ=0.45），归因也高度变异（基因级ρ=0.41）。蛋白质组模型（更高性能、更小规模）比基因型模型归因一致性显著更高（基因级ρ中位数~0.5 vs ~0.3），但系统级归因仍不稳定。
- **解释空间呈现结构化，揭示疾病异质性**：101个2型糖尿病蛋白质组模型的系统级归因谱层次聚类出两大解释簇：① 代谢/细胞结构/组织重塑相关（如BCAT2、SNAP23、VWF）；② 免疫/细胞因子/炎症信号相关（如GDF15、IFN通路）。这两簇对应的模型对个体风险预测权重不同——代谢簇高估代谢表型（腰围、体脂）个体风险，免疫簇高估血小板和嗜碱性粒细胞计数高的个体风险。这镜像了2型糖尿病的异质性（代谢型 vs 炎症型）。
- **结论**：预测多重性不应仅被视为不稳定性，而应作为探索复杂疾病替代机制的工具。通过分析解释空间，可以从模型多样性中提取差异化生物学假说。

## 7. 优点

- **技术贡献**：FastBINN显著提升了BINN在生物样本库规模上的实用性，为后续大规模可解释预测研究提供了高效工具。
- **问题新颖性**：首次系统揭示BINNs中的预测多重性及其在疾病异质性中的结构，将解释不稳定性转化为发现手段。
- **分析严谨性**：进行了网络拓扑偏差的量化与校正，使用独立外部数据源（ClinVar、Open Targets嵌入）验证归一化后的归因。
- **生物学洞察**：在2型糖尿病中发现两种解释模式对应已知的炎症和代谢通路，并结合个体表型差异验证了模型行为的生物学一致性。
- **公开资源**：代码已在GitHub公开，数据来源明确（UK Biobank、Open Targets、GWAS Catalog、GO）。

## 8. 不足与局限

- **计算限制**：基因型模型由于训练成本高，仅训练有限重复，无法像蛋白质组那样深入分析解释空间结构，限制了结论的推广性。
- **一般性受限**：多重性分析仅针对2型糖尿病一个疾病，其他疾病（如阿尔茨海默病、甲亢等）是否呈现类似结构尚待验证。
- **偏差风险**：
  - 归一化可能同时去除有意义的生物结构（如广泛作用的基因），理想方法需区分真实生物学偏差与人为标注偏差。
  - 空模型使用合成基因型可能不真实，影响校正效果。
  - GO图本身存在标注偏倚（偏爱研究热点基因），BINNs无法避免这一先验偏倚。
- **影响多重性的因素未充分探索**：仅测试了网络深度和输入冗余，未系统评估正则化、学习率、优化器、归因方法（如DeepLIFT vs Integrated Gradients）等的影响。
- **实验设计主观性**：解释簇的划分基于层次聚类的第一个分裂点，缺乏统计检验（如Bootstrap验证聚类稳定性）。
- **应用限制**：基于冷冻血浆蛋白和基因型数据，需要前瞻性验证是否适用于其他人群或纵向数据。模型目前为二分类，未考虑发病时间、严重程度等时间依赖信息。

（完）
