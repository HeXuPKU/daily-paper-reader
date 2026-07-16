---
title: "JanusX: an integrated and high-performance platform for scalable genome-wide association studies and genomic selection"
title_zh: "JanusX: 一个集成且高性能的可扩展全基因组关联研究与基因组选择平台"
authors: "Fu, J., Jia, A., Wang, H., Liu, H.-J."
date: 2026-07-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.20.700366v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 可扩展GWAS和基因组选择的集成平台
tldr: "随着基因组数据规模增长，GWAS和GS需要高效可重复的流程。JanusX集成框架统一数据处理、模型执行和可视化，优化LMM、FarmCPU、BLUP等算法，并集成贝叶斯和机器学习预测器。GWAS中LMM推理比GEMMA快19倍，FarmCPU比rMVP快11.4倍且内存降低84.9%；GS中500k个体×500k SNP的五折交叉验证35分钟完成，内存仅14.3GiB。该平台实现大规模队列的高效位点发现和基因组预测。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1732, \"height\": 870, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1570, \"height\": 1249, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1797, \"height\": 903, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1804, \"height\": 1437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1292, \"height\": 918, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 718, \"height\": 1473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 723, \"height\": 1024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 635, \"height\": 1089, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 628, \"height\": 1106, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1799, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 906, \"height\": 800, \"label\": \"Figure\"}]"
motivation: 现有GWAS和GS平台在大规模数据中计算效率低、内存消耗大，需要统一高性能框架。
method: 集成GPU加速的LMM、稀疏GRM的GRAMMAR-Gamma校准、优化FarmCPU、自适应BLUP求解器及PCG迭代，统一接口集成贝叶斯和机器学习模型。
result: "LMM推理19倍加速，FarmCPU内存降低84.9%；500k×500k五折交叉验证35.1分钟，峰值内存14.3GiB。"
conclusion: JanusX为大规模基因组分析提供高效、可扩展的解决方案，统一GWAS和GS流程，降低计算瓶颈。
---

## 摘要
随着基因组数据集在样本量和标记密度上的不断扩展，全基因组关联研究（GWAS）和基因组选择（GS）需要从基因型矩阵到决策相关输出的整个分析路径上保持统计严谨、计算高效且可重复的工作流程。本文介绍JanusX，一个集成的高性能框架，通过统一数据处理、模型执行和可视化，为GWAS和GS提供精简、用户导向的工作流程。在模拟和真实数据集上，JanusX与已有基线保持了高度一致性，同时大幅减少了运行时间和内存使用。在GWAS中，JanusX在线性混合模型（LMM）推断上相比GEMMA实现了高达19倍的加速，并基于稀疏基因组关系矩阵实现了额外的LMM推断，结合GRAMMAR-Gamma校准，缓解了大规模队列中的计算和内存瓶颈。JanusX还在其GWAS模块中提供了FarmCPU实现，相比rMVP实现了中位数11.4倍的运行时间改进，并将峰值内存使用减少了84.9%。在GS中，JanusX集成了一个优化的最佳线性无偏预测（BLUP）后端，自适应选择样本空间和SNP空间求解器，并加入了预条件共轭梯度（PCG）求解器。该实现有效地完成了50万个个体×50万个单核苷酸多态性（SNP）的五折交叉验证，耗时35.1分钟，峰值内存仅为14.3吉比字节（GiB）。在BLUP之外，JanusX在单一界面下集成了贝叶斯和机器学习预测器，并带有紧凑的自动调优，以确保稳健的跨模型性能。因此，JanusX使得即使在大型队列中也能在一致的分析假设下实现高效的位点发现和基因组预测。

