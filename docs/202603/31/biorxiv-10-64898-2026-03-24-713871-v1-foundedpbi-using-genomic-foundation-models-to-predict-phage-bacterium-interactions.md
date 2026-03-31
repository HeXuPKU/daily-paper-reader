---
title: "FoundedPBI: Using Genomic Foundation Models to predict Phage-Bacterium Interactions"
title_zh: FoundedPBI：利用基因组基础模型预测噬菌体-细菌相互作用
authors: "Carrillo Barrera, P., Babey, A., Pena, C. A."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.713871v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 利用在DNA语料库上预训练的基因组基础模型
tldr: "FoundedPBI 是一种利用基因组基础模型预测噬菌体与细菌相互作用的集成深度学习方法。该研究通过整合针对原核生物和噬菌体预训练的多种 DNA 语言模型（如 Nucleotide Transformer v2、DNABERT-2 和 MegaDNA），并采用长文本聚合策略处理超长基因组序列，显著提升了预测精度。在 PredPHI 和 CI4CB 数据集上，该方法分别达到了 76% 和 93% 的 F1 分数，超越了现有最先进技术，为加速噬菌体疗法的筛选提供了高效的计算工具。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-713871-v1/fig-001.webp\", \"caption\": \"Figure 2 Joint UMAP projection of phage embeddings from the three foundation models. The distinct spatial organisation across models confirms that they capture complementary genomic features. Inset: Spearman ρ between pairwise distance matrices computed on the original embeddings.\", \"page\": 5, \"index\": 1, \"width\": 534, \"height\": 470}]"
motivation: 传统的实验筛选噬菌体-细菌匹配对耗时耗力，限制了噬菌体疗法的规模化应用，亟需高效的计算预测方法。
method: 提出 FoundedPBI 框架，通过集成三种针对不同基因组数据预训练的基础模型，并结合长文本 NLP 聚合策略来处理长达 5M bp 的全基因组序列。
result: "在 PredPHI 基准测试中 F1 分数达到 76%，比现有 SOTA 方法提升了 7%，在内部数据集上提升了 4%。"
conclusion: 研究证明了通过集成学习和有效的长文本处理，可以将基因组基础模型的知识成功迁移到噬菌体-细菌相互作用预测等专业任务中。
---

## 摘要
噬菌体疗法作为抗生素的可行替代或补充，其可扩展性受到识别兼容噬菌体-细菌对所需的大量实验筛选工作的限制。为了加速这一发现过程，我们提出了 FoundedPBI，这是一种集成深度学习方法，利用了基因组基础模型（在海量 DNA 语料库上预训练的大语言模型）的涌现能力，仅通过 DNA 序列预测噬菌体-细菌的相互作用。我们采用了一种集成策略，将三个最先进的 DNA 语言模型的输出聚合为一个统一的元嵌入（meta-embedding），然后由神经分类器进行处理。我们的方法有两个主要贡献：(1) 我们证明了在针对不同基因组数据（即原核生物（Nucleotide Transformer v2, DNABERT-2）和噬菌体（MegaDNA）基因组）训练的模型之间进行集成学习，可以捕捉到部分正交的生物信号，相比于最佳的单一模型，F1 分数提高了 6%。(2) 我们改进了长上下文 NLP 聚合策略，以处理完整的细菌和噬菌体基因组（高达 500 万个碱基对），这些基因组超过了基础模型上下文窗口（12-96K bp）50 到 100 倍，这是先前基因组深度学习工作中很大程度上未解决的关键挑战。在 PredPHI 基准测试中，FoundedPBI 达到了 76% 的 F1 分数，比当前最先进的方法（PBIP）高出 7%。在我们的内部数据集（CI4CB）上，我们达到了 93% 的 F1 分数，比我们之前的最佳方法提高了 4%。这些结果表明，结合适当的长上下文处理，集成学习能够实现基因组基础模型向专门预测任务的有效知识迁移。

## Abstract
The scalability of phage therapy as a viable alternative or complement to antibiotics is limited by the labor-intensive experimental screening required to identify compatible phage-bacterium pairs. To accelerate this discovery process, we propose FoundedPBI, an ensemble deep learning approach that leverages the emergent capabilities of genomic foundation models, large language models pre-trained on vast DNA corpuses to predict phage-bacterium interactions from DNA sequences alone. We employ an ensemble strategy that aggregates outputs from three state-of-the-art DNA language models into a unified meta-embedding, which is then processed by a neural classifier. Our approach makes two key contributions: (1) We demonstrate that performing ensemble learning across models trained on different genomic data--i.e., prokaryotic (Nucleotide Transformer v2, DNABERT-2) and bacteriophage (MegaDNA) genomes--captures partially-orthogonal biological signals, yielding 6% F1-score improvement over the best individual model. (2) We adapt long-context NLP aggregation strategies to handle whole bacterial and phage genomes (up to 5M base pairs) that exceed the foundation models context windows (12-96K bp) by a factor of 50-100, a critical challenge largely unaddressed in prior genomic deep learning work. On the PredPHI benchmark, FoundedPBI achieves a 76% F1-score outperforming the current state-of-the-art (PBIP) by 7%. On our internal dataset (CI4CB), we achieve 93% F1-score, improving our previous best methods by 4%. These results demonstrate that ensemble learning with proper long-context handling enables effective knowledge transfer of genomic foundation models to specialized prediction tasks.

---

## 论文详细总结（自动生成）

### 论文总结：FoundedPBI —— 利用基因组基础模型预测噬菌体-细菌相互作用

