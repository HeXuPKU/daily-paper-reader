---
title: "General, orders-of-magnitude faster whole-genome analysis with genotype representation graphs"
title_zh: 基于基因型表示图的通用、数量级提速的全基因组分析
authors: "DeHaas, D., Adonizio, C., Pan, Z., Wei, X."
date: 2026-04-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717786v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 利用基因型表示图对生物样本库规模队列进行更快的全基因组分析
tldr: 针对生物样本库规模的全基因组测序数据分析效率低下的问题，本文提出了基因型表示图（GRG）v2及其配套工具grapp。GRG v2通过分层图结构实现基因型数据的无损压缩，显著降低了存储和内存占用。配套的grapp工具利用图运算加速了GWAS、PCA等常规分析，其PCA速度比现有方法快51-492倍，为大规模群体遗传学研究提供了极具扩展性的新方案。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717786-v1/fig-001.webp\", \"caption\": \"Table 1: Constructing a GRG vs. constructing PGEN.\", \"page\": 6, \"index\": 1, \"width\": 967, \"height\": 245}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717786-v1/fig-002.webp\", \"caption\": \"Figure 3: PCA runtime performance and example applications. a. Comparing times to obtain top 10 PCs on unfiltered simulated data of different sample sizes. Datasets contain between 14.5 and 23.7 million variants. b. The same tests as panel a, but showing RAM usage. c. Comparing times to obtain top 10 PCs on simulated data filtered such that derived allele frequency >0.05. Datasets contain about 440,000 variants. d. The same tests as panel c, but showing RAM usage. For panels a-d, the y-axis is log scale. e. Time to run PCA on the UK Biobank dataset with 490,541 individuals and 137,116,837 variants over 22 autosomes with 22 threads. f. Same as panel e, except RAM usage.\", \"page\": 7, \"index\": 2, \"width\": 979, \"height\": 296}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717786-v1/fig-003.webp\", \"caption\": \"Figure 5: grapp usage examples. a. Example workflow using a simulated phenotype and PCA covariates as input to GWAS with GRG and grapp. b. Principal Component Analysis (PCA) implemented with a grapp linear operator and scipy: eigen decomposition of on the standardized genotype matrix . Meant to illustrate the simplicity and power of the linear operators; 𝑋𝑋𝑇 𝑋 for PCA, users can just use the grapp.linalg.PCs() method (which has additional options).\", \"page\": 10, \"index\": 3, \"width\": 979, \"height\": 491}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717786-v1/fig-004.webp\", \"caption\": \"Figure 4: GWAS with covariates. a. Time to perform the same GWAS (with 10 PCs as covariates) on simulated data for GRG and PLINK2 PGEN. GRG uses 1 thread (GRG T1), PLINK2 was given 1 (PGEN T1) or 25 (PGEN T25) threads. b. Same as panel a, but RAM usage. c. PLINK2 vs. grapp p-values for the same GWAS (PCA covariates) on simulated data and phenotype. d. GWAS p-values for body mass index (BMI) on UK Biobank chromosome 8, unrelated white British individuals, covariates are the top 20 PCs and sex. Each Manhattan plot uses PCs from a different PCA method: PCA on all autosomes (ALL), leave-one-chromosome out (LOCO) PCA, or the LD-pruned PCA (PRUNE, from UK Biobank field 22009). e. Correlation between PC10 (PC11) and the chromosome 8 genotypes, with PCs computed from PCA on all autosomes (ALL). f. p-values from GWAS using covariate PCs from LOCO (y-axis), vs. from ALL (x-axis, left) or PRUNE (x-axis, right).\", \"page\": 8, \"index\": 4, \"width\": 979, \"height\": 741}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717786-v1/fig-005.webp\", \"caption\": \"Figure 1: Graph-based matrix representation and multiplication. a. A GRG represents the same genotype matrix as tabular formats, and can be constructed from VCF or IGD. Matrix multiplication against GRG integrates with numpy and scipy to enable\", \"page\": 4, \"index\": 5, \"width\": 979, \"height\": 591}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717786-v1/fig-006.webp\", \"caption\": \"Figure 2: Improved GRG results on UK Biobank. a. Illustration of GRG Build algorithm, where H(i) is the haplotype (i.e., set of variants) shared by all samples beneath node i. In this example, node p captures the common set of variants between node i and j, where H(i) H(j) represents the set intersect. The green nodes become roots and capture the “residual haplotypes” that do ∩ not reach the parent of nodes i and j, or the set differences (H(i)\\\\H(j), and H(j)\\\\H(i)). Because {H(i)\\\\H(j)} {H(i) H(j)}= H(i), ∪ ∩ the graph emitted from Build contains all the haplotype to variant information. b. After the tree is constructed, all root nodes (green) are connected to the relevant mutation nodes (light blue) for the haplotypes they capture. c. Improvement of GRG v2 over v1 on the UK Biobank 200,000 phased individuals WGS dataset, reflecting how much smaller, faster, or cheaper our improved GRG construction and file format are. d. GRG file sizes for both the 490,541 (500k) and 200,011 (200k) phased individuals WGS datasets. e. Elapsed time for constructing GRGs from IGD with 64 threads (500K dataset) and 70 threads (200K dataset). f. Cost, in GBP, of constructing GRGs.\", \"page\": 5, \"index\": 6, \"width\": 979, \"height\": 598}]"
motivation: 传统的表格基因型格式在存储和分析生物样本库规模的超大规模全基因组数据时效率极低。
method: 提出GRG v2格式及构建算法，并开发了支持图运算和线性算子的Python库grapp，实现直接在图结构上进行高效计算。
result: GRG v2文件体积比PGEN小8倍以上，且grapp在处理英国生物样本库数据时，PCA运行速度提升了两个数量级。
conclusion: GRG v2与grapp的结合为大规模基因组分析提供了超越传统格式的扩展性和方法论灵活性。
---

