---
title: "Corpus-wide causality: Algorithm design & application for aggregating gene-disease causal evidence"
title_zh: 全语料库因果关系：聚合基因-疾病因果证据的算法设计与应用
authors: "Bansal, N., Parsodkar, A. P., Pathak, A., Narayanan, M."
date: 2026-05-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.08.723796v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 利用大语言模型从文献中汇总基因-疾病因果证据
tldr: 本研究旨在从海量生物医学文献中提取基因与疾病间的因果关系，而非简单的关联。作者开发了CWCS方法，通过整合基因调控网络信号（CWCS-Net）和基于真值发现算法的文献证据（CWCS-TD）来评估因果得分。CWCS-TD利用文献计量特征解决了因果断言稀疏性的挑战。实验表明，该方法在识别因果关系方面优于GPT-4o等大语言模型，显著提升了预测的精确度，为药物研发提供了更可靠的靶点依据。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的生物医学关系提取研究多关注关联而非因果，且缺乏针对全语料库因果推断的专业框架及与大语言模型的基准对比。
method: 提出CWCS方法，结合多层网络中心性算法提取基因网络信号，并利用改进的真值发现算法整合包含文献计量特征的文献证据。
result: 在十种疾病的评估中，CWCS的F1得分达到0.600，显著优于GPT-4o和MMed-Llama 3等大语言模型，有效降低了假阳性率。
conclusion: 该研究证明了结合网络信号与文献证据的专门算法在生物医学因果关系推断中比通用大模型更具优势，具有广泛的应用前景。
---

## 摘要
识别因果关系并将其与关联关系区分开来是一项核心科学任务，具有广泛的应用；例如，了解基因与疾病之间的因果联系可以使药物研发专注于治愈疾病，而不仅仅是症状管理。尽管已有若干研究致力于从 PubMed 等大型生物医学文献语料库中自动提取实体间的关系，但只有少数研究从摘要中提取因果关系，而总结语料库级别因果联系证据的研究则更少。最近，大语言模型（LLMs）越来越多地被用于总结生物医学信息和提取关系；然而，目前明显缺乏明确的基准测试，来比较这些基于通用 LLM 的方法与专门针对全语料库因果推理的领域感知框架。在这项工作中，我们开发了一种方法，通过整合两类证据来推断基因-疾病（G-D）对的全语料库因果评分（CWCS）：(i) 先验基因调控网络中基于网络的因果信号，使用现有的多层网络中心性算法量化为 CWCS-Net 评分；(ii) 全语料库文献证据，使用新开发的真理发现（Truth Discovery, TD）算法量化为 CWCS-TD 评分。我们的 CWCS-TD（评分）算法在对共同提及这些 G-D 对的 PubMed 摘要的可靠性进行建模的同时，联合且迭代地估计多个 G-D 对的因果评分；由于该算法结合了出版物的文献计量特征，以应对断言 G-D 因果关系的摘要稀疏性挑战，代表了 TD 算法领域的进步。使用 OMIM 作为外部专家策划的参考来评估 G-D 对是否为因果关系的分类，我们的 CWCS 方法在十种疾病中实现了 0.600 的因果类别 F1 分数，优于 GPT-4o 和 MMed-Llama 3 这两种 LLM（当使用精确率-召回率曲线下面积作为评估指标时，这一性能趋势依然保持）。两种 LLM 都表现出高召回率但精确率相对较低，由于存在大量假阳性预测，导致因果类别 F1 分数较低（GPT-4o 为 0.505，MMed-Llama 3 为 0.522）。综上所述，这些评估和其他消融研究表明，我们精心设计的算法在整理和整合来自网络和文献来源的生物医学因果关系证据方面具有前景，从而支持了其更广泛的适用性。

## Abstract
Identifying causal relationships and distinguishing them from associations is a central scientific endeavor with many applications; knowing causal links between genes and diseases, for instance, can focus drug discovery on curing diseases beyond just symptom management. Despite several studies on automatically extracting relations between entities from large biomedical literature corpora like PubMed, only a few studies extract causal relations from abstracts and even fewer summarize corpus-level evidence for causal links. Recently, Large Language Models (LLMs) have been increasingly deployed to summarize biomedical information and extract relations; however, there is a distinct lack of explicit benchmarking comparing these generalized LLM-based methods against specialized, domain-aware frameworks for corpus-wide causal inference. In this work, we develop a method to infer Corpus-Wide Causal Score (CWCS) of a gene-disease (G-D) pair by integrating two pieces of evidence: (i) network-based causal signals in a prior gene regulatory network, quantified as a CWCS-Net score using an existing multilayer network centrality algorithm; and (ii) corpus-wide literature evidence, quantified as a CWCS-TD (TD for Truth Discovery) score using a newly-developed TD algorithm. Our CWCS-TD (scoring) algorithm jointly and iteratively estimates causal scores for multiple G-D pairs while modeling the reliability of PubMed abstracts co-mentioning them; and represents an advance in the field of TD algorithms due to its incorporation of bibliometric features of publications to address the challenge of sparsity of abstracts that assert a G-D causal relation. Using OMIM as an external expert-curated reference to evaluate classifications of G-D pairs as causal or not, our CWCS method achieved a causal class F1 score of 0.600 across ten diseases, outperforming both LLMs, GPT-4o and MMed-Llama 3 (this performance trend also persists when using area under the precision-recall curve as the evaluation metric). Both LLMs exhibit high recall accompanied by comparatively low precision, resulting in lower causal class F1 scores (0.505 for GPT-4o and 0.522 for MMed-Llama 3) due to large number of false positive predictions. Taken together, these evaluations and other ablation studies show the promise of our carefully designed algorithm in collating and integrating evidence of biomedical causal relations from both network- and literature-based sources, thereby supporting its broader applicability.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **CWCS（Corpus-Wide Causal Score，全语料库因果评分）** 的框架，旨在从海量生物医学文献中自动聚合基因与疾病（G-D）之间的因果证据。

