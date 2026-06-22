---
title: "MultiPopPred: A Trans-Ethnic Disease Risk Prediction Method, and its Application to the South Asian Population"
title_zh: MultiPopPred：一种跨族裔疾病风险预测方法及其在南亚人群中的应用
authors: "Kamal, R., Narayanan, M."
date: 2026-06-21
pdf: "https://www.biorxiv.org/content/10.1101/2024.11.26.625410v4.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 跨族群多基因风险评分方法MultiPopPred
tldr: "现有GWAS主要基于欧美人群，对南亚等低资源人群的疾病风险预测不足。MultiPopPred提出一种简洁的跨种族PRS方法，通过Nesterov平滑惩罚收缩模型和L-BFGS优化，从多个辅助人群迁移学习个体级数据。模拟实验表明，该方法平均提升南亚人群预测性能38%，在UK Biobank的16个性状中多数优于最新方法。该工作为低资源人群的复杂性状风险预测提供了可靠方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有跨种族PRS方法对南亚等低资源人群预测效果有限，亟需利用多人群共享遗传信息提高预测能力。
method: 提出MultiPopPred，采用Nesterov平滑惩罚收缩模型和L-BFGS优化，从多个辅助人群迁移学习个体级数据至目标人群。
result: "模拟实验显示平均提升38%预测性能，在UK Biobank 16个性状中多数优于SBayesRC-Multi等最新方法。"
conclusion: MultiPopPred为南亚等低资源人群提供了可靠的跨种族PRS估计，适合复杂全基因性状。
---

## 摘要
全基因组关联研究（GWAS）在识别白人群体的疾病相关单核苷酸多态性（SNPs）方面做出了显著贡献，但对其他研究不足的低资源非白人群体关注有限。多年来，人们积极努力理解和利用不同人群或族裔间基因型-表型关系的群体特异性与共享方面，以弥合这一差距。然而，比现有方法更简单且利用个体层面数据的迁移学习模型的有效性仍是一个未解问题。我们提出MultiPopPred，一种新颖且简单的跨族裔多基因风险评分（PRS）估计方法，该方法挖掘不同人群间的共享遗传风险，并将从多个研究充分的辅助人群学习到的信息迁移到研究不足的目标人群。默认版本的MultiPopPred（MPP-PRS+）使用专门设计的Nesterov平滑惩罚收缩模型和L-BFGS优化程序来利用个体层面数据。基于模拟基因型-表型数据（假设无穷小/泛基因模型）进行的广泛比较分析表明，与包括SBayesRC-Multi和PROSPER在内的最先进跨族裔PRS估计方法相比，MPP-PRS+在所有模拟设置下平均将南亚人群的PRS预测提高了38%。在目标样本量较小的设置和半模拟设置中，这种改进更加显著。这些预测优势在对16个英国生物银行数量性状和二元性状的真实世界评估中得到了进一步印证。例如，与SBayesRC-Multi相比，MPP-PRS+在3个性状上达到了相当的性能（在SOTA性能的5%以内），在另外7个性状上表现更优，在4个（脂质相关）性状上落后。两种方法均未能对剩余2个性状进行有意义的预测。与PROSPER相比，MPP-PRS+保持了相似但不同的竞争性表现趋势。这些表现趋势令人鼓舞，鼓励应用MultiPopPred对低资源人群的复杂泛基因性状利用个体层面数据进行可靠的PRS估计。

