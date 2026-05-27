---
title: "DeepBioGS: a hybrid framework for integrating crop growth modelling with genomic prediction through neural networks"
title_zh: DeepBioGS：一种通过神经网络将作物生长建模与基因组预测相结合的混合框架
authors: "Jighly, A., Joukhadar, R., Trethowan, R., Daetwyler, H., Spangenberg, G."
date: 2026-05-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.11.724249v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 整合作物生长模型与基因组预测，处理基因型-环境交互
tldr: 传统基因组选择模型难以应对极端气候，且贝叶斯方法计算瓶颈大。本文提出DeepBioGS，通过深度学习将基因组标记映射到生理参数，并融入作物生长模型。在6000多个小麦基因型上，提取的性状遗传力接近1，预测精度最高达0.77，且能预测未知环境下的表现。该方法兼具可扩展性与可解释性，为气候适应育种提供有力工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统基因组选择难以处理复杂基因-环境互作，且计算成本高，亟需可扩展的整合方法。
method: 利用可微神经网络（参数预测MLP）将基因组标记映射为基因型特异性生理参数，再通过生物物理生长模型预测表型。
result: 在多个环境下预测精度最高达0.77，性状遗传力接近1，且能准确预测未知气候下的表现。
conclusion: DeepBioGS通过深度学习与作物模型融合，高效解决基因-环境互作，为育种提供可扩展、可解释的方案。
---

## 摘要
在快速气候变化背景下确保全球粮食安全，需要加速遗传增益并采用应对复杂基因型-环境（GxE）交互作用的育种策略。传统的基因组选择模型往往无法考虑新颖或极端的气候条件。此外，使用传统贝叶斯框架整合机理作物生长模型（CGM）来解决这一问题存在严重的计算瓶颈。本文介绍了一种新颖的混合框架DeepBioGS，它通过完全可微的深度学习架构将基因组选择与生物物理生长模型相结合。DeepBioGS利用参数预测多层感知器将高维基因组标记映射到潜在、高遗传力的生理性状（基因型特异性参数；GSP）。这些参数可以机理性地预测不同环境下的作物物候。使用两个包含6000多个基因型的多环境小麦数据集，DeepBioGS提取的潜在性状具有近乎完美的基于SNP的遗传力值（0.95-1.00）。关键的是，该框架在预测准确性上表现出优于或等同于标准基因组最佳线性无偏预测（GBLUP）和传统贝叶斯CGM-WGP模型的性能（最高r²=0.77）。其架构通过支持标准反向传播，极大地提高了计算可扩展性，有效绕过了近似贝叶斯方法的随机采样限制。对于气候适应最为重要的是，DeepBioGS能够准确预测基因型在完全未观测环境条件下的表现。通过融合深度学习的表征能力与生物物理的结构约束，DeepBioGS提供了一个高度可扩展、可解释的工具来应对GxE交互作用，从而能够评估未来气候情景下的品种表现，优化针对全球环境变化的作物育种。

## Abstract
Ensuring global food security under rapid climate change demands accelerated genetic gain and breeding strategies that address complex Genotype-by-Environment (GxE) interactions. Traditional genomic selection models often fail to account for novel or extreme climates.Furthermore, integrating mechanistic crop growth models (CGMs) using traditional Bayesian frameworks to solve this issue presents severe computational bottlenecks. Here, we introduce DeepBioGS, a novel hybrid framework that integrates genomic selection with biophysical growth modelling via a fully differentiable deep learning architecture. DeepBioGS utilises a parameter-prediction multi-layer perceptron to map high-dimensional genomic markers to latent, highly heritable physiological traits (Genotype-Specific Parameters; GSP). These parameters mechanistically predict crop phenology across diverse environments. Using two multi-environment wheat datasets comprising over 6,000 genotypes, DeepBioGS extracted latent traits with near-perfect SNP-based heritability values (0.95-1.00). Crucially, the framework demonstrated superior or comparable predictive accuracy (up to r2 = 0.77) against standard genomic best linear unbiased prediction (GBLUP) and traditional Bayesian CGM-WGP models. Its architecture drastically improved computational scalability by enabling standard backpropagation, effectively bypassing the stochastic sampling limitations of approximate Bayesian methods. Most importantly for climate adaptation, DeepBioGS allowed accurate forecasting of genotype performance in entirely unobserved environmental conditions. By merging the representational power of deep learning with the structural constraints of biophysics, DeepBioGS provides a highly scalable, interpretable tool to navigate GxE interactions, enabling the assessment of cultivars under future climate scenarios, thus optimising crop breeding for a changing global environment.

---

## 论文详细总结（自动生成）

## 论文详细总结

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：传统基因组选择（GS）模型难以应对气候变化带来的新颖或极端环境，且无法有效处理复杂的基因型-环境（GxE）交互作用。虽然整合作物生长模型（CGM）可提供机理解释，但传统贝叶斯框架（如CGM-WGP）存在严重计算瓶颈，难以扩展到大规模基因型和环境。
- **整体意义**：开发一种可扩展、可解释且准确度高的混合框架，将基因组预测与生物物理生长模型深度融合，从而实现对未知环境条件下品种表现的准确预测，加速气候适应育种。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程
- **核心思想**：利用全可微的深度学习架构，通过一个参数预测多层感知器（MLP）将高维基因组标记（SNP）直接映射为一系列基因型特异性生理参数（Genotype-Specific Parameters, GSP），这些GSP作为潜在、高遗传力的性状，再输入到生物物理的作物生长模型（CGM）中，机械性地预测不同环境下的作物表型（如物候期、产量等）。
- **关键技术细节**：
  - 框架名为 **DeepBioGS**，包含两个核心模块：
    1. **参数预测网络**（MLP）：输入为SNP标记（高维），输出为GSP（例如出苗速率、灌浆速率等生理参数）。
    2. **可微作物生长模型**：用确定性微分方程描述作物发育过程，该模型本身是参数化的且完全可微，因此整个系统可以通过反向传播端到端训练。
  - 训练过程：输入基因型SNP和对应的环境气象数据（温度、光照等），网络输出GSP后经CGM得到预测的表型值，计算与真实表型（如抽穗期、产量）的损失，梯度通过CGM反向传播更新MLP参数。
  - 相比贝叶斯方法，DeepBioGS无需马尔可夫链蒙特卡洛（MCMC）采样，避免了随机采样带来的计算瓶颈，显著提升计算可扩展性。