#### 1. 核心问题与研究动机
*   **核心问题**：如何利用计算方法准确预测噬菌体（病毒）与细菌之间的感染关系，以加速噬菌体疗法的筛选过程。
*   **研究动机**：多重耐药菌（MDR）已成为全球健康威胁，噬菌体疗法是抗生素的重要补充。然而，由于噬菌体与其宿主之间存在高度特异性，传统的实验筛选方法耗时耗力。虽然基因组序列中包含相互作用的信息，但现有的预测模型在处理超长基因组序列和利用大规模预训练模型方面仍存在局限。

#### 2. 方法论
FoundedPBI 采用了一种集成深度学习框架，其核心流程如下：
*   **多模型集成（Ensemble Learning）**：整合了三种具有不同架构和训练数据的基因组基础模型（GFM）：
    *   **Nucleotide Transformer v2**：基于编码器架构，在人类及多种生物基因组上训练（不含病毒）。
    *   **DNABERT-2**：基于 BERT 架构，使用 BPE 分词，在多物种基因组上训练。
    *   **MegaDNA**：基于解码器架构，专门在 10 万个噬菌体基因组上训练。
*   **长上下文处理策略**：针对细菌基因组（约 5M bp）远超模型上下文窗口（12K-96K bp）的问题，借鉴 NLP 处理长文档的策略，测试了包括截断（Truncate）、平均（Average）、最大值（Maximum）以及平滑重叠窗口（TK-Pert）等多种聚合方法。
*   **元嵌入（Meta-Embedding）构建**：
    1.  将三个模型的输出拼接。
    2.  使用 **PCA（主成分分析）** 将维度压缩至 500 维（保留 99.99% 方差）。
    3.  引入 **NEFTune 噪声增强**：在训练期间向嵌入中添加高斯噪声，以提高泛化能力。
*   **分类头**：使用简单的多层感知机（MLP）作为唯一的训练组件，进行二分类预测。

#### 3. 实验设计
*   **数据集**：
    *   **CI4CB**：内部数据集，包含 7721 次相互作用（231 种细菌，3539 种噬菌体），用于与团队前期工作对比。
    *   **PredPHI**：独立基准数据集，包含 6938 次相互作用（301 种细菌，3449 种噬菌体），用于与 SOTA 方法对比。
*   **对比方法（Benchmark）**：
    *   **PERPHECT**：基于 CNN 的早期模型。
    *   **Distilled DNABERT**：基于 DNABERT 和 LSTM 的改进模型。
    *   **PBIP（当前 SOTA）**：基于蛋白质序列嵌入（UniRep）和 CNN-GRU 架构的模型。
    *   **PredPHI**：该数据集的原始基准模型。

#### 4. 资源与算力
*   **算力说明**：论文中**未明确列出**具体的 GPU 型号、数量或总训练时长。
*   **相关提及**：作者提到在处理 PredPHI 数据集时，由于显存（VRAM）限制，不得不将 DNABERT-2 的上下文长度缩减至 16K bp。这暗示了该模型对显存有一定要求，但整体框架由于只需训练轻量级的 MLP 分类头，计算开销相对较小。

#### 5. 实验数量与充分性
*   **实验规模**：
    *   针对长上下文策略进行了网格搜索，测试了 **1,296 种配置**。
    *   采用了 **10 折交叉验证**（10-Fold Cross Validation）以确保结果的稳定性。
    *   进行了详细的**消融实验**，验证了集成学习、长上下文策略、PCA 压缩和噪声增强的有效性。
*   **充分性评价**：实验设计较为充分且客观。通过在内部和外部两个数据集上的验证，证明了模型的泛化能力。特别是针对不同细菌家族的分类错误分析，体现了研究的深度。

#### 6. 主要结论与发现
*   **集成优势**：集成不同训练背景的模型（原核生物 vs 噬菌体）能捕捉正交的生物信号。在 PredPHI 上，集成模型比表现最好的单一模型（MegaDNA）F1 分数高出 6%。
*   **性能突破**：FoundedPBI 在 PredPHI 基准测试中 F1 达到 76%，超越 SOTA 方法 PBIP 达 7%；在 CI4CB 数据集上达到 93%，比前期方法提升 4%。
*   **长上下文的重要性**：简单的截断策略会导致性能大幅下降（PredPHI 上下降 12%），证明了整合全基因组信息对预测的重要性。
*   **分类差异**：预测难度具有显著的分类学依赖性。革兰氏阴性菌（如假单胞菌属）的预测错误率远高于放线菌，这可能与复杂的表面受体结构有关。

#### 7. 优点
*   **模块化设计**：框架灵活，可以轻松更换或添加新的基因组基础模型。
*   **跨领域迁移**：成功将 NLP 领域的长文本处理和集成学习技术迁移至基因组学任务。
*   **高效性**：无需对庞大的基础模型进行微调（Fine-tuning），仅训练分类头即可达到 SOTA 性能，节省了计算资源。

#### 8. 不足与局限
*   **生物可解释性**：目前模型仍是一个“黑盒”，虽然预测准确，但尚未能明确指出是哪些具体的 DNA 序列特征（如特定受体结合蛋白）决定了相互作用。
*   **分类学偏差**：对于临床上急需噬菌体疗法的某些病原体（如假单胞菌），模型的错误率仍然较高，表明模型可能未完全捕捉到多变的表面结构信息。
*   **数据依赖**：尽管使用了基础模型，但分类头的性能仍受限于训练数据的质量和多样性。

（完）
