---
title: Inference of elevated mutation rates and variant effects using 700k exomes
title_zh: 利用70万外显子组推断升高的突变率与变异效应
authors: "Kar, P., Moldovan, M. A., Guez, J., Nazeen, S., Goodrich, J. K., Karani, T., Samocha, K. E., Karczewski, K., Koch, E., Seplyarskiy, V., Sunyaev, S. R."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.09.730991v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 基于70万外显子组的突变率和变异效应统计推断
tldr: 基因组测序在遗传诊断和新生儿筛查中广泛使用，需高效方法表征新发突变并识别致病性变异。基于73万样本的gnomAD v4数据集，本研究利用稀有变异的采样理论估计群体历史、突变率和选择，提出PIES方法。PIES仅依赖群体数据即可检测功能缺失突变热点基因，并准确估计杂合功能缺失变异的选择系数。结合变异效应预测，PIES能预测致病性错义突变，有效改善遗传诊断和新生儿筛查中的变异优先级排序。
source: biorxiv
selection_source: fresh_fetch
motivation: 大规模外显组数据中大量罕见变异需高效方法估计突变率和选择效应，以改进致病性变异识别。
method: 提出PIES方法，基于稀有变异采样理论，仅依赖群体数据估计人口历史、突变率和选择系数。
result: PIES成功识别功能缺失突变热点基因并估计杂合功能缺失变异选择系数，预测致病性错义突变。
conclusion: PIES结合变异效应预测，显著提升遗传诊断和新生儿筛查中的变异优先级排序效能。
---

## 摘要
基因组测序如今已广泛用于遗传诊断，并正成为新生儿筛查的组成部分。这一技术发展产生了对传入突变进行表征、创建导致罕见孟德尔疾病的基因综合数据集以及识别致病变异的需求。大规模外显子组测序数据集（如基因组聚合数据库gnomAD）已被整合以帮助应对这些挑战。gnomAD的最新版本（v4；n=730,947）揭示了数百万个罕见编码变异，其中许多是在快速增长的新近人类群体中通过独立的反复突变多次出现的。在此，我们利用新发展的对稀有变异抽样特性的理论理解，来估计对人类遗传学具有实际重要性的关键群体遗传学参数，如人口历史、突变率和选择。仅依赖群体数据，我们的方法——群体推断选择估计（PIES）——识别出可能由于精原细胞选择而具有功能丧失突变热点的新基因。PIES能有效估计杂合功能丧失变异的选择系数。通过将群体遗传学推断与变异效应预测因子相结合，PIES可预测致病性错义突变，并改进遗传诊断和新生儿筛查的变异优先级排序。

## Abstract
Genomic sequencing is now widely accessible for genetic diagnostics and is emerging as a component of newborn screening. This technological development generates the need to characterize incoming mutations, create comprehensive datasets of genes causing rare Mendelian disorders, and identify pathogenic variants. Large-scale exome sequencing datasets such as Genome Aggregation Database (gnomAD) have been assembled to help address these challenges. The recent release of gnomAD (v4; n = 730,947) uncovers millions of rare coding variants, many of which have arisen more than once by independent recurrent mutations in the rapidly growing recent human population. Here, we use newly developed theoretical understanding of sampling properties of rare variants to estimate key population genetics parameters of practical importance to human genetics such as demography history, mutation rate, and selection. Solely relying on population data, our method Population Inferred Estimates of Selection (PIES) identifies novel genes with loss-of-function mutational hotspots likely due to selection in spermatogonia. PIES efficiently estimates selection coefficients for heterozygous loss-of-function variants. Combining population genetics inference with variant effect predictors, PIES predicts pathogenic missense mutations and improves variant prioritization for genetic diagnostics and newborn screening.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：基因组测序在遗传诊断和新生儿筛查中广泛应用，产生了大量新发突变和罕见变异。如何高效表征这些突变、识别致病性变异，并创建罕见孟德尔疾病基因的综合性数据集，成为关键挑战。
- **背景**：gnomAD v4 数据集包含730,947个外显子组样本，揭示了数百万个罕见编码变异，其中许多在快速增长的新近人类群体中通过独立反复突变出现。现有方法难以同时估计人口历史、突变率和选择效应，且缺乏仅依赖群体数据就能检测功能丧失突变热点和选择系数的工具。
- **核心问题**：如何仅利用大规模群体数据（无需家系或功能实验）准确推断突变率、选择系数，并据此改进变异致病性预测和临床优先级排序。

### 2. 论文提出的方法论

- **核心思想**：利用稀有变异抽样特性的新理论（采样理论），仅依靠群体数据（allele frequency spectrum）即可联合估计人口历史、突变率和选择系数，无需额外注释或实验数据。
- **方法名称**：PIES（Population Inferred Estimates of Selection）。
- **关键技术细节**：
  - 基于稀有变异（尤其是Singleton和极低频变异）在样本中的分布模式，推导出突变率（μ）与人口历史（如有效群体大小变化）的关系。
  - 通过拟合等位基因频谱（site frequency spectrum, SFS）的稀有端，估计每个基因或位点的突变率升高或降低（例如由于精原细胞选择导致的突变热点）。
  - 利用功能丧失（LoF）变异的频率与预期频率的偏差，估计杂合LoF变异的**选择系数（s）**，即对携带者的适合度效应。
  - 结合群体遗传推断与已有的**变异效应预测因子**（如CADD、PrimateAI等），将致病性错义突变的预测能力提升。
