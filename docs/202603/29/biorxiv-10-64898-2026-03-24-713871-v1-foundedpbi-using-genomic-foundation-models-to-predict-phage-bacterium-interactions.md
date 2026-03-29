---
title: "FoundedPBI: Using Genomic Foundation Models to predict Phage-Bacterium Interactions"
title_zh: FoundedPBI：利用基因组基础模型预测噬菌体-细菌相互作用
authors: "Carrillo Barrera, P., Babey, A., Pena, C. A."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.713871v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 在海量DNA语料库上预训练的基因组基础模型
tldr: FoundedPBI 是一种利用基因组基础模型预测噬菌体-细菌相互作用（PBI）的集成深度学习方法。针对传统实验筛选效率低的问题，该研究整合了针对原核生物和噬菌体预训练的多种 DNA 语言模型，并创新性地解决了超长基因组序列（达 5M bp）的上下文处理难题。实验证明，该方法在 PredPHI 和 CI4CB 数据集上均显著优于现有技术，为加速噬菌体疗法开发提供了高效的计算工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-713871-v1/fig-001.webp\", \"caption\": \"Figure 2 Joint UMAP projection of phage embeddings from the three foundation models. The distinct spatial organisation across models confirms that they capture complementary genomic features. Inset: Spearman ρ between pairwise distance matrices computed on the original embeddings.\", \"page\": 5, \"index\": 1, \"width\": 534, \"height\": 470}]"
motivation: 传统的噬菌体-细菌相互作用实验筛选过程耗时耗力，限制了噬菌体疗法的大规模应用。
method: 采用集成学习策略融合了 Nucleotide Transformer v2、DNABERT-2 和 MegaDNA 三种基础模型的特征，并结合长文本聚合策略处理超长基因组序列。
result: "在 PredPHI 基准测试中 F1 分数达到 76%，比现有最优模型提升 7%，在内部数据集上达到 93% 的 F1 分数。"
conclusion: 通过集成不同基因组背景的基础模型并妥善处理长上下文，可以有效提升噬菌体-细菌相互作用预测的准确性。
---

## 摘要
噬菌体疗法作为抗生素的可行替代或补充，其可扩展性受到识别兼容噬菌体-细菌对所需的大量实验筛选工作的限制。为了加速这一发现过程，我们提出了 FoundedPBI，这是一种集成深度学习方法，利用了基因组基础模型（在海量 DNA 语料库上预训练的大语言模型）的涌现能力，仅通过 DNA 序列预测噬菌体-细菌相互作用。我们采用了一种集成策略，将三个最先进的 DNA 语言模型的输出聚合为一个统一的元嵌入（meta-embedding），然后由神经分类器进行处理。我们的方法有两个主要贡献：(1) 我们证明了在针对不同基因组数据（即原核生物（Nucleotide Transformer v2, DNABERT-2）和噬菌体（MegaDNA）基因组）训练的模型之间进行集成学习，可以捕捉到部分正交的生物信号，使 F1 分数比最佳单一模型提高了 6%。(2) 我们调整了长上下文 NLP 聚合策略，以处理完整的细菌和噬菌体基因组（高达 500 万个碱基对），这些基因组超过了基础模型上下文窗口（12-96K bp）50-100 倍，这是先前基因组深度学习工作中很大程度上未解决的关键挑战。在 PredPHI 基准测试中，FoundedPBI 实现了 76% 的 F1 分数，比当前最先进的方法 (PBIP) 高出 7%。在我们的内部数据集 (CI4CB) 上，我们实现了 93% 的 F1 分数，比我们之前的最佳方法提高了 4%。这些结果表明，结合适当的长上下文处理，集成学习能够实现基因组基础模型向专门预测任务的有效知识迁移。

## Abstract
The scalability of phage therapy as a viable alternative or complement to antibiotics is limited by the labor-intensive experimental screening required to identify compatible phage-bacterium pairs. To accelerate this discovery process, we propose FoundedPBI, an ensemble deep learning approach that leverages the emergent capabilities of genomic foundation models, large language models pre-trained on vast DNA corpuses to predict phage-bacterium interactions from DNA sequences alone. We employ an ensemble strategy that aggregates outputs from three state-of-the-art DNA language models into a unified meta-embedding, which is then processed by a neural classifier. Our approach makes two key contributions: (1) We demonstrate that performing ensemble learning across models trained on different genomic data--i.e., prokaryotic (Nucleotide Transformer v2, DNABERT-2) and bacteriophage (MegaDNA) genomes--captures partially-orthogonal biological signals, yielding 6% F1-score improvement over the best individual model. (2) We adapt long-context NLP aggregation strategies to handle whole bacterial and phage genomes (up to 5M base pairs) that exceed the foundation models context windows (12-96K bp) by a factor of 50-100, a critical challenge largely unaddressed in prior genomic deep learning work. On the PredPHI benchmark, FoundedPBI achieves a 76% F1-score outperforming the current state-of-the-art (PBIP) by 7%. On our internal dataset (CI4CB), we achieve 93% F1-score, improving our previous best methods by 4%. These results demonstrate that ensemble learning with proper long-context handling enables effective knowledge transfer of genomic foundation models to specialized prediction tasks.

---

## 论文详细总结（自动生成）

### 论文总结：FoundedPBI——利用基因组基础模型预测噬菌体-细菌相互作用

