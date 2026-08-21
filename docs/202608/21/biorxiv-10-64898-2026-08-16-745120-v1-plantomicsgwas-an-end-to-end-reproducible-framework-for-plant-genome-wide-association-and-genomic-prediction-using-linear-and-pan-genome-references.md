---
title: "PlantOmicsGWAS: An end-to-end, reproducible framework for plant genome-wide association and genomic prediction using linear and pan-genome references"
title_zh: PlantOmicsGWAS：基于线性与泛基因组参考的植物全基因组关联分析与基因组预测的端到端可重复框架
authors: "Khan, F. S., Yassin, A., Rehman, S. u., Sun, T., Wang, X., Sun, H., Abe-Kanoh, N., Su, Y. H., Guo, L., Ye, W."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.16.745120v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 面向植物GWAS与基因组预测的端到端可重复框架，直接对应GWAS统计方法与算法需求
tldr: 植物全基因组关联分析常受工具碎片化、格式不一和计算环境差异影响，现有框架多局限于单一线性参考基因组，难以解析结构变异与存在/缺失变异。PlantOmicsGWAS是一个开源Python框架，整合从索引构建到可视化的完整流程，支持线性参考与泛基因组模块。在葡萄基准数据上，该框架减少了人工流程碎片化，产出标准化关联结果，并支持多种关联测试与机器学习方法，提升了可重复性与可扩展性。
source: biorxiv
selection_source: fresh_fetch
motivation: 植物GWAS分析工具异构、格式不兼容，且传统线性参考框架无法解析结构变异和PAV，阻碍可重复性与全面研究。
method: 构建集成式Python框架，统一索引、比对、变异 calling、关联测试、预测和可视化，支持线性参考与泛基因组图变异分析。
result: "在含120个葡萄品系和118,247个图变异的数据上，减少人工流程碎片化，生成标准化关联输出，兼容多种方法。"
conclusion: PlantOmicsGWAS提供模块化可扩展平台，提升植物GWAS可重复性，适用多种测序策略和基因组，服务从个体到群体的研究。
---

## 摘要
全基因组关联分析（GWAS）在揭示植物复杂性状的遗传基础中发挥着关键作用，但也因异构工具、不兼容的文件格式和不同的计算环境的应用而受到阻碍。现有的GWAS框架通常局限于单一的线性参考基因组，限制了对植物群体内结构变异和存在/缺失变异（PAV）的分析能力。这些问题对可重复性、可扩展性和全面研究构成了障碍。在此，我们提出PlantOmicsGWAS，一个用于可重复的植物全基因组关联分析和基因组预测的开源Python框架。它在统一的Linux和HPC工作流中集成了参考索引、FASTQ质量控制、比对、变异检测、VCF标准化、PLINK转换、连锁不平衡分析、群体结构估计、关联检验、标记评分、基因组预测和可视化。该框架支持传统的线性参考分析，并包含一个可选的泛基因组导向模块，用于处理多组装和基于图的变异。利用包含120个品种和118,247个基于图的变体的Vitis基准数据集，PlantOmicsGWAS减少了手动工作流的碎片化，并生成了标准化的关联输出。该工具为植物GWAS和泛GWAS工作流提供了一个模块化和可扩展的平台，同时保持与既有命令行工具和常见基因型格式的兼容性。本文所述的GWAS工作流适用于多种测序方法和植物基因组，将作物相关问题的研究从个体生物水平桥接到整个群体水平。PlantOmicsGWAS通过GEMMA实现了贝叶斯稀疏线性混合模型（BSLMM）进行多性状关联发现，同时支持FaST-LMM、基于回归的方法以及机器学习算法（随机森林、XGBoost）作为基准替代方案。PlantOmicsGWAS是一个多功能工具包，可在GitHub https://github.com/plantomicsgwas1-boop/PlantOmicsGwas_V1 以及Linux和HPC平台（https://pypi.org/project/PlantOmicsGwas/1.0.2/）上获取。

