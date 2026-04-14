---
title: "TPCAV: Interpreting deep learning genomics models via concept attribution"
title_zh: TPCAV：通过概念归因解释基因组学深度学习模型
authors: "Yang, J., Mahony, S."
date: 2026-04-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.20.700723v4.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 使用概念归因解释基因组学深度学习模型
tldr: 基因组学深度学习模型的解释通常局限于碱基序列，难以处理染色质状态等通用特征。本文提出TPCAV，将概念激活向量（TCAV）引入基因组学，并通过PCA去相关变换解决了嵌入特征冗余问题。TPCAV不仅能解释DNA基序，还能分析重复序列和染色质状态等复杂生物学概念，且适用于分词化的基础模型。该方法为理解基因组模型提供了灵活且鲁棒的全局解释框架。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-20-700723-v4/fig-001.webp\", \"caption\": \"Figure 4: Concept specific attribution map reveals differential usage of concepts across prediction heads in BPNet. a) Top 10 motif concepts identified in the last shared convolutional layer by all prediction heads. b) CAV cosine similarity heatmap of top 30 motif concepts (F-score > 0.9) in BPNet. c) Log TPCAV scores of top 30 motif concepts (F-score > 0.9) across all prediction tasks, bar color indicates whether a concept is positive (red) or negative (blue) influence.\", \"page\": 15, \"index\": 1, \"width\": 950, \"height\": 1152}]"
motivation: 现有的特征归因方法主要局限于碱基序列输入，难以评估染色质状态或基因组重复序列等更通用的生物学特征对模型的影响。
method: 提出TPCAV方法，通过引入PCA去相关变换改进了传统的TCAV，以解决基因组深度学习模型中常见的嵌入特征冗余问题。
result: TPCAV在基序解释上与主流方法相当，并能成功解释重复元件、染色质状态以及分词化基础模型所学习到的复杂生物学概念。
conclusion: TPCAV为基因组学模型提供了一个灵活且鲁棒的解释补充工具，能够识别与特定生物学概念相关的关键区域和调控机制。
---

## 摘要
解释基因组学深度学习模型仍然具有挑战性。现有的特征归因方法很大程度上局限于独热编码（one-hot）的 DNA 输入，因此无法评估更通用的基因组特征（如染色质状态或基因组重复序列）的影响。概念归因方法提供了一种与输入无关的全局解释框架，但尚未被系统地应用于解释基因组学中的神经网络应用。我们通过改进“基于概念激活向量的测试”（TCAV）方法，首次将概念归因应用于解释基因组学深度学习模型。我们在原始 TCAV 方法的基础上进行了改进，引入了基于主成分分析（PCA）的去相关变换，以解决基因组学深度学习模型中常见的相关且冗余的嵌入特征，从而提出了“基于 PCA 投影概念激活向量的测试”（TPCAV）方法。我们还引入了一种提取特定概念输入归因图的策略。我们通过在涵盖多种输入表示和预测任务的多样化基因组模型集中解释具有影响力的生物学概念，对我们的方法进行了评估。我们证明，在基于独热编码 DNA 的转录因子结合预测模型上，TPCAV 提供了与 TF-MoDISco 相当的主题（motif）特征解释。TPCAV 还能对更通用的生物学概念（如重复元件和染色质状态注释）如何对预测做出贡献进行稳健的解释性分析。TPCAV 具有独特的泛化能力，可以解释由分词化（tokenized）基础模型以及将染色质信号作为输入的模型所学习到的特征。我们进一步表明，TPCAV 可以识别与特定概念相关的代表性区域，从而推动对不同调控机制的下游研究。TPCAV 为现有的模型解释技术提供了一个灵活且稳健的补充。

## Abstract
Interpreting genomics deep learning models remains challenging. Existing feature attribution methods are largely restricted to one-hot DNA inputs and therefore cannot assess the influence of more general genomic features such as chromatin states or genomic repeats. Concept attribution methods offer an input-agnostic global interpretation framework, yet they have not been systematically applied to interpret neural network applications in genomics. We present the first application of concept attribution to interpret genomics deep learning models by adapting the Testing with Concept Activation Vectors (TCAV) method. We improve upon the original TCAV method by incorporating a PCA-based decorrelation transformation to address correlated and redundant embedding features commonly observed in genomics deep learning models, resulting in the Testing with PCA-projected Concept Activation Vectors (TPCAV) approach. We also introduce a strategy for extracting concept-specific input attribution maps. We evaluate our approach by interpreting influential biological concepts across a diverse set of genomics models spanning multiple input representations and prediction tasks. We demonstrate that TPCAV provides comparable motif feature interpretation to TF-MoDISco on one-hot encoded DNA-based transcription factor binding prediction models. TPCAV also enables robust interpretive analysis of how more general biological concepts such as repetitive elements and chromatin state annotations contribute towards predictions. TPCAV uniquely generalizes to interpret features learned by tokenized foundation models as well as models incorporating chromatin signals as inputs. We further show that TPCAV can identify representative regions associated with specific concepts, motivating downstream investigation of distinct regulatory mechanisms. TPCAV provides a flexible and robust complement to existing model interpretation techniques.

---

## 论文详细总结（自动生成）

以下是对论文《TPCAV: Interpreting deep learning genomics models via concept attribution》的结构化深入总结：

