---
title: "CausalKnowledgeTrace: A Novel Computational Framework for Automated Literature-Based Causal Graph Construction and Evidence-Based Variable Selection in Biomedical Research"
title_zh: CausalKnowledgeTrace：一种用于生物医学研究中自动化文献驱动因果图构建与循证变量选择的新型计算框架
authors: "Upadhayaya, R., Pradhan, M. M., Metzger, V. T., Malec, S. A."
date: 2026-05-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.07.723601v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 生物医学研究中的因果图构建和变量选择
tldr: 针对生物医学观察性研究中因变量选择困难且易产生偏差的问题，本文开发了CausalKnowledgeTrace计算框架。该框架利用SemMedDB的大规模结构化因果知识，通过六阶段流水线自动构建因果图，并识别混杂因素、中介因子及对撞因子。研究证明该系统能高效处理复杂网络并提供证据溯源，为流行病学和临床研究提供了科学、可扩展的因果建模支持。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决生物医学研究中因手动筛选变量效率低且易忽略文献中已记录的复杂偏倚结构而导致的因果推断偏差。
method: 提出一种集成SemMedDB知识库的自动化框架，通过图论算法进行周期检测、节点过滤及因果偏倚识别。
result: 成功应用于高血压与阿尔茨海默症关联分析，在秒级时间内识别出炎症、糖尿病等关键混杂因素及复杂的M型偏倚结构。
conclusion: CausalKnowledgeTrace实现了从文献到因果模型的自动化转化，是生物医学因果推断领域的一项重要计算进展。
---

## 摘要
背景：从观察性生物医学数据中进行因果推断的变量选择具有挑战性，因为忽视混杂因素（confounders）或对对撞因子（colliders）进行条件化会导致估计偏差。虽然生物医学文献中存在海量的因果知识，但大规模手动提取这些信息以进行规范的变量选择是不切实际的。

方法：我们开发了 CausalKnowledgeTrace，这是一个基于 Python 和 Django Web 界面的计算框架，系统地利用语义 MEDLINE 数据库（SemMedDB）中的结构化因果知识，为因果研究中的变量选择提供信息。该系统使用 NetworkX 进行图操作，实现了一个六阶段分析流水线，包括图解析、基础分析、全面环路检测、系统性通用节点移除、移除后分析以及带有偏差检测的形式化因果推断。

结果：对高血压与阿尔茨海默症关系在三个度数邻域（1-3 度）内的分析展示了因果复杂性的系统性扩展：361-866 个变量，429-1,442 个关系，图密度为 0.0033-0.0019。分析揭示了复杂的环路结构，各度数水平包含 54-606 个基准环路。三个度数的处理时间均在 0.3-1.0 秒之间，证明了处理复杂生物医学网络的高计算效率。在所有度数中识别出的关键混杂因素包括炎症、糖尿病、胰岛素抵抗、肥胖和缺血。在三度图中，该流水线从因果图中结构化地识别出 39 个混杂因素、11 个中介因子（mediators）和 3 个对撞因子。在识别出的关键混杂因素和中介因子中——包括肥胖、氧化应激、缺血和血管疾病——均在已有的流行病学和病理生理学文献中找到了强有力的支持证据。

结论：CausalKnowledgeTrace 提供了一种可扩展的、循证的因果图构建方法，能够系统地识别传统方法经常遗漏的混杂因素和偏差结构。Python-Django 架构使其既能进行独立分析，也能集成到更大的计算工作流中，代表了生物医学研究因果推断计算支持方面的重大进展。

重要性声明：
问题：从观察性生物医学数据集中选择合适的混杂因素和变量进行因果推断具有挑战性，且常因专业知识有限或人工审查而产生偏差。
已知现状：现有方法依赖于领域专家、统计变量筛选或人工构建因果图，但这些方法往往忽视了文献记载的混杂因素和复杂的偏差。
本文贡献：本文介绍了一个自动化的、基于文献的框架，用于合成和验证因果图，识别关键变量和复杂的偏差结构（如 M-偏差和蝴蝶偏差），并具有完整的证据可追溯性。
受益群体：寻求为观察性研究提供可靠且透明的因果建模的流行病学家、生物医学研究人员、信息学家和临床研究人员。

## Abstract
BackgroundVariable selection for causal inference from observational biomedical data is challenging, as overlooking confounders or conditioning on colliders leads to biased estimates. While vast causal knowledge exists in biomedical literature, manually extracting this information for principled variable selection is impractical at scale.

MethodsWe developed CausalKnowledgeTrace, a Python-based computational framework with Django web interface that systematically leverages structured causal knowledge from the Semantic MEDLINE Database (SemMedDB) to inform variable selection in causal studies. The system implements a six-stage analysis pipeline using NetworkX for graph operations, including graph parsing, basic analysis, comprehensive cycle detection, systematic generic node removal, post-removal analysis, and formal causal inference with bias detection.

ResultsAnalysis of the hypertension-Alzheimers relationship across three degree neighborhoods (1-3) demonstrated systematic scaling of causal complexity: 361-866 variables, 429-1,442 relationships, with graph densities of 0.0033-0.0019. The analysis revealed complex cyclic structures with 54-606 baseline cycles across degree levels. Processing times ranged from 0.3-1.0 seconds for all three degrees, demonstrating computational efficiency for complex biomedical networks. Key confounders identified across all degrees included inflammation, diabetes, insulin resistance, obesity, and ischemia. In the third degree of graph, the pipeline structurally identified 39 confounders, 11 mediators, and 3 colliders from the causal graph. Among the key identified confounders and mediators--including obesity, oxidative stress, ischemia, and vascular diseases--all were found to have strong supporting evidence in established epidemiological and pathophysiological literature.

ConclusionsCausalKnowledgeTrace provides a scalable, evidence-based approach to causal graph construction that systematically identifies confounders and bias structures often missed by conventional approaches. The Python-Django architecture enables both standalone analysis and integration into larger computational workflows, representing a significant advance in computational support for causal inference in biomedical research.

Statement of SignificanceO_ST_ABSProblem or IssueC_ST_ABSSelecting proper confounders and variables for causal inference from observational biomedical datasets is challenging and often biased by limited expertise or manual review.

What is Already KnownExisting approaches rely on domain experts, statistical variable screening, or manual construction of causal graphs, but these often overlook literature-documented confounders and complex biases.

What this Paper AddsThis paper introduces an automated, literature-based framework for synthesizing and validating causal graphs, identifying critical variables and complex bias structures, such as M-bias and butterfly bias, with full evidentiary traceability.

Who would benefit from the new knowledge in this paper?Epidemiologists, biomedical researchers, informaticians, and clinical investigators seeking reliable and transparent causal modeling for observational studies.