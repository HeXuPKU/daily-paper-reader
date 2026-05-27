---
title: A General Statistical Framework for Hardy-Weinberg Equilibrium Inference on the X Chromosome
title_zh: X染色体上哈迪-温伯格平衡推断的一般统计框架
authors: "Zhang, L., Paterson, A. D., Sun, L."
date: 2026-05-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.17.725730v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: X染色体哈代-温伯格平衡推断的统计框架，用于GWAS质量控制
tldr: X染色体上哈代-温伯格平衡（HWE）检验因性别特异性基因型和性别差异等位基因频率（sdMAF）而复杂化。现有检验假设不同，导致零假设模糊，且当sdMAF存在时易产生膨胀的I类错误。本文提出基于等位基因回归模型的通用统计框架，直接参数化HWD，统一了已有的Pearson χ2检验，并允许协变量和群体结构校正。模拟和1000 Genomes Project数据表明，新框架在sdMAF下仍提供稳健、可解释的推断。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有X染色体HWE检验对性别差异等位基因频率的假设不一，导致零假设不明确且易产生错误推断。
method: 提出基于等位基因回归模型的通用框架，将HWE检测转化为等位基因水平依赖性检验，直接参数化Hardy-Weinberg不平衡。
result: 模拟和1000 Genomes数据表明，常用X染色体检验在sdMAF下I类错误膨胀或推断误导，而新框架稳健。
conclusion: 该框架建立了跨常染色体和X染色体的统一统计基础，提供稳健、灵活且可解释的HWE推断。
---

## 摘要
检验哈迪-温伯格平衡（HWE）是遗传数据分析的基本组成部分，广泛应用于质量控制和模型验证。尽管HWE检验在常染色体位点上已十分成熟，但由于性别特异性基因型结构以及潜在的小等位基因频率性别差异（sdMAF），X染色体上的推断更为复杂。现有检验在sdMAF假设和男性样本纳入方面存在差异，往往导致不同但特征不明的零假设。

我们利用稳健的等位基因回归模型，开发了一个用于HWE推断的一般统计框架。通过将HWE检验表述为等位基因层面的依赖性评估，该框架直接参数化哈迪-温伯格不平衡，在明确的建模假设下统一了现有的基于皮尔逊χ²的检验，并阐明了它们的零假设、自由度以及对sdMAF的敏感性。该框架还在统一的基于回归的公式中容纳了协变量和群体结构校正。

所提出的框架提供了稳健、可解释且灵活的推断，为常染色体和X染色体区域的HWE检验建立了统一的统计基础。模拟研究和对高覆盖度千人基因组计划数据的分析表明，当存在sdMAF时，常用的X染色体检验可能表现出膨胀的第一类错误或误导性推断。

## Abstract
Testing for Hardy-Weinberg equilibrium (HWE) is a fundamental component of genetic data analysis, widely used for quality control and model validation. Although HWE testing is well established for autosomal loci, inference on the X chromosome is more complex due to sex-specific genotype structures and potential sex differences in minor allele frequency (sdMAF). Existing tests differ in their assumptions about sdMAF and male sample inclusion, often leading to distinct but poorly characterized null hypotheses.

We develop a general statistical framework for HWE inference using the robust allele-based regression model. By formulating HWE testing as an assessment of allele-level dependence, the framework directly parameterizes Hardy-Weinberg disequilibrium, unifies existing Pearson{chi} 2-based tests under explicit modeling assumptions, and clarifies their null hypotheses, degrees of freedom, and sensitivity to sdMAF. The framework also accommodates covariate and population-structure adjustment within a unified regression-based formulation.

The proposed framework provides robust, interpretable, and flexible inference, establishing a unified statistical foundation for HWE testing across autosomal and X-chromosomal regions. Simulation studies and analysis of high-coverage 1000 Genomes Project data demonstrate that commonly used X-chromosome tests can exhibit inflated type I error or misleading inference when sdMAF is present.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：X染色体上的哈迪-温伯格平衡（HWE）检验因性别特异性基因型结构以及可能存在的性别间小等位基因频率差异（sdMAF）而变得复杂。现有检验对sdMAF的假设和男性样本的处理方式不一致，导致不同的零假设，且当sdMAF真实存在时，容易产生膨胀的I类错误或误导性推断。
- **研究动机**：为X染色体HWE推断建立一个通用、稳健且解释性强的统计框架，统一现有的基于皮尔逊χ²的检验，并澄清它们的零假设、自由度以及对sdMAF的敏感性；同时允许协变量和群体结构校正。
- **整体含义**：该框架建立了常染色体和X染色体HWE检验的统一统计基础，对遗传数据质量控制（GWAS中的QC）具有重要意义。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：利用稳健的等位基因回归模型，将HWE检验表述为**等位基因层面的依赖性评估**，直接参数化哈迪-温伯格不平衡（Hardy-Weinberg disequilibrium）。
- **关键技术细节**：
  - 通过等位基因回归模型，将HWE检验转化为检验等位基因是否独立（即等位基因水平上的依赖性）。
  - 在明确的建模假设下，该框架统一了已有的基于皮尔逊χ²的检验（如常规的性别分层χ²检验、合并男女的检验等），并阐明了它们的零假设、自由度以及对sdMAF的敏感性。
  - 该框架是一个基于回归的公式，可以自然地**纳入协变量和群体结构校正**（如主成分等），从而控制混杂因素。