## Abstract
As genomic datasets expand in both sample size and marker density, genome-wide association studies (GWAS) and genomic selection (GS) require workflows that remain statistically rigorous, computationally efficient, and reproducible across the full analysis path, from genotype matrix to decision-relevant outputs. Here we present JanusX, an integrated high-performance framework that provides a streamlined, user-oriented workflow for GWAS and GS by unifying data handling, model execution, and visualization. Across simulated and real datasets, JanusX maintained high concordance with established baselines while substantially reducing runtime and memory usage. In GWAS, JanusX achieved up to a 19-fold speedup over GEMMA in linear mixed model (LMM) inference, and implemented additional LMM inference based on a sparse genomic relationship matrix with GRAMMAR-Gamma calibration, alleviating computational and memory bottlenecks in large-scale cohorts. JanusX also provides a FarmCPU implementation within its GWAS module, achieving a median 11.4-fold runtime improvement and reducing peak memory usage by 84.9% relative to rMVP. In GS, JanusX integrates an optimized best linear unbiased prediction (BLUP) backend that adaptively selects sample- and SNP-space solvers and incorporates a Preconditioned Conjugate Gradient (PCG) solver. This implementation efficiently completes five-fold cross-validation of 500k individuals x 500k single-nucleotide polymorphisms (SNPs) in 35.1 minutes with only 14.3 gibibyte (GiB) of peak memory. Beyond BLUP, JanusX integrates Bayesian and machine-learning predictors under a single interface with compact automatic tuning to ensure robust cross-model performance. JanusX therefore enables efficient locus discovery and genomic prediction under consistent analytical assumptions, even in large-scale cohorts.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

随着基因组数据集在样本量和标记密度上的急剧增长（如UK Biobank、FinnGen等大型队列），全基因组关联研究（GWAS）和基因组选择（GS）面临两大挑战：一是现有软件生态系统碎片化——GWAS和GS通常使用不同工具、不同输入格式、不同输出惯例，导致预处理、模型执行、结果对比和可视化难以一致，增加了学习曲线和可重复性风险；二是大规模数据带来的计算瓶颈，尤其是线性混合模型（LMM）和最佳线性无偏预测（BLUP）族模型对内存和运行时间要求极高。

该论文的核心动机是开发一个**统一、高性能、可扩展的平台**，将GWAS、GS、群体结构分析和可视化集成到单一工作流程中，同时保持统计严谨性，并与已有基石工具高度一致。JanusX旨在解决“碎片化”和“性能”双重问题，使研究人员能在不断增长的数据规模下高效进行位点发现和基因组预测。

## 2. 方法论：核心思想、关键技术细节

### 2.1 整体架构

- **统一输入**：自动解码基因型（PLINK/VCF/HapMap）、表型和协变量，进行质量控制（QC）和样本匹配，生成分析就绪数据集。
- **共享表示**：从基因型数据统一构建基因组关系矩阵（GRM）和主成分（PCs），用于下游分析。
- **模块化流程**：分为关联分析（GWAS）和基因组预测（GS）两大模块，以及群体结构分析模块（fastpop）和可视化模块。

### 2.2 GWAS模型

- **`-lm`**：一般线性模型
- **`-lmm`**：基于稠密GRM的完全LMM，使用特征分解（EVD），每个SNP重新估计方差组分，类似GEMMA-lmm。
- **`-fvlmm`**：固定方差LMM，仅在零模型下一次估计方差组分，固定后全基因组扫描，加速。
- **`-splmm`**：基于稀疏GRM的LMM，采用Cholesky分解结合GRAMMAR-Gamma校准，适用于大规模队列，类似GCTA-fastGWA。
- **`-farmcpu`**：迭代使用固定和随机效应模型（FEM/REM），优化内存和速度。

**关键优化**：
- 低内存基因型流式解码：采用packed-BED内存映射、两块异步缓冲流式SNP迭代器，减少内存压力。
- BLAS加速（OpenBLAS/Accelerate）和位运算（AVX2/NEON），多线程（Rayon框架）实现硬件感知加速。
- 稀疏GRM构建采用Cholesky分解，减少计算和内存开销。

### 2.3 GS模型

- **BLUP族**：GBLUP和rrBLUP，动态选择样本空间或SNP空间求解器，在高内存需求时自动切换至预条件共轭梯度（PCG）迭代求解器，避免显式构建完整样本空间系统。
- **贝叶斯模型**：BayesA、BayesB、BayesC（带π参数），采用Gibbs采样框架，遵循BGLR先验结构。
- **机器学习模型**：随机森林、极端随机树、梯度提升决策树、极限梯度提升（XGBoost）、支持向量机、弹性网络，带有内置紧凑自动调优。

**关键优化**：
- 自适应求解器选择：根据样本数和SNP数相对大小，自动选择GBLUP（样本空间）或rrBLUP（SNP空间）或PCG迭代求解器。
- 贝叶斯模型进行收敛诊断，确定稳定采样长度（BayesA:4000迭代、BayesB:8000、BayesC:2000）。

### 2.4 群体结构与可视化

