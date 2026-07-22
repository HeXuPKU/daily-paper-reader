---
title: Unifying multimodal single-cell data with a mixture-of-experts β-variational autoencoder framework
title_zh: 使用混合专家β-变分自编码器框架统一多模态单细胞数据
authors: "Ashford, A. J., Enright, T., Somers, J., Nikolova, O., Demir, E."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.1101/2025.02.28.640429v3.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 单细胞多模态整合使用VAE，与虚拟细胞模型生成和基因组模型相关。
tldr: 多模态单细胞数据整合面临模态不匹配、稀疏性和覆盖不均的挑战。本文提出UniVI，基于混合专家β-VAE框架，通过模态特异编码器/解码器、共享潜在先验和对称跨模态对齐，无需预注释参考即可学习共享潜在空间。在RNA-蛋白、RNA-染色质等数据上，UniVI产生连贯嵌入，提升标签转移和跨模态重构性能，且在三模态和镶嵌设计中表现稳健。该方法提供了灵活、可解释的多模态整合方案，支持参考到查询投影。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1728, \"height\": 2303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1765, \"height\": 2122, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1704, \"height\": 2263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1744, \"height\": 2229, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1600, \"height\": 2173, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1660, \"height\": 2163, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1691, \"height\": 2147, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1761, \"height\": 2198, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1717, \"height\": 2231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1607, \"height\": 2055, \"label\": \"Figure\"}]"
motivation: 解决多模态单细胞数据整合中模态不匹配、稀疏性和覆盖不均的问题。
method: 提出UniVI，一种混合专家β-VAE，包含模态特异编码器/解码器、共享潜在先验和对称跨模态对齐。
result: 在CITE-seq等配对数据上实现连贯嵌入，改善标签转移，支持跨模态重构与去噪，且在三模态和镶嵌设计中保持稳健。
conclusion: 为配对、三模态和镶嵌研究设计提供灵活的多模态整合框架，并支持参考到查询投影。
---

## 摘要
多模态单细胞分析检测细胞状态的互补层面，但模态不匹配、稀疏性和不均一的队列覆盖使整合变得复杂。我们提出UniVI（统一变分推理），一种可扩展的混合专家β-变分自编码器，能够在保留模态特定结构的同时学习共享潜在空间。UniVI将模态特定的编码器/解码器与共享潜在先验和对称的跨模态对齐目标相结合，无需精心设计的特征链接图或预先注释的参考图谱即可实现配对测量的一致整合；当标签可用时，可选择性添加监督头。在涵盖人类外周血单核细胞和小鼠背部皮肤（一种具有连续分化等级的非造血组织）的配对RNA-蛋白质（CITE-seq）和RNA-染色质（10x多组学、SHARE-seq）数据上，UniVI生成连贯的嵌入，改善标签转移，并实现跨模态重建和去噪。扩展到三模态测量，UniVI在RNA、染色质可及性和表面蛋白（TEA-seq）之间保持稳健的三向对齐，并在配对scNMT-seq小鼠原肠胚概念验证中，在β-二项式似然下容纳DNA甲基化。在严重的细胞类型不平衡和存在模态专属群体的情形下，性能优雅地退化。在急性髓系白血病马赛克设计中，配对RNA-蛋白质桥接锚定了独立的仅RNA和蛋白质+基因型队列，揭示了与基因型相关的邻域，并通过突变感知微调得到锐化。因此，UniVI提供了一个灵活、可解释的框架，适用于配对、三模态和马赛克研究设计的多模态整合，并支持部分观测研究中的实用参考到查询投影。