- **公式或算法流程**（文字说明）：
  - 不依赖于具体的概率分布假设，而是直接建模每个等位基因的观测（例如用逻辑回归或线性回归），通过回归系数是否为零来判断等位基因之间是否存在依赖性（即HWD）。
  - 在只有男女常规数据时，回归模型可以分别包含性别、等位基因计数等变量，并通过似然比检验或得分检验判断HWE是否成立。
  - 该框架可以灵活扩展，例如加入群体结构主成分作为协变量，实现校正后的HWE检验。

## 3. 实验设计：数据集、基准、对比方法
- **数据集**：
  - **模拟数据**：用于评估不同检验方法在有无sdMAF下的I类错误和检验功效。
  - **高覆盖度千人基因组计划数据**：真实数据，用于验证框架的实际表现。
- **基准**：没有明确的外部基准，但以传统的X染色体HWE检验方法（如基于χ²的性别分层检验）作为对比基线。
- **对比方法**：文中所说的“常用X染色体检验”，包括那些在sdMAF假设上不一致的现有χ²检验方法（具体名称摘要未详细列出，但提及了“Pearson χ²-based tests”的变体）。

## 4. 资源与算力
- **未明确说明**：论文摘要和元数据中没有提及使用的GPU型号、数量、训练时长等硬件资源。由于方法主要是统计推断和模拟，可能以CPU为主，但文中未给出具体算力信息。

## 5. 实验数量与充分性
- **实验数量**：摘要中只概括性地提到“模拟研究”和“高覆盖度千人基因组计划数据的分析”，没有给出具体模拟场景数、数据集分割数或消融实验数目。
- **充分性评估**：
  - 模拟实验覆盖了有无sdMAF两种主要情景，较为充分。
  - 真实数据分析使用了千人基因组（高覆盖度），具有代表性。
  - 但缺少与其他更现代的方法（如精确检验、贝叶斯方法）的比较，也没有详细讨论不同MC（minor allele count）条件下的性能。
  - 未提及重复实验次数或不确定性量化（例如标准误差和置信区间）。
  - 总体而言，实验设计尚可，但不够详尽，可视为初步验证，充分性中等。

## 6. 论文的主要结论与发现
- **主要结论**：
  - 提出的基于等位基因回归的通用统计框架，在sdMAF存在时仍能提供**稳健、可解释且灵活**的HWE推断。
  - 该框架统一了常染色体和X染色体的HWE检验基础，允许协变量和群体结构校正，避免了现有检验因sdMAF而膨胀的I类错误或误导性推断。
- **具体发现**：
  - 常用X染色体检验在sdMAF下I类错误膨胀或推断误导。
  - 新框架通过直接参数化HWD，使检验更可靠，且更容易解释因子（如性别、群体分层）的影响。

## 7. 优点：方法或实验设计上的亮点
- **方法优点**：
  - **统一性**：将常染色体和X染色体的HWE检验纳入同一回归框架，数学基础清晰。
  - **可扩展性**：容易加入协变量（如年龄、性别、主成分），从而校正群体分层和其他混淆因素。
  - **稳健性**：基于等位基因回归，对sdMAF不敏感，避免了现有检验的缺陷。
  - **解释性**：直接参数化不平衡的方向和大小，帮助理解偏离HWE的原因。
- **实验设计优点**：
  - 同时使用了模拟数据和真实数据，从理想条件和真实条件验证方法。
  - 模拟涵盖了存在sdMAF的关键场景，直击现有方法的弱点。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制
- **实验覆盖不足**：
  - 没有详细报告不同等位基因频率、样本量、性别不均衡比例下的表现。
  - 没有与其他近期方法（如精确检验、Fd回归、贝叶斯方法）进行广泛比较。
  - 没有提供计算复杂度（时间复杂度）的分析。
- **偏差风险**：框架基于回归模型，若回归模型假设（如线性或逻辑函数形式）被严重违反，可能仍有偏差。文中提及“稳健”但未提供敏感性分析。
- **应用限制**：
  - 需要用户正确指定模型中的协变量，错误指定可能影响结果。
  - 对于极低等位基因频率或稀有变异，等位基因回归的渐近性质可能不佳，建议谨慎。
  - X染色体的特殊区域（如伪常染色体区PAR）可能需要单独处理，文中未讨论。
- **现实可行性**：框架需要实现代码，但文中未提供公开软件或R包链接（可能后续会提供）。

（完）
