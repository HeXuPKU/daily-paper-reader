---
title: "PG-LLM: Benchmarking General-Purpose Language Models for Protein Variant Ranking"
title_zh: PG-LLM：用于蛋白质变异排序的通用语言模型基准测试
authors: "Arora, R. K., Chen, L. T., Du, M., Marks, D., Church, G."
date: 2026-08-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.27.741045v3.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 针对蛋白质变异排序的语言模型基准，与基因组大模型相关
tldr: 通用大语言模型在蛋白质变体排序中的能力尚不明确。为此提出PG-LLM基准，包含217个ProteinGym任务和59个时间上留出的新任务，要求模型仅根据野生型序列和测定描述排序变体，不提供工具或结构。评估13个LLM和95个已发布预测器，Claude Opus 5与GPT 5.6 Sol表现最佳（rho约0.40），超过多数序列方法但低于最强专用模型VenusREM（rho=0.523）。性能随测试时计算增加而提升，留出集验证了趋势，表明免工具LLM捕获了显著变体信号。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有通用语言模型用于蛋白质设计日益增多，但其变体效应排序能力缺乏系统评估，且需防范训练数据污染。
method: 构建PG-LLM基准，统一任务格式，在相同变体与指标下比较13个LLM和95个已发布预测器，并新增时间留出集。
result: Opus 5和GPT 5.6 Sol的Spearman相关分别为0.406和0.402，超过41/46序列方法，接近ESM2-650M但低于VenusREM的0.523；性能随测试时计算缩放。
conclusion: 免工具LLM具备实质蛋白质变体排序能力，优于多数序列预测器，但仍不及最强专用模型，留出集验证结果稳健。
---

## 摘要
通用前沿语言模型越来越多地被用于蛋白质设计工作，但它们理解和评估变异效应的能力仍不清楚。为此，我们推出了PG-LLM，一个包含276个蛋白质变异优先级排序任务的基准：其中217个来自ProteinGym，另外59个来自近期发表研究的时间保留集。每个任务都遵循相同的格式：仅给定野生型蛋白质序列和检测描述，语言模型需要对一组变异序列进行排序，且无法访问工具、多序列比对或蛋白质结构。我们在相同的变异集和相同评估指标下，评估了十三个语言模型和95个已发表的蛋白质预测器。表现最佳的LLM是Claude Opus 5（Max）和GPT 5.6 Sol（Max），Spearman相关系数分别为ρ=0.406和0.402。Opus 5优于95个已发表蛋白质预测器中的49个，包括46个纯序列方法中的41个，并以ρ=0.411接近ESM2-650M，但仍低于领先预测器VenusREM（ρ=0.523）。我们观察到，在GPT、Claude和Gemini模型中，变异排序性能随测试时计算量增加而提升，但在缩小与专门蛋白质预测器的差距之前，增益逐渐趋于平缓。为解决污染风险，我们创建了一个保留评估集，包含来自19项研究的59个DMS检测，其分数首次公开于2026年1月之后。在该数据集上，我们观察到的性能和测试时计算扩展趋势与来自ProteinGym的217个任务相似。PG-LLM表明，无工具的语言模型能够捕捉大量的蛋白质变异信号，优于许多基于序列的预测器，但仍未达到最强专门模型的水平。

## Abstract
General-purpose frontier language models are being increasingly utilized for protein-design work, yet their ability to understand and evaluate variant effects remains unclear. Here, we introduce PG-LLM, a benchmark comprising 276 protein-variant prioritization tasks: 217 from ProteinGym and a temporally held-out set of 59 from recently published studies. Each task follows the same format: a language model is asked to rank a list of variant sequences given only the wild-type protein sequence and an assay description with no access to tools, multiple-sequence alignments, or protein structures. We evaluate thirteen language models and 95 published protein predictors on the same variants with the same evaluation metric. Claude Opus 5 (Max) and GPT 5.6 Sol (Max) are the best performing LLMs with Spearman correlations of{rho} = 0.406 and 0.402 respectively. Opus 5 outperforms 49 of 95 published protein predictors, including 41 of 46 sequence-only methods, and approaches ESM2-650M at{rho} = 0.411, but remains below the leading predictor VenusREM at{rho} = 0.523. We observe that variant-ranking performance scales with test-time compute across GPT, Claude, and Gemini models, but gains taper before closing the gap to specialist protein predictors. To address contamination risk, we create a held-out evaluation set with 59 DMS assays from 19 studies whose scores first became public after January 2026. On this set, we observe performance and test time compute scaling trends similar to those on the 217 tasks derived from ProteinGym. PG-LLM shows that tool-free language models capture substantial protein-variant signal, outperforming many sequence-based predictors while remaining below the strongest specialized models.