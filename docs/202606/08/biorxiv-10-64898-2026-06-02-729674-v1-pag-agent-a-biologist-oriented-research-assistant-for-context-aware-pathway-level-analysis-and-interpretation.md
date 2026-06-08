---
title: "PAG-Agent: a biologist-oriented research assistant for context-aware pathway-level analysis and interpretation"
title_zh: "PAG-Agent: 面向生物学家的上下文感知通路级分析与解读研究助手"
authors: "Nguyen, Q.-H., Zhang, Z., Le, D.-H., Chen, J. Y., Ku, W.-S., Chen, H., Yue, Z."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.729674v1.full.pdf"
tags: ["query:med-ai"]
score: 7.0
evidence: 面向生物学家的AI研究助手，集成大语言模型推理的上下文感知通路分析
tldr: 现有通路分析工具常孤立分析基因集，难以结合实验上下文。为此开发PAG-Agent，一款面向生物学家的虚拟研究助手，整合统计分析与上下文感知解释。在阿尔茨海默病转录组数据集中，PAG-Agent一致识别出神经退行相关通路，并在引用检索任务中超越多个大语言模型。该工具降低了通路分析的技术门槛，助力研究者从数据到生物学推断。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统通路分析工具孤立分析基因集，难以结合实验条件与目标，导致结果生物学解释困难。
method: 构建PAG-Agent，整合统计分析、上下文感知解释、文献检索与写作支持，支持点击与聊天交互。
result: 在阿尔茨海默病数据集中一致识别关键通路，引用检索基准测试优于六个LLM。
conclusion: 降低技术门槛，助力研究者从转录组数据获得生物学洞见与科学沟通。
---

## 摘要
通路分析是将基因级组学结果转化为生物学机制的关键步骤，然而现有工作流通常只给研究人员提供一长串统计显著的通路列表，这些列表难以解读、验证，也难与实验背景关联。我们开发了PAG-Agent，这是一个面向生物学家的虚拟研究助手，它将通路级统计分析、上下文感知的生物学解读、基于文献的推理以及科学写作支持集成在一个统一的工作流中。PAG-Agent支持批量及单细胞转录组数据，用户可通过点击和聊天交互进行数据预处理、差异表达分析、通路分析、通路级共识分析以及通路级荟萃分析。与大多数孤立分析基因集的传统通路分析工具不同，PAG-Agent会纳入实验条件和研究目标，以优先识别生物学相关通路并生成可解读的假设。该系统还提供基因与通路注释、文献引用检索、可视化以及写作润色功能。在利用三个转录组数据集开展的阿尔茨海默病案例研究中，PAG-Agent在多种分析方法和数据集上均一致识别出神经退行性相关通路。在引用检索基准测试中，PAG-Agent在五种常见文献支持场景下优于六种竞争性大语言模型，展现出更强的提供上下文相关且有效参考文献的能力。总体而言，PAG-Agent降低了通路级分析的技术门槛，帮助研究人员从转录组数据迈向基于生物学的解读、假设生成和科学交流。

## Abstract
Pathway analysis is a critical step for translating gene-level omics results into biological mechanisms, yet existing workflows often leave researchers with long lists of statistically significant pathways that are difficult to interpret, validate, and connect to experimental context. We developed PAG-Agent, a biologist-oriented virtual research assistant that integrates pathway-level statistical analysis, context-aware biological interpretation, literature-supported reasoning, and scientific writing support within a unified workflow. PAG-Agent supports bulk and single-cell transcriptomic data and enables users to perform data preprocessing, differential expression analysis, pathway analysis, pathway-level consensus analysis, and pathway-level meta-analysis through click-based and chat-based interactions. Unlike conventional pathway-analysis tools that analyze gene sets largely in isolation, PAG-Agent incorporates experimental conditions and research objectives to prioritize biologically relevant pathways and generate interpretable hypotheses. The system also provides gene and pathway annotation, citation retrieval, visualization, and writing refinement functions. In Alzheimer's disease case studies using three transcriptomic datasets, PAG-Agent consistently identified neurodegeneration-related pathways across multiple analysis methods and datasets. In citation-retrieval benchmarking, PAG-Agent outperformed six competing LLMs across five common literature-support scenarios, demonstrating improved ability to provide contextually relevant and valid references. Overall, PAG-Agent lowers technical barriers for pathway-level analysis and helps researchers move from transcriptomic data to biologically grounded interpretation, hypothesis generation, and scientific communication.