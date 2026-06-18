---
title: "Variant annotation across homologous proteins (Paralogue Annotation) identifies disease-causing missense variants with high precision, and is widely applicable across protein families"
title_zh: 同源蛋白间的变异注释（旁系同源注释）能够高精度识别致病变异，并广泛适用于多种蛋白质家族
authors: "Li, N., Zhang, X., Mazaika, E., Theotokis, P., Jang, M., Ahmad, M., Powell, G., Heyne, H. O., Lal, D., Barton, P. J., Walsh, R., Whiffin, N., Ware, J. S."
date: 2026-06-13
pdf: "https://www.biorxiv.org/content/10.1101/2023.08.07.552236v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 利用同源蛋白进行变体功能注释以整合GWAS
tldr: 准确区分致病性和良性错义变异是临床遗传学的难题，现有工具精度不足。本文提出Paralogue Annotation框架，利用同源蛋白中已表征变异的信息来预测致病性。在ClinVar数据集上，该方法精度达0.95，严格参数下可达0.99，但敏感性较低；通过跨同源结构域注释可提高敏感性。在心律失常和神经发育障碍的病例-对照研究中，被该方法预测为致病的稀有变异与疾病显著关联。该方法为临床变异解读提供了高精度的补充证据，且随数据积累敏感性将进一步提升。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有预测工具精度低，需要高精度的致病变异识别方法以辅助临床解读。
method: 利用同源蛋白（旁系同源物）中已表征的错义变异信息，通过序列比对和保守性评估预测目标基因变异的致病性。
result: 在ClinVar数据集上，Paralogue Annotation精度达0.95（4328真阳性/245假阳性），严格参数下精度升至0.99，敏感性低于常用工具；跨结构域注释可提升敏感性。
conclusion: 该方法以高精度预测致病性错义变异，作为互补证据可提升临床变异解读的可靠性，且灵敏度随数据库增长而改善。
---

## 摘要
背景：区分致病变异与罕见但良性的变异仍是临床遗传学中的关键挑战，尤其是对于那些此前未被观察和表征的人类变异。体外和体内功能表征通常耗费资源，且模型系统可能无法准确预测对人类疾病的影响。许多计算机工具已被开发用于预测哪些变异会导致疾病，但通常缺乏精确性。本研究展示了一种名为“旁系同源注释”的框架的适用性，该框架利用同源蛋白中已表征变异的信息来预测目标基因中的变异是否可能致病。

方法：我们通过三种正交方法评估了旁系同源注释的性能：（1）使用来自ClinVar的47,016个错义变异，涵盖3,524个基因（代表多种蛋白质类别），与已建立的计算机变异预测工具进行比较，计算精确度和敏感性；（2）针对大规模变异效应功能测定进行评估；（3）比较来自遗传性心律失常综合征以及神经发育障碍伴癫痫的病例对照关联检验的比值比，按旁系同源注释对变异进行分层。

结果：旁系同源注释正确注释了4,328个ClinVar致病变异，假阳性245个，精确度为0.95。使用更严格的注释参数（要求注释的直系同源物之间氨基酸具有更高的保守性）时，精确度提高到0.99，但敏感性有所降低。与已建立的工具相比，旁系同源注释在识别致病变异方面具有更高的精确度，尽管在不同测试集中的敏感性较低。通过在 homologous 蛋白质结构域之间转移注释（而非全长蛋白质旁系同源物）来扩展该技术，可提高敏感性。在通过病例对照队列方法测试的8个基因中，有6个基因中，被旁系同源注释预测为致病的罕见变异比未分层的罕见变异具有更强的疾病关联性（比值比增加）。

结论：我们证明旁系同源注释在预测致病错义变异方面具有高精确度，为临床变异解读提供了有用的证据，并对其他正在使用的方法形成补充。随着ClinVar等参考数据集中已表征变异的数量增加，旁系同源注释的敏感性和适用性将进一步提高。

## Abstract
BackgroundDistinguishing pathogenic variants from those that are rare but benign remains a key challenge in clinical genetics, especially for variants not previously observed and characterised in humans. In vitro and in vivo functional characterisation are typically resource intensive, and model systems may not accurately predict influence on human disease. Many in silico tools have been developed to predict which variants are disease-causing, but typically lack precision. Here we demonstrate the applicability of a framework, called Paralogue Annotation, that draws on information from previously-characterised variants in homologous proteins to predict whether variants in a gene of interest are likely disease causing.

MethodsWe assessed the performance of Paralogue Annotation through three orthogonal approaches: (1) comparison to established in silico variant prediction tools using 47,016 missense variants from ClinVar across 3,524 genes representing a broad range of diverse protein classes, by calculating precision and sensitivity; (2) evaluation against large-scale functional assays of variant effect; and (3) comparing odd ratios calculated from case-control association tests for inherited cardiac arrhythmia syndromes, and neurodevelopmental disorders with epilepsy, stratifying variants by Paralogue Annotation.

ResultsParalogue Annotation correctly annotates 4,328 ClinVar pathogenic variants, with 245 false positives, yielding a precision of 0.95. This increases to 0.99 with more stringent annotation parameters (requiring greater conservation of amino acids between annotated orthologues) at the expense of sensitivity. Compared to established tools, Paralogue Annotation has higher precision for the identification of pathogenic variants, albeit with lower sensitivity across diverse test sets. Extending the technique by transferring annotations between homologous protein domains, rather than full-length protein paralogues, increases sensitivity. Rare variants predicted pathogenic by Paralogue Annotation were more strongly disease-associated (increased odds ratio) than unstratified rare variants for six out of eight genes tested with case-control cohort approaches.

ConclusionsWe demonstrate that Paralogue Annotation has high precision for predicting pathogenic missense variants, providing a useful line of evidence for clinical variant interpretation that is complementary to other approaches in use. As the number of characterised variants increases in reference datasets such as ClinVar, Paralogue Annotation will further increase in sensitivity and applicability.