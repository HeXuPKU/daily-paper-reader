---
title: "fastman: A Fast Algorithm for Visualising GWAS Results Using Manhattan and Q-Q Plots in R"
title_zh: fastman：一种在 R 中使用曼哈顿图和 Q-Q 图快速可视化 GWAS 结果的算法
authors: "Paria, S. S., Rahman, S. R., Adhikari, K."
date: 2026-04-20
pdf: "https://www.biorxiv.org/content/10.1101/2022.04.19.488738v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 使用曼哈顿图和Q-Q图可视化GWAS结果的算法
tldr: 针对现有GWAS可视化工具在处理非模型生物、复杂基因组及大规模数据集时的局限，本文推出了R包fastman。该工具采用启发式算法显著提升绘图速度，支持非数值染色体ID、支架序列以及FST、D-stats等多种遗传统计量的可视化，并提供灵活的标注功能，为基因组研究提供了高效、全面的绘图方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有工具在处理非模型生物草图基因组、非数值染色体ID及多样化遗传评分时存在显著局限。
method: 开发了集成启发式算法的R包fastman，旨在不损失视觉精度的前提下极速处理大规模数据集。
result: 实现了对复杂基因组结构、负值统计量及多种遗传指标的高效绘图，并增强了高亮和注释的灵活性。
conclusion: fastman是一个功能强大且快速的R语言工具，极大地扩展了GWAS及群体遗传学结果的可视化能力。
---

## 摘要
GWAS 汇总统计数据（特别是 P 值）以曼哈顿图的形式进行可视化在 GWAS 出版物中非常普遍，并且已有许多流行的软件工具，例如 R 包 qqman。然而，仍有进一步开发的重大需求，例如处理来自非模式生物的数据集。我们提供了一个新的 R 包 fastman，与现有软件包相比，它具有显著的额外功能。例如，它可以处理涉及非模式生物基因组的数据集，即使是在由大量尚未组装成染色体的 contig 和 scaffold（较短的组装 DNA 序列片段）组成的草图阶段。该包还支持非数字染色体 ID。此外，我们的软件包能够绘制其他遗传评分，例如其他 GWAS 统计量（如回归 beta 值或比值比）、固定指数（FST）、D 统计量以及各种选择统计量（如 PBS）。重要的是，该软件包支持负值或双尾值。在我们的软件包中，我们实现了一种启发式算法，在不损失视觉精度的前提下，大幅缩短了海量数据集的绘图时间，并支持多种不同的数据类型和缺失数据。我们还在高亮显示和注释方面提供了极大的额外灵活性。该包可以直接根据 PLINK 的关联分析输出生成图表。或者，它可以从任何具有自定义列的 R 数据框生成图表，并能处理大型数据集以快速生成图表。它可在 https://github.com/adhikari-statgen-lab/fastman 公开使用。

## Abstract
Visualisation of GWAS summary statistics, specifically P-values, as Manhattan plots are widespread in GWAS publications, and many popular software tools are available, such as the R package qqman. However, there is a substantial need for further development, such as handling datasets from non-model organisms. We provide a new R package, fastman, with major additional capabilities compared to currently available packages. For example, it handles datasets involving genomes from non-model organisms, even at a draft stage consisting of numerous contigs and scaffolds (shorter stretches of assembled DNA sequences) that have not been compiled into chromosomes. Non-numeric chromosome IDs are also supported. Additionally, our package has the capability of plotting other genetic scores, such as other GWAS statistics (e.g. regression betas or odds ratios), fixation index(FST), D-statistics, and various selection statistics, such as PBS. Importantly, negative or two-tailed values are supported in this package. In our package, we implement a heuristic algorithm that drastically reduces plotting time for huge datasets without losing visual precision, allowing for many different data types and missing data. We also provide substantial additional flexibility in highlighting and annotation. The package can produce plots directly from association outputs by PLINK. Alternatively, it can produce plots from any R data frame with custom columns and can handle large datasets to generate plots rapidly. It is available for public use at https://github.com/adhikari-statgen-lab/fastman.

---

## 论文详细总结（自动生成）

这是一份关于论文 **《fastman: A Fast Algorithm for Visualising GWAS Results Using Manhattan and Q-Q Plots in R》** 的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
全基因组关联研究（GWAS）产生的数据量呈爆炸式增长，单个研究往往涉及数千万个遗传变异。现有的 R 语言可视化工具（如最流行的 `qqman`）在处理大规模数据集时存在显著瓶颈：
*   **性能低下**：处理数百万个 SNP 时绘图速度极慢，耗时可达数十分钟。
*   **兼容性差**：通常仅支持数值型染色体 ID，无法处理非模型生物（如植物、昆虫）的草图基因组（包含大量非数字命名的 contigs 或 scaffolds）。
*   **功能局限**：大多仅支持 P 值绘图，难以直接处理固定指数（$F_{ST}$）、D-statistics、回归系数（Beta）或比值比（OR）等具有不同分布特征或包含负值的遗传评分。