### 1. 核心问题与研究动机
*   **核心问题**：如何有效地解释基因组学深度学习模型所学习到的高层生物学特征？
*   **研究背景**：
    *   现有的解释方法（如 DeepLIFT, TF-MoDISco）主要针对独热编码（one-hot）的 DNA 序列，难以处理非序列特征（如染色质状态、重复序列）。
    *   随着“基础模型”（Foundation Models）的兴起，分词化（Tokenized）输入变得普遍，传统基于碱基归因的方法在这些模型上失效。
    *   局部归因方法（Local Attribution）难以总结模型在全局范围内的决策逻辑。
*   **研究动机**：引入计算机视觉中的“概念归因”（Concept Attribution）思想，并针对基因组学数据的特性（特征高度冗余和相关）进行改进，开发一种通用的、与输入格式无关的解释框架。

### 2. 方法论
*   **核心思想**：基于“概念激活向量测试”（TCAV）框架，通过定义一组代表特定生物学“概念”（如某个 Motif、某种重复序列）的样本，在模型的中间层寻找代表该概念的方向向量（CAV），从而量化该概念对模型预测的贡献。
*   **关键技术细节——TPCAV**：
    *   **PCA 去相关变换**：作者发现基因组模型中间层的神经元激活往往高度相关且冗余，导致原始 TCAV 训练的线性分类器不稳定。TPCAV 在训练分类器前引入了 **PCA 投影**，对嵌入空间进行去相关处理，显著提升了 CAV 的准确性。
    *   **概念定义**：通过构建“概念集”（包含目标特征的序列）和“随机集”（背景序列）来定义生物学概念。
    *   **Motif 敏感度得分**：引入了一种校正 GC 含量偏差的新指标，用于对不同 Motif 概念的重要性进行排名。
    *   **概念特定归因图**：开发了一种策略，将归因信号投影到特定的 CAV 方向上，从而在输入序列上可视化特定概念（如特定转录因子结合位点）的具体贡献区域。

### 3. 实验设计
*   **数据集与场景**：
    *   **TF 结合预测**：使用 ENCODE DREAM Challenge 数据集（HepG2, H1-hESC 细胞系）。
    *   **多任务模型**：BPNet 模型（预测 mES 细胞中的 OSKN 四因子结合）。
    *   **多模态模型**：maxATAC 模型（结合 DNA 序列和 ATAC-seq 信号）。
    *   **基础模型**：DNABERT-2、Nucleotide Transformer、HyenaDNA。
*   **Benchmark 与对比方法**：
    *   **TF-MoDISco**：作为 DNA Motif 解释的标准基准。
    *   **原始 TCAV**：验证 PCA 改进的效果。
    *   **Tomtom**：用于验证发现的 Motif 与已知数据库的匹配度。

### 4. 资源与算力
*   **软件框架**：基于 PyTorch Lightning、Captum（归因库）和 Scikit-learn 实现。
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号、数量或总训练时长。但提到模型训练使用了 AdamW 优化器和 OneCycleLR 调度策略，且 TPCAV 作为一个后验（post-hoc）解释工具，其计算开销主要集中在中间层激活提取和线性分类器训练上，通常比重新训练模型要轻量得多。

### 5. 实验数量与充分性
*   **实验规模**：
    *   涵盖了从简单的 CNN-Transformer 到复杂的 BPNet 和多模态 maxATAC 等多种架构。
    *   测试了超过 30 种转录因子的结合模型。
    *   对 3 种主流基因组基础模型进行了基准测试。
*   **充分性评价**：实验设计非常充分。作者不仅验证了方法在已知 Motif 上的准确性，还通过消融实验证明了 PCA 变换的必要性。此外，通过跨模型、跨模态的对比，证明了该方法的普适性和客观性。

### 6. 主要结论与发现
*   **PCA 的必要性**：在处理基因组模型时，PCA 投影能纠正原始 TCAV 出现的“符号错误”（例如将正向贡献的 Motif 误判为负向）。
*   **解释一致性**：在 one-hot 模型上，TPCAV 识别出的核心 Motif 与 TF-MoDISco 高度一致，且结果更易解读（无正负抵消的歧义）。
*   **非序列特征解释**：TPCAV 成功识别出重复序列（如 GC-rich repeats）和染色质开放性信号对预测的贡献。
*   **基础模型评估**：发现 DNABERT-2 在嵌入空间中比 Nucleotide Transformer 和 HyenaDNA 更有效地编码了调控 Motif 信息。
*   **异质性发现**：在 BPNet 实验中，TPCAV 揭示了同一转录因子的不同结合峰（Peaks）在利用生物学概念上存在异质性，并能据此对 Peaks 进行功能分类。

### 7. 优点
*   **通用性（Input-agnostic）**：不限制输入格式，是目前极少数能解释分词化基础模型和多模态模型的全局工具。
*   **鲁棒性**：通过 PCA 解决了深度学习模型中常见的特征共线性问题。
*   **灵活性**：用户可以根据先验知识自定义任何“概念集”（如特定的增强子类别、重复元件等）进行查询。
*   **可解释性深度**：不仅提供全局得分，还能生成特定概念的局部归因图。

### 8. 不足与局限
*   **依赖先验概念**：TPCAV 是一种“基于查询”的方法，需要用户预先定义概念集。它不能像 TF-MoDISco 那样完全从头（de novo）发现未知的序列模式。
*   **计算开销**：对于包含数千个概念的数据库，需要为每个概念训练分类器，虽然单次训练快，但大规模筛选时仍有一定计算量。
*   **线性假设**：CAV 假设概念在嵌入空间中是线性可分的，虽然在深层网络中这通常成立，但在浅层网络中可能失效。

（完）
