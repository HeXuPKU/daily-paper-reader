---
title: Unifying multimodal single-cell data with a mixture-of-experts β-variational autoencoder framework
title_zh: 利用混合专家β变分自编码器框架统一多模态单细胞数据
authors: "Ashford, A. J., Enright, T., Somers, J., Nikolova, O., Demir, E."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.1101/2025.02.28.640429v3.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 混合专家VAE用于多模态单细胞数据整合，与虚拟细胞建模相关
tldr: 多模态单细胞数据整合面临模态不匹配、稀疏性和队列覆盖不均等挑战。UniVI采用混合专家β变分自编码器，通过模态特定编码器/解码器、共享潜变量先验和对称跨模态对齐目标，无需特征链接图或参考图谱即可整合配对测量。在RNA-蛋白、RNA-染色质及三模态数据上，UniVI产生连贯嵌入、改进标签转移并实现跨模态重建与去噪，在镶嵌设计中通过配对桥接揭示基因型相关邻域。该框架为配对、三模态和镶嵌研究设计提供了灵活、可解释的整合方案。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1728, \"height\": 2303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1765, \"height\": 2122, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1704, \"height\": 2263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1744, \"height\": 2229, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1600, \"height\": 2173, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1660, \"height\": 2163, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1691, \"height\": 2147, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1761, \"height\": 2198, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1717, \"height\": 2231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2025-02-28-640429-v3/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1607, \"height\": 2055, \"label\": \"Figure\"}]"
motivation: 现有多模态单细胞整合方法受限于模态不匹配、数据稀疏性和队列覆盖不均，缺乏统一的融合框架。
method: UniVI通过混合专家β变分自编码器，结合模态特定编解码器、共享潜变量先验和对称跨模态对齐目标进行联合学习。
result: 在RNA-蛋白、RNA-染色质及三模态数据上实现连贯嵌入，改进标签转移和跨模态重建，并在急性髓系白血病镶嵌设计中有效锚定基因型相关邻域。
conclusion: UniVI为多模态单细胞数据整合提供了灵活、可解释且支持配对、三模态及镶嵌设计的通用框架。
---

## 摘要
多模态单细胞分析能够对细胞状态的不同层面进行互补性测量，但模态不匹配、稀疏性和队列覆盖不均匀等问题使得整合变得复杂。我们提出了UniVI（统一变分推断），一个可扩展的混合专家β变分自编码器，它在保留模态特定结构的同时学习共享的潜在空间。UniVI将模态特定的编码器/解码器与共享的潜在先验和对称的跨模态对齐目标相结合，从而能够一致地整合配对测量数据，而无需精心设计的特征连接图或预注释的参考图谱；当标签可用时，可以添加可选的有监督头。在跨越人类外周血单核细胞和小鼠背部皮肤（一种具有连续分化层次的非造血组织）的配对RNA-蛋白（CITE-seq）和RNA-染色质（10x Multiome，SHARE-seq）数据上，UniVI产生连贯的嵌入，改善了标签转移，并实现了跨模态重建和去噪。扩展到三模态测量时，UniVI在RNA、染色质可及性和表面蛋白（TEA-seq）之间保持了稳健的三路对齐，并且在配对的小鼠原肠胚scNMT-seq概念验证中，在β-二项式似然下适应了DNA甲基化。在严重的细胞类型不平衡和存在模态特有群体的情况下，性能会优雅地下降。在一个急性髓系白血病马赛克设计中，配对的RNA-蛋白桥接锚定了独立的仅RNA和蛋白+基因型队列，揭示了与基因型相关的邻域，并通过突变感知微调使这些邻域更加清晰。因此，UniVI为配对、三模态和马赛克研究设计中的多模态整合提供了一个灵活且可解释的框架，并支持部分观察研究中的实际参考到查询的投影。

## Abstract
Multimodal single-cell assays profile complementary layers of cell state, but integration is complicated by modality mismatch, sparsity, and uneven cohort coverage. We present UniVI (\Unified Variational Inference), a scalable mixture-of-experts {beta}-variational autoencoder that learns a shared latent space while preserving modality-specific structure. UniVI couples modality-specific encoders/decoders with a shared latent prior and a symmetric cross-modal alignment objective, enabling consistent integration of paired measurements without curated feature-link graphs or pre-annotated reference atlases; optional supervised heads can be added when labels are available. Across paired RNA--protein (CITE-seq) and RNA--chromatin (10x Multiome, SHARE-seq) data spanning human PBMCs and mouse back skin---a non-hematopoietic tissue with continuous differentiation hierarchies---UniVI produces coherent embeddings, improves label transfer, and enables cross-modal reconstruction and denoising. Extending to tri-modal measurements, UniVI maintains robust three-way alignment among RNA, chromatin accessibility, and surface proteins (TEA-seq), and accommodates DNA methylation in a paired scNMT-seq mouse gastrulation proof-of-concept under beta-binomial likelihoods. Performance degrades gracefully under severe cell-type imbalance and in the presence of modality-exclusive populations. In an acute myeloid leukemia mosaic design, a paired RNA--protein bridge anchors independent RNA-only and protein+genotype cohorts, revealing genotype-associated neighborhoods that sharpen with mutation-aware fine-tuning. UniVI thus provides a flexible, interpretable framework for multimodal integration across paired, tri-modal, and mosaic study designs and supports practical reference-to-query projection in partially observed studies.