## Abstract
Genome-wide association studies (GWAS) have guided significant contributions towards identifying disease associated Single Nucleotide Polymorphisms (SNPs) in Caucasian populations, albeit with limited focus on other understudied low-resource non-Caucasian populations. There have been active efforts over the years to understand and exploit the population specific versus shared aspects of the genotype-phenotype relation across different populations or ethnicities to bridge this gap. However, the efficacy of transfer learning models that are simpler than existing approaches and utilize individual-level data remains an open question. We propose MultiPopPred, a novel and simple trans-ethnic polygenic risk score (PRS) estimation method that taps into the shared genetic risk across populations and transfers information learned from multiple well-studied auxiliary populations to a less-studied target population. The default version of MultiPopPred (MPP-PRS+) harnesses individual-level data using a specially designed Nesterov-smoothed penalized shrinkage model and an L-BFGS optimization routine. Extensive comparative analyses performed on simulated genotype-phenotype data, assuming an infinitesimal/omnigenic model, reveal that MPP-PRS+ improves PRS prediction in the South Asian population by 38% on average across all simulation settings when compared to state-of-the-art trans-ethnic PRS estimation methods including SBayesRC-Multi and PROSPER. This improvement is enhanced in settings with low target sample sizes and in semi-simulated settings. These predictive advantages are further echoed in real-world evaluations against 16 UK Biobank quantitative and binary traits. For example, compared to SBayesRC-Multi, MPP-PRS+ achieves comparable performance (within 5% of SOTA performance) on 3 traits, superior performance on 7 other traits, and lags behind on 4 (lipid-related) traits. Neither method could meaningfully predict the remaining 2 traits. MPP-PRS+ maintains a similarly competitive, albeit distinct, performance trend compared to PROSPER. These performance trends are promising and encourage application of MultiPopPred for reliable PRS estimation in low-resource populations with individual-level data for complex omnigenic traits.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义
- **研究动机**：全基因组关联研究（GWAS）主要基于欧美白人群体，对南亚等低资源非白人群体的疾病风险预测研究严重不足。现有跨种族多基因风险评分（PRS）方法对这类人群预测效果有限，亟需利用多人群间共享遗传信息进行迁移学习。
- **核心问题**：能否设计一种更简洁、利用个体层面数据的迁移学习模型，从多个研究充分的辅助人群（如欧洲、东亚）中将遗传风险知识迁移到研究不足的目标人群（南亚），提升其PRS预测性能。
- **整体含义**：为低资源人群提供可靠的疾病风险预测工具，有助于弥补精准医学的种族偏差，促进全球健康公平。

## 2. 论文提出的方法论
- **核心思想**：提出MultiPopPred方法，挖掘不同人群间的共享遗传风险，采用迁移学习框架，从多个辅助人群（如欧洲、东亚、非洲等）的个体级基因型-表型数据中学习，并将信息迁移到目标南亚人群。
- **关键技术细节**：
  - 默认版本（MPP-PRS+）采用**Nesterov平滑惩罚收缩模型**（Nesterov-smoothed penalized shrinkage model），该模型结合了平滑技巧以处理高维SNP效应估计中的优化困难。
  - 使用**L-BFGS优化算法**（有限内存拟牛顿法）进行参数求解，适合大规模个体级数据。
  - 模型假设为无穷小/泛基因模型（omnigenic model），即所有SNP都对性状有一定效应，通过惩罚收缩实现效应估计与迁移。
- **公式/算法流程**（文字说明）：
  1. 收集多个辅助人群的个体级基因型-表型数据及目标人群的少量个体级数据。
  2. 构建跨人群的联合惩罚似然函数，其中包含辅助人群的效应估计项和目标人群的收缩项。
  3. 使用Nesterov加速梯度技术对惩罚项进行平滑处理，避免非光滑优化问题。
  4. 采用L-BFGS迭代求解最优SNP效应向量。
  5. 输出目标人群的PRS计算公式（各SNP效应加权和）。

## 3. 实验设计
- **数据集与场景**：
  - **模拟实验**：基于人工生成的基因型-表型数据（假设无穷小模型），模拟不同样本量、不同遗传关联结构等场景，重点评估南亚人群预测性能。
  - **半模拟实验**：结合真实基因型（如1000 Genomes Project）和模拟表型，检验方法稳健性。
  - **真实世界评估**：使用英国生物银行（UK Biobank）数据，对16个性状（包括数量性状和二元性状，如脂质相关、身高、BMI等）进行PRS预测验证。
