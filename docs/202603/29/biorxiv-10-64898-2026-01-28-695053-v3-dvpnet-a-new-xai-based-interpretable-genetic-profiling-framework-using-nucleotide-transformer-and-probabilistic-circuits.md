---
title: "DVPNet: A New XAI-Based Interpretable Genetic Profiling Framework Using Nucleotide Transformer and Probabilistic Circuits"
title_zh: DVPNet：一种基于 Nucleotide Transformer 和概率电路的新型 XAI 可解释基因图谱分析框架
authors: "Kusumoto, T."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.28.695053v3.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用核苷酸Transformer进行遗传分析
tldr: 本研究提出DVPNet，一种结合Nucleotide Transformer和概率电路的可解释AI遗传分析框架。该框架利用Transformer强大的特征提取能力和概率电路的可解释性，量化基因在区分癌细胞与正常细胞中的重要性。通过对肺癌单细胞数据集的分析，DVPNet识别出关键基因及其生物通路，揭示了超越传统统计学的生物学洞察，为癌症研究提供了新的可解释性工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-001.webp\", \"caption\": \"Table 2: Representative GO enrichment terms (top5) for each module (ordered by S(genes | all samples) descending).\", \"page\": 11, \"index\": 1, \"width\": 1010, \"height\": 1396}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-002.webp\", \"caption\": \"Table 5: Bottom GO terms by S(mean)\", \"page\": 15, \"index\": 2, \"width\": 1064, \"height\": 1264}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-003.webp\", \"caption\": \"Figure 1: Overall experimental workflow: (a) Sample preparation using the Nucleotide Transformer, and (b) model training and extraction of gene-wise probabilistic contributions for each sample.\", \"page\": 3, \"index\": 3, \"width\": 852, \"height\": 1200}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-004.webp\", \"caption\": \"Table 7: Top 100 genes among the 1,524 genes exhibiting contradictory count–score pairs.\", \"page\": 18, \"index\": 4, \"width\": 1064, \"height\": 1264}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-005.webp\", \"caption\": \"Table 3: Top GO terms by S(mean)\", \"page\": 13, \"index\": 5, \"width\": 1064, \"height\": 1264}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-006.webp\", \"caption\": \"Table 8: Bottom 100 genes among the 1,524 genes exhibiting contradictory count–score pairs. $\", \"page\": 19, \"index\": 6, \"width\": 1064, \"height\": 1264}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-007.webp\", \"caption\": \"Figure 2: Relationship between label-wise gene occurrence count differences and the mean probabilistic contribution score S(gene). Pearson’s r and Spearman’s ρ are reported in the plot.\", \"page\": 9, \"index\": 7, \"width\": 940, \"height\": 866}]"
motivation: 旨在开发一种能够超越传统统计方法、通过可解释AI过程量化基因重要性的遗传分析框架。
method: 结合Nucleotide Transformer进行特征提取与概率电路构建可处理的分类模型，实现概率层面的可解释性。
result: 在肺癌数据集上成功识别出1524个贡献度与出现频率不一致的关键基因，其中包括ITGA5和TP73等已知癌症相关基因。
conclusion: DVPNet通过整合深度学习特征与概率推理，为癌症遗传研究提供了比传统表达水平分析更深层的学术见解。
---

## 摘要
在本研究中，我们提出了一种基于 XAI 的基因图谱分析框架，该框架基于可解释的 AI 决策过程，量化了区分癌细胞与正常细胞的基因重要性。我们提出了一种结合了概率电路与 Nucleotide Transformer 的新型可解释人工智能 (XAI) 分类模型。通过利用 Nucleotide Transformer 强大的特征提取能力，我们设计了一个基于概率电路的可处理分类框架，同时保留了概率可解释性。为了证明该框架的能力，我们使用了 GSE131907 单细胞肺癌图谱，并构建了一个由癌细胞和正常细胞类别组成的数据集。从每个样本中随机选择 900 种基因类型，并使用 Nucleotide Transformer 将其转换为嵌入向量，随后对分类模型进行训练。然后，我们从该可处理模型中提取了特定类别的概率贡献，并为癌细胞类别定义了贡献分数。基于这些分数进行基因图谱分析，为哪些基因和生物通路对分类任务最重要提供了见解。值得注意的是，在 9,540 个观察到的基因中，有 1,524 个基因的贡献分数与其按类别出现的频率预期相矛盾，这表明该图谱分析通过利用 Nucleotide Transformer 编码的生物特征表示，超越了简单的统计数据。在这些矛盾案例中，排名靠前的基因包括癌症研究中几种经过深入研究的基因（例如 ITGA5、SIGLEC9、NOTUM 和 TP73）。总之，这些分析超越了传统的统计或基因表达水平方法，为遗传学研究提供了新的学术见解。

## Abstract
In this study, we present an XAI-based genetic profiling framework that quantifies gene importance for distinguishing cancer cells from normal cells based on an interpretable AI decision process. We propose a new explainable AI (XAI) classification model that combines probabilistic circuits with the Nucleotide Transformer. By leveraging the strong feature-extraction capability of the Nucleotide Transformer, we design a tractable classification framework based on probabilistic circuits while preserving probabilistic interpretability.

