---
title: "FoundedPBI: Using Genomic Foundation Models to predict Phage-Bacterium Interactions"
title_zh: FoundedPBI：利用基因组基础模型预测噬菌体-细菌相互作用
authors: "Carrillo Barrera, P., Babey, A., Pena, C. A."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.713871v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 基因组基础模型和DNA语言模型用于噬菌体-细菌相互作用
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
噬菌体疗法作为抗生素的可行替代或补充，其可扩展性受到识别兼容噬菌体-细菌对所需的大量实验筛选工作的限制。为了加速这一发现过程，我们提出了 FoundedPBI，这是一种集成深度学习方法，它利用了基因组基础模型（在海量 DNA 语料库上预训练的大语言模型）的涌现能力，仅通过 DNA 序列来预测噬菌体-细菌的相互作用。我们采用了一种集成策略，将三个最先进的 DNA 语言模型的输出聚合为一个统一的元嵌入（meta-embedding），然后由神经分类器进行处理。我们的方法有两个主要贡献：(1) 我们证明了在针对不同基因组数据（即原核生物（Nucleotide Transformer v2, DNABERT-2）和噬菌体（MegaDNA）基因组）训练的模型之间进行集成学习，可以捕捉到部分正交的生物信号，使 F1 分数比最佳单一模型提高了 6%。(2) 我们调整了长上下文 NLP 聚合策略，以处理完整的细菌和噬菌体基因组（高达 500 万个碱基对），这些基因组超过了基础模型上下文窗口（12-96K bp）50-100 倍，这是先前基因组深度学习工作中很大程度上未解决的关键挑战。在 PredPHI 基准测试中，FoundedPBI 达到了 76% 的 F1 分数，比当前最先进的方法 (PBIP) 提高了 7%。在我们的内部数据集 (CI4CB) 上，我们达到了 93% 的 F1 分数，比我们之前的最佳方法提高了 4%。这些结果表明，结合适当的长上下文处理，集成学习能够实现基因组基础模型向专门预测任务的有效知识迁移。

## Abstract
The scalability of phage therapy as a viable alternative or complement to antibiotics is limited by the labor-intensive experimental screening required to identify compatible phage-bacterium pairs. To accelerate this discovery process, we propose FoundedPBI, an ensemble deep learning approach that leverages the emergent capabilities of genomic foundation models, large language models pre-trained on vast DNA corpuses to predict phage-bacterium interactions from DNA sequences alone. We employ an ensemble strategy that aggregates outputs from three state-of-the-art DNA language models into a unified meta-embedding, which is then processed by a neural classifier. Our approach makes two key contributions: (1) We demonstrate that performing ensemble learning across models trained on different genomic data--i.e., prokaryotic (Nucleotide Transformer v2, DNABERT-2) and bacteriophage (MegaDNA) genomes--captures partially-orthogonal biological signals, yielding 6% F1-score improvement over the best individual model. (2) We adapt long-context NLP aggregation strategies to handle whole bacterial and phage genomes (up to 5M base pairs) that exceed the foundation models context windows (12-96K bp) by a factor of 50-100, a critical challenge largely unaddressed in prior genomic deep learning work. On the PredPHI benchmark, FoundedPBI achieves a 76% F1-score outperforming the current state-of-the-art (PBIP) by 7%. On our internal dataset (CI4CB), we achieve 93% F1-score, improving our previous best methods by 4%. These results demonstrate that ensemble learning with proper long-context handling enables effective knowledge transfer of genomic foundation models to specialized prediction tasks.

---

## 论文详细总结（自动生成）

这是一份关于论文《FoundedPBI: Using Genomic Foundation Models to predict Phage-Bacterium Interactions》的结构化深度总结：

### 1. 核心问题与整体含义
*   **研究动机**：多重耐药菌（MDR）已成为全球健康威胁，噬菌体疗法是极具潜力的替代方案。然而，噬菌体与其宿主细菌之间具有高度特异性，传统的实验筛选（如双层平板法）效率极低，难以应对海量的噬菌体资源。
*   **核心问题**：如何仅利用 DNA 序列信息，准确且快速地预测噬菌体与细菌之间的相互作用（PBI），从而加速临床匹配过程？
*   **整体含义**：该研究提出了一种名为 **FoundedPBI** 的集成深度学习框架，通过融合多个针对不同基因组背景预训练的“基因组基础模型”，并引入长文本处理策略，显著提升了预测精度，刷新了该领域的性能记录。

