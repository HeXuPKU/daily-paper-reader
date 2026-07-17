---
title: "JanusX: an integrated and high-performance platform for scalable genome-wide association studies and genomic selection"
title_zh: JanusX：一个用于大规模全基因组关联研究和基因组选择的集成高性能平台
authors: "Fu, J., Jia, A., Wang, H., Liu, H.-J."
date: 2026-07-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.20.700366v2.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 直接针对GWAS统计方法和算法的平台
tldr: "针对基因组数据规模增大导致的GWAS和GS计算效率问题，本文提出JanusX集成平台，统一数据处理、模型执行和可视化。通过优化线性混合模型、FarmCPU和BLUP后端，实现LMM推理19倍加速，FarmCPU加速11.4倍并节省84.9%内存，500k×500k五折交叉验证仅需35.1分钟和14.3GiB内存。该平台在大规模队列中实现高效位点发现和基因组预测，保证了统计严谨性和可复现性。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1732, \"height\": 870, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1570, \"height\": 1249, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1797, \"height\": 903, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1804, \"height\": 1437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1292, \"height\": 918, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 718, \"height\": 1473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 723, \"height\": 1024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 635, \"height\": 1089, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 628, \"height\": 1106, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1799, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700366-v2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 906, \"height\": 800, \"label\": \"Figure\"}]"
motivation: 现有GWAS/GS平台在大规模样本和标记下存在计算和内存瓶颈，需统一高效框架。
method: 集成高性能框架，包括稀疏GRM的GRAMMAR-Gamma校准、优化FarmCPU、自适应BLUP求解器（含PCG）及贝叶斯/机器学习预测器。
result: "GWAS中LMM加速19倍，FarmCPU中位数加速11.4倍、内存降84.9%；GS中500k×500k五折交叉验证35.1分钟，峰值内存14.3GiB。"
conclusion: JanusX提供高效可复现的GWAS/GS工作流，适用于大规模队列且保持分析一致性。
---

## 摘要
随着基因组数据集的样本量和标记密度不断增加，全基因组关联研究（GWAS）和基因组选择（GS）需要保持统计严谨、计算高效且从基因型矩阵到决策相关输出的整个分析路径上可重复的工作流程。本文介绍JanusX，一个集成的高性能框架，通过统一数据处理、模型执行和可视化，为GWAS和GS提供简化、用户导向的工作流程。在模拟和真实数据集上，JanusX与既定基线保持高度一致性，同时显著减少了运行时间和内存使用。在GWAS中，JanusX在线性混合模型（LMM）推断中比GEMMA实现了高达19倍的加速，并基于稀疏基因组关系矩阵与GRAMMAR-Gamma校准实施了额外的LMM推断，缓解了大规模队列中的计算和内存瓶颈。JanusX还在其GWAS模块中提供了FarmCPU实现，相对于rMVP，实现了中位数11.4倍的运行时间改进，并将峰值内存使用降低了84.9%。在GS中，JanusX集成了一个优化的最佳线性无偏预测（BLUP）后端，自适应选择样本和SNP空间求解器，并引入了预条件共轭梯度（PCG）求解器。该实现高效完成了50万个体×50万单核苷酸多态性（SNP）的五折交叉验证，耗时35.1分钟，峰值内存仅为14.3吉比字节（GiB）。除BLUP外，JanusX在统一接口下集成了贝叶斯和机器学习预测器，并配备紧凑的自动调优，以确保跨模型的稳健性能。因此，JanusX能够在一致的分析假设下实现高效的位点发现和基因组预测，即使在大规模队列中也是如此。

## Abstract
As genomic datasets expand in both sample size and marker density, genome-wide association studies (GWAS) and genomic selection (GS) require workflows that remain statistically rigorous, computationally efficient, and reproducible across the full analysis path, from genotype matrix to decision-relevant outputs. Here we present JanusX, an integrated high-performance framework that provides a streamlined, user-oriented workflow for GWAS and GS by unifying data handling, model execution, and visualization. Across simulated and real datasets, JanusX maintained high concordance with established baselines while substantially reducing runtime and memory usage. In GWAS, JanusX achieved up to a 19-fold speedup over GEMMA in linear mixed model (LMM) inference, and implemented additional LMM inference based on a sparse genomic relationship matrix with GRAMMAR-Gamma calibration, alleviating computational and memory bottlenecks in large-scale cohorts. JanusX also provides a FarmCPU implementation within its GWAS module, achieving a median 11.4-fold runtime improvement and reducing peak memory usage by 84.9% relative to rMVP. In GS, JanusX integrates an optimized best linear unbiased prediction (BLUP) backend that adaptively selects sample- and SNP-space solvers and incorporates a Preconditioned Conjugate Gradient (PCG) solver. This implementation efficiently completes five-fold cross-validation of 500k individuals x 500k single-nucleotide polymorphisms (SNPs) in 35.1 minutes with only 14.3 gibibyte (GiB) of peak memory. Beyond BLUP, JanusX integrates Bayesian and machine-learning predictors under a single interface with compact automatic tuning to ensure robust cross-model performance. JanusX therefore enables efficient locus discovery and genomic prediction under consistent analytical assumptions, even in large-scale cohorts.

