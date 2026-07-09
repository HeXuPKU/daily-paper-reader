---
title: LDSC regression-based heritability estimates can be biased when summary statistics are obtained from meta-analysis or imputed variants
title_zh: 基于LDSC回归的遗传力估计在汇总统计来自元分析或插值变异时可能存在偏差
authors: "Dong, R., Wang, M., Wang, G. T., deWan, A. T., Leal, S. M."
date: 2026-07-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.05.736573v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: LDSC遗传力估计偏差分析
tldr: "LDSC回归是常用的遗传力估计方法，但基于meta分析或imputed variants的汇总统计可能导致偏差。研究发现，meta分析合并不同祖先或表型定义的研究时，缺乏合适的LD参考面板，导致遗传力低估。imputed variants即使信息得分高（如INFO>0.9），也会使阿尔茨海默病遗传力从0.265降至0.160，类似偏差在个体层面GCTA-GREML分析中也出现。这些结果警示，使用meta分析或imputed数据估计遗传力需谨慎，应优先采用基因型或测序数据。"
source: biorxiv
selection_source: fresh_fetch
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-05-736573-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1942, \"height\": 438, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-05-736573-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1536, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-05-736573-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1225, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-05-736573-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 916, \"height\": 452, \"label\": \"Table\"}]"
motivation: 研究LDSC回归在meta分析或imputed variants下产生偏差的原因，确保遗传力估计的可靠性。
method: 使用多个阿尔茨海默病研究的汇总统计和不同LD参考面板，比较LDSC与个体数据方法的估计结果。
result: Meta分析或imputed variants导致遗传力低估，例如AD遗传力从0.265降至0.160（se 0.041）。
conclusion: 使用meta分析或imputed数据估计遗传力需谨慎，应优先采用基因型或测序数据。
---

## 摘要
动机：连锁不平衡评分（LDSC）回归是一种流行的使用汇总统计和连锁不平衡（LD）参考面板估计复杂性状遗传力的方法，提供了需要个体级数据的方法的实用替代方案。尽管其广泛使用，LDSC回归可能产生有偏的遗传力估计。我们使用来自几个大型阿尔茨海默病（AD）研究和各种LD参考面板的汇总统计，研究了LDSC回归的性质。将这些遗传力估计与从个体级数据获得的估计进行比较。结果：当LDSC回归应用于来自元分析的汇总统计时，导致遗传力被低估。如果使用元分析来合并不同祖先的研究，可能导致缺乏适当的LD参考面板的警告。此外，元分析通常包括具有不同表型定义的研究，这不仅影响遗传力估计，还使其无法解释。从插值变异生成的汇总统计，即使具有高插值准确性，也可能导致遗传力被低估。例如，与仅分析基因型阵列变异相比，当包含插值变异（INFO>0.9）时，AD的遗传力估计从0.265（标准误0.148）降低到0.160（标准误0.041）。使用GCTA-GREML分析个体级插值变异数据时，也观察到遗传力估计的下降。我们的发现强调了使用元分析汇总统计或插值数据而非基因型或测序数据估计遗传力的注意事项。

## Abstract
Motivation: Linkage disequilibrium score (LDSC) regression is a popular method to estimate heritability for complex traits using summary statistics and linkage disequilibrium (LD) reference panels, offering a practical alternative to methods requiring individual-level data. Despite its widespread use, LDSC regression can produce biased heritability estimates. The properties of LDSC regression were investigated using summary statistics from several large-scale Alzheimer's disease (AD) studies and a variety of LD reference panels. These heritability estimates were compared with those obtained from individual-level data. Results: When LDSC regression was applied to summary statistics obtained from meta-analysis, it led to an underestimation of heritability. This can occur if meta-analysis is used to combine studies of different ancestries leading to the caveat of the lack of an appropriate LD reference panel. Additionally meta-analyses often include studies with different phenotype definitions, that not only impacts heritability estimates but also makes them uninterpretable. Summary statistics generated from imputed variants, even those with high imputation accuracy, can lead to underestimation of heritability. For example, the heritability estimates for AD were reduced from 0.265 (se 0.148) to 0.160 (se 0.041) when imputed variants (INFO>0.9) were included compared to analyzing only genotype array variants. A decrease in heritability estimates was also observed when individual-level imputed variant data were analyzed using GCTA-GREML. Our findings highlight the caveats of estimating heritability using meta-analysis summary statistics or imputed data instead of genotyped or sequence data.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：LDSC回归（Linkage Disequilibrium Score regression）是一种广泛使用的利用GWAS汇总统计和LD参考面板估计复杂性状遗传力的方法，但在某些情况下（如汇总统计来自元分析或使用插值变异）会产生有偏的遗传力估计，导致结果远低于基于个体数据（如GCTA-GREML）或双生子研究的估计值。
- **整体含义**：提示研究者在解读大型GWAS元分析或插值数据报告的遗传力时需谨慎，偏差可能源于人群祖先不匹配、表型定义不一致以及变异质量差异，低估的遗传力可能掩盖真实的遗传组成，影响后续研究决策（如样本量规划、遗传风险预测等）。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：通过对比LDSC回归与个体级数据方法（GCTA-GREML），系统评估不同因素（LD参考面板来源、元分析异质性、表型定义、变异类型及其质量）对遗传力估计的影响，揭示偏差来源。
- **关键技术细节**：
  - **关联分析**：使用REGENIE（基于近似广义线性混合模型）生成汇总统计，校正性别、年龄、5个主成分。
  - **LD参考面板构建**：分别使用UK Biobank内部样本（3,708病例+14,099对照）、1000 Genomes Project欧洲人群（EUR）及英国人群（GBR，n=87）、Pan-UK Biobank（n=420,531）计算LD分数。
  - **遗传力估计**：LDSC回归（基于Bulik-Sullivan 2015），并转换为5%患病率下的 liability 尺度。GCTA-GREML（个体级数据）作为对比基准。
  - **变异过滤**：排除MAF≤0.01、链模糊变异、非SNP及不重叠的变异；仅保留HapMap3变异用于LD参考面板。
  - **插值变异处理**：按INFO评分分层（0.9-1, 0.99-1等），比较基因型变异与插值变异的效果。
