---
title: "FoundedPBI: Using Genomic Foundation Models to predict Phage-Bacterium Interactions"
title_zh: FoundedPBI：利用基因组基础模型预测噬菌体-细菌相互作用
authors: "Carrillo Barrera, P., Babey, A., Pena, C. A."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.713871v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于生物预测的基因组基础模型和 DNA 语言模型
tldr: "FoundedPBI 是一种利用基因组基础模型预测噬菌体与细菌相互作用的集成深度学习方法。针对传统实验筛选效率低的问题，该方法集成了 Nucleotide Transformer v2、DNABERT-2 和 MegaDNA 三种模型，并创新性地解决了超长基因组序列（达 5M bp）的处理难题。实验表明，该方法在 PredPHI 基准测试中 F1 分数达到 76%，显著优于现有技术，为加速噬菌体疗法开发提供了高效的计算工具。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-713871-v1/fig-001.webp\", \"caption\": \"Figure 2 Joint UMAP projection of phage embeddings from the three foundation models. The distinct spatial organisation across models confirms that they capture complementary genomic features. Inset: Spearman ρ between pairwise distance matrices computed on the original embeddings.\", \"page\": 5, \"index\": 1, \"width\": 534, \"height\": 470}]"
motivation: 传统的噬菌体-细菌相互作用实验筛选过程耗时耗力，限制了噬菌体疗法的规模化应用。
method: 提出 FoundedPBI 框架，通过集成多种针对原核生物和噬菌体预训练的基因组基础模型，并结合长文本聚合策略处理全基因组序列。
result: "在 PredPHI 基准测试中 F1 分数提升至 76%（比 SOTA 提高 7%），在内部数据集上达到 93% 的 F1 分数。"
conclusion: 集成学习结合有效的长序列处理策略，能成功将基因组基础模型的知识迁移到特定的生物预测任务中。
---

## 摘要
噬菌体疗法作为抗生素的可行替代或补充，其可扩展性受到识别兼容噬菌体-细菌对所需的高强度实验筛选的限制。为了加速这一发现过程，我们提出了 FoundedPBI，这是一种集成深度学习方法，利用了基因组基础模型（在海量 DNA 语料库上预训练的大语言模型）的涌现能力，仅通过 DNA 序列来预测噬菌体-细菌相互作用。我们采用了一种集成策略，将三种最先进的 DNA 语言模型的输出聚合为一个统一的元嵌入（meta-embedding），随后由神经分类器进行处理。我们的方法有两个主要贡献：（1）我们证明了在针对不同基因组数据（即原核生物（Nucleotide Transformer v2, DNABERT-2）和噬菌体（MegaDNA）基因组）训练的模型之间进行集成学习，可以捕捉到部分正交的生物信号，相比于最佳的单一模型，F1 分数提高了 6%。（2）我们改进了长上下文 NLP 聚合策略，以处理完整的细菌和噬菌体基因组（高达 500 万个碱基对），这些基因组超过了基础模型上下文窗口（12-96K bp）50 到 100 倍，这是先前基因组深度学习工作中很大程度上未解决的关键挑战。在 PredPHI 基准测试中，FoundedPBI 达到了 76% 的 F1 分数，比目前最先进的方法（PBIP）高出 7%。在我们的内部数据集（CI4CB）上，我们达到了 93% 的 F1 分数，比我们之前的最佳方法提高了 4%。这些结果表明，结合适当的长上下文处理，集成学习能够实现基因组基础模型向专门预测任务的有效知识迁移。

## Abstract
The scalability of phage therapy as a viable alternative or complement to antibiotics is limited by the labor-intensive experimental screening required to identify compatible phage-bacterium pairs. To accelerate this discovery process, we propose FoundedPBI, an ensemble deep learning approach that leverages the emergent capabilities of genomic foundation models, large language models pre-trained on vast DNA corpuses to predict phage-bacterium interactions from DNA sequences alone. We employ an ensemble strategy that aggregates outputs from three state-of-the-art DNA language models into a unified meta-embedding, which is then processed by a neural classifier. Our approach makes two key contributions: (1) We demonstrate that performing ensemble learning across models trained on different genomic data i.e., prokaryotic (Nucleotide Transformer v2, DNABERT-2) and bacteriophage (MegaDNA) genomes, captures partially-orthogonal biological signals, yielding 6% F1-score improvement over the best individual model. (2) We adapt long-context NLP aggregation strategies to handle whole bacterial and phage genomes (up to 5M base pairs) that exceed the foundation models context windows (12-96K bp) by a factor of 50-100, a critical challenge largely unaddressed in prior genomic deep learning work. On the PredPHI benchmark, FoundedPBI achieves a 76% F1-score outperforming the current state-of-the-art (PBIP) by 7%. On our internal dataset (CI4CB), we achieve 93% F1-score, improving our previous best methods by 4%. These results demonstrate that ensemble learning with proper long-context handling enables effective knowledge transfer of genomic foundation models to specialized prediction tasks.

