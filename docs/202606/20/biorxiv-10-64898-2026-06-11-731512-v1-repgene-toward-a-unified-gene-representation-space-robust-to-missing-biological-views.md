---
title: "RepGene: Toward a Unified Gene Representation Space Robust to Missing Biological Views"
title_zh: RepGene：面向缺失生物学视图鲁棒的统一基因表示空间
authors: "Hou, H., Xia, T., Hu, L., Qin, H., Zhang, Y., Li, Y., Fang, S., Cao, L."
date: 2026-06-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.11.731512v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 统一基因表示整合多生物学视图
tldr: 基因可由多种异质性生物视图描述，但现有嵌入多针对单模态且难以比较复用。RepGene提出轻量级单分支框架，通过模态适配器、共享编码器、存在感知融合与自监督跨视图目标，将五种视图映射到统一潜在空间。在固定特征设置下，两阶段训练后，线性探测表明完整模态下性能竞争，且缺失任一模态时性能变化有限。该工作作为可行性研究，为多视图基因表示的统一与鲁棒性提供了初步方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基因嵌入多为单模态，难以在多种生物视图缺失时比较或复用，亟需统一的表示空间。
method: RepGene使用模态适配器对齐各视图嵌入，经共享编码器与存在感知融合，辅以自监督跨视图目标训练。
result: 在完整模态下性能竞争，缺失单视图时平均性能变化有限，单视图推理仍保持非平凡结果。
conclusion: RepGene作为可行性研究，展示了统一基因表示空间的初步潜力，但需更全面的基线消融与泄漏验证。
---

## 摘要
基因可以通过多种异质的生物学视图来描述，包括基因组序列、转录本序列、蛋白质序列、文本知识以及单细胞表达背景，然而现有的基因嵌入大多局限于特定模态，并且在许多视图不可用时难以比较或重用。我们研究了一个较窄但具有实际意义的问题：来自这些不同来源的预训练嵌入能否被组织成一个共享的基因表示接口，并在严重的模态缺失条件下仍然可用？为了探究这一问题，我们引入了RepGene，这是一个轻量级的单分支框架，结合了模态适配器、共享编码器、存在感知融合以及自监督跨视图目标，将五种生物学视图映射到一个潜在空间中。我们的目标并非宣称一种新的多模态学习原理，也不是证明其优于所有更简单的融合策略，而是提供一个初步的技术实例，以测试在固定特征设置下这种共享接口是否可行。在采用两阶段协议（即在冻结的上游嵌入上对RepGene进行自监督训练，并通过下游线性探测进行评估）的情况下，我们发现了初步证据表明，所学习的表示在全模态设置中具有广泛的竞争力，并且在推理时仅观察到部分模态子集时仍能提供信息。我们研究中最强的信号是在缺失视图下的鲁棒性：当移除一个模态时，平均性能变化通常有限，甚至在评估基准中，单视图推理仍然具有一定的价值。这些结果并未解决统一的生物学表示学习问题，并且应结合不完整的简单融合基线、有限的结构消融、基准依赖以及可能的上游特征暴露来进行解读。因此，我们将RepGene定位为一项可行性研究，以及进行更强比较、更广泛基准和泄漏感知验证的起点。

## Abstract
Genes can be described through multiple heterogeneous biological views, including genomic sequence, transcript sequence, protein sequence, textual knowledge, and single-cell expression context, yet existing gene embeddings remain largely modality-specific and difficult to compare or reuse when many views are unavailable. We study a narrower but practically important question: whether pretrained embeddings from these distinct sources can be organized into a shared gene representation interface that remains usable under severe missing-modality conditions. To investigate this question, we introduce RepGene, a lightweight single-branch framework that combines modality adapters, a shared encoder, presence-aware fusion, and self-supervised cross-view objectives to map five biological views into one latent space. Our goal is not to claim a new multimodal learning principle or to establish superiority over all simpler fusion strategies, but to provide an initial technical instantiation for testing whether such a shared interface is feasible in a fixed-feature setting. Under a two-stage protocol in which RepGene is trained self-supervised on frozen upstream embeddings and evaluated by downstream linear probing, we find preliminary evidence that the learned representation is broadly competitive in the full-modality setting and remains informative when only partial modality subsets are observed at inference time. The strongest signal in our study is robustness under missing views: average performance changes are often limited when one modality is removed, and even single-view inference remains non-trivial in the evaluated benchmark regime. These results do not resolve unified biological representation learning, and they should be interpreted in light of incomplete simple-fusion baselines, limited architectural ablation, benchmark dependence, and possible upstream feature exposure. We therefore position RepGene as a feasibility study and a starting point for stronger comparisons, broader benchmarks, and leakage-aware validation.