## 摘要
生物样本库规模队列的全基因组测序 (WGS) 产生的数据集，传统的表格化基因型格式已无法高效存储或分析。基因型表示图 (GRGs) 提供了一种极具吸引力的替代方案：这是一种受生物学启发、分层的、基于图的表示方法，能够紧凑且无损地编码基因型，并支持直接在图上而非实体化的基因型矩阵上进行计算。在此，我们介绍了两项进展，共同使 GRG 成为生物样本库规模群体遗传学和统计遗传学的实用基础。首先，我们提出了 GRG v2，这是一种经过大幅改进的格式和构建算法，可将构建时间缩短 10-20 倍，将生成文件的磁盘和内存占用减半，并将加载速度提高 20 倍以上。应用于最近完成相位化 (phased) 的英国生物样本库 (UK Biobank) WGS 数据集（490,541 人，706,556,181 个变异位点），GRG v2 生成的文件比 .vcf.gz 小 25 倍，比 PLINK2 的 PGEN 格式小 8 倍以上，而构建成本不足 90 英镑。其次，我们推出了 grapp，这是一个 Python 库和命令行工具，利用 GRG 的计算优势进行常规分析和新方法开发。grapp 提供了变异和样本过滤、带协变量的全基因组关联研究 (GWAS)、主成分分析 (PCA) 以及数据导出的标准流水线，所有这些均作为基于图的操作实现。此外，它提供了与 numpy 和 scipy 稀疏线性代数生态系统集成的线性算子，能够通过底层的 GRG 实现针对标准化基因型矩阵、连锁不平衡 (LD) 矩阵和遗传亲缘关系矩阵的隐式矩阵乘法。利用这些算子，基于 scipy 的 PCA 仅需四行 Python 代码即可实现，运行速度比现有方法快 51-492 倍，且内存占用更低。对英国生物样本库中 89,988,512 个变异位点进行 PCA 仅需 2 到 4 小时。这种可扩展性使我们能够引入一种用于 GWAS 协变量构建的“留一染色体法” (LOCO)，在无需进行 LD 剪枝的情况下避免 LD 伪影。总之，GRG v2 和 grapp 实现了传统基因型格式无法达到的可扩展性和方法论灵活性。

