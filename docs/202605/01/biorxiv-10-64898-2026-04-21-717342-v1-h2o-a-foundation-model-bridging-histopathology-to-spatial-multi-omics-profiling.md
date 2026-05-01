---
title: "H2O: A Foundation Model Bridging Histopathology to Spatial Multi-Omics Profiling"
title_zh: H2O：连接组织病理学与空间多组学分析的基础模型
authors: "Gu, Y., Wu, Z., Yan, R., Wang, Z., Li, Y., Lin, S., Cui, Y., Lai, H., Luo, X., Zhou, S. K., Yuan, Z., Yao, J."
date: 2026-04-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.21.717342v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 利用大语言模型连接组织病理学与空间多组学的基座模型
tldr: "H2O是一个连接组织病理学与空间多组学的通用AI框架。它通过对比学习将视觉Transformer与大语言模型结合，使常规H&E染色图像能直接推断空间转录组和蛋白质组景观。在涵盖25种器官的130万个样本上训练后，H2O在预测精度和泛化性上显著超越现有模型，为低成本、大规模的空间多组学分析和组织图谱构建提供了新途径。"
source: biorxiv
selection_source: fresh_fetch
motivation: "旨在解决空间组学技术成本高、通量低的问题，通过AI弥合常规H&E染色图像与分子特异性信息之间的鸿沟。"
method: 采用对比学习策略，将视觉Transformer提取的组织形态特征与大语言模型编码的分子语义知识进行跨模态对齐。
result: "在多器官数据集上实现了高精度的空间组学预测，并能从H&E图像中直接恢复具有生物学意义的细胞间通讯信号轴。"
conclusion: H2O证明了从常规病理形态推断复杂分子景观的可行性，为临床研究和组织表型分析提供了强大的可扩展工具。
---

## 摘要
空间组学技术彻底改变了组织的分子分析，但仍受限于高昂的成本和有限的可扩展性。虽然苏木精-伊红（H&E）染色无处不在，但它缺乏分子特异性。在这里，我们提出了 H2O（Histopathology to Omics），这是一个通用的 AI 框架，它弥合了组织病理学与空间多组学之间的模态鸿沟，能够从常规 H&E 图像中直接推断空间转录组学（ST）和蛋白质组学（SP）图谱。H2O 通过对比学习将视觉 Transformer（ViT）与大语言模型（LLM）集成，以使组织形态学与语义分子知识对齐。这种跨模态方法允许模型将空间表达谱纳入组织学模式识别中，从而有效地解码组织形态背后的分子异质性。H2O 在涵盖 25 个器官和癌症类型的 130 万个 H&E-空间配对切片的泛组织数据集上进行了训练，它从组织学预测的空间组学表达与测序测量结果高度一致，并在三个癌症基准测试中始终优于最先进的模型。值得注意的是，H2O 直接从 H&E 图像中恢复了 MIF-CD74/CD44 信号轴，突显了其在无需分子分析的情况下推断具有生物学意义的细胞间通讯的能力。应用于涵盖胎儿和儿科胸腺组织、人类转移性淋巴结和乳腺癌的另外三个公共队列，涉及人类发育、3D 空间框架和综合多组学，H2O 产生了生物学上一致的见解，在不同场景的现实应用中展示了卓越的准确性、鲁棒性和泛化能力。H2O 通过计算生成转录组和蛋白质组图谱，将常规组织病理学转化为空间分辨率多组学分析的门户，从而增强了组织表型分析，并实现了可扩展的、综合性的组织图谱构建。

## Abstract
Spatial omics technologies have revolutionized the molecular profiling of tissues but remain constrained by high costs and limited scalability. While hematoxylin and eosin (H&E) staining is ubiquitous, it lacks molecular specificity. Here, we present H2O (Histopathology to Omics), a generalist AI framework that bridges the modality gap between histopathology and spatial multi-omics, enabling the direct inference of spatial transcriptomics (ST) and proteomics (SP) landscapes from routine H&E images. H2O integrates Vision Transformers (ViT) with Large Language Models (LLM) via contrastive learning to align histological morphology with semantic molecular knowledge. This cross-modal approach allows the model to incorporate spatial expression profiles into histological pattern recognition, effectively decoding the molecular heterogeneity underlying tissue morphology. Trained on a pan-tissue dataset of 1.3 million paired H&E-spatial patches across 25 organs and cancer types, H2O predicts spatial omics expression from histology with high concordance to sequenced measurements and consistently outperforms state-of-the-art models across three cancer benchmarks. Notably, H2O recovers the MIF-CD74/CD44 signaling axis directly from H&E images, highlighting its capacity to infer biologically meaningful cell-cell communication without molecular profiling. Applying on three additional public cohorts covering fetal and paediatric thymus tissues, human metastatic lymph node, and breast cancer, encompassing human development, 3D spatial frameworks, and integrative multi-omics, H2O yields biologically concordant insights, demonstrating superior accuracy, robustness, and generalizability across real-world applications in diverse scenarios. H2O converts routine histopathology into a portal for spatially resolved multi-omics profiling by computationally generating transcriptomic and proteomic landscapes, thereby enhancing tissue phenotyping and enabling scalable, integrative tissue-atlas construction.