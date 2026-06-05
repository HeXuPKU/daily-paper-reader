---
title: Ultra-Fast Implementation of Multivariate GWAS in Genomic SEM Using Flexible Analytic Estimation
title_zh: 使用灵活解析估计的基因组结构方程模型中多变量GWAS的超快实现
authors: "de la Fuente, J., Rhemtulla, M., Mallard, T. T., Nivard, M., Grotzinger, A. D., Tucker-Drob, E. M."
date: 2026-06-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.729606v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 多变量GWAS方法，使用基因组结构方程模型
tldr: 多变量GWAS用于解析复杂遗传结构，但原有迭代估计方法计算量大、依赖高性能计算。本文提出基于封闭解析解的灵活估计方法，直接计算SNP效应。在M4 Max芯片的MacBook Pro上，约2分钟即可完成5个共同因子、13个表型的多变量GWAS（约100万SNP），速度提升超过800倍。新方法降低了计算门槛，已集成到GenomicSEM包并开放alpha测试。
source: biorxiv
selection_source: fresh_fetch
motivation: 原有多变量GWAS迭代估计计算耗时，严重依赖高性能计算集群，限制了其广泛应用。
method: 采用封闭解析解直接计算SNP效应，替代原有迭代估计器，避免迭代收敛问题。
result: 速度提升800倍，在普通笔记本上约2分钟完成5因子13表型的多变量GWAS（~100万SNP）。
conclusion: 新方法大幅降低计算需求，使多变量GWAS更易普及，已开源并附带教程供alpha测试。
---

## 摘要
许多医学、生理学和精神疾病的性状和障碍具有高度多基因性，并表现出复杂的遗传共享和分化模式。2018年，我们引入了基因组结构方程模型（Genomic SEM）作为一个正式框架和免费开源、基于R的软件，用于对连续和二元全基因组关联研究（GWAS）表型的多变量遗传结构进行建模，探究它们共同和独特的功能基因组途径，并利用表型间遗传关系的经验模型来指导多变量GWAS发现。在此，我们介绍了一种在Genomic SEM中估计多变量GWAS内SNP效应的封闭形式解析解。该估计器比现有的迭代估计器快800倍以上，大大减少了对高性能计算（HPC）的依赖。在配备M4 Max芯片的MacBook Pro笔记本电脑上，对13个表型背后的5个共同因子进行多变量GWAS（约100万个SNP）只需大约2分钟。随着本预印本的发布，我们正在向GenomicSEM包中的userGWAS函数添加一个解析估计选项，用于Alpha测试，并在我们的GitHub Wiki上提供教程。

## Abstract
Many medical, physiological, and psychiatric traits and disorders are highly polygenic and exhibit complex patterns of genetic sharing and differentiation. In 2018, we introduced Genomic Structural Equation Modelling (Genomic SEM) as a formal framework and free, open source, R-based software for modelling the multivariate genetic architecture of both continuous and binary Genome-Wide Association Study (GWAS) phenotypes, interrogating their joint and distinct functional genomic pathways, and leveraging empirical models of the genetic relations among phenotypes to guide multivariate GWAS discovery. Here we introduce a closed-form analytic solution for estimating SNP effects within multivariate GWAS in Genomic SEM. This estimator is over 800 times faster than the existing iterative estimator, drastically decreasing reliance on high performance computing (HPC). On a MacBook pro laptop with M4 Max chip, a multivariate GWAS (~1M SNPs) of 5 common factors underlying 13 phenotypes takes approximately 2 minutes. Concurrent with the release of this preprint, we are adding an analytic estimation option to the userGWAS function in the GenomicSEM package for alpha testing along with a tutorial on our GitHub wiki.

---

## 论文详细总结（自动生成）

# 论文总结：使用灵活解析估计的基因组结构方程模型中多变量GWAS的超快实现

## 1. 核心问题与整体含义

- **研究动机**：多变量GWAS能够解析复杂性状间的遗传共享与分化，但原有基于迭代估计的方法计算量巨大，严重依赖高性能计算（HPC）集群，限制了该方法在普通计算环境下的广泛应用。
- **整体含义**：本文提出封闭形式的解析解估计器，极大降低计算门槛，使多变量GWAS可在普通笔记本电脑上快速完成，有望推动复杂遗传结构研究的大规模普及。

