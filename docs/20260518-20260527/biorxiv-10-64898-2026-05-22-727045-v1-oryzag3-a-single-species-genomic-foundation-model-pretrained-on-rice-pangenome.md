---
title: "OryzaG3: A Single-species Genomic Foundation Model Pretrained on Rice Pangenome"
title_zh: OryzaG3：一种在水稻泛基因组上预训练的单物种基因组基础模型
authors: "Yang, L., Xia, Y., Yang, Z., Xia, C., Wu, T., Zou, M., Xia, Z."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.22.727045v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 基于水稻泛基因组预训练的单物种基因组基础模型
tldr: 多物种基因组语言模型虽有效，但高质量单物种基础模型稀缺。提出OryzaG3，基于149个水稻基因组共59.20 Gb序列，采用3-mer分词和因果语言模型预训练，支持32k上下文。在polyA预测任务中性能媲美多物种模型，推理吞吐量提升4倍。证明轻量单物种模型结合高质量泛基因组可降低计算开销，为水稻功能基因组和分子育种提供可扩展框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基因组模型多聚焦多物种，单物种作物基础模型缺乏，需利用水稻泛基因组提升表示效率。
method: 基于149个高质量水稻基因组的59.20 Gb序列，采用非重叠3-mer分词和因果语言模型预训练，参数7亿，支持32k上下文。
result: 在polyA预测任务中性能与多物种模型相当，推理吞吐量提升4倍，兼顾准确与效率。
conclusion: 轻量级单物种模型OryzaG3通过高质量泛基因组匹配多物种基准，降低计算开销，适用于水稻研究和育种。
---

## 摘要
尽管多物种基因组语言模型推动了生物表示学习的发展，但针对作物的高质量单物种基础模型仍然稀缺。利用近期扩展的水稻泛基因组资源，我们推出OryzaG3——一个具有7亿参数、物种特异性的DNA语言模型。OryzaG3采用非重叠3-标记分词策略和因果语言建模目标，在来自149个高质量水稻基因组的59.20 Gb染色体级序列上进行预训练，支持长达32k标记的上下文长度变体。在Plants Genomic Benchmark polyA预测任务中，OryzaG3与领先的多物种模型相比，取得了具有竞争力的预测性能，同时在相同长上下文条件下实现了推理吞吐量四倍的提升。最终，OryzaG3证明，基于高质量泛基因组训练的轻量级单物种基础模型能够匹敌多物种基准，同时显著降低计算开销。这项工作为水稻功能基因组学、分子育种以及目标作物基础模型开发提供了可扩展的框架。

## Abstract
While multi-species genomic language models have advanced biological representation learning, high-quality, single-species foundation models for crops remain scarce. Leveraging recently expanded rice pangenome resources, we introduce OryzaG3, a species-specific DNA language model with 700M parameters. OryzaG3 was pretrained on 59.20 Gb of chromosome-level sequences from 149 high-quality rice genomes using a non-overlapping 3-mer tokenization strategy and a causal language modeling objective, featuring context-length variants up to 32k tokens. On the Plants Genomic Benchmark polyA prediction task, OryzaG3 achieves competitive predictive performance against leading multi-species models while delivering a four-fold increase in inference throughput under identical long-context conditions. Ultimately, OryzaG3 demonstrates that lightweight, single-species foundation models trained on high-quality pangenomes can match multi-species benchmarks while significantly reducing computational overhead. This work provides a scalable framework for rice functional genomics, molecular breeding, and targeted crop foundation model development.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：多物种基因组语言模型（如DNABERT、HyenaDNA等）在生物学表示学习上取得了进展，但针对单一作物的高质量基础模型仍然稀缺。水稻作为重要粮食作物，其功能基因组学和分子育种需要高效、低成本的计算工具。
- **背景**：近期水稻泛基因组资源（来自149个高质量水稻基因组）得到扩展，为构建单物种基础模型提供了充足且高质量的序列数据。现有多物种模型计算开销大，而轻量级单物种模型有望在保持性能的同时大幅降低资源需求。
- **整体含义**：探索基于高质量泛基因组训练的轻量级单物种基础模型是否能在关键下游任务（如polyA预测）上匹敌甚至超越多物种模型，从而为水稻研究提供更经济、可扩展的框架。

## 2. 论文提出的方法论