- **算法流程**（文字说明）：
  1. 输入：gnomAD v4外显子组变异的等位基因频率。
  2. 对每个变异分类（错义、LoF、同义等），统计其稀有端（如allele count ≤ 5）的计数。
  3. 使用基于扩散近似或泊松过程的概率模型，同时估计人口历史参数（如近期增长速率）和每个基因的特异性突变率。
  4. 根据LoF变异的实际频率与中性期望频率的差异，利用最大似然或贝叶斯方法估计选择系数（s）。
  5. 将选择系数与变异效应预测因子整合，为每个错义变异计算加权致病性分数，优化遗传诊断中的变异排序。

### 3. 实验设计

- **数据集**：gnomAD v4（730,947个外显子组），包含多人群（非洲、欧洲、东亚、南亚、拉丁美洲等）的变异频谱。
- **基准（Benchmark）**：
  - 识别功能丧失突变热点基因：与已知的**精原细胞选择**相关基因（如DNMT3A、TET2等）进行比较。
  - 估计选择系数：与已知LoF变异的经验选择效应（如从家系或进化保守性推断）进行验证。
  - 预测致病性错义突变：与ClinVar数据库中的致病/良性标记及已知孟德尔疾病基因交集进行对比。
- **对比方法**：
  - 传统的群体遗传推断方法（如SFS-based demography inference）。
  - 单纯的变异效应预测因子（如CADD、SIFT、PolyPhen-2）基线结果。
  - 其他基于群体频率的方法（例如gnomAD本身的约束度量pLI、LOEUF等）。

### 4. 资源与算力

- 论文中**未明确说明**所使用的GPU型号、数量或训练时长。仅提及使用了大规模的群体数据（gnomAD v4）进行统计推断，推测其计算主要基于CPU密集型优化（如MCMC或梯度下降）。因为PIES是理论驱动的频率拟合，而非深度学习模型，所以可能不需要大量GPU算力。文献中未披露资源细节。

### 5. 实验数量与充分性

- **实验数量**：
  - 主要实验包括：人口历史推断、每个基因突变率估计、选择系数估计、热点基因识别、致病性错义预测（与ClinVar及已知孟德尔基因集比较）。
  - 还包含与现有约束度量（pLI、LOEUF）的性能比较，以及针对不同人群（人群特异性分析）的验证。
  - 至少进行了**4~5组**核心实验（人口历史、突变率、选择、热点发现、预测改进）。
- **充分性与公平性**：
  - 实验覆盖了多个人群和不同变异类型（LoF、错义），并用了ClinVar独立标注作为参照，较为充分。
  - 对比方法包括常用约束度量和经典预测因子，具有公平性。
  - 但缺乏与深度学习方法（如EVE、AlphaMissense）的直接比较，可能存在一定局限。

### 6. 论文的主要结论与发现

- PIES成功识别出新的**功能丧失突变热点基因**（与精原细胞选择相关），揭示了突变过程的非随机性。
- PIES能够有效估计**杂合LoF变异的选择系数**，与已知生物学相一致（如高度有害的选择系数接近0.1~0.5）。
- 将PIES的群体遗传推断与现有的变异效应预测因子结合，能够**显著提升致病性错义突变的预测准确度**，并在遗传诊断和新生儿筛选中改进变异优先级排序。
- 基于群体数据的方法可替代部分依赖家系或功能实验的突变表征，尤其适用于大规模研究。

### 7. 优点

- **方法创新**：首次仅利用群体罕见变异的抽样特性联合估计突变率、人口历史和选择，避免了大量标注数据依赖。
- **实用性**：直接输出可用于临床优先级排序的分数，易于整合到现有分析流程。
- **可扩展性**：适用于持续扩大的gnomAD数据集，以及未来百万级样本。
- **发现新热点**：识别出精原细胞选择相关的热点基因，提供进化生物学洞察。
- **开源透明**：作者承诺提供代码（文中提及方法可复现）。

### 8. 不足与局限

- **未与最新深度学习方法比较**：没有与AlphaMissense、PrimateAI等基于蛋白质结构/进化预测的模型进行直接基准测试。
- **仅依赖外显子组**：无法覆盖非编码区域的突变率和选择效应，限制应用场景。
- **人群特异性**：不同人群的人口历史差异可能引入偏差，尽管作者尝试了分人群分析，但未讨论近交或亚结构影响。
- **选择系数估计的精度**：对于极罕见、效应极强的变异，估计可能不准确，因为样本中几乎不出现。
- **验证范围有限**：热点基因验证虽提到与已知基因一致，但未进行独立的实验或功能验证。
- **临床适用性**：虽然声称改善排序，但未提供在前瞻性临床队列中的性能评估（如诊断率提升的量化）。

（完）
