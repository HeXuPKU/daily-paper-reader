---
title: "LT-FGRS: a unifying R-package for the estimation of family-based genetic liabilities at population-scale"
title_zh: LT-FGRS：一个用于群体规模下基于家庭的遗传易感性估计的统一R包
authors: "Pedersen, E. M., Steinbach, J., Valstad, M., Ohlsson, H., Rasmussen, L. A., Eilertsen, E. M., Kendler, K. S., Vilhjalmsson, B. J., Schork, A. J., Krebs, M. D."
date: 2026-06-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.731517v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 用于家族遗传易损性估计的统一R包，直接相关于PRS计算
tldr: 在生物医学研究中，基于大规模家族数据的个体遗传责任估计被广泛应用于解析复杂性状的遗传结构、增强基因定位统计效力以及改善风险预测。然而，现有方法存在多个独立实现，不利于方法比较与综合应用。LT-FGRS包应运而生，它作为统一框架整合了包括基于阈值模型和变分贝叶斯在内的多种前沿方法，支持群体规模家系数据的计算。通过在北欧国家登记数据（涵盖数百万个体）中进行基准测试，LT-FGRS在可管理的计算时间内精确复现了已有实现的结果，验证了其准确性和效率。该R包的发布降低了方法学应用门槛，为家庭遗传责任估计领域提供了标准化、易用的计算工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有家族遗传责任估计方法分散于不同实现，导致方法比较困难、应用效率低下，亟需统一框架。
method: LT-FGRS R包整合了基于阈值模型和贝叶斯方法，以统一接口处理群体规模家系基因型与家系结构数据。
result: 在覆盖数百万个体的北欧登记数据中，LT-FGRS以较低计算成本精确重现了已有实现的估计结果。
conclusion: LT-FGRS提供了标准化、易用的R包，降低了方法比较与大规模应用的门槛，有望推动遗传责任估计研究的整合与发展。
---

## 摘要
来自大规模家系数据的个体遗传易感性估计在生物医学研究中常规用于描述性状和疾病的遗传病因、增强基因定位研究的效力以及改善风险预测。在这里，我们介绍LT-FGRS，一个用于处理群体规模家系谱并实施多种前沿方法从这些数据中估计遗传易感性的R包。在群体规模的北欧登记数据中的基准测试表明，LT-FGRS能以可管理的计算成本复现现有实现的估计结果。LT-FGRS将先前的并行实现统一到一个单一框架中，降低了方法学比较和应用使用的门槛。LT-FGRS作为R包可在CRAN上获取（https://CRAN.R-project.org/package=LTFGRS）。