- **算法流程**：  
  ① 获取或生成汇总统计（如通过REGENIE）；  
  ② 选择匹配或内部LD参考面板并计算LD分数；  
  ③ 使用LDSC软件拟合回归（χ²统计量对LD分数）；  
  ④ 输出遗传力估计及其标准误；  
  ⑤ 与GCTA-GREML结果对比验证。

### 3. 实验设计：使用了哪些数据集/场景、其benchmark、对比方法
- **数据集/场景**：
  - **主要分析数据集**：UK Biobank（英国白种人）——3,708 AD病例、14,099对照、47,052 AD代理病例（有家族史但未患病）。所有个体不相关。
  - **外部元分析结果（表1）**：Jansen 2019（n=71,880病例，含代理）、Kunkle 2019（n=21,982，仅临床病例）、Wightman 2021（n=86,531）、Bellenguez 2022（n=85,934），涵盖多国欧洲人群。
  - **LD参考面板**：内部（UK Biobank同批样本）、外部（1kGP EUR/GBR）、Pan-UK Biobank（用于插值变异）。
  - **变异类型**：仅基因型变异 vs. 插值变异（不同INFO阈值）。
- **Benchmark**：GCTA-GREML（个体级数据）作为“黄金标准”对比。
- **对比方法**：LDSC回归与GCTA-GREML；不同LD参考面板（内部、外部、不同祖先）；不同表型定义（AD病例、AD代理、混合）；不同变异类型（基因型、插值不同质量）。

### 4. 资源与算力：文中未明确说明
- **未提及**：论文未报告使用的GPU型号、数量、训练时长或计算集群信息。仅提及使用REGENIE、GCTA、LDSC等软件，未量化算力消耗。

### 5. 实验数量与充分性
- **实验数量**：共4个主要表格和多个比较：
  - 表1：4个大型元分析的LDSC h²估计。
  - 表2：同一数据集下GCTA-GREML vs LDSC（内部、外部LD参考面板）。
  - 表3：不同表型定义（AD病例、含代理、仅代理）的LDSC估计。
  - 表4：不同INFO阈值的插值变异对LDSC估计的影响。
- **充分性评价**：
  - **优点**：覆盖了最主要的偏差因素（祖先不匹配、表型异质性、插值质量），逻辑清晰，逐步验证。
  - **不足**：样本量有限（仅3,708病例），导致标准误较大（如基因型变异h²=0.265, se=0.148），部分比较的置信区间重叠，统计效力不足。仅针对阿尔茨海默病一个复杂性状，推广性待验证。未进行跨性状复现或模拟研究以控制未知混杂。未包含其他遗传力估计方法（如SumHer、HESS）的对比，公平性有限。

### 6. 论文的主要结论与发现
- **主要结论**：
  - LDSC回归在汇总统计来自元分析时会产生**向下偏差**，尤其是合并不同祖先或表型定义的研究导致无可参考的LD面板。
  - **插值变异**（即使INFO>0.9）也会显著低估遗传力，例如AD从0.265降至0.160；该偏差在GCTA-GREML中同样存在（0.361降至0.221），说明问题不限于LDSC。
  - **表型定义不一致**（如混合临床病例与代理病例）使h²估计不可解释且偏低。
  - **使用内部LD参考面板**获得最高且最接近个体级方法的估计（h²=0.247 vs GCTA-GREML的0.361），但仍低于后者，说明LDSC本身可能仍有遗漏。
  - **推荐**：优先使用基因型或全基因组测序变异，匹配祖先的LD参考面板，采用一致的表型定义，避免元分析混合人群或插值数据。

### 7. 优点：方法或实验设计上的亮点
- **系统性分析**：逐一拆解LDSC偏差的潜在来源，而非仅报出一个总误差。
- **真实世界数据验证**：使用UK Biobank完整个体数据，可直接与GCTA-GREML对比，提供可靠基准。
- **层次化变异质量分析**：按INFO评分分层，证明即使高精度插值也会引入噪声，指导实践。
- **强调表型定义关键性**：明确指出合并AD病例与代理病例导致h²不可解释，对大型元分析设计有警示意义。

### 8. 不足与局限
- **实验覆盖有限**：仅研究阿尔茨海默病，其他复杂性状（如身高、BMI）中因素作用是否一致未评估。
- **统计效力不足**：样本量小（3,708病例）导致标准误大，部分差异未达到统计显著，结论依赖趋势而非严格检验。
- **方法对比不全面**：未纳入SumHer、HESS等其他汇总统计遗传力方法，无法断定LDSC是否最差或最优。
- **未讨论其他偏差源**：如GWAS中的混淆（群体分层、隐性关联）、优势比膨胀等可能的影响。
- **LD参考面板限制**：内部面板仅含17,807人，可能不稳定；外部面板（1kGP GBR仅87人）代表性差，导致进一步低估，但未系统评估面板大小对偏差的贡献。
- **缺乏模拟验证**：难以完全排除真实遗传结构差异（如插值变异可能覆盖更低LD区域）对结果的干扰。

（完）
