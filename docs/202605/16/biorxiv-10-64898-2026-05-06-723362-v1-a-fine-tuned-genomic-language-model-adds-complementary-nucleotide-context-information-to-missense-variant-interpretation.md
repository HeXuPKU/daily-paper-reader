---
title: A fine-tuned genomic language model adds complementary nucleotide-context information to missense variant interpretation
title_zh: 微调的基因组语言模型为错义变异解读增加了互补的核苷酸上下文信息
authors: "Su, Y., Lin, Y.-J."
date: 2026-05-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.06.723362v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 用于变异解读的基因组语言模型
tldr: 本研究系统地将基因组语言模型应用于ClinVar错义变异致病性预测，开发了GLM-Missense模型。研究发现，该模型能提供与现有蛋白质水平预测因子互补的核苷酸上下文信息，且在集成模型MetaMissense中表现出极高的信息贡献度。结果表明，微调后的基因组语言模型在捕捉剪接相关背景及优化变异解释方面具有显著优势，有效提升了临床基因组学的预测精度。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在明确基因组语言模型是否能为错义变异致病性预测提供除蛋白质水平和注释先验之外的非冗余核苷酸上下文信号。
method: 通过对比不同架构和微调策略开发了GLM-Missense，并将其与AlphaMissense等多种预测因子集成构建了MetaMissense模型。
result: GLM-Missense展现出独特的预测信号，且集成模型MetaMissense在各项性能指标上均优于现有的单一及集成预测方法。
conclusion: 微调后的基因组语言模型通过提供互补的核苷酸上下文信息，显著增强了对错义变异致病性的解释和预测能力。
---

## 摘要
错义变异解读仍然是临床基因组学中的一个核心挑战。错义致病性预测因子已取得强劲性能，但许多预测因子强调蛋白质水平的后果或重叠的注释先验。基因组语言模型是否能为错义解读增加非冗余的核苷酸上下文信号仍不清楚。在本研究中，我们跨骨干架构、表示策略、分类器头和适配方案，系统地将基因组语言模型应用于 ClinVar 错义致病性预测。在我们的分析中，变异位置嵌入（variant-position embeddings）的表现始终优于池化序列表示，多物种预训练提供了最强的骨干级优势，且低秩自适应（low-rank adaptation）的泛化效果优于全量微调。由此产生的微调模型 GLM-Missense 的表现显著优于同一预训练模型的零样本评分。为了测试 GLM-Missense 是否贡献了现有方法之外的信息，我们构建了 MetaMissense，这是一个结合了 GLM-Missense 与 AlphaMissense、ESM1b、REVEL、CADD、SIFT 和 PolyPhen-2 的 XGBoost 集成模型。GLM-Missense 与其他预测因子的一致性最低，在控制其他预测因子后仍保留了与致病性最强的偏相关性，并被评为 MetaMissense 中信息量最大的非集成输入。MetaMissense 在交叉验证和留出测试中均取得了最佳性能。对被 GLM-Missense 正确分类但被几种现有预测因子错误分类的变异进行的分析表明了两种模式：首先，GLM-Missense 的部分信号可能反映了与剪接相关的外显子上下文；其次，在其他预测因子可能过度权重等位基因频率、基因级约束或氨基酸变化严重程度的情况下，GLM-Missense 似乎增加了价值。然而，这些特征仅解释了 GLM-Missense 正确子集与背景之间约 10% 的差异。总之，我们的结果表明，微调的基因组语言模型为错义变异解读贡献了互补的核苷酸上下文信息。

## Abstract
Missense variant interpretation remains a central challenge in clinical genomics. Missense pathogenicity predictors achieve strong performance, but many emphasize protein-level consequences or overlapping annotation priors. Whether genomic language models add non-redundant nucleotide-context signal to missense interpretation remains unclear. Here, we systematically adapted genomic language models to ClinVar missense pathogenicity prediction across back-bone architectures, representation strategies, classifier heads, and adaptation regimes. In our analysis, variant-position embeddings consistently outperformed pooled sequence representations, multi-species pretraining provided the strongest backbone-level advantage, and low-rank adaptation generalized better than full fine-tuning. The resulting fine-tuned model, GLM-Missense, substantially outperformed zero-shot scoring from the same pretrained model.

To test whether GLM-Missense contributes information beyond existing methods, we built MetaMissense, an XGBoost ensemble combining GLM-Missense with AlphaMissense, ESM1b, REVEL, CADD, SIFT, and PolyPhen-2. GLM-Missense showed the lowest concordance with other predictors, retained the strongest partial association with pathogenicity after controlling for the other predictors, and ranked as the most informative non-ensemble input to MetaMissense. MetaMissense achieved the best performance in both cross-validation and held-out testing. Analyses of variants correctly classified by GLM-Missense but misclassified by several established predictors suggested two patterns. First, part of the GLM-Missense signal may reflect splice-relevant exonic context. Second, GLM-Missense appears to add value in settings where other predictors may overweight allele frequency, gene-level constraint, or amino-acid-change severity. However, these features explained only about 10% of the distinction between the GLM-Missense-correct subset from the background. Together, our results demonstrate that fine-tuned genomic language models contribute complementary nucleotide-context information to missense variant interpretation.