---
title: "DVPNet: A New XAI-Based Interpretable Genetic Profiling Framework Using Nucleotide Transformer and Probabilistic Circuits"
title_zh: DVPNet：一种基于 XAI 的新型可解释遗传分析框架，利用 Nucleotide Transformer 和概率电路
authors: "Kusumoto, T."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.28.695053v3.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于遗传图谱分析的核苷酸Transformer
tldr: 本研究提出DVPNet，一种结合Nucleotide Transformer和概率电路的可解释AI遗传分析框架，旨在通过可解释的决策过程区分癌细胞与正常细胞。该框架利用Transformer强大的特征提取能力和概率电路的可处理性，量化基因重要性并进行遗传分析。在肺癌单细胞数据集上的实验表明，该方法能识别出传统统计学难以发现的关键癌症相关基因，为遗传研究提供了超越表达水平的新见解。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-001.webp\", \"caption\": \"Table 2: Representative GO enrichment terms (top5) for each module (ordered by S(genes | all samples) descending).\", \"page\": 11, \"index\": 1, \"width\": 1010, \"height\": 1396}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-002.webp\", \"caption\": \"Table 5: Bottom GO terms by S(mean)\", \"page\": 15, \"index\": 2, \"width\": 1064, \"height\": 1264}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-003.webp\", \"caption\": \"Figure 1: Overall experimental workflow: (a) Sample preparation using the Nucleotide Transformer, and (b) model training and extraction of gene-wise probabilistic contributions for each sample.\", \"page\": 3, \"index\": 3, \"width\": 852, \"height\": 1200}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-004.webp\", \"caption\": \"Table 7: Top 100 genes among the 1,524 genes exhibiting contradictory count–score pairs.\", \"page\": 18, \"index\": 4, \"width\": 1064, \"height\": 1264}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-005.webp\", \"caption\": \"Table 3: Top GO terms by S(mean)\", \"page\": 13, \"index\": 5, \"width\": 1064, \"height\": 1264}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-006.webp\", \"caption\": \"Table 8: Bottom 100 genes among the 1,524 genes exhibiting contradictory count–score pairs. $\", \"page\": 19, \"index\": 6, \"width\": 1064, \"height\": 1264}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-007.webp\", \"caption\": \"Figure 2: Relationship between label-wise gene occurrence count differences and the mean probabilistic contribution score S(gene). Pearson’s r and Spearman’s ρ are reported in the plot.\", \"page\": 9, \"index\": 7, \"width\": 940, \"height\": 866}]"
motivation: 旨在开发一种能够量化基因重要性并提供生物学解释的AI框架，以克服传统统计方法在区分癌细胞时的局限性。
method: 结合Nucleotide Transformer进行特征提取与概率电路构建可处理的分类模型，通过提取类特定概率贡献度进行遗传分析。
result: 在肺癌数据集上成功识别出1524个贡献度与出现频率不一致的关键基因，其中包括ITGA5和TP73等已知癌症相关基因。
conclusion: DVPNet通过整合深度学习特征与概率解释性，为癌症遗传分析和生物通路研究提供了一种超越传统统计学的新型学术视角。
---

## 摘要
在本研究中，我们提出了一种基于可解释人工智能（XAI）的遗传分析框架，该框架基于可解释的 AI 决策过程，量化了用于区分癌细胞与正常细胞的基因重要性。我们提出了一种结合了概率电路（Probabilistic Circuits）与 Nucleotide Transformer 的新型可解释 AI 分类模型。通过利用 Nucleotide Transformer 强大的特征提取能力，我们设计了一个基于概率电路的可处理分类框架，同时保留了概率可解释性。为了证明该框架的能力，我们使用了 GSE131907 单细胞肺癌图谱，并构建了一个包含癌细胞和正常细胞类别的数据集。从每个样本中随机选择 900 种基因类型，并使用 Nucleotide Transformer 将其转换为嵌入向量，随后对分类模型进行训练。随后，我们从该可处理模型中提取了特定类别的概率贡献，并为癌细胞类别定义了贡献得分。基于这些得分进行遗传分析，从而深入了解哪些基因和生物通路对分类任务最为重要。值得注意的是，在 9,540 个观察到的基因中，有 1,524 个基因的贡献得分与其类别出现频率所预期的结果相矛盾，这表明该分析通过利用 Nucleotide Transformer 编码的生物特征表示，超越了简单的统计数据。在这些矛盾案例中，排名靠前的基因包括癌症研究中几种经过深入研究的基因（例如 ITGA5、SIGLEC9、NOTUM 和 TP73）。总之，这些分析超越了传统的统计或基因表达水平方法，为遗传学研究提供了新的学术见解。

## Abstract
In this study, we present an XAI-based genetic profiling framework that quantifies gene importance for distinguishing cancer cells from normal cells based on an interpretable AI decision process. We propose a new explainable AI (XAI) classification model that combines probabilistic circuits with the Nucleotide Transformer. By leveraging the strong feature-extraction capability of the Nucleotide Transformer, we design a tractable classification framework based on probabilistic circuits while preserving probabilistic interpretability.