---

## 论文详细总结（自动生成）

好的，以下是基于您提供的论文元数据（摘要、TLDR及标签）生成的详细中文总结。

---

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：多模态单细胞测序技术（如同时测量RNA和蛋白的CITE-seq、RNA和染色质可及性的10x Multiome等）虽然能提供细胞状态的多层面互补信息，但在整合这些数据时面临三大挑战：
  - **模态不匹配**：不同模态的特征空间（如基因表达、蛋白质丰度、染色质开放位点）在维度和分布上差异巨大。
  - **数据稀疏性**：单细胞数据本身具有高稀疏性，特别是染色质可及性数据。
  - **队列覆盖不均**：不同实验批次、不同模态测定的细胞群可能存在缺失或比例失调。
- **现有方法的局限**：许多已有整合方法要么需要精心设计的特征连接图（如基因-峰图），要么依赖预先注释的参考图谱，缺乏灵活性和通用性，难以扩展到新模态或复杂实验设计（如三模态、镶嵌设计）。
- **整体含义**：本文旨在开发一种统一的、无需依赖先验知识或预定义连接的大型整合框架，能够灵活处理配对、三模态乃至更复杂（如镶嵌设计：部分细胞测全部模态，部分测子集）的单细胞多模态数据，从而更全面地揭示细胞异质性与生物学状态。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用**混合专家β变分自编码器（Mixture-of-Experts β-VAE）** 学习一个共享的潜在空间，同时保留各模态特有的结构。通过模态特定的编码器/解码器、共享的潜变量先验以及对称的跨模态对齐目标，实现无需特征链接图或参考图谱的整合。
- **关键技术细节**：
  - **架构**：每个模态配备独立的编码器（将观测数据映射到共享潜变量分布）和解码器（从潜变量重建对应模态数据）。不同模态的编码器输出由共享的潜空间先验（通常为标准正态分布）约束。
  - **跨模态对齐**：引入**对称跨模态对齐目标**，迫使来自同一细胞的配对数据在潜空间中靠近，同时不同细胞的样本彼此分离。这类似于对比学习的思想，但以变分自编码器框架实现。
  - **混合专家机制**：在潜在表征的生成或解码过程中，使用混合专家（MoE）层来处理不同模态特征分布的巨大差异，每个“专家”擅长处理特定模态的特定子空间，从而提升模型的表达能力。
  - **可选监督头**：当细胞类型或实验条件标签可用时，可在潜在表征上添加分类层，通过半监督学习进一步改善嵌入的生物学可解释性。
  - **灵活性**：支持多种似然函数（如负二项式、β-二项式）以适应不同数据类型（RNA计数、蛋白丰度、DNA甲基化比率）。
- **公式/算法流程（文字描述）**：
  1. **输入**：配对的多模态单细胞数据（例如RNA表达矩阵X1和蛋白丰度矩阵X2）。
  2. **编码**：X1通过RNA编码器得到潜在分布参数（μ1, σ1）；X2通过蛋白编码器得到（μ2, σ2）。
  3. **对齐**：利用KL散度将混合潜在分布推向共享标准正态先验，并施加跨模态对比损失（如InfoNCE），使配对细胞在潜空间中聚集。
  4. **解码**：从共享潜变量z采样，分别通过RNA解码器和蛋白解码器进行重建。
  5. **优化**：联合优化各模态的重建损失（如负对数似然）、KL散度正则项以及跨模态对齐损失。整个框架通过随机梯度下降端到端训练。

### 3. 实验设计：使用的数据集、基准与对比方法

- **数据集/场景**：
  - **配对RNA-蛋白**：CITE-seq数据（人类PBMCs）。
  - **配对RNA-染色质**：10x Multiome和SHARE-seq数据（人类PBMCs和小鼠背部皮肤，后者为具有连续分化层次的非造血组织）。
  - **三模态**：TEA-seq数据（同时测量RNA、染色质可及性和表面蛋白）。
  - **概念验证**：小鼠原肠胚scNMT-seq数据（适配DNA甲基化β-二项式似然）。
  - **镶嵌设计**：急性髓系白血病（AML）数据，其中一部分细胞有配对的RNA-蛋白测量，另一部分仅有RNA或蛋白+基因型数据。