以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：在生物医学领域，区分基因与疾病之间的“因果关系”与“简单关联”至关重要（如用于药物靶点发现）。虽然已有大量研究提取 G-D 关联，但针对全语料库（如 PubMed 全量数据）自动总结因果证据的研究极少。
*   **研究动机**：
    *   现有的简单聚合方法（如多数投票）在处理复杂的因果断言时表现不佳。
    *   通用大语言模型（LLMs）虽然能提取关系，但在全语料库级别的因果推断中缺乏专业基准测试。
    *   文献中关于因果关系的描述往往具有稀疏性（Sparsity）和不确定性。

### 2. 方法论：核心思想与关键技术
该方法通过整合**生物网络信号**和**文献证据**来计算最终的因果得分：
*   **CWCS-Net（网络证据）**：
    *   构建一个双层网络：一层是基因-疾病（G-D）关系，另一层是基因-基因（G-G）调控关系（数据源自 OmniPath）。
    *   使用 **MultiCens（多层网络中心性算法）**，通过类似 PageRank 的机制，计算基因对疾病的局部和全局影响力。
*   **CWCS-TD（文献证据）**：
    *   开发了一种改进的**真值发现（Truth Discovery, TD）算法**。
    *   **核心创新**：引入了**文献计量特征**（期刊 H 指数、引用次数、发表年限）作为先验信息，以解决因果断言在摘要中极其稀疏的问题。
    *   **差异化奖励**：对明确的因果断言和模糊的非因果断言给予不同的权重，迭代估计摘要的可靠性和 G-D 对的真实因果得分。
*   **聚合机制**：使用 **RRF（Reciprocal Rank Fusion，倒数排名融合）** 算法将网络得分和文献得分结合，生成最终的 CWCS(comb) 评分。

### 3. 实验设计
*   **数据集/场景**：
    *   **验证集**：从 **OMIM（在线人类孟德尔遗传数据库）** 中选择了 10 种具有代表性的疾病（如乳腺癌、阿尔茨海默病、帕金森病等）作为金标准。
    *   **全量应用**：将算法应用于 PubMed 中关于阿尔茨海默病（AD）和帕金森病（PD）的所有摘要（超过 12 万篇）。
*   **Benchmark 与对比方法**：
    *   **LLMs**：GPT-4o 和 MMed-Llama 3（医疗专用大模型）。
    *   **基准算法**：随机分类器、CausalRatio（基于预测比例的简单排序）。
    *   **评估指标**：F1 分数、PR-AUC（精确率-召回率曲线下面积）、Recall@K。

### 4. 资源与算力
*   **算力说明**：文中提到 **MMed-Llama-3-8B** 是在本地部署运行的，而 **GPT-4o** 是通过 OpenAI API 调用的。
*   **具体细节**：论文**未明确列出**运行 CWCS 算法所需的具体 GPU 型号、数量或训练时长。由于 CWCS 核心算法基于矩阵运算和迭代优化，其计算开销通常远小于 LLM 的训练，但在处理全量 PubMed 数据时仍需一定的计算资源。

### 5. 实验数量与充分性
*   **实验规模**：
    *   涵盖了 10 种不同类型的疾病进行交叉验证。
    *   进行了**消融实验**，分别测试了 CWCS-Net、CWCS-TD 及其组合的效果。
    *   对比了 LLM 在相同任务下的表现。
*   **充分性评价**：实验设计较为充分且客观。通过使用专家策划的 OMIM 数据库作为外部参考，保证了评估的公平性。同时，针对 AD 和 PD 的全语料库应用展示了该算法发现新候选因果基因的潜力。

### 6 主要结论与发现
*   **CWCS 表现优异**：CWCS(comb) 在 10 种疾病上的平均 F1 分数达到 **0.600**，PR-AUC 为 **0.601**，显著优于所有对比方法。
*   **LLM 的局限性**：GPT-4o 和 MMed-Llama 3 表现出**高召回率但低精确率**（F1 分数分别为 0.505 和 0.522）。LLM 倾向于产生大量的假阳性（False Positives），即容易将相关性误判为因果性。
*   **互补性**：网络信号（Net）和文献证据（TD）具有很强的互补性，两者结合后的 PR-AUC 提升了约 17%。
*   **可靠性建模**：证明了引入文献计量特征（尤其是期刊 H 指数和发表年限）能有效提升对研究可靠性的评估。

### 7. 优点（亮点）
*   **领域感知设计**：不同于通用的 NLP 方法，该框架深度整合了生物学先验知识（调控网络）。
*   **解决稀疏性**：通过 TD 算法结合文献计量学特征，巧妙解决了生物医学因果证据在文本中分布稀疏的难题。
*   **可解释性**：相比于 LLM 的“黑箱”推理，CWCS 提供了基于网络拓扑和文献可靠性的量化评分，更易于生物医学专家理解。

### 8. 不足与局限
*   **数据源限制**：目前主要依赖于 PubMed **摘要**，未利用全文数据，可能会遗漏隐藏在正文实验细节中的因果证据。
*   **假阳性风险**：虽然优于 LLM，但在某些情况下（如表 3 所示），算法仍会将受强调控影响的非因果基因误判为高分。
*   **依赖预训练模型**：CWCS-TD 的输入依赖于前端的分类模型（如 BioBERT+SVM），前端模型的误差会传递给后续的聚合步骤。

（完）
