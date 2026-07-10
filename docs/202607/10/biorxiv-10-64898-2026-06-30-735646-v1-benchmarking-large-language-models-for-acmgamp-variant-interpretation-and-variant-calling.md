---
title: Benchmarking large language models for ACMG/AMP variant interpretation and variant calling
title_zh: 大型语言模型在ACMG/AMP变异解读和变异检出中的基准测试
authors: "Corpas, M."
date: 2026-07-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.30.735646v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 在基因组学中基准测试LLM用于变异解读和检测
tldr: 大语言模型在基因组变异解读中应用广泛，但仅用准确率评估不足以判断系统安全性或定位失败源头。ClawBench框架通过时间盲验证集和失败封闭证据契约，从有效性、安全性、可溯源性等多个维度评估模型。结果显示危险误分类罕见且与模型无关，不同变异类型的瓶颈层不同；变体调用中信任属性差异体现架构依赖，而非模型能力差异。该框架表明可信度源于管道架构而非模型，为领域提供可移植的归因单位。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1610, \"height\": 970}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1652, \"height\": 433}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1381, \"height\": 747}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1552, \"height\": 718}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1240, \"height\": 891}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1283, \"height\": 555}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 781, \"height\": 374}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1581, \"height\": 262}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1785, \"height\": 210}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1277, \"height\": 308}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1694, \"height\": 260}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1298, \"height\": 258}]"
motivation: 现有评估仅依赖准确率，无法揭示系统安全性或定位工作流中失败来源，需要多维度归因框架。
method: 提出ClawBench框架，采用时间盲验证集和失败封闭证据契约，评估有效性、安全性、可溯源性和可重复性。
result: 危险误分类罕见且模型无关；不同变异类别瓶颈不同；变体调用中信任属性差异源于架构而非模型能力。
conclusion: 相同结果可能来自不同失败模式，可信度取决于管道架构而非模型，提供抗污染的归因方法。
---

## 摘要
智能体大型语言模型越来越多地用于基因组工作流程，从变异检出到临床解读，然而它们仅通过准确率来评估，单一的数字无法说明系统是否安全，也无法指出工作流程中故障源自何处。我们提出ClawBench，一个框架，将每个结果归因于产生它的架构层，涵盖标准管道的两个部分。两个设计选择消除了使智能体基因组学难以评估的混淆因素：一个时间盲检的真实集，其中每个被评分的ClinVar标签在测试的每个模型的训练截止日期之后才首次可用；以及一个故障封闭的证据契约，阻止证据与真实标签循环。我们在约束梯度下评估有效性、安全性、来源和可重复性，而不仅仅是准确率，该约束将正确性从模型的先验知识转移到可执行、经过验证的代码中。

我们展示了三件事。首先，危险的错误分类罕见且与模型无关，是可执行架构的受控前提条件而非前沿问题，而伪造的证据是可测量的，并通过执行而被中和。其次，不同的变异类别受到不同层的速率限制：功能丧失变异受确定性组合器阈值限制，罕见错义变异受证据形成限制，其中证据获取不对称且有上限，而强度分配是一个可恢复层，天真的强度许可提示会混淆该层。第三，对于变异检出，各系统分支的区别不在于模型是否能规划管道（所有模型都能），而在于信任属性、固定性、来源、可审计性和可重复性，这些属性单调地向经过验证的执行攀升；本地开放权重模型重现了安全性结果，但满足结构化输出和来源契约的频率远低于前沿模型，这是一种合规性差距，而非能力或安全性差距。端到端联合将故障归因于整个工作流程，将遗漏的检出与传播的基因型错误以及正确检出但错误解读的变异区分开来。

ClawBench表明，看似相同的结果来源于不同且可独立测量的故障模式，并且智能体基因组学中的可信度是管道架构的属性而非模型的属性，为该领域提供了一个可移植、抗污染的归因单元。

## Abstract
Agentic large language models are increasingly used across the genomic workflow, from variant calling to clinical interpretation, yet they are evaluated by accuracy alone, a single figure that cannot say whether a system is safe or where in the workflow a failure originates. We present ClawBench, a framework that attributes each outcome to the architectural layer that produced it across both halves of the canonical pipeline. Two design choices remove the confounds that make agentic genomics hard to evaluate: a temporally blinded truth set, in which every scored ClinVar label first became available only after the training cutoff of every model tested, and a fail-closed evidence contract that blocks evidence circular with the truth label. We score validity, safety, provenance and reproducibility, not accuracy alone, under a constraint gradient that relocates correctness from a models prior into executed, validated code.

We show three things. First, dangerous misclassification is rare and model-invariant, a controlled precondition of the executed architecture rather than a frontier, while fabricated evidence is measurable and is neutralised by execution. Second, different variant classes are rate-limited by different layers: loss-of-function variants by the deterministic combiner threshold, and rare missense by evidence formation, where evidence acquisition is asymmetric and capped and strength assignment is a recoverable layer that naive strength-licensing prompts confound. Third, for variant calling the arms separate not on whether a model can plan a pipeline, which all do, but on trust properties, pinning, provenance, auditability and reproducibility, which climb monotonically toward validated execution; and a local open-weight model reproduces the safety result yet meets the structured-output and provenance contract far less often than frontier models, a conformance gap rather than a capability or safety gap. An end-to-end join attributes failures across the whole workflow, separating a missed call from a propagated genotype error from a correctly called but misinterpreted variant.

ClawBench shows that apparently identical outcomes arise from distinct, independently measurable failure modes, and that trustworthiness in agentic genomics is a property of the pipeline architecture rather than of the model, providing a portable, contamination-resistant unit of attribution for the field.