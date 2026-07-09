---
title: "One score to rule them all: regularized ensemble polygenic risk prediction with GWAS summary statistics"
title_zh: 一统天下的评分：基于GWAS汇总统计数据的正则化集成多基因风险预测
authors: "Zhao, Z., Dorn, S., Wu, Y., Yang, X., Beckerman, A., Jin, J., Lu, Q."
date: 2026-07-09
pdf: "https://www.biorxiv.org/content/10.1101/2024.11.27.625748v3.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 基于GWAS汇总统计的集成多基因风险预测
tldr: 集成学习提高了多基因风险评分性能，但现有方法需个体级基因数据，限制了非欧洲人群应用。本文提出基于GWAS汇总统计量的正则化集成框架，无需个体数据即可整合候选PRS模型。跨多个性状和人群分析表明，该方法一致优于现有PRS方法。该框架实现新旧PRS模型的无缝集成，为PRS开发提供可扩展的通用方案。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-11-27-625748-v3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1662, \"height\": 953, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-11-27-625748-v3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1685, \"height\": 899, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-11-27-625748-v3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1672, \"height\": 1305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-11-27-625748-v3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1387, \"height\": 1279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-11-27-625748-v3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1187, \"height\": 1276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-11-27-625748-v3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1284, \"height\": 1283, \"label\": \"Figure\"}]"
motivation: 现有集成PRS方法依赖个体级基因数据，在非欧洲人群中应用受限。
method: 提出基于GWAS汇总统计量的正则化集成框架，整合大量候选PRS模型。
result: 在多个性状和人群中，该方法一致优于现有PRS方法。
conclusion: 该框架实现“一个评分统治所有”，可无缝集成新旧PRS模型，提供通用解决方案。
---

## 摘要
集成学习已成为提高多基因风险评分（PRS）预测准确性的基石，几乎所有最新的多祖先PRS方法都将集成学习作为最后一步。然而，现有的集成方法需要个体水平的基因型数据进行模型训练，这限制了其在现实世界中的应用，尤其是在没有足够基因组样本的非欧洲人群中。在这里，我们介绍了一个统计框架，用于构建正则化集成PRS，该框架仅使用全基因组关联研究汇总统计数据即可整合大量候选PRS模型。通过对多个性状和人群的广泛分析，我们证明了我们的方法在祖先内和跨祖先中始终优于最先进的PRS方法。该框架提供了“一统天下的评分”，因为它能够将新开发的PRS模型与现有模型无缝集成，为未来的PRS开发和应用提供了可扩展的通用解决方案。

## Abstract
Ensemble learning has become a cornerstone for improving the predictive accuracy of polygenic risk scores (PRS), and nearly all recent multi-ancestry PRS methods incorporate ensemble learning as a final step. However, existing ensemble approaches require individual-level genotype data for model training, which limits their real-world applications, especially in non-European populations without sufficient genomic samples. Here, we introduce a statistical framework for constructing regularized ensemble PRS that integrates a large number of candidate PRS models using only genome-wide association study summary statistics. Through extensive analyses across multiple traits and populations, we demonstrate that our method consistently outperforms state-of-the-art PRS approaches within and across ancestries. This framework presents "one score to rule them all" for its capability to enable seamless integration of newly developed PRS models with existing ones, providing a scalable and general solution for future PRS development and application.

---

## 论文详细总结（自动生成）

# 论文总结：One score to rule them all: regularized ensemble polygenic risk prediction with GWAS summary statistics

## 1. 核心问题与整体含义（研究动机和背景）
- **研究背景**：多基因风险评分（PRS）在复杂性状和疾病预测中广泛应用。集成学习（Ensemble learning）能通过组合多个PRS模型显著提升预测精度，几乎所有现代PRS方法都引入了集成学习作为最后一步。
- **核心问题**：现有集成PRS方法均需要个体水平的基因型和表型数据（holdout数据集）进行模型训练，这在实践中往往难以获得，尤其在非欧洲人群中缺乏大规模个体数据。仅靠GWAS汇总统计数据（summary statistics）无法直接进行常规集成学习，导致该方法在非欧洲人群、资源有限场景下应用受限。
- **整体含义**：本文提出仅基于GWAS汇总统计量的正则化集成PRS框架（PUMAS-ensemble），规避了个体级数据需求，实现新旧PRS模型的无缝集成，被视为“一统天下的评分”通用方案。

