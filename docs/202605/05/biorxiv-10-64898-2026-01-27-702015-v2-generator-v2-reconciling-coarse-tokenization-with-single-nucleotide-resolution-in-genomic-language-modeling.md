---
title: "GENERator-v2: Reconciling Coarse Tokenization with Single-Nucleotide Resolution in Genomic Language Modeling"
title_zh: GENERator-v2：在基因组语言建模中调和粗粒度分词与单核苷酸分辨率
authors: "Li, Q., Zhan, Z., Feng, S., Zhu, Y., He, Y., Wu, W., Shi, Z., Wang, S., Hu, Z., Yang, Z., Li, J., Tang, J., Liu, H., Qin, T."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.27.702015v2.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 基因组基础模型与大规模基因组语言建模
tldr: 基因组基础模型在处理长序列时面临长程上下文、单核苷酸分辨率与计算效率之间的权衡。本文提出GENERator-v2，通过分解核苷酸监督（FNS）将高效的k-mer分词与单核苷酸似然对齐，并利用基因组压缩预训练（GCP）优化数据分布。该模型支持高达98k bp的上下文，在保持核苷酸级精度的同时显著提升了推理效率，在多项基准测试中达到或超越了现有SOTA水平。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决基因组模型在长序列建模中难以兼顾计算效率、长程上下文和单核苷酸分辨率的问题。
method: 提出了分解核苷酸监督（FNS）以对齐k-mer与单核苷酸概率，并结合基因组压缩预训练（GCP）聚焦关键功能区域。
result: 模型在零样本评估和下游微调任务中均优于先前方法，且在支持长达98k bp上下文的同时实现了更高效的推理。
conclusion: 通过在监督机制和数据构建上对齐生物学结构，为构建可扩展且生物学保真的基因组语言模型提供了有效路径。
---

## 摘要
基因组基础模型旨在直接从 DNA 序列中学习通用表示，从而在广泛的生物学任务中实现序列理解、生成和概率推理。然而，由于长程上下文、核苷酸级分辨率和实际计算效率之间的矛盾，将此类模型扩展到基因组长度仍然具有挑战性。架构创新虽然实现了越来越长的名义输入，但往往难以将额外的上下文转化为显著的性能提升，特别是在真核基因组中存在稀疏功能信号的情况下。在这项工作中，我们从训练目标和数据构建的角度重新审视了长上下文基因组基础模型的设计。我们引入了因子化核苷酸监督（Factorized Nucleotide Supervision, FNS），通过概率边缘化将高效的 k-mer 分词与单核苷酸似然相调和；以及基因组压缩预训练（Genome Compression Pretraining, GCP），通过专注于以基因为中心和调控区域来重塑训练分布。这些技术共同使标准的 Transformer 模型能够在不牺牲核苷酸级保真度或计算效率的情况下，执行功能性上下文学习。基于这些想法，我们提出了一系列自回归基因组基础模型，支持跨真核和原核基因组的高达 98k 碱基对的上下文。在免训练评估和下游微调基准测试中，我们的模型始终优于之前的方法，并达到或超过了最先进的基准，同时实现了显著更高效的推理。总之，这些结果表明，将监督和数据方案与基因组序列的生物结构对齐，为实现可扩展且生物学上忠实的基因组语言建模提供了一条原则性且有效的路径。用于下游分析的模型、数据和脚本可在 https://huggingface.co/GenerTeam 公开获取。

## Abstract
Genomic foundation models aim to learn general-purpose representations directly from DNA sequence, enabling sequence understanding, generation, and probabilistic reasoning across a wide range of biological tasks. Scaling such models to genomic lengths, however, remains challenging due to the tension between long-range context, nucleotide-level resolution, and practical computational efficiency. Architectural innovations have enabled increasingly long nominal inputs, but often struggle to translate additional context into meaningful performance gains, particularly in the presence of sparse functional signal along eukaryotic genomes. In this work, we revisit the design of long-context genomic foundation models from the perspective of training objective and data construction. We introduce Factorized Nucleotide Supervision (FNS), which reconciles efficient k-mer tokenization with single-nucleotide likelihoods through probability marginalization, and Genome Compression Pretraining (GCP), which reshapes the training distribution by concentrating on gene-centric and regulatory regions. Together, these techniques enable standard transformer-based models to perform functional in-context learning without sacrificing nucleotide-level fidelity or computational efficiency. Building on these ideas, we present a family of autoregressive genomic foundation models supporting contexts of up to 98k base pairs across eukaryotic and prokaryotic genomes. Across training-free evaluations and downstream fine-tuning benchmarks, our models consistently improve over prior approaches and match or exceed state-of-the-art baselines while enabling substantially more efficient inference. Together, these results demonstrate that aligning supervision and data regimes with the biological structure of genomic sequence provides a principled and effective path toward scalable and biologically faithful genomic language modeling. Models, data, and scripts for downstream analyses are publicly available at https://huggingface.co/GenerTeam.