---

## 论文详细总结（自动生成）

# 详细中文总结：JanusX：一个用于大规模全基因组关联研究和基因组选择的集成高性能平台

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：随着基因组数据集的样本量和标记密度持续增加（如biobank级规模），全基因组关联研究（GWAS）和基因组选择（GS）的传统分析流程面临**计算效率低、内存消耗大、工作流碎片化**等挑战。现有工具（如GEMMA、GCTA、rMVP、rrBLUP、BGLR等）在输入格式、模型接口、输出规范和可视化能力上差异显著，导致学习曲线陡峭、重现性风险高、维护成本增加。
- **整体含义**：作者提出JanusX——一个**集成、高性能的统一平台**，旨在将数据预处理、模型执行（GWAS/GS）、结果可视化整合到单一可复现管道中，同时保持统计严谨性和计算可扩展性，特别适用于从中小型实验群体到大规模队列的遗传与育种研究。

## 2. 方法论：核心思想、关键技术细节、算法流程
- **核心思想**：通过**统一的底层架构**（共享基因型/表型输入、自动QC、标准化输出）和**系统级优化**（内存流式加载、BLAS加速、位运算、多线程并行）消除工作流碎片，并提供多种稀疏/密集GRM求解策略，针对不同数据规模自适应切换。
- **关键模块与算法**：
  - **GWAS模块**：
    - `-lmm`：基于密集GRM特征值分解（EVD）的完全LMM，类似GEMMA-lmm；对每个SNP重新估计方差组分。
    - `-fvlmm`：基于密集GRM、固定方差LMM（仅估计一次零模型方差组分），类似FaST-LMM。
    - `-splmm`：基于**稀疏GRM**（Cholesky分解）和GRAMMAR-Gamma校准的大规模LMM，类似GCTA-fastGWA；可大幅降低内存和计算开销。
    - `-farmcpu`：复现FarmCPU算法（固定效应-随机效应迭代），使用FEM/REM迭代。
    - 统计检验：Wald检验和似然比检验。
  - **GS模块**：
    - `-BLUP`：自适应BLUP后端——根据样本数和标记数自动选择**样本空间求解（GBLUP）**、**SNP空间求解（rrBLUP）** 或**预条件共轭梯度（PCG）迭代求解器**，避免显式构建大规模样本空间矩阵。
    - 贝叶斯模型：BayesA、BayesB、BayesC（Gibbs采样框架）。
    - 机器学习模型：随机森林、额外树、梯度提升决策树、XGBoost、支持向量机、弹性网（通过scikit-learn包装，带自动调参）。
  - **种群结构分析模块**：`fastpop`（基于ADMIXTURE框架的优化版本），并集成PCA（EVD或随机SVD）。
  - **可视化模块**：曼哈顿图、LD块三角图、预测vs观测散点图、标记效应图、祖先比例堆叠条形图、PCA散点图等。
- **工程优化**：
  - 使用**packed-BED内存表示**（每元素4位）、内存映射访问、流式解码、两块异步缓冲等策略减少内存压力。
  - 基于BLAS（OpenBLAS/Accelerate）加速矩阵运算，AVX2/NEON位运算、Rayon多线程并行执行。
  - Rust编写核心后端（高性能），Python 3.10+作为前端接口。

## 3. 实验设计：数据集、场景、基准与对比方法
- **数据集**：
  1. **真实数据集**：
     - 玉米CUBIC群体：1493个体，SNP数866万（MAF≥0.02,缺失率≤0.05）。使用4个农艺性状（LMM族基准）和全部23个性状（FarmCPU基准）。
     - 小麦BGLR数据集：599个体，1259标记（GS基准）。
  2. **模拟数据集**（在真实基因型骨架基础上生成表型）：
     - 玉米CUBIC和RiceAtlas面板，分别模拟10或100个因果QTN，三种遗传力场景（V_QTN:V_Bg:V_E = 0.5:0.0:0.5, 0.3:0.3:0.4, 0.1:0.6:0.3），共12种模拟场景。
  3. **全合成数据集**：用JanusX自身的快速模拟模块生成用于纯性能测试的大规模基因型-表型数据（如1000到100万个个体、5000到100万SNP，以及500k×500k的超大矩阵）。
- **基准与对比方法**：
  - GWAS LMM族：GEMMA-lmm、GCTA-mlma、GCTA-fastGWA、rMVP-MLM。
  - GWAS FarmCPU：rMVP-FarmCPU。
  - GS BLUP族：rrBLUP、sommer、HIBLUP。
  - GS贝叶斯族：BGLR（BayesA/B/C）。
- **评估指标**：
  - 一致性：Pearson相关系数（效应值）、Spearman相关系数（显著性排序）、伪QTN召回率（FarmCPU）。
  - 性能：运行时间（关联测试阶段、整体流程）、峰值内存（RSS）、并行加速比。