### 2. 方法论
*   **核心思想**：利用集成学习（Ensemble Learning）融合不同预训练模型的“正交生物信号”，并借鉴自然语言处理（NLP）中的长文档嵌入技术来处理超长的基因组序列。
*   **关键技术细节**：
    *   **多模型集成**：选取了三个架构和训练数据各异的模型：
        1.  **Nucleotide Transformer v2**：基于原核生物基因组训练。
        2.  **DNABERT-2**：基于多物种基因组训练，使用 BPE 分词。
        3.  **MegaDNA**：专门针对 10 万个噬菌体基因组训练的生成式模型。
    *   **长上下文处理**：细菌基因组（约 5M bp）远超模型窗口（12K-96K bp）。研究采用了多种聚合策略，如 **TK-PERT**（平滑重叠窗口加权）、**Top+Bottom Truncate**（首尾截断拼接）和 **Average/Maximum** 策略，将全基因组分块嵌入后合并。
    *   **元嵌入（Meta-embedding）处理**：将三个模型的输出拼接，通过 **PCA（主成分分析）** 降维至 500 维（保留 99.99% 方差），并引入 **NEFTune** 噪声增强技术（添加高斯噪声）以提高泛化能力。
    *   **分类头**：采用简单的多层感知机（MLP）作为唯一的训练组件。

### 3. 实验设计
*   **数据集**：
    *   **CI4CB**：内部数据集，包含 7721 次交互（231 种细菌，3539 种噬菌体），用于与团队前期方法对比。
    *   **PredPHI**：独立外部基准数据集，包含 6938 次交互（301 种细菌，3449 种噬菌体），用于与 SOTA 方法对比。
*   **对比方法**：
    *   **PERPHECT**：基于卷积神经网络（CNN）的早期方法。
    *   **Distilled DNABERT**：基于单一基础模型加 LSTM 的方法。
    *   **PBIP (SOTA)**：目前最先进的方法，基于蛋白质序列嵌入（UniRep）和 CNN-GRU 架构。
    *   **PredPHI**：该基准数据集的原始预测模型。

### 4. 资源与算力
*   **算力说明**：论文**未明确列出**具体的 GPU 型号、数量或总训练时长。
*   **间接信息**：文中提到在处理 PredPHI 数据集时，由于 **VRAM（显存）限制**，不得不将 DNABERT-2 的上下文窗口从 32K bp 缩减至 16K bp，这暗示了该方法对显存有一定要求，但在推理阶段由于分类头极轻量，资源消耗较低。

### 5. 实验数量与充分性
*   **实验规模**：
    *   在两个大型数据集上进行了完整测试。
    *   **消融实验**：针对长上下文聚合策略进行了 1296 种配置的网格搜索，并验证了 PCA 降维和 NEFTune 噪声的贡献。
    *   **多样性分析**：通过 UMAP 可视化和 Spearman 相关性分析，证明了三个基础模型捕捉到的特征具有互补性。
    *   **错误分析**：深入到了分类学（科、属级别）的错误率统计。
*   **评价**：实验设计较为充分且客观。通过跨数据集验证和详细的消融实验，排除了偶然性因素，证明了集成策略的有效性。

### 6. 主要结论与发现
*   **集成优势**：集成模型比表现最好的单一模型（MegaDNA）在 F1 分数上提高了 6%，证明了融合原核背景和病毒背景模型的必要性。
*   **长文本策略至关重要**：相比简单的首部截断（Truncate），采用优化的长上下文聚合策略使 F1 分数提升了 12%。
*   **性能领先**：在 PredPHI 基准上，FoundedPBI 的 F1 分数达到 76%，比 SOTA 方法 PBIP 高出 7%，且在召回率（Recall）上提升了 11%。

### 7. 优点
*   **模块化与灵活性**：框架不依赖于特定的基础模型，可以随 DNA 语言模型的发展轻松升级。
*   **跨域知识融合**：首次系统性地证明了结合“细菌视角”和“噬菌体视角”的模型能产生更强的生物信号。
*   **解决尺度难题**：为基因组深度学习中普遍存在的“超长序列 vs 短上下文窗口”矛盾提供了切实可行的 NLP 借鉴方案。

### 8. 不足与局限
*   **特定类群预测困难**：分类学分析显示，对于临床关键的革兰氏阴性菌（如铜绿假单胞菌、鲍曼不动杆菌），错误率远高于放线菌。这可能是因为这些细菌的噬菌体受体结构变异极快，参考基因组嵌入难以捕捉。
*   **缺乏可解释性**：目前模型仍属于“黑盒”，无法明确指出是 DNA 序列中的哪些具体基序（Motifs）决定了相互作用。
*   **数据依赖性**：尽管使用了基础模型，但下游分类器的性能仍受限于带标签的 PBI 实验数据的质量和多样性。

（完）