---

## 论文详细总结（自动生成）

这是一份关于论文《FoundedPBI: Using Genomic Foundation Models to predict Phage-Bacterium Interactions》的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **研究背景**：抗生素耐药性（AMR）已成为全球公共卫生威胁，噬菌体疗法（使用病毒杀灭细菌）是极具潜力的替代方案。
*   **核心问题**：噬菌体具有高度特异性，传统的实验筛选（如双层琼脂平板法）耗时耗力，严重限制了噬菌体疗法的规模化应用。
*   **研究目标**：开发一种仅基于 DNA 序列即可准确预测噬菌体与细菌相互作用（PBI）的计算工具，以加速临床匹配过程。

### 2. 论文提出的方法论：FoundedPBI
*   **核心思想**：利用**基因组基础模型（Genomic Foundation Models）**的涌现能力，通过集成学习捕捉不同维度的生物信号。
*   **关键技术细节**：
    *   **集成架构**：集成了三种最先进的 DNA 语言模型：
        1.  **Nucleotide Transformer v2 (NTv2)**：在海量原核生物基因组上预训练。
        2.  **DNABERT-2**：采用多物种基因组训练，具有良好的通用性。
        3.  **MegaDNA**：专门针对噬菌体基因组进行预训练。
    *   **长序列处理策略**：针对细菌基因组（可达 5M bp）远超模型上下文窗口（12K-96K bp）的问题，采用**滑动窗口截断 + 均值池化（Mean Pooling）**的聚合策略，将全基因组信息压缩为固定维度的嵌入向量。
    *   **元嵌入分类器**：将三个模型的输出拼接成“元嵌入（Meta-embedding）”，输入到一个多层感知机（MLP）分类器中进行最终的二元预测（相互作用 vs 不相互作用）。

### 3. 实验设计
*   **数据集**：
    *   **PredPHI**：公开的基准数据集，包含多种噬菌体和细菌对。
    *   **CI4CB**：研究团队内部的数据集，包含更丰富的样本。
*   **Benchmark（基准）**：
    *   **PBIP**：目前该领域最先进的（SOTA）预测方法。
    *   **单模型对比**：分别测试 NTv2、DNABERT-2 和 MegaDNA 独立运行的效果。
*   **评估指标**：主要使用 F1 分数、准确率（Accuracy）和召回率（Recall）。

### 4. 资源与算力
*   **算力说明**：论文中提到处理长达 5M bp 的序列对计算资源提出了巨大挑战，但**未明确列出具体的 GPU 型号、数量或具体的训练总时长**。
*   **实现细节**：提到了使用长上下文 NLP 聚合策略来优化内存使用，暗示了该方法对显存有较高要求。

### 5. 实验数量与充分性
*   **实验规模**：
    *   进行了跨数据集的验证（PredPHI 和 CI4CB）。
    *   进行了**消融实验**，对比了不同模型组合（如单模型 vs 双模型 vs 三模型集成）的效果。
    *   对比了不同的长序列聚合策略（如首位 Token 聚合 vs 均值池化）。
*   **充分性评价**：实验设计较为充分，通过 UMAP 可视化证明了不同基础模型捕捉到的生物信号具有“正交性”（互补性），有力支撑了集成学习的必要性。

### 6. 主要结论与发现
*   **性能提升**：FoundedPBI 在 PredPHI 基准测试中 F1 分数达到 **76%**，比之前的 SOTA（PBIP）高出 **7%**。在内部数据集上达到 **93%**。
*   **集成优势**：集成模型比表现最好的单一模型（NTv2）在 F1 分数上提高了 **6%**，证明了结合原核生物背景和噬菌体背景模型的有效性。
*   **长序列处理**：证明了即使基础模型的上下文窗口有限，通过合理的聚合策略，依然可以从全基因组尺度提取关键的交互特征。

### 7. 优点（亮点）
*   **多模型协同**：创新性地结合了针对不同生物领域（细菌 vs 噬菌体）预训练的模型，捕捉到了更全面的生物特征。
*   **突破长度限制**：解决了基因组深度学习中长期存在的“超长序列处理”难题，使模型能够处理真实世界的完整基因组。
*   **端到端预测**：无需人工提取复杂的生物学特征（如蛋白质结构或受体结合蛋白），仅依赖原始 DNA 序列。

### 8. 不足与局限
*   **计算开销**：集成三个大型基础模型意味着推理时的计算成本和延迟较高，可能不利于在资源受限的环境下部署。
*   **黑盒性质**：虽然预测精度高，但对于“为什么”这对噬菌体和细菌会发生相互作用，缺乏直观的生物学解释性（可解释性不足）。
*   **数据偏差风险**：尽管在基准集上表现良好，但 PBI 数据集通常存在严重的类不平衡问题（负样本远多于正样本），模型在极稀有菌株上的泛化能力仍需进一步验证。

（完）
