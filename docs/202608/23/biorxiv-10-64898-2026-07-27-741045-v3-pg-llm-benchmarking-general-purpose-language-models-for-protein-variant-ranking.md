---
title: "PG-LLM: Benchmarking General-Purpose Language Models for Protein Variant Ranking"
title_zh: PG-LLM：用于蛋白质变体排序的通用语言模型基准测试
authors: "Arora, R. K., Chen, L. T., Du, M., Marks, D., Church, G."
date: 2026-08-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.27.741045v3.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 评测通用语言模型在蛋白质变异排序上的表现，关联基因组大模型与医学大语言模型主题
tldr: 通用大语言模型正被用于蛋白质设计，但其对突变效应的排序能力缺乏系统评估。本文提出PG-LLM基准，涵盖217个ProteinGym任务和59个时序保留任务，要求模型仅根据野生型序列与测定描述对变异排名。Claude Opus 5和GPT 5.6 Sol表现最佳，Spearman相关分别为0.406和0.402，超过95个已发表预测器中的49个，接近ESM2-650M但低于VenusREM。性能随测试时计算量扩展但增益饱和，无工具LLM能捕获大量变异信号，仍不及最强专用模型。
source: biorxiv
selection_source: fresh_fetch
motivation: 语言模型评估蛋白质变异效应的能力未明，缺乏统一基准。
method: 构建PG-LLM，整合ProteinGym与59个新任务，统一评估13个LLM与95个预测器。
result: Claude Opus 5最佳，ρ=0.406，超半数预测器，但低于VenusREM；计算量缩放收益递减。
conclusion: 无工具LLM有较强变异信号，但仍弱于专用模型，基准可指导未来评估。
---

## 摘要
通用前沿语言模型正越来越多地被用于蛋白质设计工作，但其理解和评估变体效应的能力仍不明确。在此，我们介绍了PG-LLM，一个包含276个蛋白质变体优先级排序任务的基准测试：其中217个来自ProteinGym，另有59个来自近期发表研究的时间保持集。每项任务采用相同格式：仅根据野生型蛋白质序列和检测描述，要求语言模型对一组变体序列进行排序，且无法访问工具、多序列比对或蛋白质结构。我们使用相同的评估指标，在相同的变体上评估了十三个语言模型和95个已发表的蛋白质预测器。Claude Opus 5（Max）和GPT 5.6 Sol（Max）是表现最佳的LLM，Spearman相关性分别为ρ=0.406和0.402。Opus 5优于95个已发表蛋白质预测器中的49个，包括46个仅序列方法中的41个，并接近ESM2-650M（ρ=0.411），但仍低于领先的预测器VenusREM（ρ=0.523）。我们观察到，变体排序性能随GPT、Claude和Gemini模型的测试时计算量呈比例提升，但在接近专家级蛋白质预测器的差距之前增益逐渐减小。为解决污染风险，我们创建了一个保持评估集，包含来自19项研究的59个DMS检测，其分数首次公开于2026年1月之后。在该集合上，我们观察到的性能和测试时计算比例趋势与源自ProteinGym的217项任务相似。PG-LLM表明，无工具语言模型能够捕获大量蛋白质变体信号，优于许多基于序列的预测器，但仍低于最强专用模型。

## Abstract
General-purpose frontier language models are being increasingly utilized for protein-design work, yet their ability to understand and evaluate variant effects remains unclear. Here, we introduce PG-LLM, a benchmark comprising 276 protein-variant prioritization tasks: 217 from ProteinGym and a temporally held-out set of 59 from recently published studies. Each task follows the same format: a language model is asked to rank a list of variant sequences given only the wild-type protein sequence and an assay description with no access to tools, multiple-sequence alignments, or protein structures. We evaluate thirteen language models and 95 published protein predictors on the same variants with the same evaluation metric. Claude Opus 5 (Max) and GPT 5.6 Sol (Max) are the best performing LLMs with Spearman correlations of{rho} = 0.406 and 0.402 respectively. Opus 5 outperforms 49 of 95 published protein predictors, including 41 of 46 sequence-only methods, and approaches ESM2-650M at{rho} = 0.411, but remains below the leading predictor VenusREM at{rho} = 0.523. We observe that variant-ranking performance scales with test-time compute across GPT, Claude, and Gemini models, but gains taper before closing the gap to specialist protein predictors. To address contamination risk, we create a held-out evaluation set with 59 DMS assays from 19 studies whose scores first became public after January 2026. On this set, we observe performance and test time compute scaling trends similar to those on the 217 tasks derived from ProteinGym. PG-LLM shows that tool-free language models capture substantial protein-variant signal, outperforming many sequence-based predictors while remaining below the strongest specialized models.