## Abstract
Multimodal single-cell assays profile complementary layers of cell state, but integration is complicated by modality mismatch, sparsity, and uneven cohort coverage. We present UniVI (\Unified Variational Inference), a scalable mixture-of-experts {beta}-variational autoencoder that learns a shared latent space while preserving modality-specific structure. UniVI couples modality-specific encoders/decoders with a shared latent prior and a symmetric cross-modal alignment objective, enabling consistent integration of paired measurements without curated feature-link graphs or pre-annotated reference atlases; optional supervised heads can be added when labels are available. Across paired RNA--protein (CITE-seq) and RNA--chromatin (10x Multiome, SHARE-seq) data spanning human PBMCs and mouse back skin---a non-hematopoietic tissue with continuous differentiation hierarchies---UniVI produces coherent embeddings, improves label transfer, and enables cross-modal reconstruction and denoising. Extending to tri-modal measurements, UniVI maintains robust three-way alignment among RNA, chromatin accessibility, and surface proteins (TEA-seq), and accommodates DNA methylation in a paired scNMT-seq mouse gastrulation proof-of-concept under beta-binomial likelihoods. Performance degrades gracefully under severe cell-type imbalance and in the presence of modality-exclusive populations. In an acute myeloid leukemia mosaic design, a paired RNA--protein bridge anchors independent RNA-only and protein+genotype cohorts, revealing genotype-associated neighborhoods that sharpen with mutation-aware fine-tuning. UniVI thus provides a flexible, interpretable framework for multimodal integration across paired, tri-modal, and mosaic study designs and supports practical reference-to-query projection in partially observed studies.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：多模态单细胞测序技术（如CITE-seq、10x Multiome、TEA-seq）可以同时检测同一细胞的多个分子层面（如RNA、蛋白质、染色质可及性、DNA甲基化），但数据整合面临三大挑战：**模态不匹配**（不同模态特征空间不同）、**数据稀疏性**（尤其染色质可及性数据）以及**队列覆盖不均**（不同样本或实验可能只有部分模态数据）。
- **整体含义**：现有方法（如基于参考图谱的整合）通常需要精心设计的特征链接图或预先注释的参考，当参考不可用或模态不完全重叠时表现不佳。因此，需要一种无需参考、可扩展的框架，能够灵活处理配对、三模态甚至“马赛克”设计（部分细胞只有部分模态）的数据整合。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：提出**UniVI（Unified Variational Inference）**，一种**混合专家β-变分自编码器（mixture-of-experts β-VAE）**，通过模态特异的编码器/解码器、共享潜在先验和对称跨模态对齐目标，学习一个统一的潜在空间，同时保留每个模态的特有结构。
- **关键技术细节**：
  - **模态特异的编码器/解码器**：每种模态（如RNA、蛋白质、染色质）都有独立的神经网络处理其特有特征，避免强制特征对齐。
  - **共享潜在先验**：所有模态的编码器输出映射到同一潜在空间，使用标准正态先验。
  - **对称跨模态对齐**：通过配对样本的潜在表示之间的一致性损失（如KL散度或对比损失）进行训练，无需预注释参考。
  - **可选监督头**：当细胞类型标签可用时，可添加分类损失来辅助学习。
  - **扩展性**：支持三模态（TEA-seq）和DNA甲基化（scNMT-seq，使用β-二项式似然），并支持马赛克设计（通过部分观测的跨模态桥接）。
- **算法流程简述**：
  1. 输入各模态原始数据（如基因表达计数、蛋白丰度、染色质peak计数）。
  2. 每个模态通过独立编码器生成潜在分布的参数（均值、方差）。
  3. 使用重参数化技巧采样潜在变量。
  4. 解码器从潜在变量重建各模态数据（使用适当似然函数，如负二项、泊松、β-二项式）。
  5. 损失函数 = 各模态的重建误差 + β ×（潜在空间与先验的KL散度）+ 跨模态对齐损失（可选标签损失）。
  6. 对于马赛克设计，利用配对模态（如RNA-蛋白质）作为桥梁，预测缺失模态的潜在表示。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集与场景**：
  - 配对RNA-蛋白质：CITE-seq（人类PBMCs）。
  - 配对RNA-染色质：10x Multiome、SHARE-seq（人类PBMCs和小鼠背部皮肤，一种具有连续分化等级的非造血组织）。
  - 三模态：TEA-seq（RNA、染色质可及性、表面蛋白）。
  - 配对+甲基化：scNMT-seq（小鼠原肠胚，概念验证，使用β-二项式似然）。
  - 马赛克设计：急性髓系白血病（AML）数据，包括配对RNA-蛋白质桥接+仅RNA队列+蛋白质+基因型队列。
  - 极端不平衡和模态专属群体测试（性能优雅退化）。