To demonstrate the capability of this framework, we used the GSE131907 single-cell lung cancer atlas and constructed a dataset consisting of cancer-cell and normal-cell classes. From each sample, 900 gene types were randomly selected and converted into embedding vectors using the Nucleotide Transformer, after which the classification model was trained. We then extracted class-specific probabilistic contributions from the tractable model and defined a contribution score for the cancer-cell class. Genetic profiling was performed based on these scores, providing insights into which genes and biological pathways are most important for the classification task. Notably, 1,524 of the 9,540 observed genes showed contribution scores that contradicted what would be expected from their class-wise occurrence frequencies, suggesting that the profiling goes beyond simple statistics by leveraging biological feature representations encoded by the Nucleotide Transformer. The top-ranked genes among these contradictory cases include several well-studied genes in cancer research (e.g., ITGA5, SIGLEC9, NOTUM, and TP73). Overall, these analyses go beyond traditional statistical or gene-expression-level approaches and provide new academic insights for genetic research.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **DVPNet** 的新型可解释人工智能（XAI）框架，旨在通过整合基因组基础模型与概率推理，为癌症遗传研究提供深层的生物学见解。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：传统的基因共表达网络（如 WGCNA）主要依赖于 RNA 表达水平的统计相关性，难以捕捉基因间的因果关系、功能调控或上下文相关的复杂生物学逻辑。此外，现有的深度学习模型（如 CNN 或 Transformer）虽然特征提取能力强，但其“黑盒”性质限制了在临床和生物学研究中的可解释性。
*   **研究动机**：开发一种既能利用大规模预训练模型（基础模型）捕捉到的深层生物学特征，又能通过数学上的“可处理性（Tractability）”提供清晰决策解释的遗传图谱分析工具，从而识别出区分癌细胞与正常细胞的关键驱动基因。

### 2. 方法论：核心思想与关键技术
*   **核心思想**：将 **Nucleotide Transformer**（基因组基础模型）的强大特征提取能力与 **概率电路（Probabilistic Circuits, PCs）** 的精确概率推理相结合。
*   **关键技术流程**：
    1.  **序列编码**：针对单细胞中的每个表达基因，提取其转录起始位点（TSS）上游 2000bp 到下游 500bp 的核苷酸序列。
    2.  **特征提取**：使用预训练的 Nucleotide Transformer v2（5亿参数）将 DNA 序列转换为 1024 维的“基因向量（Gene Vector）”。
    3.  **模型构建（DVPNet）**：基于 VPNet 架构，将基因向量输入概率电路。该电路通过严格遵守“平滑性（Smoothness）”和“可分解性（Decomposability）”结构约束，确保模型可以精确计算每个基因对特定类别（如癌症）的条件概率贡献。
    4.  **贡献评分**：定义 $S(gene)$ 分数，通过比较癌细胞和正常细胞类别的对数似然贡献，量化单个基因在分类决策中的重要性。

### 3. 实验设计
*   **数据集**：使用 **GSE131907 单细胞肺癌图谱**，包含来自 44 名患者的 20.8 万个细胞。
*   **场景设置**：构建了“癌细胞”与“正常上皮细胞”的二分类任务。
*   **实验分组**：
    *   **患者混合模型**：随机划分训练/测试集。
    *   **患者独立模型**：确保训练集和测试集来自完全不同的患者，以验证模型的泛化性和鲁棒性。
*   **对比与验证**：
    *   将模型给出的基因贡献度与基因出现的统计频率进行对比。
    *   进行下游分析，包括基于贡献度的 WGCNA 网络构建和 GO（基因本体）功能富集分析。

### 4. 资源与算力
*   **模型规模**：使用了拥有 5 亿参数的 Nucleotide Transformer v2。
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号、数量或总训练时长。仅提到了超参数设置（如 Batch Size 为 20，使用 Adam 优化器）。

### 5. 实验数量与充分性
*   **实验规模**：模型在数千个细胞样本上进行了训练和验证，涵盖了 9,540 个观察基因。
*   **充分性评价**：实验设计较为充分。作者不仅验证了分类性能（AUROC 达 0.97-0.99），还重点分析了 1,524 个“矛盾基因”（即贡献度与统计频率不符的基因），证明了模型确实学习到了序列特征而非简单的统计计数。此外，通过患者独立验证，增强了结果的可信度。

### 6. 主要结论与发现
*   **高性能与泛化性**：DVPNet 在区分肺癌细胞与正常细胞方面表现出极高的准确性，且在未见过的患者数据上依然稳健。
*   **超越统计学**：识别出 1,524 个关键基因，其重要性无法通过简单的出现频率解释，说明 Nucleotide Transformer 捕捉到了深层的生物学功能信号。
*   **生物学一致性**：排名靠前的基因（如 *ITGA5*, *SIGLEC9*, *NOTUM*, *TP73*）在现有癌症文献中已被证实具有重要的促癌或抑癌作用，验证了框架的有效性。

### 7. 优点
*   **创新的架构**：首次将基因组基础模型与概率电路结合，解决了深度学习在基因组学中“高性能”与“高解释性”不可兼得的问题。
*   **精确的特征量化**：能够量化单个基因在特定细胞样本中的贡献，支持样本特异性的分析。
*   **多维视角**：提供的基因图谱分析补充了传统差异表达分析（DEA）的不足，能从序列功能的角度发现潜在靶点。

### 8. 不足与局限
*   **癌症类型局限**：目前仅在肺癌数据集上进行了验证，其结论是否能推广到其他癌症类型尚需更多实验。
*   **微环境偏差**：样本可能包含肿瘤微环境细胞，导致模型可能捕捉的是免疫反应差异而非纯粹的癌细胞特征。
*   **随机采样策略**：每细胞随机抽取 900 个基因的策略虽然公平，但可能忽略了极低表达或特定关键通路的完整性。
*   **缺乏湿实验验证**：虽然有文献支持，但论文未包含针对新发现候选基因的实验室功能验证。

（完）