## Abstract
Genome-wide association studies (GWAS) play a crucial role in unraveling the genetic foundations of complex traits in plants but are also hampered by the application of heterogeneous tools, incompatible file formats and disparate computational environments. Existing GWAS frameworks are often restricted to a single linear reference genome, limiting the capacity for the analysis of structural variations and presence/absence variations (PAV) within plant populations. These issues pose obstacles to reproducibility, scalability, and comprehensive investigations. Here, we present PlantOmicsGWAS, an open-source Python framework for reproducible plant genome-wide association analysis and genomic prediction. It integrates reference indexing, FASTQ quality control, alignment, variant calling, VCF normalization, PLINK conversion, linkage disequilibrium analysis, population-structure estimation, association testing, marker scoring, genomic prediction, and visualization within a unified Linux and HPC workflow. The framework supports conventional linear-reference analyses and includes an optional pangenome-oriented module for working with multiple assemblies and graph-derived variation. Using a Vitis benchmark dataset containing 120 accessions and 118,247 graph-derived variants, PlantOmicsGWAS reduced manual workflow fragmentation and generated standardized association outputs. This tool provides a modular and extensible platform for plant GWAS and pan-GWAS workflows while retaining compatibility with established command-line tools and common genotype formats. The GWAS workflow described herein is adaptable to a range of sequencing methods and plant genomes, bridging research on crop related issues across various biological levels, from the individual organism to entire populations. PlantOmicsGWAS implements Bayesian sparse linear mixed modeling (BSLMM) through GEMMA for multi-trait association discovery, while also supporting FaST-LMM, regression-based approaches, and machine-learning algorithms (Random Forest, XGBoost) as benchmarking alternatives. The PlantOmicsGWAS, a versatile toolkit is available at GitHub https://github.com/plantomicsgwas1-boop/PlantOmicsGwas_V1 and on Linux and HPC platform (https://pypi.org/project/PlantOmicsGwas/1.0.2/).

---

## 论文详细总结（自动生成）

# PlantOmicsGWAS 论文详细总结

## 1. 论文的核心问题与整体含义

- **研究背景**：全基因组关联分析（GWAS）是解析植物复杂性状遗传基础的关键工具，但现有 GWAS 分析流程存在严重碎片化问题——数据分析依赖多种异构工具，文件格式互不兼容，运行环境差异大，严重阻碍了分析的可重复性。
- **核心痛点**：现有 GWAS 框架大多局限于单一线性参考基因组，无法有效处理植物群体中的**结构变异（SV）**和**存在/缺失变异（PAV）**，而这些变异类型对植物表型多样性的贡献不可忽视。
- **研究目标**：该论文旨在开发一个端到端的、可重复的、模块化的开源框架 PlantOmicsGWAS，统一植物 GWAS 与基因组预测的完整分析流程，同时支持传统的线性参考基因组分析与新兴的泛基因组（pan-genome）图变异分析。

## 2. 方法论：核心思想、技术细节与算法流程

- **核心思想**：通过构建一个高度集成的 Python 框架，将 GWAS 全流程的各个步骤在统一的计算环境（Linux 和 HPC 工作流）中串联起来，以消除工具碎片化和格式转换障碍。
- **集成的主要流程模块**（采用流水线式设计）：
  1. **参考索引构建**：支持多种植物基因组的索引构建。
  2. **FASTQ 质量控制**：对原始测序数据进行质量评估与过滤。
  3. **序列比对（Alignment）**：将 reads 比对到参考基因组或泛基因组图。
  4. **变异检测（Variant Calling）**：识别 SNP、InDel 等变异，泛基因组模块支持基于图的变异（graph-derived variants）。
  5. **VCF 标准化**：统一 VCF 文件格式，保证下游兼容性。
  6. **PLINK 格式转换**：将 VCF 转换为 PLINK 格式，便于关联分析。
  7. **连锁不平衡（LD）分析**：评估标记间的连锁不平衡模式。
  8. **群体结构估计**：计算亲缘关系矩阵和种群结构主成分，用于校正 GWAS 模型（控制假阳性）。
  9. **关联检验（Association Testing）**：
     - 通过 GEMMA 实现**贝叶斯稀疏线性混合模型（BSLMM）**，支持多性状关联发现；
     - 同时支持 **FaST-LMM**；
     - 支持基于回归的关联方法；
     - 提供**机器学习替代基准**：随机森林（Random Forest）、XGBoost。
  10. **标记评分（Marker Scoring）**：对显著关联位点进行评估和排名。
  11. **基因组预测（Genomic Prediction）**：基于基因型数据对表型进行预测。
  12. **可视化**：生成曼哈顿图、QQ 图等标准 GWAS 可视化结果。
- **双参考模块设计**：
  - **线性参考模块**：支持传统的单参考基因组分析流程；
  - **泛基因组模块**：支持多组装和基于图（graph-based）的变异分析，从而捕捉传统线性参考框架丢失的结构变异和 PAV。
- **兼容性设计**：保留与既有命令行工具和通用基因型格式（如 VCF、PLINK）的兼容性，降低用户迁移成本。

## 3. 实验设计：数据集、Benchmark 与对比方法