- `fastpop`模块：优化ADMIXTURE框架，输出祖先比例堆叠条形图，结合PCA散点图。
- GWAS可视化：曼哈顿图、LD块三角图。
- GS可视化：预测vs观测散点图、标记效应曼哈顿图。

## 3. 实验设计：数据集、场景与对比方法

### 3.1 数据集

| 数据集类型 | 名称 | 样本量 | SNP数 | 用途 |
|-----------|------|--------|-------|------|
| 真实数据 | 玉米CUBIC群体 | 1,493 | 8,666,018（过滤后） | GWAS LMM和FarmCPU基准测试（23个农艺性状） |
| 真实数据 | BGLR小麦数据集 | 599 | 1,259 | GS BLUP和贝叶斯模型基准测试 |
| 模拟数据（基于真实基因型） | 玉米CUBIC + RiceAtlas骨架 | 同源 | 保留真实MAF、LD、群体结构 | 6种遗传力场景（QTN数10/100，方差分配0.5:0:0.5等） |
| 全合成数据 | JanusX快速模拟模块 | 1k–1M个体, 5k–1M SNP | 完全随机 | 运行时、吞吐量、峰值内存、生物库规模压力测试 |

### 3.2 基准与对比方法

- **GWAS LMM**：对比GEMMA-lmm、GCTA-mlma、GCTA-fastGWA、rMVP-MLM。
- **GWAS FarmCPU**：对比rMVP-FarmCPU。
- **GS BLUP**：对比rrBLUP、sommer、HIBLUP。
- **GS 贝叶斯**：对比BGLR（BayesA/BayesB/BayesC）。

### 3.3 评价指标

- 统计一致性：Pearson相关系数（效应值）、Spearman秩相关（显著性）、伪QTN召回率。
- 计算性能：运行时间（关联阶段/总流程）、峰值内存（RSS）、并行扩展效率。

## 4. 资源与算力

论文未使用GPU，全部计算在CPU集群完成。

- 运行环境：Rocky Linux 8.9，Intel Xeon 8458P处理器（3.00 GHz）。
- 常规GWAS-LMM和FarmCPU基准：4或8 CPU核心。
- GS可扩展性基准：最高32 CPU核心，内存上限64 GiB。
- 生物库规模压力测试（500k×500k）：64 CPU核心。
- 软件版本：rMVP v1.4.6, GCTA v1.94.1, GEMMA v0.98.5, sommer v4.3.2, rrBLUP v4.6.2, HIBLUP v1.6.0, BGLR v1.1.4, JanusX v1.0.26。

**注意**：论文未明确报告训练总时长或GPU型号，但生物库规模测试中GWAS（splmm）205秒，GS（BLUP五折交叉验证）35.1分钟。

## 5. 实验数量与充分性

### 5.1 实验数量

- **GWAS一致性**：模拟数据12种遗传架构场景（6种方差场景 × 2个面板） + 真实数据23个性状（FarmCPU）和4个性状（LMM）。
- **GWAS计算基准**：单核性能（1个数据集：10k个体×1M SNP）；样本规模扩展（1k–50k个体，1M SNP）；SNP规模扩展（1–20M SNP，10k个体）；并行扩展（2–32核）。
- **GS一致性**：BLUP与3种工具对比（4个模型版本）；贝叶斯与BGLR对比（3种模型×3种链长设置，有收敛诊断）。
- **GS计算基准**：样本规模扩展（1k–1M个体，10k SNP）；SNP规模扩展（5k–1M SNP，5k个体）；生物库压力测试（20k–500k个体×相同SNP）。
- **FarmCPU基准**：23个玉米CUBIC性状完整运行。
- **群体结构与可视化**：有示例但未做定量基准。

### 5.2 充分性与公平性评价

- **充分性**：覆盖不同数据规模、多种模型、统计与计算双重角度。模拟数据精心设计（保留真实遗传结构），真实数据具有代表性。对比工具均采用最新稳定版本，设置尽量一致（如相同方差组分估计、相同MCMC链长）。
- **公平性**：论文指出机器学习和贝叶斯大规模测试受限（贝叶斯因MCMC并行化困难），这是诚实的局限。BLUP对比中，HIBLUP、rrBLUP、sommer在更大样本量（如>100k）时因内存失败，而JanusX成功，因此公平性体现为“能跑 vs 不能跑”。
- **潜在偏差**：主要基准数据集（玉米CUBIC）为植物，小麦数据集较小，可能偏向植物育种场景。人骨数据（如UK Biobank）未直接使用，仅用合成数据模拟生物库规模。此外，部分对比工具可能未被优化至最新版本（如GEMMA已多年未更新）。