- **Benchmark与对比方法**：
  - 最先进跨种族PRS方法：**SBayesRC-Multi**（基于贝叶斯的跨种族方法）和**PROSPER**（基于个体级数据的迁移学习方法）。
  - 评估指标：预测R²（解释方差）或AUC，并计算相对提升百分比。
- **目标人群**：南亚人群（UK Biobank中的南亚裔个体）。

## 4. 资源与算力
- 论文摘要及元数据中**未明确说明**使用的GPU型号、数量及训练时长。仅提及使用L-BFGS优化（通常运行在CPU或多核环境），未强调特殊算力需求。可能是在标准计算集群上完成，未详细披露硬件配置。

## 5. 实验数量与充分性
- **实验数量**：
  - 模拟实验：涵盖多种设置（不同样本量、遗传架构等），平均性能提升基于“所有模拟设置”。
  - 半模拟实验：额外验证。
  - 真实世界实验：16个UK Biobank性状的全面评估，并分别与SBayesRC-Multi和PROSPER逐性状对比。
- **充分性评价**：
  - 模拟实验覆盖了不同场景（小样本、大样本等），且与两个强基线对比，提供了平均38%提升的量化证据。
  - 真实数据上16个性状的评估数量可观，但均为UK Biobank单队列数据，且仅聚焦南亚人群，缺乏其他低资源人群（如非洲、拉丁美洲）的验证。
  - 未提及消融实验（如去掉某个辅助人群的影响、不同惩罚函数对比等），方法学贡献的拆解不够充分。
  - 总体实验设计较为全面，但客观性受限于单队列和单一目标人群。

## 6. 论文的主要结论与发现
- **主要结论**：MultiPopPred（MPP-PRS+）是一种简洁有效的跨种族PRS估计方法，尤其在目标样本量较小的情况下，显著优于SBayesRC-Multi和PROSPER。
- **关键发现**：
  - 模拟实验中，MPP-PRS+平均提升南亚人群预测性能38%。
  - 在UK Biobank 16个性状中：与SBayesRC-Multi相比，MPP-PRS+在3个性状上相当（差异<5%），7个性状上更优，4个脂质相关性状上落后，2个性状两者均无意义；与PROSPER相比，表现趋势相似但具有不同的竞争性表现。
  - 方法复杂度低于现有方法，且利用个体级数据，有利于在实际低资源场景下部署。

## 7. 优点
- **方法简洁**：采用Nesterov平滑惩罚+L-BFGS，避免了复杂的贝叶斯抽样或深层神经网络，计算高效且易实现。
- **迁移学习有效**：充分利用多人群的个体级数据，而非仅汇总统计量，在样本稀缺时优势明显。
- **性能提升显著**：尤其是在目标样本量小的场景下，提升幅度大（远超38%），具有实际应用价值。
- **全面比较**：同时对比两个SOTA方法，并在模拟和真实数据上验证，结果可信度较高。

## 8. 不足与局限
- **实验覆盖局限**：
  - 仅针对南亚人群，未测试非洲、拉丁美洲等其他低资源人群的泛化性。
  - 真实评估仅使用UK Biobank一个队列，可能存在队列特异性偏差（如UK Biobank的招募偏差）。
- **方法局限性**：
  - 依赖个体级数据，而许多低资源场景可能无法获取；未探讨仅用汇总统计量的变体（如MPP-PRS-summary）。
  - 假设无穷小模型，对具有大效应位点的寡基因性状可能效果不佳。
  - 在4个脂质相关性状上落后于SBayesRC-Multi，表明对某些遗传架构可能不匹配。
- **消融与分析不足**：未进行消融实验（如去除某一辅助人群的影响、惩罚参数敏感性分析），也未分析迁移学习的知识来源贡献。
- **资源与可重复性**：未提供代码或详细超参数设置，限制了复现和实际应用。
- **未说明算力**：可能在小规模集群即可运行，但缺乏具体资源信息。

（完）
