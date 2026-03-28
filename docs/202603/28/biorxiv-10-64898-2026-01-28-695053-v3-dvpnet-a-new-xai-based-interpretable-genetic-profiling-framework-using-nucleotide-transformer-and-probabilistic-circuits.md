---
title: "DVPNet: A New XAI-Based Interpretable Genetic Profiling Framework Using Nucleotide Transformer and Probabilistic Circuits"
title_zh: DVPNet：一种基于 Nucleotide Transformer 和概率电路的新型 XAI 可解释基因图谱分析框架
authors: "Kusumoto, T."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.28.695053v3.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用核苷酸Transformer的遗传分析框架
tldr: 本研究提出DVPNet，一种基于可解释人工智能（XAI）的基因分析框架，旨在区分癌细胞与正常细胞。该框架结合了Nucleotide Transformer强大的特征提取能力与概率电路的可解释性，通过量化基因贡献度进行遗传分析。在肺癌单细胞数据集上的实验表明，该方法能识别出传统统计学难以发现的关键基因（如ITGA5、TP73），为癌症研究提供了超越基因表达水平的新学术见解。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-001.webp\", \"caption\": \"Table 2: Representative GO enrichment terms (top5) for each module (ordered by S(genes | all samples) descending).\", \"page\": 11, \"index\": 1, \"width\": 1010, \"height\": 1396}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-002.webp\", \"caption\": \"Table 5: Bottom GO terms by S(mean)\", \"page\": 15, \"index\": 2, \"width\": 1064, \"height\": 1264}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-003.webp\", \"caption\": \"Figure 1: Overall experimental workflow: (a) Sample preparation using the Nucleotide Transformer, and (b) model training and extraction of gene-wise probabilistic contributions for each sample.\", \"page\": 3, \"index\": 3, \"width\": 852, \"height\": 1200}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-004.webp\", \"caption\": \"Table 7: Top 100 genes among the 1,524 genes exhibiting contradictory count–score pairs.\", \"page\": 18, \"index\": 4, \"width\": 1064, \"height\": 1264}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-005.webp\", \"caption\": \"Table 3: Top GO terms by S(mean)\", \"page\": 13, \"index\": 5, \"width\": 1064, \"height\": 1264}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-006.webp\", \"caption\": \"Table 8: Bottom 100 genes among the 1,524 genes exhibiting contradictory count–score pairs. $\", \"page\": 19, \"index\": 6, \"width\": 1064, \"height\": 1264}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-28-695053-v3/fig-007.webp\", \"caption\": \"Figure 2: Relationship between label-wise gene occurrence count differences and the mean probabilistic contribution score S(gene). Pearson’s r and Spearman’s ρ are reported in the plot.\", \"page\": 9, \"index\": 7, \"width\": 940, \"height\": 866}]"
motivation: 旨在解决传统遗传分析方法在区分癌细胞时缺乏深度生物特征表示及决策过程透明度不足的问题。
method: 开发了结合Nucleotide Transformer嵌入与概率电路的DVPNet模型，构建了一个兼具高性能与概率可解释性的分类框架。
result: "成功识别出1,524个贡献度得分与出现频率不一致的关键基因，其中包括多个已证实的癌症相关重要基因。"
conclusion: 该框架通过利用生物特征表示和可解释决策过程，为遗传研究和癌症诊断提供了超越传统统计学的新型分析工具。
---

## 摘要
在本研究中，我们提出了一种基于 XAI 的基因图谱分析框架，该框架基于可解释的 AI 决策过程，量化了区分癌细胞与正常细胞的基因重要性。我们提出了一种结合了概率电路与 Nucleotide Transformer 的新型可解释人工智能 (XAI) 分类模型。通过利用 Nucleotide Transformer 强大的特征提取能力，我们设计了一个基于概率电路的可处理分类框架，同时保留了概率可解释性。为了证明该框架的能力，我们使用了 GSE131907 单细胞肺癌图谱，并构建了一个由癌细胞和正常细胞类别组成的数据集。从每个样本中随机选择 900 种基因类型，并使用 Nucleotide Transformer 将其转换为嵌入向量，随后对分类模型进行训练。然后，我们从该可处理模型中提取了特定类别的概率贡献，并为癌细胞类别定义了贡献分数。基于这些分数进行基因图谱分析，为哪些基因和生物通路对分类任务最重要提供了见解。值得注意的是，在 9,540 个观察到的基因中，有 1,524 个基因的贡献分数与其按类别出现的频率预期相矛盾，这表明该图谱分析通过利用 Nucleotide Transformer 编码的生物特征表示，超越了简单的统计数据。在这些矛盾案例中，排名靠前的基因包括癌症研究中几种经过深入研究的基因（例如 ITGA5、SIGLEC9、NOTUM 和 TP73）。总之，这些分析超越了传统的统计或基因表达水平方法，为遗传学研究提供了新的学术见解。

## Abstract
In this study, we present an XAI-based genetic profiling framework that quantifies gene importance for distinguishing cancer cells from normal cells based on an interpretable AI decision process. We propose a new explainable AI (XAI) classification model that combines probabilistic circuits with the Nucleotide Transformer. By leveraging the strong feature-extraction capability of the Nucleotide Transformer, we design a tractable classification framework based on probabilistic circuits while preserving probabilistic interpretability.