- **核心思想**：采用非重叠3-mer分词（tokenization）策略，将DNA序列分割为连续的3碱基片段作为词汇单元；使用因果语言建模（causal language modeling）目标进行自监督预训练。
- **关键技术细节**：
  - 模型架构：基于Transformer的因果语言模型，参数规模为7亿（700M）。
  - 预训练数据：来自149个高质量水稻基因组的59.20 Gb染色体级序列。
  - 上下文长度：支持高达32k token的变体（即最长可处理32k个3-mer标记，对应96k碱基对）。
  - 分词方式：非重叠3-mer，可保留三联体密码子语义信息。
- **算法流程**（文字说明）：
  1. 数据收集：整合149个水稻泛基因组的染色体级序列。
  2. 预处理：将序列按非重叠窗口分割为3-mer token。
  3. 预训练：采用因果语言模型（类似GPT）的next-token prediction任务，在59.20 Gb数据上训练7亿参数模型。
  4. 微调与评估：在下游任务（如polyA预测）中对模型进行微调，并与多物种基线对比。

## 3. 实验设计

- **数据集**：主要使用上述149个水稻基因组序列用于预训练。下游任务采用Plants Genomic Benchmark中的polyA预测任务（多腺苷酸化位点预测）。
- **Benchmark**：Plants Genomic Benchmark，具体比较了polyA位点预测的准确性。
- **对比方法**：与“领先的多物种模型”进行比较（文中未明确列出模型名称，推测可能包括DNABERT、HyenaDNA、NT等）。
- **评估指标**：预测性能（如准确率、F1等）以及推理吞吐量（tokens/秒）。

## 4. 资源与算力

- **文中未明确说明**具体的GPU型号、数量或训练时长。仅提到模型参数为7亿，预训练数据量为59.20 Gb，支持32k上下文。在推理阶段，OryzaG3在相同长上下文条件下实现了推理吞吐量四倍提升（相比多物种模型），但未给出具体算力配置。

## 5. 实验数量与充分性

- **实验数量**：论文仅报告了一个主要下游任务（polyA预测）的结果。未提及在更多任务（如基因注释、调控元件预测等）上的消融实验或跨数据集验证。
- **充分性与客观性**：
  - 优点：使用了公认的Plants Genomic Benchmark，对比了多物种模型，保证了比较的公平性。
  - 不足：实验覆盖较窄，仅一个任务；缺乏消融研究（如不同分词策略、不同上下文长度的影响）；未展示在更多水稻特异性任务上（如产量相关基因预测、抗病性等）的效果，泛化性证据不足。

## 6. 论文的主要结论与发现

- 基于高质量泛基因组训练的轻量级单物种基础模型（7亿参数，OryzaG3）在polyA预测任务上取得了与领先多物种模型相当的表现。
- 在同一长上下文条件下，OryzaG3的推理吞吐量比多物种模型高出4倍，显著降低了计算开销。
- 证明了“单物种 + 高质量泛基因组”策略可以替代更庞大的多物种模型，为水稻功能基因组学和分子育种提供了更高效、可扩展的基础模型框架。

## 7. 优点

- **方法创新**：首次将水稻泛基因组资源用于单物种DNA语言模型预训练，充分利用物种内多样性。
- **效率优先**：采用3-mer分词和因果LM，模型轻量（7亿参数），推理速度快，适合大规模应用。
- **实用性**：支持32k长上下文，可捕获较长范围基因组依赖关系。
- **基准贡献**：为作物基因组学提供了可复现的基准模型和框架。

## 8. 不足与局限

- **实验覆盖不足**：仅评估一个下游任务（polyA预测），未在更多功能基因组任务（如启动子预测、剪接位点识别、基因表达预测）上进行验证，性能泛化性存疑。
- **缺乏消融研究**：未比较不同分词粒度（如1-mer、6-mer）、不同模型大小、不同上下文长度对性能/效率的影响，无法明确最优配置。
- **偏差风险**：训练数据仅来自149个水稻基因组，可能偏向某些亚种或栽培品种，泛化到野生稻或其他作物需验证。
- **未说明预训练细节**：如学习率、优化器、训练步数、损失曲线等均未提供，可复现性受限。
- **算力信息缺失**：无法评估训练资源需求与机会成本。
- **应用限制**：模型仅面向水稻，无法直接迁移至其他作物；且需要高质量泛基因组作为前提。

（完）
