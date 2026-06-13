---
title: "MIDFA: Scalable Bayesian Factor Analysis for Mixed and Incomplete Data"
title_zh: MIDFA：面向混合和不完整数据的可扩展贝叶斯因子分析
authors: "Hutchings, G., Samartsidis, P., Donnay, C., Gaetano, L., Fisher, E., Nichols, T. E., Holmes, C., Häring, D. A., Ganjgahi, H."
date: 2026-06-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731315v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 针对生物银行大规模混合不完整数据的可扩展贝叶斯因子分析
tldr: 针对大规模流行病学研究中混合数据类型、高维度和结构化缺失带来的建模挑战，提出一种可扩展贝叶斯因子分析框架。该方法融合半参数高斯Copula与连续spike-and-slab先验实现稀疏因子载荷，并借助印度自助餐先验非参学习潜在维度数，采用EM算法自然处理缺失数据。在模拟研究及多发性硬化症数据集上，方法有效识别跨临床和影像变量的潜在共享维度，并实现结构化MRI数据的降维，揭示出超越传统方法的见解。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以统一处理混合数据类型、高维度和结构化缺失问题。
method: 结合半参数高斯Copula和连续spike-and-slab先验，用印度自助餐先验学习维度数，EM算法拟合。
result: 在MS数据上识别出跨临床和影像的潜在共享维度，并用于MRI降维分析。
conclusion: 方法提供了稀疏可解释的潜在结构，超越传统方法。
---

## 摘要
概率潜变量模型是揭示高维数据集结构的强大工具，特别是在生物医学应用中。大规模流行病学研究（如英国生物库）的日益普及带来了重要的建模挑战，包括混合数据类型、高维性和结构化缺失。现有方法解决了其中一些问题，但很少有统一且可扩展的框架来同时处理这些问题。在此，我们提出一个可扩展的贝叶斯因子分析框架以应对这些挑战。我们的方法将半参数高斯Copula模型与连续尖峰-平板先验相结合，以诱导稀疏且可解释的因子载荷。潜在维度的数量通过印度自助餐过程先验从数据中非参数地学习。对于模型拟合，我们开发了一种自然适应缺失数据的期望最大化算法。我们通过全面的模拟研究验证了所提出的方法。此外，我们使用诺华-牛津多发性硬化数据集以两种方式展示了所提出的模型。首先，我们识别MS临床和神经影像变量之间共享的潜在维度，表征疾病结构，同时证明模型处理多种数据类型和结构化缺失的能力。其次，我们使用该模型对结构MRI数据进行降维，提取超出传统全脑汇总统计量的下游分析特征。在这些应用中，我们的方法识别出稀疏的潜在结构，并提供了超越传统方法获得的见解。

## Abstract
Probabilistic latent variable models are a powerful tool for uncovering structure in high-dimensional datasets, particularly in biomedical applications. The increasing availability of large-scale epidemiological studies, such as the UK Biobank, poses important modelling challenges, including mixed data types, high dimensionality, and structured missingness. Existing approaches address some of these issues, but few provide a unified and scalable framework for handling them simultaneously. Here, we propose a scalable Bayesian factor analysis framework designed to address these challenges. Our method combines a semiparametric Gaussian copula model with a continuous spike-and-slab prior to induce sparse and interpretable factor loadings. The number of latent dimensions is learned nonparametrically from the data using an Indian buffet process prior. For model fitting, we develop an expectation-maximisation algorithm that naturally accommodates missing data. We validate the proposed method through comprehensive simulation studies. In addition, we showcase the proposed model using the Novartis-Oxford Multiple Sclerosis dataset in two ways. First, we identify latent dimensions shared across MS clinical and neuroimaging variables, characterising disease structure while demonstrating the model's ability to handle multiple data types and structured missingness. Second, we use the model for dimensionality reduction of structural MRI data, extracting features for downstream analysis that go beyond traditional whole-brain summary statistics. In those applications, our method identifies sparse latent structures and provides insights beyond those obtained from traditional approaches.