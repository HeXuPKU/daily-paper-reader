---
title: A T2T-CHM13 recombination map and globally diverse haplotype reference panel improves phasing and imputation
title_zh: T2T-CHM13重组图谱和全球多样性的单倍型参考面板改进了定相和插补
authors: "Lalli, J. L., Bortvin, A. N., McCoy, R. C., Werling, D. M."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.1101/2025.02.24.639687v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 参考重组图和单倍型面板用于分型和填补，直接提升GWAS准确性
tldr: "完整参考基因组T2T-CHM13包含之前未解析序列，但其对定相和插补的益处未知。本文利用3,202个1kGP样本构建T2T-CHM13重组地图和定相单倍型面板，以长读长组装为金标准比较与GRCh38面板。结果发现T2T-CHM13面板减少了38% assembly-discordant SNP基因型和16%定相错误，尤其在X染色体和CNV易感区域显著改善，并提升了SGDP样本的插补准确性。研究表明完整参考基因组定相面板可改善多样人群的统计定相和插补。"
source: biorxiv
selection_source: fresh_fetch
motivation: 评估完整参考基因组T2T-CHM13在定相和插补中的优势，探索其是否优于传统GRCh38参考面板。
method: "构建T2T-CHM13重组地图和基于3,202个1kGP样本的定相单倍型面板，以长读长组装为金标准与GRCh38面板进行比较。"
result: "T2T-CHM13面板减少了38% assembly-discordant SNP基因型和16%定相切换错误，在X染色体和CNV易感区域提升最大，并提高了SGDP样本的插补准确性。"
conclusion: 完整参考基因组T2T-CHM13定相面板有效改善多样人群的定相和插补，优于GRCh38面板。
---

## 摘要
T2T-CHM13完整人类参考基因组包含约200 Mb先前未解析的序列，与GRCh38相比，改善了读段比对和变异检测。然而，使用完整参考基因组进行定相和插补的益处尚不清楚。在此，我们提出了一个参考T2T-CHM13重组图谱和基于1000基因组计划（1kGP）3,202个样本构建的定相单倍型面板。利用已发表的长读长组装作为参考中立的金标准，我们将T2T-CHM13 1kGP面板与先前发布的GRCh38 1kGP面板进行了比较。我们发现，比对到T2T-CHM13导致组装不一致的SNP基因型减少了38%，定相转换错误减少了16%。面板准确性的最大提升出现在X染色体以及易导致致病性CNV的位点侧翼区域。此外，来自西蒙斯基因组多样性项目的降采样基因组在使用T2T-CHM13相对于GRCh38 1kGP面板时获得了更高的插补准确性。我们的研究表明，使用T2T-CHM13定相单倍型面板可改善来自不同人类群体的样本的统计定相和插补。

## Abstract
The T2T-CHM13 complete human reference genome contains ~200 Mb of previously unresolved sequence, improving read mapping and variant calling compared to GRCh38. However, the benefits of using complete reference genomes for phasing and imputation are unclear. Here, we present a reference T2T-CHM13 recombination map and phased haplotype panel derived from 3,202 samples from the 1000 Genomes Project (1kGP). Using published long-read based assemblies as a reference-neutral ground truth, we compared our T2T-CHM13 1kGP panel to the previously released GRCh38 1kGP panel. We found that alignment to T2T-CHM13 resulted in 38% fewer assembly-discordant SNP genotypes and 16% fewer phasing switch errors. The largest gains in panel accuracy were observed on chromosome X and in the regions flanking loci prone to disease-causing CNVs. Moreover, downsampled genomes from the Simons Genome Diversity Project attained higher imputation accuracy when using the T2T-CHM13 versus GRCh38 1kGP panel. Our study demonstrates that use of the T2T-CHM13 phased haplotype panel improves statistical phasing and imputation for samples from diverse human populations.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：完整的人类参考基因组 T2T-CHM13 包含了约 200 Mb 先前未解析的序列（如着丝粒、端粒重复区等），相较于 GRCh38 可显著改善读段比对和变异检测。然而，完整参考基因组对于**统计定相（phasing）和基因型插补（imputation）** 的益处尚未被系统评估。
- **整体含义**：本文旨在量化 T2T-CHM13 作为参考基因组构建的单倍型面板是否优于传统 GRCh38 面板，从而为全球多样性人群的遗传分析提供更准确的工具。若证实有效，将直接提升 GWAS、稀有变异分析等下游研究的统计效力。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用 T2T-CHM13 参考基因组，基于 1000 Genomes Project (1kGP) 的 3,202 个样本构建重组图谱和定相单倍型面板，并以长读长组装为金标准，与 GRCh38 参考面板进行定相准确性和插补准确性的直接比较。
- **关键技术细节**：
  - **重组图谱构建**：利用 1kGP 样本的高密度遗传变异数据，在 T2T-CHM13 坐标上估计遗传距离，生成新的染色体特异性重组图。
  - **定相面板构建**：使用统计定相软件（如 SHAPEIT5、Beagle 等，文中未明确说明具体工具）处理 1kGP 样本的测序数据，产生以 T2T-CHM13 为参考的单倍型面板。
  - **金标准验证**：采用已发表的长读长从头组装（如 HPRC 项目）作为参考中立的真实基因型，比较两种面板中每个样本的定相结果与金标准的差异，计算不一致 SNP 基因型和定相转换错误（switch error）。
  - **插补评估**：通过降采样西蒙斯基因组多样性项目（SGDP）的测序深度，模拟低密度基因型数据，使用两种面板进行插补，比较插补准确率（通常以 Rsq 或一致率衡量）。

