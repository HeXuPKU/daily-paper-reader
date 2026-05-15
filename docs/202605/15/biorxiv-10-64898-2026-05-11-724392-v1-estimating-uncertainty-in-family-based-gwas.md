---
title: Estimating uncertainty in family-based GWAS
title_zh: 估计基于家庭的 GWAS 中的不确定性
authors: "Miao, X., Edge, M. D., Harpak, A."
date: 2026-05-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.11.724392v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 用于估计家系GWAS和多基因评分中不确定性的统计方法
tldr: 传统的全基因组关联分析（GWAS）易受混杂因素影响，而基于同胞的GWAS（sib-GWAS）虽能减少混杂，但其效应估计值的波动性较大。准确量化这种不确定性对于多基因评分和因果推断至关重要。本研究探讨了sib-GWAS中不确定性的来源，发现效应异质性或异方差性会导致现有估算方法产生偏差。为此，作者提出了一种基于重采样的稳健方法，通过模拟和UK Biobank数据验证，证明该方法在各种场景下均能提供无偏的不确定性估计。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决基于同胞的GWAS在样本量较小时，因效应异质性和异方差性导致的不确定性估算偏差问题。
method: 提出了一种新的基于重采样（resampling-based）的方法，用于更准确地衡量sib-GWAS等位基因效应估计值的不确定性。
result: 发现现有方法在处理稀有变异或小样本时存在显著偏差，而新提出的重采样方法在所有测试场景下均表现出近似无偏性。
conclusion: 该研究揭示了家庭关联研究中不确定性的来源，并为遗传学研究提供了一个更稳健的统计工具。
---

## 摘要
标准的全基因组关联研究（GWAS）容易受到混杂因素的影响，包括群体分层、选择性交配和王朝效应。基于家庭的研究，如基于同胞的 GWAS（sib-GWAS），可以减轻此类混杂，并正成为区分直接遗传效应（即个体基因型对其自身表型的因果效应）与其他因素的首选工具。然而，部分由于样本量较小，sib-GWAS 的等位基因效应估计值比标准（即基于群体的）GWAS 估计值具有更大的变异性。这种不确定性的量化对于 sib-GWAS 的许多用途至关重要，包括多基因评分、因果推断（如孟德尔随机化）、区分直接与间接家庭效应以及衡量选择性交配。在本文中，我们研究了 sib-GWAS 等位基因效应估计量中不确定性的来源。我们研究了它们对三种不确定性测量方法偏差的影响，包括两种常用方法和我们提出的一种新的基于重采样的方法。我们发现，等位基因效应的异质性或家庭间的异方差性（例如，由于遗传背景或环境的差异）会使现有方法产生偏差，且这种偏差在小样本和罕见变异中更为严重。相比之下，我们提出的基于重采样的方法在所有考虑的情景下都是近似无偏的。我们利用模拟和英国生物样本库（UK Biobank）的实证分析验证了我们的理论预测，以及效应异质性和异方差性的重要性。总之，本研究有助于理解基于家庭的基因型-表型关联研究中不确定性的来源，并提供了一种稳健的不确定性估计方法。

## Abstract
Standard genome-wide association studies (GWASs) are vulnerable to confounding factors, including stratification, assortative mating, and dynastic effects. Family studies such as sibling-based GWAS (sib-GWAS) mitigate such confounding and are becoming the tool of choice for teasing apart direct genetic effects---causal effects of one's genotype on one's own phenotype---from other factors. However, due in part to their smaller sample sizes, sib-GWAS allelic effect estimates are substantially more variable than standard (i.e., population-based) GWAS estimates. The quantification of this uncertainty is essential for many uses of sib-GWAS, including polygenic scoring, causal inference (e.g., Mendelian randomization), disentangling direct from indirect familial effects, and measuring assortative mating. Here, we investigate sources of uncertainty in sib-GWAS allelic effect estimators. We study their impacts on the biases of three uncertainty measurement methods, including two that are commonly used and a new resampling-based approach we propose. We find that heterogeneity in allelic effects or heteroskedasticity across families (e.g., due to variation in genetic backgrounds or environments) can bias existing methods, and that this bias is more severe for small samples and rare variants. In contrast, the resampling-based approach we propose is approximately unbiased under all scenarios we considered. We validate our theoretical predictions, as well as the importance of effect heterogeneity and heteroskedasticity, using simulations and empirical analysis in the UK Biobank. In sum, this study helps understand the sources of uncertainty in family-based genotype-phenotype association studies and provides a robust method to estimate uncertainty.

---

## 论文详细总结（自动生成）

这篇论文对基于家庭的全基因组关联分析（family-based GWAS，特别是 sib-GWAS）中等位基因效应估计值的不确定性（方差）进行了深入的理论探讨与实证分析。