## 2. 方法论

- **核心思想**：用封闭解析解直接计算多变量GWAS中每个SNP的效应，替代原有的迭代估计算法，从而避免迭代收敛问题和大量重复计算。
- **关键技术细节**：基于Genomic SEM框架，将多变量遗传协方差结构建模为公共因子模型，然后推导出SNP效应的显式代数表达式。该解析估计器可一步得到SNP对潜在因子的回归系数，无需多次迭代。
- **算法流程**（文字说明）：
  1. 基于GWAS汇总统计量构建多变量遗传协方差矩阵。
  2. 根据预设的因子结构（如5个共同因子）进行结构方程建模。
  3. 对每个SNP，利用封闭公式直接计算其对各因子的效应量（包括标准误）。
  4. 输出全基因组SNP效应结果，用于后续关联发现。

## 3. 实验设计

- **数据集/场景**：文中仅提及一个示例：对13个表型背后的5个共同因子进行多变量GWAS，使用约100万个SNP。**未明确说明具体使用的GWAS数据集来源（如UK Biobank、PGC等）**。
- **Benchmark**：对比原有基于迭代估计的实现（即Genomic SEM中的默认估计器）。速度提升超过800倍。
- **对比方法**：仅与自身旧方法对比，未与其他多变量GWAS方法（如MTAG、MOSTest等）进行外部比较。

## 4. 资源与算力

- **硬件**：测试设备为配备M4 Max芯片的MacBook Pro笔记本电脑（未提供GPU型号或数量，推测使用了CPU或M4 Max内置的GPU加速）。
- **时长**：上述5因子13表型~1M SNPs的多变量GWAS耗时约2分钟。
- **说明**：论文未明确提及训练/计算中的详细资源分配（如CPU核心数、内存等）。

## 5. 实验数量与充分性

- **实验数量**：文中仅报告了一个示例场景（13表型、5因子、1M SNPs）。**未提供多个不同规模、不同因子结构的对比实验，也未进行消融分析或模拟研究**。
- **充分性**：作为预印本/Alpha测试阶段的方法论文，实验覆盖非常有限。速度提升的夸张倍数（>800倍）基于单一场景，缺乏对不同模型复杂性、SNP数量、样本量下的系统验证。实验不充分，存在选择性报告风险。
- **公平性**：仅与自身旧迭代方法对比，未设置独立的基准或重复性验证，结果可能存在偏向。

## 6. 主要结论与发现

- 封闭解析解估计器比原有迭代估计器快800倍以上，可在普通笔记本电脑上2分钟内完成大规模多变量GWAS（5因子、13表型、~1M SNPs）。
- 大幅降低对高性能计算集群的依赖，使多变量GWAS分析更易访问和普及。
- 该方法已集成到GenomicSEM包的`userGWAS`函数中，并已开放Alpha测试和配套教程。

## 7. 优点

- **速度革命性提升**：从需要HPC集群数小时/天的计算缩减至笔记本几分钟，实用性极强。
- **降低技术门槛**：使得计算资源有限的实验室也能开展多变量GWAS分析。
- **易于集成与推广**：直接在已有GenomicSEM包中添加选项，用户可平滑过渡。
- **标准误差可直接计算**：解析解避免了迭代不收敛问题，提高了稳健性。

## 8. 不足与局限

- **实验验证不足**：仅展示一个示例，缺乏模拟数据验证、不同遗传架构下的性能测试、以及与现有其他多变量方法（如MTAG、MOSTest、GWAS by subtraction）的直接比较。
- **适用范围未明确**：封闭解是否适用于所有因子模型（如允许交叉载荷、相关残差等）？是否受SNP遗传力、样本重叠程度等影响？文中未讨论。
- **偏差风险**：可能是选择性展示最佳案例，未报告失败情况或性能波动。
- **Alpha测试阶段**：代码尚未正式发布，可能存在未发现的数值稳定性或准确性bug。
- **未提供完整的统计学理论推导**：仅宣称有解析解，但未在文中展示公式或证明，可复现性有待加强。
- **缺乏硬件细节**：M4 Max芯片的性能与典型HPC集群的GPU（如A100）相比如何？未进行横向对比。

（完）
