---
title: Benchmarking large language models for ACMG/AMP variant interpretation and variant calling
title_zh: 大语言模型在ACMG/AMP变异解读与变异检出中的基准测试
authors: "Corpas, M."
date: 2026-07-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.30.735646v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 基准测试大语言模型在变体解读和变体检出中的性能
tldr: 现有大模型评估仅用准确率，无法定位基因组流水线中的故障源头。我们提出ClawBench框架，通过时间盲真值集和故障关闭证据合约，从架构层面归因每个输出。结果发现危险误分类罕见且模型不变，不同变异类型受不同层限制，本地模型存在符合性差距。研究揭示可信度取决于流水线架构而非模型本身，为领域提供可移植的归因单元。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有评估仅用准确率，无法定位基因组流水线中故障源头，缺乏安全性归因。
method: 提出ClawBench框架，包含时间盲真值集与故障关闭证据合约，归因架构各层输出。
result: 危险误分类罕见且模型不变；不同变异类型受不同层限制；本地模型存在符合性差距。
conclusion: 基因组流水线可信度是架构属性而非模型属性，相同结果可源于不同故障模式。
---

## 摘要
代理型大语言模型越来越多地用于基因组学工作流程，从变异检出到临床解读，但评估仅基于准确性这一单一指标，无法判断系统是否安全或故障源于工作流的哪一环节。我们提出ClawBench框架，将每个结果归因于生成它的架构层，覆盖标准管线的两个半部分。两个设计选择消除了使代理型基因组学难以评估的混杂因素：时间盲的真实集（每个被评分的ClinVar标签仅在所有被测模型的训练截止日期后首次可用）和故障封闭的证据契约（阻止证据与真实标签形成循环）。我们评估有效性、安全性、溯源性和可重复性，而不仅仅是准确性，在约束梯度下将正确性从模型先验转移到执行和验证的代码中。

我们展示了三点。第一，危险错误分类罕见且与模型无关，是执行架构受控前提而非前沿问题，而捏造证据可测量并被执行消除。第二，不同变异类别受不同层速率限制：功能缺失变异受确定性组合器阈值限制，罕见错义变异受证据形成限制，其中证据获取不对称且有上限，强度赋值是可恢复层，但朴素强度授权提示会混淆。第三，在变异检出中，模型的区别不在于能否规划管线（所有模型都能），而在于信任属性、固定性、溯源、可审计性和可重复性，这些属性单调地向验证执行提升；本地开源权重模型再现了安全结果，但在结构化输出和溯源契约上的符合度远低于前沿模型，这是符合性差距而非能力或安全差距。端到端联合将故障归因于整个工作流，区分未检出、传播的基因型错误和正确检出但错误解读的变异。

ClawBench表明，看似相同的结果源于不同且独立可测的故障模式，代理型基因组学的可信度是管线架构而非模型的属性，为该领域提供了可移植、抗污染的结果归因单元。

## Abstract
Agentic large language models are increasingly used across the genomic workflow, from variant calling to clinical interpretation, yet they are evaluated by accuracy alone, a single figure that cannot say whether a system is safe or where in the workflow a failure originates. We present ClawBench, a framework that attributes each outcome to the architectural layer that produced it across both halves of the canonical pipeline. Two design choices remove the confounds that make agentic genomics hard to evaluate: a temporally blinded truth set, in which every scored ClinVar label first became available only after the training cutoff of every model tested, and a fail-closed evidence contract that blocks evidence circular with the truth label. We score validity, safety, provenance and reproducibility, not accuracy alone, under a constraint gradient that relocates correctness from a models prior into executed, validated code.

We show three things. First, dangerous misclassification is rare and model-invariant, a controlled precondition of the executed architecture rather than a frontier, while fabricated evidence is measurable and is neutralised by execution. Second, different variant classes are rate-limited by different layers: loss-of-function variants by the deterministic combiner threshold, and rare missense by evidence formation, where evidence acquisition is asymmetric and capped and strength assignment is a recoverable layer that naive strength-licensing prompts confound. Third, for variant calling the arms separate not on whether a model can plan a pipeline, which all do, but on trust properties, pinning, provenance, auditability and reproducibility, which climb monotonically toward validated execution; and a local open-weight model reproduces the safety result yet meets the structured-output and provenance contract far less often than frontier models, a conformance gap rather than a capability or safety gap. An end-to-end join attributes failures across the whole workflow, separating a missed call from a propagated genotype error from a correctly called but misinterpreted variant.

ClawBench shows that apparently identical outcomes arise from distinct, independently measurable failure modes, and that trustworthiness in agentic genomics is a property of the pipeline architecture rather than of the model, providing a portable, contamination-resistant unit of attribution for the field.