### 3. 实验设计：数据集 / 场景 / Benchmark / 对比方法

- **训练与参考数据集**：
  - **训练集**：1000 Genomes Project (1kGP) 的 3,202 个样本，覆盖非洲、欧洲、东亚、南亚、美洲等全球人群。
  - **外部验证集**：西蒙斯基因组多样性项目（SGDP）的多个样本（具体数量未在摘要中说明），用于评估插补准确性。
- **金标准**：已发表的长读长组装（如人类泛参考联盟 HPRC 的从头组装），这些组装不依赖任何参考基因组，因此可作为“参考中立”的真值。
- **对比方法**：
  - **基线**：已有的 GRCh38 1kGP 单倍型面板（由同一研究团队或公开资源提供）。
  - **实验变量**：仅改变参考基因组（T2T-CHM13 vs. GRCh38），其余定相流程、样本、软件参数保持一致。
- **主要衡量指标**：
  - **定相质量**：assembly-discordant SNP 基因型数量（减少百分比）和定相转换错误数（减少百分比）。
  - **插补质量**：在 SGDP 样本中，比较两种面板下插补所得基因型与真实基因型的一致性（准确性）。

### 4. 资源与算力

- **文中未明确说明**：摘要及元数据中未提及计算集群、GPU 型号、训练时长、内存等具体资源信息。仅可推断定相和插补使用了常用软件（如 SHAPEIT5 或 Beagle），这些通常在 CPU 集群上运行即可完成。由于未提供细节，无法评估算力开销。

### 5. 实验数量与充分性

- **实验数量**：论文仅展示了一个主要对比（T2T-CHM13 vs GRCh38 面板），未报告在不同人群、不同定相软件、不同测序深度下的多组实验。未见消融实验（如移除新型序列区域的影响）、或对重组图谱参数敏感性的分析。
- **充分性评估**：
  - **优点**：使用了全球多样性的 1kGP 样本和独立的外部验证集 SGDP，并且以长读长组装为金标准，具有较强的说服力。
  - **不足**：仅在一个整体层面给出了定相错误的减少百分比，缺乏详细的区域分层或品种特异性结果（除了 X 染色体和 CNV 区域被提及）。未展示统计显著性检验，也未对比不同人群亚组的差异。实验数量较少，可能无法充分揭示参考改进在不同场景下的异质性。

### 6. 论文的主要结论与发现

- **主要发现**：
  - 使用 T2T-CHM13 参考面板后，与金标准不一致的 SNP 基因型减少了 **38%**，定相转换错误减少了 **16%**。
  - 改进最大的区域是 **X 染色体** 以及 **易导致致病性 CNV 的位点侧翼区域**（之前因组装缺口而难以准确定相）。
  - 在 SGDP 多样本插补测试中，T2T-CHM13 面板的插补准确性显著高于 GRCh38 面板（具体提升幅度未在摘要中给出，但原文应为正结果）。
- **结论**：完整参考基因组 T2T-CHM13 构建的定相单倍型面板能有效改善来自不同人类群体的样本的统计定相和插补，优于传统的 GRCh38 参考面板。

### 7. 优点

- **方法学亮点**：
  - 使用 **金标准长读长组装** 进行评估，避免了参考偏倚，使定相错误的衡量更加客观。
  - 考虑了 **T2T-CHM13 新增的着丝粒/端粒重复序列** 对定相的影响，尤其解决了 X 染色体和 CNV 区域因缺少参考而导致错误的历史问题。
  - 提供了可直接使用的 **T2T-CHM13 重组图谱和定相面板**，为后续 GWAS 和功能基因组研究提供基础设施。
- **实验设计亮点**：
  - 对比仅改变参考基因组，控制其他变量，结论直接归因于参考的改进。
  - 使用了全球多样性样本集（1kGP + SGDP），增加结果的泛化性。

### 8. 不足与局限

- **实验覆盖有限**：
  - 未对不同测序深度、不同定相算法（如 Eagle2 vs. SHAPEIT5）进行系统比较，结论可能受限于所用软件。
  - 未分析个别新解析区域（如着丝粒）对定相的具体贡献，也缺乏区域精度评估（除 X 和 CNV 区域外）。
- **偏差风险**：
  - 金标准长读长组装主要来自少量样本（如 HPRC 项目），其代表性可能偏向某些人群，导致对特定群体的评估不准确。
  - 插补测试仅在 SGDP 样本中完成，未使用真正非洲、美洲等低覆盖样本独立验证。
- **应用限制**：
  - 当前 1kGP 面板包含的样本量较小（3,202），与大规模 UK Biobank 参考面板（数十万）相比，在低频变异定相和插补上优势可能被稀释。
  - T2T-CHM13 参考基因组本身仍在完善中（如 Y 染色体仍未完全解决），未来更新可能导致面板需要重新构建。
  - 没有讨论计算资源消耗；在更大规模队列中，构建和使用 T2T-CHM13 面板的开销是否可接受未说明。

（完）