## 2. 方法论
### 核心思想
- 通过统计重采样方法将完整GWAS汇总统计量划分为多个独立子集，分别用于PRS模型训练、集成模型拟合和性能评估，完全替代个体级数据拆分过程。
- 引入正则化（elastic net 和 super learning）解决多个候选PRS之间的高相关性（共线性）问题，实现稳定、自适应的集成。

### 关键技术细节
- **数据划分**：给定全量GWAS汇总统计量（样本量 \( N \)），使用条件正态分布推导出任意子样本统计量的条件分布，从而将完整统计量划分为三个独立子集：
  - 训练子集（\( N_{\text{train}} \)）：用于训练多个单PRS模型（如Lassosum、LDpred2、PRS-CS等8种方法，共110个模型）。
  - 集成学习子集（\( N_{\text{ensemble}} \)）：进一步分割为两部分，用于弹性网模型调参（PUMAS-EN）或Super Learner的两层训练（PUMAS-SL）。
  - 测试子集（\( N_{\text{test}} \)）：用于评估集成PRS预测性能。
- **PUMAS-EN（弹性网集成）**：
  - 目标函数：\( \frac{1}{2n} \| \mathbf{y} - \mathbf{X}\mathbf{W}\mathbf{b} \|^2 + \alpha\lambda \|\mathbf{b}\|_1 + \frac{1-\alpha}{2}\lambda \|\mathbf{b}\|_2^2 \)
  - 通过坐标下降法迭代更新集成权重 \( \mathbf{b} \)，仅需 \( \mathbf{X}^T\mathbf{y} \) 和 \( \mathbf{X}^T\mathbf{X} \)（均来自汇总统计量和LD参考数据）。
  - 超参数 \( \alpha \in \{0,0.25,0.5,0.75,1\} \)，\( \lambda = 10^\psi \)（\( \psi \) 在[-5,0]均匀取51个值）。
- **PUMAS-SL（Super Learner集成）**：
  - 第一层：分别训练LASSO、Ridge、弹性网三种正则化集成模型（Level-1 ensemble）。
  - 第二层：对第一层模型的预测结果进行非负最小二乘加权组合（Level-2 ensemble），获得最终Super Learner PRS。
  - 使用两层交叉验证划分集成学习子集，避免过拟合。
- **性能评估**：在测试子集上计算预测 \( R^2 \)，公式基于汇总统计量近似计算。

## 3. 实验设计
### 数据集与场景
- **模拟数据**：基于UK Biobank（UKB）中10万欧洲血统个体的真实基因型，模拟不同遗传力（\( h^2=0.3,0.7 \)）和因果变异比例（0.1%,5%）的连续性状。
- **UKB真实数据**：16个复杂性状（如身高、BMI等），使用UKB欧洲血统个体（约38.5万训练样本，3.8万独立holdout集）。
- **外部验证（All of Us）**：
  - 欧洲血统个体：身高、BMI及6种疾病（双相障碍、重度抑郁、精神分裂症、乳腺癌、冠心病、2型糖尿病）。
  - 东亚血统个体：身高、BMI、舒张压、收缩压，使用UKB（欧裔）和BBJ（日裔）GWAS汇总数据。
- **跨祖先脂质性状（GLGC）**：HDL、LDL、logTG、总胆固醇（4个祖先：非洲、东亚、欧洲、南亚），在UKB对应祖先样本中验证。

### Benchmark与对比方法
- **单PRS模型**：8种方法共110个模型（Lassosum、LDpred2-grid/auto、PRS-CS/auto、MegaPRS、SBayesR/SBayesRC、DBSLMM、Vilma、SBLUP）。
- **对比的集成方法**：
  - 基于个体级数据的弹性网/Super Learner（gold standard）。
  - 无正则化的线性回归集成。
  - PRSmix（弹性网集成+过滤）。
  - PRS-PCA（无监督集成）。
  - PRS-CSx（跨祖先方法）。