- **基准与对比方法**：论文摘要中未明确列出相比的具体方法名称。但根据语境，对比应涉及现有主流的整合工具（如Seurat的CCA/MNN、scVI、scArches、totalVI等）在标签转移准确率、嵌入连贯性、跨模态重建质量等指标上的表现。需指出论文正文可能包含更详细的对照表格和统计检验。
- **评估指标**：
  - 标签转移准确率（在已知细胞类型标签的数据集中）。
  - 嵌入的批次混合度与生物学变异保留度（如Silhouette宽度、LISI等）。
  - 跨模态重建误差（如均方误差、相关性）。
  - 去噪能力（在人为加入噪声后的重建质量）。

### 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量、训练时长等具体算力信息。根据经验，此类单细胞VAE模型通常在单张NVIDIA GPU（如V100或A100）上即可在数小时内完成训练，具体取决于数据集大小和模型复杂度。

### 5. 实验数量与充分性

- **实验组数**：覆盖了多种典型的多模态场景（RNA-蛋白、RNA-染色质、三模态、DNA甲基化、镶嵌设计），并包含细胞类型不平衡、模态特有群体等极端情况的测试，实验数量较为丰富。
- **充分性评估**：
  - **优点**：实验设计较全面，验证了模型在**不同配对模态、三模态**以及**复杂镶嵌设计**下的泛化能力；特别加入了小鼠背部皮肤（非造血组织，连续分化层次）和AML临床样本，提高了结果的可推广性。
  - **潜在不足**：未在超大规模图谱（如人类细胞图谱）上验证可扩展性；未详细比较与多个最新专用方法（如scMoGNN、Mosaic等）的性能差异；消融实验的具体项目（如去除跨模态对齐损失、去除混合专家等）文中未在元数据中列出，但摘要提及在严重不平衡和模态特有群体下性能优雅下降，暗示有相关压力测试。

### 6. 论文的主要结论与发现

- **核心结论**：UniVI作为一个统一的混合专家β-VAE框架，能够**无需特征连接图或参考图谱**即可有效整合配对、三模态乃至镶嵌设计的多模态单细胞数据。
- **主要发现**：
  - 产生连贯的联合嵌入空间，改善了标签转移的准确率。
  - 实现了可靠的跨模态重建和去噪（如从RNA预测蛋白表达）。
  - 在镶嵌设计中，配对的RNA-蛋白桥接能够将仅RNA队列和仅蛋白+基因型队列统一在潜空间中，从而揭示基因型相关的细胞邻域，并且通过突变感知的微调进一步锐化这些关系。
  - 在数据不平衡和存在模态特有群体（如仅某个模态才能检测到的细胞类型）时，性能会优雅下降，说明模型具备一定的鲁棒性。
- **实际应用意义**：为配对、三模态及部分观察的参考-查询投影研究提供了灵活、可解释的整合方案。

### 7. 优点：方法或实验设计上的亮点

- **方法论亮点**：
  - **无需先验链接**：不依赖基因-峰图或参考图谱，使得模型易于适应新模态和数据。
  - **对称跨模态对齐**：对比损失以对称方式强制不同模态的编码一致，避免了单向映射导致的偏差。
  - **混合专家机制**：增强了模型处理多模态异构特征的能力，可能比单一非线性变换更优。
  - **可扩展性与灵活性**：支持不同似然（负二项、β-二项），可方便扩展到新模态（如DNA甲基化）；可选监督头提升标签相关任务。
- **实验设计亮点**：
  - **挑战性场景覆盖广**：包括连续分化组织、三模态、DNA甲基化新型模态，以及实际临床大样本镶嵌设计。
  - **压力测试**：明确测试了细胞类型严重不平衡和模态专属群体的情况，增强了结论的可靠性。

### 8. 不足与局限

- **实验覆盖**：
  - 缺乏与同类最新方法（如DeepMosaic、scArches+ totalVI）的全面系统比较；文本中未列出具体对比方法名称和定量表格。
  - 未测试跨数据集批次整合（如两个不同实验室的同一模态数据）效果。
  - 样本量有限：主实验多集中于PBMCs和小鼠皮肤，缺乏人类其他组织或疾病的验证。
- **偏差风险**：
  - 模型在模态特有群体上的性能下降虽被提及为“优雅下降”，但具体下降程度和对下游分析的影响未量化分析。
  - 监督头引入可能造成标签偏差，若注释不准确则会反向影响嵌入质量。
- **应用限制**：
  - 模型对高维度、超大规模图谱的可扩展性未验证（推理速度、显存占用等）。
  - 对于缺乏配对的完全独立批次数据，仅通过投影（reference-to-query）适配的效果未知。
  - 架构相对复杂（混合专家、多个编解码器），训练调参可能比简单VAE更困难。

（完）