### 1. 论文的核心问题与整体含义
*   **研究动机**：虽然基于同胞的 GWAS（sib-GWAS）能有效消除群体分层、选择性交配等混杂因素，但其样本量通常较小，导致效应估计值的波动性（不确定性）远高于普通 GWAS。
*   **核心问题**：准确量化这种不确定性对于多基因评分（PGS）、孟德尔随机化和研究家庭间接效应至关重要。然而，现有的不确定性估计方法（如 OLS 和置换检验）在存在效应异质性或异方差性时可能存在显著偏差。
*   **整体含义**：论文旨在揭示这些偏差的来源，并提出一种更稳健的估计方法。

### 2. 论文提出的方法论
论文对比了三种估计等位基因效应估计值方差（$\text{Var}[\hat{\beta}_0]$）的方法：
*   **OLS 方法（普通最小二乘法）**：通过回归残差平方和来估计方差。
    *   **核心缺陷**：假设残差同方差。论文推导出其偏差与“异方差因子”（效应异质性 $\tau^2$ 和非焦点方差随基因型对比变化的斜率 $\sigma_1$ 之和）成正比。
*   **置换检验方法（Permutation）**：通过在家庭内部随机交换同胞表型来生成零分布。
    *   **核心缺陷**：假设零假设（效应为 0）成立。论文证明当真实效应 $\beta_0 \neq 0$ 时，该方法会产生向上的偏差。
*   **分块杰克刀法（Block Jackknife, BJK）**：**论文推荐的新方法**。
    *   **核心思想**：通过反复随机剔除一部分家庭（“块”），在剩余样本上重新估计效应值，利用这些估计值的变异性来衡量不确定性。
    *   **技术细节**：论文给出了确定重采样次数 $m$ 的决策准则：$m > 2 / (\delta^2 \alpha)$，以确保标准差估计值的误差在 $\delta$ 范围内且置信度为 $1-\alpha$。

### 3. 实验设计
*   **数据集**：使用 **UK Biobank** 中的 17,353 对白人英国同胞。
*   **实验场景**：分析了 17 种性状（11 种生理性状如血压，6 种社会行为性状如家庭收入）。
*   **Benchmark**：由于分块杰克刀法在理论上是渐进无偏的，研究将其作为实证分析的基准。
*   **对比方法**：对比了 OLS、置换检验与 BJK 在不同等位基因频率（MAF）和不同显著性水平（p-value）下的表现。

### 4. 资源与算力
*   **算力说明**：论文提到使用了德克萨斯高级计算中心（TACC）的计算资源。
*   **具体细节**：文中未明确列出具体的 GPU/CPU 型号、数量或具体的训练时长。但提到 BJK 方法比传统的“留一法”杰克刀法（Leave-one-out）在处理大规模基因组数据时更具计算效率。

### 5. 实验数量与充分性
*   **实验规模**：
    *   对 **504,858 个 SNP** 进行了分析。
    *   涵盖了 **17 种不同遗传架构的性状**。
    *   进行了广泛的数学模拟实验，验证了理论推导的偏差公式（Eq. 7, 8, 9）。
*   **充分性评价**：实验设计非常充分。通过模拟验证了理论预测，又通过大规模生物样本库数据进行了实证，涵盖了从罕见变异到常见变异、从强效应到弱效应的多种场景，结果具有高度的一致性和客观性。

### 6. 论文的主要结论与发现
*   **OLS 的偏差**：当非焦点方差随基因型差异增加而增加时，OLS 会低估不确定性；反之则高估。
*   **置换检验的偏差**：当 SNP 具有真实效应时，置换检验会显著高估不确定性，且这种偏差在罕见变异中尤为严重。
*   **样本量与频率的影响**：小样本量和低等位基因频率会放大 OLS 和置换检验的偏差。
*   **BJK 的优越性**：分块杰克刀法在所有测试场景下均表现出近似无偏性，是估计 sib-GWAS 不确定性的最稳健选择。

### 7. 优点
*   **理论与实证结合**：不仅给出了偏差的数学闭式解，还通过真实大数据集进行了验证。
*   **实用性强**：为遗传学研究者提供了明确的工具选择建议，并给出了计算重采样次数的具体公式。
*   **兼容性**：提出的 BJK 方法可以方便地集成到现有的 GWAS 软件（如 PLINK）中。

### 8. 不足与局限
*   **性状类型**：主要关注连续型定量性状，虽然作者认为结论可推广至二元性状，但文中未给出详尽的二元性状实证。
*   **家庭结构**：正文主要讨论每家两名同胞的情况（虽然补充材料进行了扩展），对于更复杂的大家系结构，计算复杂度可能会增加。
*   **软件实现**：目前主流工具（如 PLINK, snipar）尚未直接内置该方法的自动化流程，研究者需自行编写脚本实现。

（完）