- **Benchmark**：未在摘要中明确列出基准方法，但应对比了其他多模态整合方法（如scVI、totalVI、MultiVI、MoMA等，从上下文推断）。摘要提到“改善标签转移”“跨模态重建与去噪”等指标，说明与标准方法进行了比较。
- **对比方法**：未明确列出，但可推断包括了无监督多模态整合模型。

### 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点。

- **未明确说明**：论文摘要及元数据中未提及具体的GPU型号、数量或训练时长。仅提及UniVI是“可扩展的”，但未提供算力细节。无法确认具体资源消耗。

### 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平。

- **实验组数**：
  - 至少4种配对场景（CITE-seq、10x Multiome、SHARE-seq、scNMT-seq）。
  - 1种三模态场景（TEA-seq）。
  - 1种马赛克设计（AML）。
  - 1种极端不平衡/专属群体测试。
  - 包括标签转移、跨模态重建、去噪、参考到查询投影等评估。
  - 消融实验未明确提及，但提到“性能优雅退化”说明可能有敏感性分析。
- **充分性**：数据集覆盖多种模态、多个组织（血液、皮肤、原肠胚），以及实际挑战（不平衡、专属群体），实验较充分。但缺少消融实验的具体描述，且未与其他方法量化对比（可能在全文中）。从摘要看，实验设计较为系统，但客观性需全文确认。

### 6. 论文的主要结论与发现

- UniVI能够生成**连贯的嵌入**，在配对数据上**改善标签转移**和**跨模态重构/去噪**。
- 扩展至**三模态**保持稳健的三向对齐；容纳DNA甲基化（scNMT-seq）作为概念验证。
- 在**严重细胞类型不平衡**和**模态专属群体**下性能优雅退化，但鲁棒。
- 在**马赛克设计**中，配对RNA-蛋白质桥接成功整合仅RNA和蛋白质+基因型队列，揭示基因型相关邻域，并通过微调进一步锐化。
- 提供了**灵活、可解释**的框架，支持**参考到查询投影**，适用于部分观测研究。

### 7. 优点：方法或实验设计上有哪些亮点

- **无需预注释参考**：对称跨模态对齐独立于标签，适用性广。
- **混合专家结构**：保留模态特异性，避免特征链接图，可扩展至任意数量模态。
- **可解释性**：潜在空间可明确解释为共享细胞状态。
- **处理缺失模态**：马赛克设计通过桥接实现部分观测数据的整合。
- **损失函数灵活性**：支持多种似然函数（负二项、泊松、β-二项式）适应不同数据类型。
- **实验覆盖多种实际场景**：包括连续分化组织、三模态、甲基化、不平衡、专属群体等。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **未报告计算资源**：缺乏GPU使用细节，难以判断可扩展性边界。
- **缺少与其他方法的直接比较**：摘要未列出性能对比表格，仅提及“改善”，但未量化（可能在全文中）。公平性需全文验证。
- **性能退化条件**：在严重不平衡和专属群体下“优雅退化”，但未说明退化程度，可能需要额外调整策略（如重采样）。
- **甲基化扩展仅为概念验证**：仅小鼠原肠胚单个数据集，缺乏广泛验证。
- **没有大规模多批次整合测试**：实验数据规模（细胞数、基因数）未提及，是否适用于百万级细胞未知。
- **潜在偏差风险**：对称对齐假设不同模态对细胞状态的贡献对称，但实际中某些模态可能主导，可能影响对齐质量。
- **泛化到新模态**：对于全新模态（如代谢、空间），可能需要定制似然函数和编码器。

（完）
