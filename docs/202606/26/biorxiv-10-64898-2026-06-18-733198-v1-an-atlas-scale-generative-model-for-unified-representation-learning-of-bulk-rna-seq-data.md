---
title: An atlas-scale generative model for unified representation learning of bulk RNA-seq data
title_zh: 面向图谱规模的生成模型，用于批量RNA-seq数据的统一表征学习
authors: "Pande, A., Uyar, B., Akalin, A."
date: 2026-06-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733198v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 批量RNA-seq数据生成模型，属于大规模基因组模型
tldr: "公共bulk RNA-seq数据因异质性标注和技术差异难以整合。本文基于118,263样本构建监督变分自编码器，将16,115个基因压缩为121维潜在空间，实现94.9%的组织分类准确率。潜在空间以组织身份为主轴，源效应为次要因素。模型在TARGET数据集验证准确率84.6%，表明其泛化能力，并提供开源模型与应用。"
source: biorxiv
selection_source: fresh_fetch
motivation: 跨研究整合bulk RNA-seq数据困难，缺少像单细胞RNA-seq那样的预训练基础模型。
method: "从TCGA、GTEx、ARCHS4收集118,263样本，映射到42个组织类别，训练监督变分自编码器压缩基因表达。"
result: "组织分类平衡准确率94.9%，TARGET独立测试一致性84.6%，数据规模增加带来边际收益递减。"
conclusion: 模型学得组织感知的统一表示，可推广至新数据集，代码与交互界面已公开。
---

## 摘要
公共批量RNA-seq存储库包含数十万个样本，为大规模表征学习创造了机会，但由于注释异质性、实验方案和技术差异，跨研究整合仍然具有挑战性。虽然单细胞RNA-seq的预训练基础模型现已广泛可用，但批量RNA-seq的类似资源仍然稀缺，这促使我们开发了一个直接从批量数据中学习统一的、组织感知表征的模型。我们在由TCGA、GTEx和ARCHS4汇编的118,263个批量RNA-seq样本的汇编数据集上训练了一个监督变分自编码器（VAE），并将其映射到42个组织类别。该模型以94.9%的平衡准确率（加权F1为96.2%）对组织起源进行分类，并将16,115个基因压缩到121维潜空间。组织身份是潜空间的主要组织轴，而来源效应保持次要地位。为了评估数据量的影响，我们以三种不同规模（38K、75K和118K样本）构建了训练集。结果表明，随着数据集的每次扩展，重建保真度逐步提高，但收益递减。我们在来自TARGET的734个儿科肿瘤样本的独立队列上验证了该模型，与预期组织起源的一致性达到84.6%。训练好的模型和代码可在GitHub（https://github.com/BIMSBbioinfo/flexynesis_tissue_vae_manuscript）上获得，并配有交互式网络应用程序。

## Abstract
Public bulk RNA-seq repositories contain hundreds of thousands of samples, creating opportunities for large-scale representation learning, but integration across studies remains challenging because of heterogeneous annotations, experimental protocols, and technical variation. While pre-trained foundation models are now widely available for single-cell RNA-seq, comparable resources for bulk RNA-seq remain scarce, motivating a model that learns a unified, tissue-aware representation directly from bulk data. We trained a supervised variational autoencoder (VAE) on a compendium of 118,263 bulk RNA-seq samples that we assembled from TCGA, GTEx, and ARCHS4 and mapped to 42 tissue categories. The model classifies tissue of origin at 94.9% balanced accuracy (weighted F1 96.2%) and compresses 16,115 genes into a 121-dimensional latent space. Tissue identity is the primary organizing axis of the latent space, while source effects remain secondary. To assess the impact of data volume, we constructed training sets at three different scales (38K, 75K, and 118K samples). Our results demonstrated that reconstruction fidelity improved incrementally with each expansion of the dataset, but with diminishing returns. We validated the model on an independent cohort of 734 paediatric tumour samples from TARGET, achieving 84.6% agreement with the expected tissue of origin. The trained model and code are available at GitHub (https://github.com/BIMSBbioinfo/flexynesis_tissue_vae_manuscript) with an interactive web application.