## Abstract
Whole-genome sequencing (WGS) of biobank-scale cohorts have generated datasets that traditional tabular genotype formats cannot efficiently store or analyze. Genotype Representation Graphs (GRGs) offer a compelling alternative: a biologically-motivated, hierarchical, graph-based representation that compactly and losslessly encodes the genotypes, and that supports computation directly on the graph rather than on a materialized genotype matrix. Here we introduce two advances that together make GRG a practical foundation for biobank-scale population and statistical genetics. First, we present GRG v2, a substantially improved format and construction algorithm that reduces construction time by 10-20x, halves the disk and RAM footprint of the resulting files, and improves load time by more than 20x. Applied to the recently phased UK Biobank WGS dataset (490,541 individuals, 706,556,181 variants), GRG v2 produces files 25 times smaller than .vcf.gz and more than 8 times smaller than PLINK2's PGEN format, while costing less than 90 GBP to construct. Second, we introduce grapp, a Python library and command-line tool that exploits the computational advantages of GRG for both routine analyses and new method development. grapp provides standard pipelines for variant and sample filtering, genome-wide association studies (GWAS) with covariates, principal component analysis (PCA), and data export, all implemented as graph-based operations. Moreover, it provides linear operators that integrate with the numpy and scipy sparse linear algebra ecosystem, enabling implicit matrix multiplication against the standardized genotype matrix, the linkage disequilibrium matrix, and the genetic relatedness matrix all via an underlying GRG. Using these operators, scipy-based PCA can be implemented in four lines of Python and runs 51-492x faster than existing methods while using less RAM. PCA on 89,988,512 variants in the UK Biobank runs in two to four hours. This scalability allows us to introduce a leave-one-chromosome-out (LOCO) approach to GWAS covariate construction that avoids LD artifacts without requiring LD pruning. Together, GRG v2 and grapp enable a level of scalability and methodological flexibility that is not achievable with traditional genotype formats.

---

## 论文详细总结（自动生成）

以下是对论文《General, orders-of-magnitude faster whole-genome analysis with genotype representation graphs》的结构化总结：

### 1. 论文的核心问题与整体含义
*   **研究背景**：随着生物样本库（如 UK Biobank）规模的扩大，全基因组测序（WGS）数据已达到数十万样本和数亿变异位点的量级。
*   **核心问题**：传统的表格化基因型存储格式（如 VCF、PLINK2 的 PGEN）在处理此类超大规模数据时，面临存储空间占用巨大、I/O 效率低下以及计算性能（如 PCA、GWAS）遭遇瓶颈的问题。
*   **整体含义**：本文提出了 **GRG v2** 格式及其配套工具 **grapp**，旨在通过一种受生物学启发的“分层图结构”来无损压缩基因型数据，并允许直接在图结构上进行高效的线性代数运算，从而实现数量级的分析提速。

### 2. 方法论
*   **核心思想**：利用基因组中的单倍型共享特性，将基因型矩阵表示为有向无环图（DAG）。图中的节点代表特定的变异集合（单倍型），边代表包含关系。
*   **关键技术细节**：
    *   **GRG v2 构建算法**：通过分层构建（Build）算法，识别样本间共享的变异集合。利用集合交集（$\cap$）和差集（$\setminus$）操作提取“残余单倍型”，显著减少了冗余节点的生成。
    *   **隐式矩阵乘法**：`grapp` 并不将图还原为原始矩阵，而是利用图的结构直接实现与向量的乘法（$y = Gx$）。这种操作在数学上等同于在基因型矩阵上进行运算，但计算复杂度大幅降低。
    *   **线性算子（Linear Operators）**：将 GRG 封装为兼容 `scipy.sparse.linalg` 的线性算子，支持对标准化基因型矩阵、LD 矩阵和遗传亲缘关系矩阵（GRM）进行隐式运算。