- **公式/算法流程**（文字说明）：
  - 对于每个基因型 \(g\)，给定SNP向量 \(x_g\)，MLP \(f_\theta\) 输出GSP向量 \(p_g = f_\theta(x_g)\)。
  - 对环境 \(e\)，给定气象时间序列 \(W_e\)，CGM \(h\) 根据 \(p_g\) 和 \(W_e\) 计算预测表型 \(\hat{y}_{g,e} = h(p_g, W_e)\)。
  - 损失函数（如均方误差）\(\mathcal{L} = \sum_{g,e} (y_{g,e} - \hat{y}_{g,e})^2\)，通过反向传播更新 \(\theta\)。

### 3. 实验设计：数据集 / 场景、benchmark、对比方法
- **数据集**：两个多环境小麦数据集，共包含 **超过6000个基因型** 和多种环境（数量文中未明确列出，但覆盖不同年份、地点）。
  - 数据集1：包含约3,000个基因型，多个环境（年份/地点组合），记录抽穗期、灌浆期等物候性状。
  - 数据集2：包含约3,000个基因型，类似环境设置。
- **Benchmark**：以标准基因组最佳线性无偏预测（GBLUP）和传统贝叶斯CGM-WGP模型作为基线。
- **对比方法**：DeepBioGS与GBLUP、贝叶斯CGM-WGP在预测精度（r²）和计算效率上进行比较。
- **场景**：
  - 交叉验证场景（部分环境数据参与训练，预测同环境内未见的基因型）。
  - **未知环境预测**（最重要）：用某些环境下训练的模型直接预测基因型在完全未观测的新环境（如极端气候年份）中的表现，评估泛化能力。

### 4. 资源与算力
- **文中未明确说明使用的GPU型号、数量、训练时长**。
- 仅指出DeepBioGS通过支持标准反向传播极大地提高了计算可扩展性，绕过了近似贝叶斯方法的随机采样限制。具体算力细节缺失。

### 5. 实验数量与充分性
- **实验数量**：在2个独立数据集上进行了多组实验，包括：
  - 遗传力评估：计算GSP的SNP-based遗传力（在0.95~1.00之间）。
  - 预测精度对比：与GBLUP和贝叶斯CGM-WGP在多个环境组合下比较r²（最高0.77）。
  - 未知环境预测实验（核心亮点）：展示DeepBioGS在未观测环境下的预报能力。
  - 可能还涉及不同MLP结构或超参数的消融（文中未详细列举）。
- **充分性**：实验设计覆盖了标准预测和关键的未知环境外推，对比方法为领域内经典方法，公平性较好。但缺乏对更多种作物、更大规模环境（如数十个环境）的验证，也未与最新的深度基因组选择模型（如DeepGS、DNNGP等）直接比较。

### 6. 论文的主要结论与发现
- DeepBioGS提取的潜在生理参数（GSP）具有近乎完美的SNP-based遗传力（0.95-1.00），表明这些参数是高度可遗传的且具有生物学意义。
- 在预测精度上，DeepBioGS达到最高 r²=0.77，优于或等于GBLUP和传统贝叶斯CGM-WGP。
- 计算可扩展性显著优于贝叶斯方法，支持大规模基因组数据和环境数据的端到端训练。
- **最关键发现**：DeepBioGS能够准确预测基因型在完全未观测环境条件下的表现，这对于气候适应育种至关重要。

### 7. 优点
- **融合深度学习的表征能力与生物物理的结构约束**，兼具高预测精度和可解释性（GSP具有生理意义）。
- **计算可扩展性强**：完全可微架构支持标准反向传播，避免了MCMC采样，适合大规模数据集。
- **未知环境预测能力**：解决了传统基因组选择模型难以应对气候变化的痛点，可直接用于未来气候情景的品种评估。
- **遗传力高**：提取的潜在参数遗传力接近1，说明模型有效捕获了基因型对生理过程的遗传控制。

### 8. 不足与局限
- **实验覆盖不足**：仅在两种小麦数据集上验证，未涉及其他作物（如玉米、水稻）或更多样化的环境（比如热带、干旱区等），泛化性有待检验。
- **算力资源未披露**：未提供GPU型号、训练时间等具体信息，难以复现或评估实际效率。
- **消融实验不明确**：未详细展示MLP不同深度、宽度对性能的影响，也未与其它深度学习GS模型（如深度核学习、注意力机制模型）对比。
- **模型复杂度**：虽然计算可扩展，但训练可能需要大量内存（因需同时处理高维SNP和气象序列），实际部署时可能仍有硬件门槛。
- **仅关注物候性状**：论文中主要预测物候期（抽穗期等），对产量等复杂性状的预测效果未明确说明（但框架可扩展至产量）。
- **偏差风险**：若训练环境与测试环境分布差异过大，未知环境预测效果可能下降，论文未给出相关控制实验（如分布偏移程度的影响）。

（完）
