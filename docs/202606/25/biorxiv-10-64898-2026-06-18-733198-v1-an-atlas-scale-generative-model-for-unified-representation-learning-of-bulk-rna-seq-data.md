---
title: An atlas-scale generative model for unified representation learning of bulk RNA-seq data
title_zh: 一种用于批量RNA-seq数据统一表示学习的图谱规模生成模型
authors: "Pande, A., Uyar, B., Akalin, A."
date: 2026-06-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733198v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 用于批量RNA-seq表示学习的生成模型
tldr: "公共bulk RNA-seq数据整合面临注释异质和技术变异挑战。本文构建监督变分自编码器，在118,263个样本上学习统一组织感知表征，以94.9%平衡准确率分类组织来源，并将16,115个基因压缩至121维潜空间。潜空间主要按组织身份组织，源效应次之。模型在独立儿童肿瘤队列中达84.6%一致，为大规模bulk数据表征学习提供有效资源。"
source: biorxiv
selection_source: fresh_fetch
motivation: 克服bulk RNA-seq数据整合困难，学习统一组织感知的潜表征。
method: "构建监督VAE，基于TCGA/GTEx/ARCHS4共118,263样本，映射至42组织类别。"
result: "94.9%平衡准确率，121维潜空间以组织身份为主轴，TARGET独立验证84.6%一致。"
conclusion: 大规模生成模型有效学习统一表征，代码与交互式应用已公开。
---

## 摘要
公共批量RNA-seq数据库包含数十万个样本，为大规模表示学习创造了机会，但由于注释、实验方案和技术差异的异质性，跨研究整合仍然具有挑战性。虽然预训练的基础模型现已广泛用于单细胞RNA-seq，但批量RNA-seq的类似资源仍然稀缺，这促使我们开发一种直接从批量数据中学习统一、组织感知表示的模型。我们在一个由TCGA、GTEx和ARCHS4收集的118,263个批量RNA-seq样本的汇编数据集上训练了一个监督变分自编码器（VAE），并将其映射到42个组织类别。该模型对组织来源的分类达到了94.9%的平衡准确率（加权F1为96.2%），并将16,115个基因压缩到一个121维的潜在空间中。组织身份是潜在空间的主要组织轴，而来源效应仍然是次要的。为了评估数据量的影响，我们构建了三个不同规模（38K、75K和118K样本）的训练集。我们的结果表明，随着数据集的每次扩展，重建保真度逐步提高，但收益递减。我们在一个来自TARGET的734个儿科肿瘤样本的独立队列上验证了该模型，与预期组织来源的一致性达到84.6%。训练好的模型和代码可在GitHub上获取（https://github.com/BIMSBbioinfo/flexynesis_tissue_vae_manuscript），并配有交互式网络应用程序。

## Abstract
Public bulk RNA-seq repositories contain hundreds of thousands of samples, creating opportunities for large-scale representation learning, but integration across studies remains challenging because of heterogeneous annotations, experimental protocols, and technical variation. While pre-trained foundation models are now widely available for single-cell RNA-seq, comparable resources for bulk RNA-seq remain scarce, motivating a model that learns a unified, tissue-aware representation directly from bulk data. We trained a supervised variational autoencoder (VAE) on a compendium of 118,263 bulk RNA-seq samples that we assembled from TCGA, GTEx, and ARCHS4 and mapped to 42 tissue categories. The model classifies tissue of origin at 94.9% balanced accuracy (weighted F1 96.2%) and compresses 16,115 genes into a 121-dimensional latent space. Tissue identity is the primary organizing axis of the latent space, while source effects remain secondary. To assess the impact of data volume, we constructed training sets at three different scales (38K, 75K, and 118K samples). Our results demonstrated that reconstruction fidelity improved incrementally with each expansion of the dataset, but with diminishing returns. We validated the model on an independent cohort of 734 paediatric tumour samples from TARGET, achieving 84.6% agreement with the expected tissue of origin. The trained model and code are available at GitHub (https://github.com/BIMSBbioinfo/flexynesis_tissue_vae_manuscript) with an interactive web application.