## 4. 资源与算力
- **硬件**：Rocky Linux 8.9集群节点，搭载**Intel Xeon 8458P处理器（3.00 GHz）**。未提及GPU使用（所有计算均基于CPU）。
- **核心分配**：
  - 常规GWAS/GS基准：4或8 CPU核心。
  - 扩展性测试：最多32核心。
  - 生物银行级压力测试（500k×500k）：64 CPU核心。
- **内存限制**：GS扩展测试中设置了64 GiB上限；实际最大峰值内存为14.3 GiB（BLUP 500k×500k）和约82 GiB（稀疏GRM构建阶段？文中提及82.0 GiB可能是GRM构建峰值，但实际GS完成仅14.3 GiB）。
- **训练时长**：
  - 例：10k个体×1M SNP单核LMM工作流：JanusX-splmm总时间22.3分钟。
  - 500k×500k GS（五折交叉验证）：35.1分钟。
  - 500k×500k GWAS（JanusX-splmm）：关联扫描205秒（稀疏GRM构建占主导）。
  - 未提供完整训练（如贝叶斯MCMC）的具体时长，但给出了链长设置（如BayesA: 4000次迭代，burn-in 1000，thinning 5）。

## 5. 实验数量与充分性
- **实验数量**：较为充分。
  - **一致性验证**：模拟12种场景×2个面板×多种工具对比；真实性状LMM族4个+ FarmCPU 23个。
  - **性能基准**：单核（10k×1M）、SNP数扩展（1-20M，10k个体）、样本数扩展（10k-50k，1M SNP）、并行扩展（2-32核）、生物银行级压力（20k-500k，20k-500k）。
  - **GS BLUP**：样本数从1k到1M（固定10k SNP），SNP数从5k到1M（固定5k个体），以及500k×500k压力测试。
  - **贝叶斯**：收敛诊断（不同链长对比R-hat等），与BGLR对照。
- **充分性与公正性**：
  - 所有工具使用最新稳定版本，参数保持一致或默认。
  - 关注一致性时使用**top 1%显著标记**避免零效应干扰。
  - 各项基准至少进行了一次以上（可能多次重复？未明确说明重复次数，但推断至少单次运行对比）。
  - 缺少消融实验（如单独评估各优化技术的贡献），但通过不同变体（lmm vs fvlmm vs splmm）间接展示了算法选择的影响。
- **局限**：未对比其他商业工具或最新的超大规模工具（如bolt-lmm、regenie），主要集中在传统常用工具；贝叶斯模型仅在小数据集上验证一致性，未在大规模上进行压力测试。

## 6. 主要结论与发现
- JanusX在**保持与现有黄金标准工具高度一致**（Pearson r≥0.9991，Spearman ρ≥0.98）的同时，实现了**显著的计算加速和内存降低**。
  - GWAS LMM：JanusX-lmm/fvlmm比GEMMA-lmm快19倍；JanusX-splmm比GCTA-fastGWA总时间更短、内存更低。
  - FarmCPU：比rMVP中位数快11.4倍，峰值内存减少84.9%。
  - BLUP：在500k×500k规模下，五折交叉验证仅需35.1分钟和14.3 GiB内存，而rrBLUP、sommer、HIBLUP在该规模下失败或内存超出。
  - 贝叶斯模型：与BGLR出色一致。
- **可扩展性证明**：从1k到1M个体，JanusX-BLUP运行时仅从2.15秒增至330.63秒，内存低于4.5 GiB；GWAS模块在500k×500k关联扫描仅需205秒（GRM构建为主）。
- 稀疏GRM构建成为新的瓶颈，但整体流程仍比传统工具高效。

## 7. 优点
- **集成性**：统一数据输入、QC、多种GWAS/GS模型、种群结构分析、可视化，减少跨工具转换和错误。
- **高性能优化**：采用内存高效的packed-BED、流式解码、BLAS加速、位运算、多线程并行、自适应求解器选择（PCG），在**大规模下保持低内存和快速计算**。
- **统计严谨性**：与主流工具高度一致，确保结果可靠；提供多种LMM变体以适应不同精度/效率需求。
- **易用性**：单命令行即可完成从输入到输出（含图表），降低使用门槛。
- **开放源码**：所有代码和基准脚本在GitHub公开，促进可复现性。

## 8. 不足与局限
- **稀疏GRM构建成为主要计算瓶颈**（图2F）。未来需分布式或分块GRM构建、LD修剪或tag-SNP选择来进一步优化。
- **贝叶斯模型的大规模压力测试不足**：由于MCMC难以并行化，文中仅在小数据集上验证贝叶斯一致性，未展示在10万+个体上的性能。
- **缺少多基因座/迭代模型**：目前未集成如mrMLM、FASTmrEMMA等多基因座GWAS模型。
- **机器学习模型依赖外部库**（scikit-learn），未进行原生优化，且未在大规模场景下测试。
- **抗噪声能力有限评估**：模拟表型假设加性遗传，未考虑复杂上位性、异质性等，实际应用中的鲁棒性需进一步验证。
- **并行扩展性测试**只做到32或64核，未在数百核分布式环境下测试。
- **与其他新型工具（如regenerie、BOLT-LMM）的直接对比缺失**，基准集中于较传统的工具集。

（完）