- **评估指标**：连续性状用预测 \( R^2 \)，二分类性状用AUC。

## 4. 资源与算力
- 文中未明确说明具体GPU型号、数量或训练时长。
- 仅提及计算耗时示例：身高数据（51个PRS模型，约120万SNP）下，PUMAS-EN耗时1.85分钟，PUMAS-SL耗时2.57分钟（4 CPU线程）。内存使用随PRS模型数量亚线性增长。
- 未提及大规模分布式训练或GPU加速，主要依赖CPU计算。

## 5. 实验数量与充分性
- **实验组数**：
  - 模拟实验：4种遗传架构设置 × 4折MCCV × 多种集成方法。
  - UKB真实数据：16个性状 × 多种对比方法。
  - All of Us欧洲样本：2个连续+6个疾病性状。
  - 跨祖先东亚：4个性状。
  - 跨祖先脂质：4种脂质性状 × 4个祖先群体。
  - 消融实验：不同训练样本量下对比、LD错配影响、计算扩展性等。
- **充分性评价**：
  - 覆盖了常见性状、多种遗传架构、多种祖先群体。
  - 对比了多个主流单PRS模型和集成方法，包括有监督/无监督、同祖先/跨祖先。
  - 统计显著性检验（Wilcoxon signed-rank test）验证了改进可靠性。
  - 实验设计较为全面，但未包含非欧洲人群在UKB外的独立大规模验证（如真实临床数据），且未涉及非线性模型集成。

## 6. 主要结论与发现
- PUMAS-EN和PUMAS-SL在模拟和真实数据上均一致优于所有单PRS模型（\( R^2 \) 提高10-30%，跨祖先场景最高达300%）。
- 性能几乎与基于个体级数据的集成学习相同，且当holdout样本量很小时（N=500）反而更优。
- 在跨祖先应用中显著提升非欧洲人群预测精度，优于PRS-CSx。
- 正则化（弹性网/Super Learner）是处理大量相关PRS模型的关键，无正则化的线性回归性能退化。
- 使用祖先匹配的LD参考数据即可，不强制要求目标人群内部LD。
- 框架可扩展性好，可不断纳入新PRS模型，具有“一统天下”潜力。

## 7. 优点
- **方法创新**：首次实现仅基于GWAS汇总统计量的集成PRS训练，突破个体级数据限制，实用性极强。
- **鲁棒性**：正则化策略有效对抗多重共线性，集成性能稳定。
- **通用性**：可无缝整合任意新旧PRS模型，框架持续进化。
- **全面验证**：覆盖多性状、多祖先、多场景（同祖先/跨祖先、不同样本量），与多种先进方法对比，统计学显著性检验充分。
- **可操作性**：提供开源软件，计算成本低（分钟级），易于推广。

## 8. 不足与局限
- **实验局限**：
  - 未包含非线性PRS模型（如机器学习模型）的集成，Super Learner的复杂设计在本研究中未带来额外增益。
  - 跨祖先验证主要依赖UKB和All of Us，缺少其他独立大型非欧洲队列（如非洲、拉丁美洲）的外部验证。
  - 未评估PRS在临床实际应用中的稳定性、校准性随时间变化等指标（仅用了 \( R^2 \) 和AUC）。
- **方法局限**：
  - 需要已知LD参考面板，且LD错配（祖先不匹配）会导致性能下降，在实践中可能难以总是获得匹配LD。
  - 当样本重叠（GWAS训练样本与集成参考样本重叠）时，方法鲁棒性未充分探讨；当前实现需假定无重叠。
  - 集成模型输入PRS的选择标准未系统化（用户需自行决定），缺少自动选择最优子集策略。
  - 未处理人群混合（admixture）和遗传连续体问题。
- **资源说明**：算力报告不详细（无GPU使用信息），可能限制大规模评估的可复现性。

（完）