To demonstrate the capability of this framework, we used the GSE131907 single-cell lung cancer atlas and constructed a dataset consisting of cancer-cell and normal-cell classes. From each sample, 900 gene types were randomly selected and converted into embedding vectors using the Nucleotide Transformer, after which the classification model was trained. We then extracted class-specific probabilistic contributions from the tractable model and defined a contribution score for the cancer-cell class. Genetic profiling was performed based on these scores, providing insights into which genes and biological pathways are most important for the classification task. Notably, 1,524 of the 9,540 observed genes showed contribution scores that contradicted what would be expected from their class-wise occurrence frequencies, suggesting that the profiling goes beyond simple statistics by leveraging biological feature representations encoded by the Nucleotide Transformer. The top-ranked genes among these contradictory cases include several well-studied genes in cancer research (e.g., ITGA5, SIGLEC9, NOTUM, and TP73). Overall, these analyses go beyond traditional statistical or gene-expression-level approaches and provide new academic insights for genetic research.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **DVPNet** 的新型可解释人工智能（XAI）框架，旨在通过整合基因组基础模型和概率推理，为癌症遗传分析提供深层的生物学见解。以下是对该论文的详细总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：传统的基因共表达网络（如 WGCNA）主要依赖于 RNA 表达水平的统计相关性。这种方法难以区分因果关系（如调节基因与被调节基因），且无法捕捉隐藏在核苷酸序列中的深层功能信息。
*   **研究动机**：利用大规模预训练的基因组基础模型（如 Nucleotide Transformer）提取的生物学特征，结合具有严格数学可解释性的概率电路（Probabilistic Circuits），构建一个不仅能分类（区分癌细胞与正常细胞），还能量化单个基因对决策贡献度的框架，从而发现超越传统统计学的新生物学标志物。

### 2. 方法论：核心思想与关键技术
*   **核心思想**：将基因的 DNA 序列特征（由 Transformer 提取）与样本分类的概率推理（由概率电路实现）相结合。
*   **关键技术细节**：
    *   **特征提取**：针对每个细胞样本，随机抽取 900 个表达基因。提取每个基因转录起始位点（TSS）上游 2000bp 到下游 500bp 的序列，输入 **Nucleotide Transformer v2 (500M)** 获得 1024 维的“基因向量”。
    *   **DVPNet 模型**：基于 VPNet 架构，将基因向量作为输入。模型核心是**概率电路（PC）**，它通过结构化设计（满足平滑性和可分解性）来编码类条件概率密度 $P(Sample | Class)$。
    *   **可解释性机制**：由于概率电路的“可处理性”（Tractability），可以精确计算单个基因向量的概率贡献。定义贡献得分 $S(gene)$ 为癌细胞类与正常细胞类对数似然之差。
    *   **算法流程**：样本准备（序列编码） $\rightarrow$ 模型训练（最大化似然/最小化交叉熵） $\rightarrow$ 贡献提取（计算单个基因的概率影响） $\rightarrow$ 遗传分析（通路富集与网络构建）。

### 3. 实验设计
*   **数据集**：使用 **GSE131907 单细胞肺癌图谱**，包含来自 44 名患者的约 20.8 万个细胞。
*   **场景设置**：
    1.  **患者混合模型**：随机划分训练/测试集。
    2.  **患者独立模型**：训练集和测试集来自完全不同的患者，以验证模型的泛化能力和鲁棒性。
*   **对比与验证**：
    *   将 AI 贡献得分与基因出现的统计频率进行对比（相关性分析）。
    *   使用 AI 得分代替表达量进行类 WGCNA 的网络分析。
    *   进行基因本体论（GO）富集分析，验证识别出的高贡献通路是否符合生物学常识。

### 4. 资源与算力
*   **模型规模**：使用了拥有 5 亿参数的 Nucleotide Transformer v2。
*   **算力说明**：文中**未明确说明**具体的 GPU 型号、数量或总训练时长。仅提到使用了 Adam 优化器和特定的超参数设置（如 Batch Size 为 20）。

### 5. 实验数量与充分性
*   **实验规模**：针对两种主要场景（患者混合与独立）进行了完整的训练和评估。
*   **充分性评价**：
    *   **较为充分**：通过“患者独立”实验证明了模型不是在背诵特定患者的特征，而是学习到了通用的生物学表示。
    *   **客观性**：通过分析 1,524 个“矛盾基因”（即 AI 认为重要但统计频率不高的基因），客观地证明了模型确实利用了 Transformer 提供的生物学特征，而非仅仅依赖简单的频率统计。
    *   **局限**：缺乏与其他深度学习分类器（如纯 CNN 或标准 Transformer）在分类性能上的直接 Benchmark 对比，但考虑到本文重点在于可解释性，这一点可以理解。

### 6. 主要结论与发现
*   **高性能**：模型在测试集上达到了极高的准确率（AUROC > 0.97），证明了 DVPNet 架构的有效性。
*   **超越统计学**：识别出 1,524 个贡献得分与出现频率不一致的基因。这表明模型捕捉到了基因序列中蕴含的、与癌症发生相关的内在功能信号。
*   **生物学验证**：排名靠前的基因（如 ITGA5, SIGLEC9, NOTUM, TP73）均是已知的癌症相关基因或潜在治疗靶点。
*   **通路发现**：识别出免疫球蛋白复合物、补体激活等与肿瘤微环境密切相关的生物通路。

### 7. 优点
*   **高度可解释**：不同于传统的“黑盒”深度学习，DVPNet 能给出每个基因对分类结果的精确概率解释。
*   **整合前沿技术**：成功将基因组大模型（Foundation Model）与可处理概率模型（Probabilistic Circuits）结合，开辟了遗传分析的新路径。
*   **鲁棒性强**：在跨患者实验中表现稳定，具有较好的泛化潜力。

### 8. 不足与局限
*   **实验覆盖面**：目前仅在肺癌数据集上进行了验证，尚不清楚该框架在其他癌症或复杂疾病上的通用性。
*   **微环境偏差**：癌细胞样本可能混杂了肿瘤微环境信号，导致模型学习到的可能是微环境差异而非纯粹的细胞内在恶性特征。
*   **缺乏湿实验验证**：虽然文献调研支持了结果，但对于模型新发现的候选基因，缺乏实验室（Wet-lab）的功能性验证。
*   **采样限制**：每细胞随机采样 900 个基因可能导致某些低表达但关键的调节基因被遗漏。

（完）