#### 1. 核心问题与整体含义（研究动机和背景）
随着多重耐药（MDR）细菌成为全球健康威胁，噬菌体疗法作为抗生素的替代方案重新受到关注。然而，噬菌体具有高度的宿主特异性，依靠传统的实验筛选来匹配有效的噬菌体-细菌对既耗时又昂贵。该研究的核心问题是如何利用计算方法，仅通过 DNA 序列高效、准确地预测噬菌体与细菌之间的相互作用（PBI）。研究背景在于，虽然基因组基础模型（Genomic Foundation Models）在多种任务中表现出色，但在 PBI 预测中面临两个挑战：一是不同模型训练数据（如仅针对原核生物或仅针对噬菌体）带来的偏差；二是基因组序列极长（达 5M bp），远超现有模型的上下文窗口（12-96K bp）。

#### 2. 方法论：核心思想与关键技术
FoundedPBI 采用了一种**集成深度学习框架**，其核心思想是融合多个具有不同生物学偏置的基础模型特征，并引入长文本处理策略。
*   **集成策略**：整合了三个最先进的模型：
    *   **Nucleotide Transformer v2 (250M)**：基于原核生物和真核生物基因组训练。
    *   **DNABERT-2**：采用 BPE 分词，在多物种基因组上训练。
    *   **MegaDNA**：专门针对 10 万个噬菌体基因组训练的生成式模型。
*   **长上下文处理**：借鉴 NLP 处理长文档的策略，将超长 DNA 序列切分为固定长度的块（Chunks），并测试了多种聚合策略（如 Truncate、Average、TK-Pert 等），以捕捉全基因组信号。
*   **元嵌入（Meta-embedding）构建**：
    1.  将三个模型的输出拼接。
    2.  使用 **PCA（主成分分析）** 将维度压缩至 500 维（保留 99.99% 方差）。
    3.  引入 **NEFTune 噪声增强**：在训练期间向嵌入添加高斯噪声，以提高泛化能力。
*   **分类头**：使用简单的多层感知机（MLP）作为唯一可训练的组件，实现最终的二分类预测。

#### 3. 实验设计
研究在两个主要基准上进行了评估：
*   **数据集**：
    *   **CI4CB**：内部数据集，包含 7721 次相互作用（231 种细菌，3539 种噬菌体），用于与团队之前的模型对比。
    *   **PredPHI**：独立外部基准数据集，包含 6938 次相互作用（301 种细菌，3449 种噬菌体），用于与 SOTA 方法对比。
*   **对比方法**：
    *   **内部基准**：PERPHECT（基于 CNN）、Distilled DNABERT（基于 LSTM）。
    *   **外部 SOTA**：PBIP（基于蛋白质嵌入和 CNN-GRU 架构）、PredPHI。
*   **评估指标**：Precision、Recall、F1-score、Accuracy、MCC 等。

#### 4. 资源与算力
论文**未明确说明**具体的 GPU 型号、数量或总训练时长。但文中提到了一些资源限制的细节：
*   在处理 PredPHI 数据集时，由于 **VRAM（显存）限制**，不得不将 DNABERT-2 的上下文长度从理论上的更长距离缩减至 16K bp。
*   由于分类头非常轻量（仅 MLP），且基础模型作为非训练骨干（Frozen Backbone），主要的计算开销集中在特征提取阶段。

#### 5. 实验数量与充分性
实验设计较为全面且客观：
*   **消融实验**：分别测试了单一基础模型 vs. 集成模型的表现，验证了集成学习的增益。
*   **策略对比**：系统评估了 1296 种长上下文聚合配置，证明了复杂聚合策略优于简单的截断（Truncate）策略。
*   **鲁棒性测试**：验证了 PCA 压缩和 NEFTune 噪声对模型性能和泛化的影响。
*   **分类学分析**：对预测错误进行了分类学层面的深入分析，探讨了模型在不同细菌家族上的表现差异。
*   **验证方法**：采用了 10 折交叉验证，并在物种水平上划分验证集，防止数据泄露。

#### 6. 主要结论与发现
*   **集成优势**：集成不同训练背景（原核 vs. 噬菌体）的模型能捕捉正交的生物信号，F1 分数比单一最佳模型提升了 6%。
*   **性能领先**：在 PredPHI 基准上 F1 达到 76%（超过 SOTA 7%）；在 CI4CB 上达到 93%（超过前作 4%）。
*   **长上下文的重要性**：在复杂数据集（PredPHI）上，合理的聚合策略比简单截断提升了 12% 的 F1 分数。
*   **分类学差异**：模型在放线菌门（如链霉菌）上表现极佳，但在某些临床关键的革兰氏阴性菌（如铜绿假单胞菌）上错误率较高，这可能与这些细菌复杂的表面受体结构有关。

#### 7. 优点
*   **模块化设计**：框架灵活，可以轻松更换或添加新的基因组基础模型。
*   **跨领域迁移**：成功将 NLP 处理长文本的成熟技术（如 TK-Pert）引入基因组学领域。
*   **无需微调**：利用预训练模型的涌现能力，仅训练极小的分类头即可达到 SOTA，降低了计算门槛。
*   **泛化能力强**：通过噪声增强和集成学习，在跨物种的独立测试集上表现稳健。

#### 8. 不足与局限
*   **生物学解释性不足**：目前模型仍属于“黑盒”，无法明确指出是哪些具体的 DNA 基序（Motifs）决定了相互作用。
*   **特定物种瓶颈**：对于某些病原体（如铜绿假单胞菌、鲍曼不动杆菌），预测错误率依然较高，这限制了其在某些紧急临床场景下的应用。
*   **计算开销**：虽然分类头轻量，但同时运行三个大型基础模型进行推理，对于资源受限的环境仍有一定压力。
*   **数据依赖**：模型性能仍受限于训练数据的质量和多样性，尤其是负样本（非感染关系）的准确性。

（完）
