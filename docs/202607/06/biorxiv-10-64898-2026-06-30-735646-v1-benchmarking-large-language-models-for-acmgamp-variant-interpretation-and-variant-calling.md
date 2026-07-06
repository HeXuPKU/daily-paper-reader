---
title: Benchmarking large language models for ACMG/AMP variant interpretation and variant calling
title_zh: 大规模语言模型在ACMG/AMP变异解读与变异检出中的基准测试
authors: "Corpas, M."
date: 2026-07-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.30.735646v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 对大语言模型进行ACMG/AMP变异解读和变异调用的基准测试
tldr: 当前大语言模型在基因组工作流中的应用仅用准确性评估，无法揭示安全性和故障来源。ClawBench框架通过时间盲法真值集和故障封闭证据合约，从有效性、安全性、来源和可重复性多维度评估模型。结果显示危险误分类罕见且模型不变，证据伪造可被执行消除；不同变异类型受不同层限制，变异调用差异源于信任属性而非能力。该框架为基因组AI系统的安全评估提供了系统化归因方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有基因组AI评估仅关注准确率，无法识别故障源头和安全性问题，需要可归因的多维度评估框架。
method: 提出ClawBench框架，包含时间盲法真值集和故障封闭证据合约，从有效性、安全性、来源和可重复性四个维度评估模型。
result: 危险误分类罕见且模型不变；不同变异类型受不同层限制；变异调用差异源于信任属性，本地模型在结构化输出上存在差距。
conclusion: ClawBench框架能有效归因基因组工作流中各层故障，推动安全评估从单一准确率转向多维度可验证体系。
---

## 摘要
智能体式大规模语言模型正越来越多地用于基因组工作流程，从变异检测到临床解读，但评估仅依赖准确性这一单一指标，无法判断系统是否安全，也无法确定故障源自工作流程的哪个环节。我们提出ClawBench框架，将每个结果归因于规范流程两半中产生它的架构层。两个设计选择消除了使智能体基因组学难以评估的混淆因素：时间盲法真实集（每个被评分的ClinVar标签在测试的所有模型训练截止点之后才首次可用）以及故障闭锁证据合约（阻止与真实标签形成循环的证据）。我们评估有效性、安全性、来源和可重复性，而非仅准确性，并在约束梯度下将正确性从模型先验转移到可执行、已验证的代码中。我们证明了三件事。首先，危险错误分类罕见且与模型无关，是执行架构的可控前提而非前沿，而捏造证据可测量且可通过执行消除。其次，不同变异类别受不同层限制：功能丧失变异受确定性组合器阈值限制，罕见错义变异受证据形成限制，其中证据获取不对称且有上限，强度分配是可恢复层，而朴素强度授权提示会造成混淆。第三，对于变异检出，各方案的分歧不在于模型是否能规划流程（所有模型都能），而在于信任属性、固定性、来源、可审计性和可重复性，这些属性单调上升向已验证执行；本地开源模型重现了安全性结果，但远不如前沿模型满足结构化输出和来源合约，这是一种符合性差距而非能力或安全性差距。一个端到端连接将整个工作流程中的故障归因，区分了遗漏检出、传播的基因型错误以及正确检出但错误解读的变异。

## Abstract
Agentic large language models are increasingly used across the genomic workflow, from variant calling to clinical interpretation, yet they are evaluated by accuracy alone, a single figure that cannot say whether a system is safe or where in the workflow a failure originates. We present ClawBench, a framework that attributes each outcome to the architectural layer that produced it across both halves of the canonical pipeline. Two design choices remove the confounds that make agentic genomics hard to evaluate: a temporally blinded truth set, in which every scored ClinVar label first became available only after the training cutoff of every model tested, and a fail-closed evidence contract that blocks evidence circular with the truth label. We score validity, safety, provenance and reproducibility, not accuracy alone, under a constraint gradient that relocates correctness from a model's prior into executed, validated code. We show three things. First, dangerous misclassification is rare and model-invariant, a controlled precondition of the executed architecture rather than a frontier, while fabricated evidence is measurable and is neutralised by execution. Second, different variant classes are rate-limited by different layers: loss-of-function variants by the deterministic combiner threshold, and rare missense by evidence formation, where evidence acquisition is asymmetric and capped and strength assignment is a recoverable layer that naive strength-licensing prompts confound. Third, for variant calling the arms separate not on whether a model can plan a pipeline, which all do, but on trust properties, pinning, provenance, auditability and reproducibility, which climb monotonically toward validated execution; and a local open-weight model reproduces the safety result yet meets the structured-output and provenance contract far less often than frontier models, a conformance gap rather than a capability or safety gap. An end-to-end join attributes failures across the whole workflow, separating a missed call from a propagated genotype error from a correctly called but misinterpreted variant.