*   **算法流程**：从相位化（phased）数据（如 VCF 或 IGD）出发 -> 构建分层图 -> 存储为压缩的 GRG v2 格式 -> 使用 `grapp` 调用线性代数库进行下游分析。

### 3. 实验设计
*   **数据集**：
    1.  **模拟数据**：包含 1.45M 至 23.7M 个变异位点，样本量从 1,000 到 100,000 不等。
    2.  **真实数据**：英国生物样本库（UK Biobank）WGS 数据集，包含 490,541 个个体和约 7.06 亿个变异位点。
*   **Benchmark（对比方法）**：
    *   **存储**：与 VCF.gz、PLINK2 (PGEN) 进行文件大小对比。
    *   **计算**：与 PLINK2、GCTA（FastPCA 逻辑）在 PCA 和 GWAS 任务上进行速度和内存对比。
*   **场景**：文件构建效率、PCA 运行耗时、带协变量的 GWAS 准确性、LOCO（留一染色体）分析。

### 4. 资源与算力
*   **算力使用**：
    *   在构建 UK Biobank 的 GRG v2 时，使用了 **64 到 70 个线程**。
    *   **成本**：在云端构建 50 万人规模的 GRG 成本低于 **90 英镑**。
*   **内存占用**：实验强调了其极低的内存需求，例如在处理 50 万样本的 PCA 时，内存占用远低于传统方法。
*   **GPU**：文中未提及使用 GPU，主要基于多核 CPU 和高效的内存管理。

### 5. 实验数量与充分性
*   **实验规模**：
    *   进行了不同样本量（1k, 5k, 10k, 50k, 100k）的扩展性测试。
    *   针对 UK Biobank 全自动体染色体进行了完整测试。
    *   对比了过滤（MAF > 0.05）与未过滤数据的性能差异。
*   **充分性评价**：实验设计非常充分且具有说服力。作者不仅验证了计算速度的提升（51-492倍），还通过 Manhattan 图和相关性分析验证了结果的生物学准确性（与 PLINK2 结果一致）。

### 6. 主要结论与发现
*   **存储优势**：GRG v2 文件比 PGEN 小 8 倍以上，比 VCF.gz 小 25 倍。
*   **计算飞跃**：在 UK Biobank 数据上，PCA 运行时间从数天/周缩短至 **2-4 小时**。
*   **方法论创新**：由于计算效率极高，可以实现以往难以负担的 **LOCO PCA**（针对每条染色体分别计算除其之外的全局 PC 作为协变量），有效消除了长程 LD 导致的伪影，且无需进行 LD 剪枝。
*   **易用性**：`grapp` 库允许用户仅用几行 Python 代码即可调用复杂的线性代数运算。

### 7. 优点
*   **极高性能**：通过图运算避开了显式矩阵运算的瓶颈，实现了真正的数量级提速。
*   **无损性**：与某些通过降采样或近似计算提速的方法不同，GRG 是对原始数据的无损表示。
*   **生态集成**：完美对接 Python 的科学计算生态（Numpy/Scipy），降低了开发新统计遗传学方法的门槛。
*   **低成本**：显著降低了大规模基因组研究的计算和存储开销。

### 8. 不足与局限
*   **数据要求**：目前主要针对**相位化（phased）**数据。虽然 WGS 数据通常会进行相位化处理，但对于未相位化的数据，其压缩率和计算优势可能会打折扣。
*   **构建开销**：虽然构建一次后受益无穷，但初始构建 GRG 仍需要一定的计算资源（尽管已比 v1 大幅优化）。
*   **应用范围**：目前主要展示了 PCA 和 GWAS 的优势，对于更复杂的非线性模型或特定类型的罕见变异分析，其表现尚需进一步验证。

（完）