- **数据集**：采用 **Vitis（葡萄）基准数据集**，包含 **120 个葡萄品种/品系（accessions）**和 **118,247 个基于图的变异（graph-derived variants）**。
- **Benchmark 评估方式**：论文未采用传统"预测精度对比"的 benchmark，而是以**工作流整合度和输出标准化**为评价标准，核心是检验框架能否减少人工流程碎片化并生成标准化关联输出。
- **所涉及的方法对比**：
  - BSLMM（通过 GEMMA 实现）作为多性状关联发现的主要方法；
  - FaST-LMM、回归方法、随机森林和 XGBoost 作为基准替代方案（benchmarking alternatives），用于横向比较关联发现结果。
- **说明**：由于论文摘要未披露全部实验细节，可确认的实验场景主要围绕这一组 Vitis 数据集展开，验证了框架在真实植物数据上的端到端可用性。

## 4. 资源与算力

- **文中未明确披露具体的算力信息**，例如：
  - 使用的 GPU 型号与数量；
  - CPU 核心数、内存配置；
  - 各步骤（比对、变异 calling、关联分析）的具体运行耗时；
  - 机器学习方法（随机森林、XGBoost）训练的算力开销。
- **可推测的信息**：框架面向 Linux 和 HPC 平台设计，暗示其预期在高性能计算集群上运行；但论文没有报告任何定量资源消耗指标，因此无法评估其在超大数据集上的计算效率表现。

## 5. 实验数量与充分性

- **实验数量有限**：目前可确认的实验数据仅为**一个 Vitis 基准数据集（120 个品种，118,247 个变异）**。
- **缺少的实验类型**：
  - 未提及在多个不同植物物种上的跨物种验证；
  - 未见消融实验（如分别评估线性参考 vs. 泛基因组模块的效果差异）；
  - 未见大规模的 GWAS 结果与已有公开 GWAS 研究的系统性对比；
  - 机器学习方法（RF、XGBoost）在此框架中的具体性能对比分析细节不明确。
- **客观性与公平性评估**：论文在单一数据集上验证了框架的可用性和流程整合能力，结论在功能层面是成立的，但**系统性对比不足**，对方法精度、假阳性控制能力、在不同遗传结构群体下的表现评价尚不充分。因此，从严格的 benchmark 角度而言，实验覆盖度仍显薄弱。

## 6. 论文的主要结论与发现

- PlantOmicsGWAS 成功将植物 GWAS 和泛 GWAS 工作流整合到一个模块化、可扩展的开源平台中。
- 在 Vitis 基准数据集上，该框架显著**减少了手动工作流的碎片化**，生成**标准化的关联分析输出**。
- 框架同时支持线性参考和泛基因组参考，弥补了现有工具无法分析结构变异和 PAV 的缺口。
- 支持多种关联分析方法（BSLMM、FaST-LMM、回归、机器学习），为用户提供灵活的方法选择空间。
- 框架适用于多种测序方法和植物基因组，能够在不同生物学层面（个体到群体）桥梁式地支撑作物相关研究。

## 7. 优点

- **端到端集成**：从原始测序数据（FASTQ）到最终可视化结果全覆盖，显著降低了流程碎片化和工具切换成本。
- **双参考支持**：同时兼容线性参考基因组与泛基因组图变异，对植物 PAV/SV 研究具有重要意义。
- **模块化与可扩展性**：各流程模块可独立替换或扩展，便于后续增加新方法。
- **方法多样性**：集成了混合线性模型（BSLMM、FaST-LMM）、传统回归方法和机器学习算法（RF、XGBoost），为用户提供多方法互为验证的能力。
- **兼容性强**：与现有常用工具和基因型格式（VCF、PLINK）兼容，降低了使用门槛。
- **开源可获取**：代码托管在 GitHub 和 PyPI 上，符合可重复性研究的基本要求。

## 8. 不足与局限

- **实验验证覆盖不足**：仅在单一物种、单一数据集上进行了演示，缺乏对模型在多种植物基因组（如水稻、玉米、小麦等）上的普适性和稳健性验证。
- **缺乏系统性对比**：没有与传统主流 GWAS 管道（如 GAPIT、TASSEL、PLINK 全流程）进行定量对比（如运行时间、内存占用、灵敏度、特异度），"减少碎片化"的改进缺乏量化证据。
- **算力消耗未量化**：未报告关键步骤的计算资源消耗，难以评估在大型群体（数万个体）上的可扩展性和实用性。
- **机器学习方法细节缺失**：随机森林和 XGBoost 的参数设置、超参数调优策略、训练/测试划分方式等细节未在摘要中体现，影响结果的可复现性。
- **应用门槛**：尽管声称"端到端"，但重新实现并整合这些复杂工具存在维护成本；用户仍需要必要的生物信息学知识来诊断中间步骤可能出现的错误。

（完）