## Abstract
Estimates of per-individual genetic liability from large-scale family data are routinely used in biomedical research to describe genetic etiology of traits and disorders, boost the power of gene-mapping studies, and improve risk predictions. Here we present LT-FGRS, an R package for handling population-scale pedigrees and implementing multiple state-of-the-field methods for estimating genetic liability from such data. Benchmarking in population-scale Nordic registry data demonstrates that LT-FGRS reproduces estimates from existing implementations at manageable computational cost. LT-FGRS unifies previous parallel implementations into a single framework, lowering barriers for methodological comparison and applied use. LT-FGRS is available as an R-package on CRAN (https://CRAN.R-project.org/package=LTFGRS)

---

## 论文详细总结（自动生成）

### 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在人类生物医学研究中，利用亲属的表型信息来估计个体遗传易感性（genetic liability）已得到广泛应用，例如增强GWAS统计效力、改善风险预测、作为遗传流行病学工具。然而，现有多种方法（如LT-FH++、PA-FGRS、Kendler等）由不同团队独立开发，各自要求不同的数据结构和输入格式，缺乏统一的软件框架，导致方法比较困难、使用门槛高、整合与复现不便。
- **整体含义**：本文旨在通过开发一个统一的R包——LT-FGRS，将分布在不同实现中的多种家系遗传易感性估计方法整合到同一个平台中，并提供标准化的数据预处理、家系构建、删失校正、易感性估计等功能，以降低方法学比较和应用的门槛，促进大规模家系数据在遗传流行病学中的规范使用。

### 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：以家系中亲属的表型信息（患病状态及发病年龄）为基础，在标准阈值模型（liability threshold model）框架下，估计每个个体（先证者）的期望遗传易感性（条件于其亲属信息）。
- **关键技术细节**：
  1. **家系构建**：使用`prepare_graph()`函数，利用高效图算法将“个体-父-母”三联数据转换为igraph图对象；`get_family_graph()`提取每个先证者周围特定范围内（如所有血缘亲属、一级亲属等）的亲属子图。
  2. **家系级别删失（familywise censoring）**：`familywise_censoring()`函数将某个指定日期之后发生的事件（如诊断）全部删除，确保风险预测时只利用先证者截止日期前可观测的亲属信息，避免信息泄露。
  3. **右删失校正**：`prepare_thresholds()`函数，基于按性别、出生年份分层的累积发病率（CIP），生成用于两种删失模型的参数：
     - **年龄依赖阈值模型（ADT）**：假设个体在观察年龄时仍未患病，则其阈值上调，反映其处于低风险尾部的可能性。
     - **混合模型（mixture）**：将未患病个体视为一部分是终生未病（阈值高），另一部分可能是未来发病（阈值与已病类似）。
  4. **易感性估计**：`estimate_liability()`提供两种估计方式：
     - **Gibbs采样**（如Pedersen 2022方法）：迭代条件采样后验均值。
     - **Pearson–Aitken迭代解析法**（如Dybdahl Krebs 2024方法）：利用多元正态条件分布的解析公式快速计算。
  5. **简化Kendler方法**：`simplified_kendler()`函数实现经典的基于患病亲属比例的经验性调整（不依赖显式阈值模型）。
- **算法流程**：图1概括了四个步骤：A）从三联数据构建家系图；B）（可选）家系级别删失；C）基于CIP计算个体化阈值；D）估计易感性。

### 实验设计：数据集、benchmark、对比方法

- **数据集**：使用北欧国家（丹麦、瑞典、挪威）的全国性家系登记数据，每个个体平均拥有约22（丹麦）、40（瑞典）、34（挪威）个亲属。具体测试基于丹麦iPSYCH数据（已获取伦理批准）。
- **Benchmark**：对比LT-FGRS的新实现与原始独立实现（LT-FH++、PA-FGRS ADT、PA-FGRS mixt），验证估计值的一致性。
- **对比方法**：
  - 基于不同亲属范围：仅一级亲属 vs 所有血缘亲属。
  - 基于删失模型：无校正（PA）、ADT、mixture。
  - 是否应用家系级别删失（FW）。
  - 简化Kendler方法。
- **实验内容**：主要报告了不同方法之间的相关性（图S1），以及计算时间开销（表S2）。

### 资源与算力

- **未明确提及GPU算力**：论文只提到“计算需求可管理，在标准HPC系统上高效且高度可并行化”，未给出具体的GPU型号、数量或训练时长。仅在补充表S2中提供了近似计算时间（例如对百万级个体、每个个体有34位亲属时的耗时），但没有硬件配置细节。

### 实验数量与充分性

- **实验数量**：主要实验为：
  - 一致性验证：将LT-FGRS估计结果与原始软件结果做相关性分析（图S1）。
  - 方法间相关性分析：不同模型选择（亲属范围、删失模型、家族删失）之间的斯皮尔曼相关系数。
  - 计算成本报告（表S2）。
- **充分性评价**：
  - 基本验证了复现性，且分析了主要模型选择的影响，但缺乏更广泛的应用场景（如不同疾病、不同人口结构）的独立测试。
  - 没有进行预测效度（如与真实表型关联、与PRS比较）的独立评估，而论文引言提到这些是重要用途。
  - 实验设计相对简单，但作为软件工具介绍可以接受；对于方法学比较，仅报告相关性而未比较预测准确性或GWAS增益，略显不足。

### 论文的主要结论与发现

1. **一致性**：LT-FGRS的估计结果与原始实现（LT-FH++、PA-FGRS）完全一致（相同输入下）。
2. **亲属范围影响最大**：使用所有亲属 vs 仅一级亲属的估计相关性仅为0.82–0.86，表明这是不同方法间差异的主要来源。
3. **删失模型影响较小**：ADT与mixture两种右删失校正方法之间的估计相关性高达0.99。
4. **家系级别删失影响中等**：是否进行家庭删失的相关系数约为0.98。
5. **计算可扩展**：可以处理数百万个体的大规模家系，计算开销在HPC上可管理。

### 优点

- **统一框架**：将分散的多种方法整合为单一R包，降低使用门槛，便于方法比较。
- **标准化数据预处理**：提供从三联数据构建家系图、提取亲属子图、家系级别动态删失等实用功能，填补了先前工具在数据清洗方面的空白。
- **灵活性**：支持两种估计算法（Gibbs、Pearson–Aitken）和三种删失处理（无、ADT、mixture），用户可根据场景选择。
- **可复现性**：代码开源发布在CRAN和GitHub，提供详尽教程（含模拟数据）。
- **性能验证**：在真实大型登记数据上验证了复现性和计算效率。

### 不足与局限

- **模型假设限制**：所有方法均基于正态分布的阈值模型，假设多基因遗传加性效应，对非加性效应、母体效应、共享环境等未建模，可能导致偏差。
- **共享环境混杂**：家系易感性估计无法区分遗传和共享家庭环境，尤其对于高度家庭聚集的性状（如文化传递）可能高估遗传成分。
- **数据质量依赖性**：估计准确性依赖于表型登记的完整性和准确性（如左删失、诊断标准变化），老一代数据可能不完整。
- **实验覆盖面有限**：仅通过相关性复现原有软件结果，未在独立数据上比较预测性能或GWAS提升效果；缺乏对不同删失场景（如罕见病、不同年龄结构）的鲁棒性测试。
- **计算资源未详述**：未提供硬件细节，不利于他人复现计算性能。
- **未支持复杂家系结构**：如近亲结婚、收养、半同胞等特殊关系处理未明确说明。

（完）
