---
title: Benchmarking large language models for ACMG/AMP variant interpretation and variant calling
title_zh: 用于ACMG/AMP变异解读和变异检测的大型语言模型基准测试
authors: "Corpas, M."
date: 2026-07-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.30.735646v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 评测大语言模型在基因组变异解读和识别中的应用
tldr: 现有ACMG/AMP变异解读仅凭准确率评估，无法定位工作流中的安全问题和失败源头。ClawBench框架通过时间盲法truth集和闭环证据合约，将每个结果归因到架构层。结果发现危险误分类罕见且不受模型影响，不同变异类受不同层限制，信任属性依赖流水线架构而非模型。该工作提供了可移植、抗污染的归因单元。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1610, \"height\": 970}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1652, \"height\": 433}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1381, \"height\": 747}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1552, \"height\": 718}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1240, \"height\": 891}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1283, \"height\": 555}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 781, \"height\": 374}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1581, \"height\": 262}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1785, \"height\": 210}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1277, \"height\": 308}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1694, \"height\": 260}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-30-735646-v1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1298, \"height\": 258}]"
motivation: 单一准确率指标无法判断系统安全性或定位工作流中的失败源头，需要分层的归因评估框架。
method: 提出ClawBench，采用时间盲法truth集和闭环证据合约，对变异解读和调用结果进行分层归因，评估有效性、安全性、可追溯性和可重复性。
result: 危险误分类罕见且模型不变；LOF变异受组合阈值限制，罕见错义受证据形成限制；信任属性随验证执行单调提升。
conclusion: 基因组AI的可信度是流水线架构的固有属性，ClawBench提供了抗污染、可移植的归因方法。
---

## 摘要
智能体大型语言模型越来越多地应用于基因组工作流程，从变异检测到临床解读，然而它们仅通过准确率来评估，这个单一指标无法说明系统是否安全，也无法指出工作流程中故障源自何处。我们提出ClawBench，一个将每个结果归因于规范流程两个半部分中产生它的架构层的框架。两个设计选择消除了使智能体基因组学难以评估的混淆因素：一个时间盲的真相集，其中每个被评分的ClinVar标签仅在所有被测试模型的训练截止日期之后才首次可用；以及一个故障关闭的证据契约，阻止了与真相标签形成循环的证据。在约束梯度下，我们评估有效性、安全性、来源和可重复性，而不仅仅是准确率，该约束将正确性从模型先验移入已执行、已验证的代码中。

我们展示了三件事。首先，危险的错误分类罕见且与模型无关，是执行架构的可控前提条件而非前沿问题，而捏造的证据是可测量的，并通过执行被中和。其次，不同的变异类别受不同层级的速率限制：功能丧失变异受确定性组合器阈值限制，罕见错义变异受证据形成限制，其中证据获取是不对称且有限制的，而强度分配是一个可恢复的层，天真的强度许可提示会混淆它。第三，对于变异检测，区别不在于模型是否能规划流程（所有模型都能），而在于信任属性、固定、来源、可审计性和可重复性，这些属性单调地向已验证的执行攀升；并且一个本地开源权重模型复制了安全结果，但在结构化输出和来源契约方面远不如前沿模型，这是一个符合性差距而非能力或安全差距。一种端到端的连接将故障归因于整个工作流程，将遗漏的呼叫与传播的基因型错误以及正确呼叫但错误解读的变异区分开。

ClawBench表明，看似相同的结果源于不同、可独立测量的故障模式，并且智能体基因组学的可信度是流程架构的属性而非模型的属性，为该领域提供了一个可移植、抗污染的归因单元。

## Abstract
Agentic large language models are increasingly used across the genomic workflow, from variant calling to clinical interpretation, yet they are evaluated by accuracy alone, a single figure that cannot say whether a system is safe or where in the workflow a failure originates. We present ClawBench, a framework that attributes each outcome to the architectural layer that produced it across both halves of the canonical pipeline. Two design choices remove the confounds that make agentic genomics hard to evaluate: a temporally blinded truth set, in which every scored ClinVar label first became available only after the training cutoff of every model tested, and a fail-closed evidence contract that blocks evidence circular with the truth label. We score validity, safety, provenance and reproducibility, not accuracy alone, under a constraint gradient that relocates correctness from a models prior into executed, validated code.

We show three things. First, dangerous misclassification is rare and model-invariant, a controlled precondition of the executed architecture rather than a frontier, while fabricated evidence is measurable and is neutralised by execution. Second, different variant classes are rate-limited by different layers: loss-of-function variants by the deterministic combiner threshold, and rare missense by evidence formation, where evidence acquisition is asymmetric and capped and strength assignment is a recoverable layer that naive strength-licensing prompts confound. Third, for variant calling the arms separate not on whether a model can plan a pipeline, which all do, but on trust properties, pinning, provenance, auditability and reproducibility, which climb monotonically toward validated execution; and a local open-weight model reproduces the safety result yet meets the structured-output and provenance contract far less often than frontier models, a conformance gap rather than a capability or safety gap. An end-to-end join attributes failures across the whole workflow, separating a missed call from a propagated genotype error from a correctly called but misinterpreted variant.

ClawBench shows that apparently identical outcomes arise from distinct, independently measurable failure modes, and that trustworthiness in agentic genomics is a property of the pipeline architecture rather than of the model, providing a portable, contamination-resistant unit of attribution for the field.