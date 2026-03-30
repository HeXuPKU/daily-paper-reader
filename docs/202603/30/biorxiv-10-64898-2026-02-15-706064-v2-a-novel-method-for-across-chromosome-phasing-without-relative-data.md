---
title: A Novel Method for Across-Chromosome Phasing without Relative Data
title_zh: 一种无需亲属数据的跨染色体定相新方法
authors: "Sapin, E., Kelly, K., keller, m."
date: 2026-03-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.15.706064v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 无需亲属数据的跨染色体相位分析
tldr: "跨染色体定相旨在确定不同染色体的单倍型是否来自同一父母。针对无亲属数据的无关个体，本文提出一种基于窗口SNP相似性度量的新方法，无需依赖亲缘关系或IBD检测。在UK Biobank数据测试中，该方法在无染色体内定相错误时准确率达95%，即使使用计算预定相数据，准确率也达到83.1%，为大规模人群遗传学研究提供了有力工具。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-02-15-706064-v2/fig-001.webp\", \"caption\": \"Figure 2: Violin plots of ACPA scores for trio offspring. The left half of each plot shows the ACPA scores for trio offspring when using the method of Noto et. al. while the right part of each violin shows ACPA scores using our method. The bottom plot shows results when input data has no within-chromosome phasing errors, while the top plot shows results when within-chromosome phasing errors are present. For each focal individual, color indicates the highest degree of relatedness (based on π̂) to any non-focal individual.\", \"page\": 6, \"index\": 1, \"width\": 641, \"height\": 1268}]"
motivation: 现有的跨染色体定相方法在缺乏亲属数据或无关个体样本中表现不佳。
method: 提出一种基于窗口SNP相似性度量的新算法，无需亲属数据即可实现跨染色体单倍型匹配。
result: "在理想实验条件下准确率达95%，在实际计算预定相数据下准确率达到83.1%。"
conclusion: 该方法主要受限于染色体内定相的准确性，随着定相技术的进步，其跨染色体匹配精度将趋于完美。
---

## 摘要
动机：跨染色体定相旨在识别不同染色体的哪些单倍型来自同一双亲。这与染色体内定相不同，后者利用连锁不平衡模式来确定每条染色体内哪些等位基因是共同遗传的，但并不匹配不同染色体间的单倍型。虽然可以利用父母或近亲的基因型进行跨染色体定相，但现有方法在处理无关个体的样本时表现较差。在此，我们介绍了一种跨染色体定相的新方法，该方法采用基于窗口的 SNP 相似性度量，消除了对近亲数据或血缘同源（IBD）单倍型检测的需求。结果：我们以父母双方均有基因型数据的 UK Biobank 后代作为金标准，在不使用父母数据的情况下对后代进行定相，从而评估了我们方法的性能。在没有染色体内定相错误的基因组数据中，我们的算法实现了 95% 的平均跨染色体定相准确率，其中 53% 的个体实现了完美定相。当使用标准的染色体内定相算法对数据进行预定相时，跨染色体定相的平均准确率下降到 83.1%。因此，我们的方法主要受限于染色体内定相的准确性，并且随着染色体内定相准确性的提高，可以接近完美的跨染色体定相准确率。

## Abstract
Motivation: Across-chromosome phasing identifies which haplotypes of different chromosomes come from the same parent. This differs from within-chromosome phasing, which uses linkage disequilibrium patterns to determine which alleles were co-inherited within each chromosome but does not match haplotypes across different chromosomes. While across-chromosome phasing can be conducted using genotypes from parents or close relatives, current methods perform poorly for samples of unrelated individuals. Here, we introduce a novel approach for across-chromosome phasing that employs a window-based SNP-similarity metric, eliminating the need for data from close relatives or detection of identical-by-descent haplotypes. Results: Using UK Biobank offspring with both parents genotyped as a gold standard, we evaluated the performance of our method by phasing the offspring without using parental data. In genomic data with no within-chromosomal phase errors, our algorithm achieved a mean across-chromosome phasing accuracy of 95%, with 53% of individuals phased perfectly. When data was pre-phased computationally using a standard within-chromosomal phasing algorithm, mean accuracy for across-chromosome phasing dropped to 83.1%. Thus, our method is limited primarily by the accuracy of within-chromosome phasing, and can approach near perfect across-chromosome phasing accuracy as within-chromosome phasing accuracy improves.

---

## 论文详细总结（自动生成）

以下是对论文《一种无需亲属数据的跨染色体定相新方法》（A Novel Method for Across-Chromosome Phasing without Relative Data）的结构化总结：

