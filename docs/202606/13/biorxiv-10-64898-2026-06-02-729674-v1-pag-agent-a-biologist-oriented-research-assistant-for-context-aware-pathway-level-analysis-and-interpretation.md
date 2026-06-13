---
title: "PAG-Agent: a biologist-oriented research assistant for context-aware pathway-level analysis and interpretation"
title_zh: PAG-Agent：面向生物学家的上下文感知通路级分析与解读研究助手
authors: "Nguyen, Q.-H., Zhang, Z., Le, D.-H., Chen, J. Y., Ku, W.-S., Chen, H., Yue, Z."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.729674v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 基于大语言模型的生物医学通路分析智能体
tldr: 针对现有通路分析结果孤立且难以解释的问题，开发了面向生物学家的PAG-Agent虚拟研究助手，集成统计分析与上下文感知的解释能力。系统通过点击和聊天交互支持数据预处理、差异表达、通路分析及共识/元分析，并融合实验条件优先排序通路。在阿尔茨海默病案例中一致识别神经退行通路，引用检索性能优于多个LLM。整体降低了通路分析技术门槛，助力从数据到生物机制解释与科学交流。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有工具孤立分析基因集，结果列表难以关联实验背景，缺乏上下文感知解释。
method: 集成统计、上下文解释、文献推理与写作辅助，支持bulk/单细胞数据，通过点击和聊天交互完成全流程。
result: 阿尔茨海默病案例中稳定识别神经退行通路，引用检索基准测试优于6个LLM。
conclusion: PAG-Agent降低技术门槛，促进转录组数据向生物机制解释、假设生成与科学交流的转化。
---

## 摘要
通路分析是将基因层面组学结果转化为生物学机制的关键步骤，然而现有工作流程往往给研究人员留下冗长的统计显著通路列表，这些通路难以解读、验证，并与实验背景关联。我们开发了PAG-Agent，这是一款面向生物学家的虚拟研究助手，它在统一工作流程中集成了通路级统计分析、上下文感知的生物学解读、文献支持的推理以及科学写作支持。PAG-Agent支持批量与单细胞转录组数据，用户可通过点击和聊天交互执行数据预处理、差异表达分析、通路分析、通路级一致性分析和通路级荟萃分析。与大多孤立分析基因集的传统通路分析工具不同，PAG-Agent结合实验条件与研究目标，优先考虑生物学相关的通路，并生成可解读的假说。该系统还提供基因与通路注释、引文检索、可视化和写作润色功能。在使用三个转录组数据集的阿尔茨海默病案例研究中，PAG-Agent在多种分析方法和数据集上一致地识别出神经退行性相关通路。在引文检索基准测试中，PAG-Agent在五个常见文献支持场景下优于六个竞争的大语言模型，展现了提供上下文相关且有效参考文献的改进能力。总体而言，PAG-Agent降低了通路级分析的技术门槛，帮助研究人员从转录组数据走向基于生物学的解读、假说生成和科学交流。

## Abstract
Pathway analysis is a critical step for translating gene-level omics results into biological mechanisms, yet existing workflows often leave researchers with long lists of statistically significant pathways that are difficult to interpret, validate, and connect to experimental context. We developed PAG-Agent, a biologist-oriented virtual research assistant that integrates pathway-level statistical analysis, context-aware biological interpretation, literature-supported reasoning, and scientific writing support within a unified workflow. PAG-Agent supports bulk and single-cell transcriptomic data and enables users to perform data preprocessing, differential expression analysis, pathway analysis, pathway-level consensus analysis, and pathway-level meta-analysis through click-based and chat-based interactions. Unlike conventional pathway-analysis tools that analyze gene sets largely in isolation, PAG-Agent incorporates experimental conditions and research objectives to prioritize biologically relevant pathways and generate interpretable hypotheses. The system also provides gene and pathway annotation, citation retrieval, visualization, and writing refinement functions. In Alzheimers disease case studies using three transcriptomic datasets, PAG-Agent consistently identified neurodegeneration-related pathways across multiple analysis methods and datasets. In citation-retrieval benchmarking, PAG-Agent outperformed six competing LLMs across five common literature-support scenarios, demonstrating improved ability to provide contextually relevant and valid references. Overall, PAG-Agent lowers technical barriers for pathway-level analysis and helps researchers move from transcriptomic data to biologically grounded interpretation, hypothesis generation, and scientific communication.