`fastman` 的开发动机是提供一个既能保持视觉精度，又能极速处理海量数据，且广泛兼容非模型生物和多种统计指标的可视化工具。

### 2. 论文提出的方法论
`fastman` 的核心思想是利用**启发式数据压缩算法**减少绘图点数，而不损失视觉上的精确度。

*   **视觉精度舍入（Rounding）**：基于显示器分辨率（DPI）的限制，微小的坐标偏移在视觉上是不可见的。算法将 Y 轴（如 $-\log_{10}P$）和 X 轴（染色体位置）的值进行舍入。
*   **自适应尾部识别**：
    *   算法通过计算统计量 $R$（右尾）和 $L$（左尾）来识别数据的分布特征：
        $$R = \frac{P_{100} - P_{99.8}}{P_{99.8} - P_{50}}, \quad L = \frac{P_0 - P_{0.2}}{P_{0.2} - P_{50}}$$
    *   如果 $R$ 或 $L > 0.1$，则判定存在显著尾部。
    *   **分段精度控制**：对于显著的“尾部”（即研究者关注的高显著性区域），保留 3 位小数精度；对于“主体”部分（非显著区域），保留 2 位小数精度。
*   **去重处理**：舍入后，大量重叠的点被合并为唯一值，极大地减少了传递给绘图引擎的数据行数。
*   **技术集成**：支持 `ggplot2` 架构，并集成 `scattermore` 包（利用栅格化技术进一步加速）和 `Cairo` 绘图引擎（提升图像质量）。

### 3. 实验设计
*   **数据集**：
    1.  **人类 GWAS 数据**：包含约 878 万个 SNP 的真实研究数据（面部毛发密度关联分析）。
    2.  **非模型生物数据**：熊蜂（*Bombus terrestris*）的关联分析结果，包含 760 个非数字命名的 contigs。
*   **Benchmark（基准）**：
    *   主要对比对象：`qqman`（行业标准）。
    *   其他对比对象：`fastman (Daniel)`（另一种通过随机抽样加速的包）、`raMWAS`、`car::qqPlot` 等。
*   **对比指标**：绘图总耗时（秒）、内存占用（MB）、绘图点数与原始数据量的关系。

### 4. 资源与算力
*   论文**未明确说明**具体的硬件配置（如 CPU 型号、内存大小）。
*   实验是在 R 环境下进行的，强调了该工具在普通个人电脑或高性能计算集群（HPC）上的适用性。
*   特别提到设计了“Vanilla R”版本，无需安装复杂依赖（如 `tidyverse`），方便在权限受限的服务器上通过 `source()` 直接调用。

### 5. 实验数量与充分性
*   **实验规模**：针对时间性能测试，每个包/函数均运行了 **100 次迭代**以获取中位数耗时，确保了结果的稳定性。
*   **覆盖范围**：实验涵盖了曼哈顿图和 Q-Q 图，测试了 P 值、Beta 值、OR 值、$F_{ST}$ 等多种数据分布。
*   **客观性**：通过随机子集测试（从 1% 到 100% 数据量）验证了算法耗时与数据量之间的线性关系，以及绘图点数与原始数据量的对数关系，证明了其在大规模数据下的优势。

### 6. 论文的主要结论与发现
*   **极速提升**：在处理 880 万个 SNP 时，`fastman` 耗时约 **57 秒**，而 `qqman` 需 **834 秒**，速度提升超过 14 倍。
*   **内存优化**：尽管增加了启发式计算步骤，但由于有效减少了绘图点数，其内存占用仍低于 `qqman`。
*   **视觉无损**：与随机抽样加速法不同，`fastman` 的舍入算法在标准分辨率下生成的图像与原始全量数据绘图在视觉上完全一致。
*   **全能兼容**：成功实现了对非数字染色体 ID 的支持，解决了非模型生物研究的痛点。

### 7. 优点
*   **高性能与高精度平衡**：通过舍入而非抽样，兼顾了速度与结果的准确性。
*   **极高的灵活性**：支持双向图（处理正负 Beta 值）、自定义基准线、基因名称注释等。
*   **低门槛使用**：语法高度兼容 `qqman`，用户迁移成本极低；提供 `ggplot2` 接口，方便后续定制。
*   **鲁棒性**：内置缺失值处理机制，避免了因数据不洁导致的绘图中断。

### 8. 不足与局限
*   **栅格化副作用**：当开启 `scattermore` 模式时，如果参数设置不当，图像在高分辨率缩放时可能会出现轻微的颗粒感或模糊。
*   **功能尚待完善**：目前尚未直接内置“迈阿密图”（Miami plots，用于对比两个 GWAS 结果）功能（作者表示将在未来版本加入）。
*   **语言限制**：目前仅限于 R 语言，尚未提供 Python 等其他流行数据科学语言的接口。

（完）