## 6. 主要结论与发现

1. **统计一致性高**：JanusX-LMM与GEMMA-lmm的Pearson r > 0.999，Spearman ρ > 0.984；JanusX-splmm与GCTA-fastGWA的Pearson r 0.9993–1.000；FarmCPU与rMVP完全一致（伪QTN 100%召回）。GS-BLUP与rrBLUP/HIBLUP/sommer的GEBV相关系数0.9994–1.000；贝叶斯模型后验效应值与BGLR相关系数>0.95–0.98。

2. **计算效率大幅提升**：
   - LMM推理：JanusX-lmm/fvlmm相对GEMMA实现最高19倍加速。
   - FarmCPU：相对rMVP中位数运行时间降低88.5%（11.4倍），峰值内存降低84.9%。
   - BLUP：在500k×500k规模下五折交叉验证仅需35.1分钟，峰值内存14.3 GiB，而HIBLUP等在该规模下无法运行。
   - 稀疏GRM的JanusX-splmm在50k个体时总运行时间比GCTA-fastGWA减少25%，峰值内存降低95%。

3. **瓶颈转移**：在生物库规模下，GWAS的主要计算瓶颈已从标记扫描阶段转移到稀疏GRM构建阶段（图2F）。GS中自适应求解器（PCG）成功避免了显式矩阵构造。

4. **统一工作流减少碎片化**：从数据输入到结果输出（可视化）的全流程一致性提高了可重复性和易用性。

## 7. 优点

- **高度集成**：单一平台覆盖GWAS、GS、群体结构分析和可视化，避免跨工具格式转换和样本匹配错误。
- **性能卓越**：通过密集的系统级优化（流式解码、BLAS、位运算、自适应求解器、PCG迭代），在小样本到百万量级队列均表现出色。
- **统计严谨**：与主流基石工具高度一致，不因优化牺牲准确性。
- **用户友好**：自动QC、自动求解器选择、自动可视化输出，降低使用门槛。
- **可扩展性**：能处理500k×500k的极端规模，适合生物库和动植物育种大数据。
- **开放共享**：代码、基准脚本和数据集均公开。

## 8. 不足与局限

1. **实验覆盖**：
   - 主要基准在单个植物数据集（玉米CUBIC）和一个较小的小麦数据集上完成，未在人/牲畜大规模真实数据上验证统计一致性（如UK Biobank、万亿级SNP数据）。
   - 合成数据用于规模测试，但真实遗传结构仅通过保持MAF/LD近似，可能无法完全代表真实数据的复杂相关性。
   - 群体结构模块（fastpop）和可视化模块未进行定量基准测试（如与ADMIXTURE精度或运行时间对比）。
   - 机器学习预测器仅封装外部库，并未做核心性能基准。

2. **资源与算力**：
   - 未使用GPU，对深度学习模型缺乏支持；未来如整合GPU加速可进一步提升贝叶斯MCMC效率。
   - 稀疏GRM构建仍是最大瓶颈（图2F），论文仅提出未来方向（分布式构建、LD修剪等），未在当前版本解决。

3. **模型限制**：
   - 贝叶斯模型大规模测试受限（MCMC本质串行），作者承认需要开发可扩展贝叶斯推断技术。
   - BLUP中PCG解算器的收敛性或许受数据条件数影响，论文未进行详细分析（如迭代次数、容差设置）。
   - 多基因背景、上位性、环境互作等复杂模型未集成。

4. **应用限制**：
   - 目前支持PLINK、VCF、HapMap格式，但缺少对最流行的BGEN/UKB格式的原生支持（需额外转换）。
   - 跨平台兼容性（Windows/macOS）未明确说明，从代码结构看可能主要针对Linux。
   - 自动调优对贝叶斯链长和机器学习超参数适用，但用户可能需要专业知识判断潜在模型欠拟合或过拟合。

5. **可重复性与公平性**：
   - 对比工具版本固定，但未来版本更新可能改善性能；部分对比（如GEMMA）已是多年未更新的旧版本，可能未充分利用硬件新特性。
   - 论文未进行统计学显著性检验（例如不同方法间差异是否随机波动），主要以描述性指标呈现。

（完）