### 1. 论文的核心问题与整体含义
*   **核心问题**：传统的“染色体内定相”（Within-chromosome phasing）只能确定单条染色体上的等位基因组合，而无法确定不同染色体（如 1 号和 2 号染色体）的单倍型是否来自同一父母。现有的“跨染色体定相”（Across-chromosome phasing, ACPA）通常依赖于父母基因型数据或近亲的血缘同源（IBD）片段。
*   **研究动机**：在缺乏亲属数据的大规模人群研究中，如何准确地将不同染色体的单倍型归类为“父源”或“母源”组，是一个尚未很好解决的挑战。

### 2. 论文提出的方法论
*   **核心思想**：利用基于窗口的 SNP 相似性度量。该方法假设个体的单倍型与其父母所属的群体背景具有遗传相似性，通过将目标个体的单倍型与参考面板（Reference Panel）进行对比，计算相似性得分。
*   **关键技术细节**：
    *   **窗口划分**：将染色体划分为多个 SNP 窗口。
    *   **相似性评分**：对于目标个体的两个单倍型（H1 和 H2），计算它们与参考人群中其他个体单倍型的匹配程度。
    *   **跨染色体匹配**：通过比较不同染色体间单倍型在参考面板中的“共现”相似性模式，将得分最高的组合判定为来自同一遗传来源。
    *   **无需 IBD**：该方法不依赖于长片段的 IBD 检测，而是通过聚合全基因组范围内的微弱相似性信号来实现定相。

### 3. 实验设计
*   **数据集**：主要使用 **UK Biobank (UKB)** 数据。
*   **Benchmark（金标准）**：利用 UKB 中具有父母基因型数据的后代（Trio offspring）作为真值。在测试算法时，故意隐藏父母数据，仅凭后代数据进行定相，再与真值对比。
*   **对比方法**：与 **Noto et al. (2020)** 提出的现有跨染色体定相方法进行了对比。
*   **测试场景**：
    1.  **理想场景**：输入数据无染色体内定相错误（无 Switch Errors）。
    2.  **现实场景**：使用标准计算定相工具（如 SHAPEIT 或 Eagle）预处理后的数据（存在 Switch Errors）。

### 4. 资源与算力
*   **算力说明**：论文摘要和提取文本中**未明确说明**具体的 GPU 型号、数量或具体的训练/运行总时长。通常此类遗传学算法运行在高性能计算集群（HPC）的 CPU 节点上，但文中缺乏具体硬件参数。

### 5. 实验数量与充分性
*   **实验规模**：利用了 UK Biobank 的大规模样本，涵盖了不同亲缘关系程度（通过 $\hat{\pi}$ 衡量）的个体。
*   **充分性评价**：实验设计较为充分。作者不仅验证了算法在理想状态下的表现，还深入探讨了“染色体内定相错误”对跨染色体定相准确性的影响。通过对比不同亲缘关系背景下的表现，证明了该方法在真正“无关个体”上的有效性。

### 6. 论文的主要结论与发现
*   **准确率表现**：
    *   在**无染色体内错误**的情况下，平均准确率达到 **95%**，且 53% 的个体实现了全基因组完美定相。
    *   在**使用计算预定相数据**的情况下，平均准确率下降至 **83.1%**。
*   **核心发现**：跨染色体定相的精度高度依赖于染色体内定相的质量。Switch Error 是限制该方法性能的主要瓶颈。
*   **性能优势**：在处理无关个体时，该方法显著优于 Noto et al. 的方法（见 Figure 2 的小提琴图对比）。

### 7. 优点
*   **突破性**：消除了对亲属数据或长 IBD 片段的强制依赖，极大地扩展了跨染色体定相的应用范围（可用于孤立样本）。
*   **鲁棒性**：在无关个体样本中表现稳健，能够捕捉到微弱的群体遗传信号。
*   **前瞻性**：随着测序技术（如长读长测序）减少染色体内定相错误，该方法的准确率有望趋近 100%。

### 8. 不足与局限
*   **对预定相的依赖**：如果初始的染色体内定相存在较多 Switch Errors，跨染色体匹配的逻辑会受到严重干扰。
*   **参考面板需求**：虽然不需要亲属，但仍需要一个具有代表性的参考面板来计算相似性得分。
*   **计算复杂度**：基于窗口的全基因组扫描和相似性计算在处理数十万样本时可能存在计算开销（文中未详细讨论扩展性）。

（完）
