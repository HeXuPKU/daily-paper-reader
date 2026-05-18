---
title: "Corpus-wide causality: Algorithm design & application for aggregating gene-disease causal evidence"
title_zh: 全语料库因果关系：聚合基因-疾病因果证据的算法设计与应用
authors: "Bansal, N., Parsodkar, A. P., Pathak, A., Narayanan, M."
date: 2026-05-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.08.723796v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 大语言模型用于从生物医学文献中提取基因-疾病因果证据
tldr: 本研究旨在从大规模生物医学文献中识别基因与疾病间的因果关系，而非简单的关联。作者开发了全语料库因果评分（CWCS）方法，通过整合基因调节网络信号（CWCS-Net）和基于改进真值发现算法的文献证据（CWCS-TD）来评估因果性。实验表明，该方法在识别因果关系方面优于GPT-4o等大语言模型，有效解决了文献稀疏性和可靠性评估的挑战，为药物研发提供了更精准的靶点筛选工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 区分基因与疾病间的因果关系对药物研发至关重要，但现有方法在全语料库证据聚合及因果推断准确性上存在不足。
method: 提出CWCS框架，结合多层网络中心性算法提取网络信号，并利用融入文献计量特征的真值发现算法量化文献证据。
result: 在OMIM基准测试中，CWCS的F1分数达到0.600，显著优于GPT-4o（0.505）和MMed-Llama 3（0.522），具有更高的预测精确度。
conclusion: 研究证明了结合网络信号与文献证据的专用算法在推断生物医学因果关系方面比通用大语言模型更具优势和应用潜力。
---

## 摘要
识别因果关系并将其与关联关系区分开来是一项核心科学任务，具有广泛的应用；例如，了解基因与疾病之间的因果联系可以使药物研发集中于治愈疾病，而不仅仅是症状管理。尽管已有几项研究致力于从 PubMed 等大型生物医学文献语料库中自动提取实体间的关系，但只有少数研究从摘要中提取因果关系，而总结语料库级别因果联系证据的研究则更少。最近，大语言模型（LLMs）越来越多地被用于总结生物医学信息和提取关系；然而，目前明显缺乏将这些通用的基于 LLM 的方法与专门的、具有领域意识的语料库级因果推理框架进行比较的明确基准测试。在这项工作中，我们开发了一种通过整合两类证据来推断基因-疾病（G-D）对的语料库级因果得分（CWCS）的方法：(i) 先验基因调控网络中基于网络的因果信号，使用现有的多层网络中心性算法量化为 CWCS-Net 得分；以及 (ii) 全语料库文献证据，使用新开发的真理发现（Truth Discovery, TD）算法量化为 CWCS-TD 得分。我们的 CWCS-TD（评分）算法在对共同提及这些 G-D 对的 PubMed 摘要的可靠性进行建模的同时，联合且迭代地估计多个 G-D 对的因果得分；由于其结合了出版物的文献计量特征，以解决断言 G-D 因果关系的摘要稀疏性挑战，该算法代表了 TD 算法领域的进步。使用 OMIM 作为外部专家策划的参考来评估 G-D 对是否为因果关系的分类，我们的 CWCS 方法在十种疾病中实现了 0.600 的因果类别 F1 分数，优于 GPT-4o 和 MMed-Llama 3 这两种 LLM（在使用精准率-召回率曲线下面积作为评估指标时，这一性能趋势依然存在）。两种 LLM 都表现出高召回率但精确率相对较低，由于存在大量假阳性预测，导致因果类别 F1 分数较低（GPT-4o 为 0.505，MMed-Llama 3 为 0.522）。综上所述，这些评估和其他消融实验表明，我们精心设计的算法在整理和整合来自网络和文献来源的生物医学因果关系证据方面具有前景，从而支持了其更广泛的适用性。

## Abstract
Identifying causal relationships and distinguishing them from associations is a central scientific endeavor with many applications; knowing causal links between genes and diseases, for instance, can focus drug discovery on curing diseases beyond just symptom management. Despite several studies on automatically extracting relations between entities from large biomedical literature corpora like PubMed, only a few studies extract causal relations from abstracts and even fewer summarize corpus-level evidence for causal links. Recently, Large Language Models (LLMs) have been increasingly deployed to summarize biomedical information and extract relations; however, there is a distinct lack of explicit benchmarking comparing these generalized LLM-based methods against specialized, domain-aware frameworks for corpus-wide causal inference. In this work, we develop a method to infer Corpus-Wide Causal Score (CWCS) of a gene-disease (G-D) pair by integrating two pieces of evidence: (i) network-based causal signals in a prior gene regulatory network, quantified as a CWCS-Net score using an existing multilayer network centrality algorithm; and (ii) corpus-wide literature evidence, quantified as a CWCS-TD (TD for Truth Discovery) score using a newly-developed TD algorithm. Our CWCS-TD (scoring) algorithm jointly and iteratively estimates causal scores for multiple G-D pairs while modeling the reliability of PubMed abstracts co-mentioning them; and represents an advance in the field of TD algorithms due to its incorporation of bibliometric features of publications to address the challenge of sparsity of abstracts that assert a G-D causal relation. Using OMIM as an external expert-curated reference to evaluate classifications of G-D pairs as causal or not, our CWCS method achieved a causal class F1 score of 0.600 across ten diseases, outperforming both LLMs, GPT-4o and MMed-Llama 3 (this performance trend also persists when using area under the precision-recall curve as the evaluation metric). Both LLMs exhibit high recall accompanied by comparatively low precision, resulting in lower causal class F1 scores (0.505 for GPT-4o and 0.522 for MMed-Llama 3) due to large number of false positive predictions. Taken together, these evaluations and other ablation studies show the promise of our carefully designed algorithm in collating and integrating evidence of biomedical causal relations from both network- and literature-based sources, thereby supporting its broader applicability.