To demonstrate the capability of this framework, we used the GSE131907 single-cell lung cancer atlas and constructed a dataset consisting of cancer-cell and normal-cell classes. From each sample, 900 gene types were randomly selected and converted into embedding vectors using the Nucleotide Transformer, after which the classification model was trained. We then extracted class-specific probabilistic contributions from the tractable model and defined a contribution score for the cancer-cell class. Genetic profiling was performed based on these scores, providing insights into which genes and biological pathways are most important for the classification task. Notably, 1,524 of the 9,540 observed genes showed contribution scores that contradicted what would be expected from their class-wise occurrence frequencies, suggesting that the profiling goes beyond simple statistics by leveraging biological feature representations encoded by the Nucleotide Transformer. The top-ranked genes among these contradictory cases include several well-studied genes in cancer research (e.g., ITGA5, SIGLEC9, NOTUM, and TP73). Overall, these analyses go beyond traditional statistical or gene-expression-level approaches and provide new academic insights for genetic research.

---

## 论文详细总结（自动生成）

以下是对论文《DVPNet: A New XAI-Based Interpretable Genetic Profiling Framework Using Nucleotide Transformer and Probabilistic Circuits》的结构化总结：

### 1. 核心问题与研究背景
*   **核心问题**：传统的遗传分析方法（如差异表达分析）往往依赖于简单的统计指标，难以捕捉复杂的生物序列特征。而现代深度学习模型虽然性能强大，但通常是“黑盒”，缺乏决策透明度，难以在临床和生物学研究中提供可解释的见解。
*   **研究背景**：在癌症诊断中，区分癌细胞与正常细胞至关重要。研究者希望开发一种既能利用预训练大模型（如 Nucleotide Transformer）提取深层生物特征，又能通过可解释人工智能（XAI）技术量化单个基因对分类决策贡献度的框架。

### 2. 方法论（DVPNet 框架）
DVPNet 的核心思想是将**深度生物特征提取**与**可处理概率推理**相结合：
*   **特征提取（Nucleotide Transformer）**：利用预训练的 Nucleotide Transformer 模型将原始 DNA 序列转换为高维嵌入向量（Embeddings）。这使得模型能够捕捉到核苷酸层面的深层生物学语义。
*   **分类与推理（概率电路，PCs）**：
    *   将嵌入向量输入到概率电路中。概率电路是一种可处理的概率模型，支持精确的概率推理。
    *   **核心算法流程**：
        1.  从单细胞数据中随机采样基因序列。
        2.  通过 Nucleotide Transformer 生成嵌入表示。
        3.  训练概率电路进行“癌细胞 vs 正常细胞”的二分类。
        4.  **贡献度量化**：利用概率电路的特性，计算特定基因在给定类别下的边际概率贡献分数（$S_{gene}$），从而实现对决策过程的量化解释。

### 3. 实验设计
*   **数据集**：使用 GSE131907 单细胞肺癌图谱（Single-cell Lung Cancer Atlas）。
*   **场景**：构建了一个包含癌细胞和正常细胞的数据集，每个样本随机选择 900 种基因类型进行训练和测试。
*   **基准与对比**：
    *   实验重点不在于单纯的分类准确率对比，而在于**可解释性的深度分析**。
    *   对比对象是“传统的统计频率”（即基因在类别中出现的频次）。研究者通过寻找“贡献分数”与“出现频率”不一致的基因，来证明模型捕捉到了超越简单统计的生物学特征。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号、数量或具体的训练时长。
*   **实现细节**：提到了使用 Nucleotide Transformer 进行嵌入提取，这类模型通常需要高性能 GPU（如 NVIDIA A100 或 V100）进行推理，而概率电路的训练则相对高效。

### 5. 实验数量与充分性
*   **实验规模**：观察了 9,540 个基因，并对 1,524 个表现出“矛盾”特征（高贡献但低频率，或反之）的基因进行了深入分析。
*   **分析维度**：
    *   进行了 **GO（Gene Ontology）富集分析**，验证了识别出的高贡献基因在生物学功能上的相关性。
    *   对特定模块（如 Module 1 到 Module 5）进行了详细的功能注释。
*   **充分性评价**：实验设计较为客观，通过大规模单细胞数据的验证和生物学功能富集分析，证明了该框架在识别癌症相关基因方面的有效性。

### 6. 主要结论与发现
*   **超越传统统计**：DVPNet 识别出 1,524 个基因，其贡献分数与出现频率不符。这表明模型是基于基因序列的生物学特征而非简单的出现概率做出的判断。
*   **关键基因识别**：成功识别出多个与癌症高度相关的关键基因，如 **ITGA5**（与肿瘤进展相关）、**TP73**（p53 家族成员，参与细胞凋亡）、**SIGLEC9** 和 **NOTUM**。
*   **生物通路见解**：通过 GO 分析发现，高贡献基因显著富集在细胞粘附、免疫反应和信号转导等与癌症发生密切相关的通路上。

### 7. 优点
*   **高可解释性**：结合了概率电路，能够提供精确的概率解释，解决了深度学习在基因组学中的“黑盒”问题。
*   **强大的特征表示**：引入 Nucleotide Transformer，使得模型能够理解复杂的 DNA 序列模式，而不仅仅是基因的表达水平。
*   **发现潜在标志物**：能够识别出那些在统计学上不显著但在生物学功能上对癌症分类至关重要的“隐匿”基因。

### 8. 不足与局限
*   **采样偏差风险**：实验中每个样本随机选择 900 个基因，这种随机采样可能导致某些关键但低频的基因在特定训练轮次中被遗漏。
*   **计算复杂性**：虽然概率电路推理很快，但随着基因数量和嵌入维度增加，构建和训练大规模概率电路的结构学习可能面临挑战。
*   **应用限制**：目前主要在肺癌单细胞数据集上验证，其在其他癌症类型或多组学数据上的泛化能力仍需进一步验证。

（完）
