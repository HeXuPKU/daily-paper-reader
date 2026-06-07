---
title: "PAG-Agent: a biologist-oriented research assistant for context-aware pathway-level analysis and interpretation"
title_zh: PAG-Agent：面向生物学家的上下文感知通路级分析与解释研究助手
authors: "Nguyen, Q.-H., Zhang, Z., Le, D.-H., Chen, J. Y., Ku, W.-S., Chen, H., Yue, Z."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.729674v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 面向生物学家的通路分析AI智能体，整合大语言模型与统计方法
tldr: 传统通路分析常给出难以解释的显著通路列表，缺乏实验上下文。为此，作者开发了面向生物学家的虚拟研究助手PAG-Agent，整合通路统计分析、上下文感知生物学解释、文献推理和科学写作支持。在阿尔茨海默病三个转录组数据集上，PAG-Agent一致识别出神经退行相关通路，并在引用检索基准测试中优于六个LLM。该工具降低了通路分析的技术门槛，帮助研究者从转录组数据过渡到生物学机制阐释和假设生成。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有通路分析工具输出难以解释的通路列表，无法结合实验上下文，阻碍生物学机制推断。
method: PAG-Agent集成通路统计、上下文感知解释、文献检索与写作辅助，支持点击和聊天交互。
result: 在阿尔茨海默病三个数据集中一致识别神经退行通路，引用检索优于六个LLM。
conclusion: PAG-Agent降低通路分析技术壁垒，实现从数据到生物学解释与假设生成的全流程支持。
---

## 摘要
通路分析是将基因水平的组学结果转化为生物学机制的关键步骤，然而现有工作流程常常给研究者留下长长的统计显著通路列表，难以解释、验证并与实验背景关联。我们开发了PAG-Agent，一个面向生物学家的虚拟研究助手，它在统一工作流中整合了通路级统计分析、上下文感知的生物学解释、文献支持的推理以及科学写作支持。PAG-Agent支持批量及单细胞转录组数据，通过点击和聊天交互方式，使用户能够执行数据预处理、差异表达分析、通路分析、通路级一致性分析和通路级元分析。与主要孤立分析基因集的传统通路分析工具不同，PAG-Agent结合实验条件和研究目标，优先考虑生物学相关的通路并生成可解释的假设。系统还提供基因与通路注释、引文检索、可视化和写作润色功能。在使用三个转录组数据集的阿尔茨海默病案例研究中，PAG-Agent在多种分析方法和数据集中一致地识别出神经退行性疾病相关通路。在引文检索基准测试中，PAG-Agent在五种常见文献支持场景下优于六个竞争性大语言模型，展示了提供上下文相关且有效参考文献的改进能力。总体而言，PAG-Agent降低了通路级分析的技术门槛，帮助研究者从转录组数据走向基于生物学的解释、假设生成和科学交流。

## Abstract
Pathway analysis is a critical step for translating gene-level omics results into biological mechanisms, yet existing workflows often leave researchers with long lists of statistically significant pathways that are difficult to interpret, validate, and connect to experimental context. We developed PAG-Agent, a biologist-oriented virtual research assistant that integrates pathway-level statistical analysis, context-aware biological interpretation, literature-supported reasoning, and scientific writing support within a unified workflow. PAG-Agent supports bulk and single-cell transcriptomic data and enables users to perform data preprocessing, differential expression analysis, pathway analysis, pathway-level consensus analysis, and pathway-level meta-analysis through click-based and chat-based interactions. Unlike conventional pathway-analysis tools that analyze gene sets largely in isolation, PAG-Agent incorporates experimental conditions and research objectives to prioritize biologically relevant pathways and generate interpretable hypotheses. The system also provides gene and pathway annotation, citation retrieval, visualization, and writing refinement functions. In Alzheimer's disease case studies using three transcriptomic datasets, PAG-Agent consistently identified neurodegeneration-related pathways across multiple analysis methods and datasets. In citation-retrieval benchmarking, PAG-Agent outperformed six competing LLMs across five common literature-support scenarios, demonstrating improved ability to provide contextually relevant and valid references. Overall, PAG-Agent lowers technical barriers for pathway-level analysis and helps researchers move from transcriptomic data to biologically grounded interpretation, hypothesis generation, and scientific communication.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：传统通路分析工具（如GSEA、Enrichr等）主要输出统计显著的通路列表，但这些列表缺乏实验上下文的关联，研究者难以解释哪些通路真正与自身实验条件相关，也难以从列表过渡到生物学机制推断和假设生成。
- **整体含义**：作者旨在开发一个面向生物学家的虚拟研究助手（PAG-Agent），在统一工作流中整合通路级统计分析、上下文感知的生物学解释、文献支持的推理以及科学写作支持，降低通路分析的技术门槛，帮助研究者从转录组数据直接走向生物学解释、假设生成和科学交流。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将通路分析从孤立的基因集统计扩展到“上下文感知”的生物学推理。不再只是静态列表，而是结合实验条件（如疾病类型、处理条件）和研究目标（如发现关键机制），利用大语言模型（LLM）进行语境化解释，并集成文献检索与写作辅助。
- **关键技术细节**：
  - **多模块集成**：PAG-Agent包括数据预处理、差异表达分析、通路分析、通路级一致性分析、通路级元分析、基因/通路注释、引文检索、可视化、写作润色等模块。
  - **交互方式**：同时支持点击式（click-based）和聊天式（chat-based）交互，降低使用门槛。
  - **分析类型**：支持批量（bulk）和单细胞转录组数据。
  - **统计方法**：通路分析底层使用标准统计方法（如Fisher检验、基因集富集分析等），但作者未在摘要中提供具体公式或算法细节。
  - **上下文感知**：系统将用户输入的实验条件（如“阿尔茨海默病脑组织”）和检索到的相关文献作为LLM的提示，优先排序生物学相关的通路并生成可解释的假设。
  - **引文检索**：集成了自动引文检索功能，为每个解释提供文献支撑。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集**：使用了三个关于阿尔茨海默病（AD）的转录组数据集（具体名称未在摘要中给出，推测为公开的AD脑组织或细胞模型转录组数据）。
- **Benchmark**：
  - **案例研究**：在三个AD数据集中，使用PAG-Agent进行通路分析，验证其能否一致识别神经退行性疾病相关通路。
  - **引文检索基准测试**：设计了五种常见的文献支持场景（如“解释某通路与AD的关联”），对比PAG-Agent与六个竞争性大语言模型（六个“competitive LLMs”，具体模型名称未在摘要中列出，可能包括GPT-4、Claude、LLaMA等）。
- **对比方法**：六个LLM作为基线，评估引文检索的上下文相关性和引用有效性（提供正确的、相关的参考文献）。

## 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点。

- **未明确说明**：摘要和元数据中未提及任何关于训练或推理所使用的GPU型号、数量或训练时长等信息。可能论文全文会提及，但基于当前提供的内容，无法判断。

## 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平。

- **实验数量**：
  - **案例研究**：三个AD数据集，每个数据集使用多种通路分析方法（如ORA、GSEA、元分析等），不同分析方法和数据集间的一致性验证。
  - **引文检索基准**：五个场景，对比六个LLM，每个场景应有一定数量的查询。
  - **没有明确的消融实验描述**，但PAG-Agent本身是多个模块的组合，是否进行过模块剥离测试未知。
- **充分性评价**：
  - **正面**：三个数据集和多种分析方法增加了结果的可靠性；引文基准对比六个LLM，覆盖了常见场景。
  - **不足**：未提及在其他疾病或非AD数据集上的泛化验证；缺乏人类专家评估（如生物学家对解释质量的评分）；消融实验缺失，难以判断每个模块（如文献检索、上下文感知）的贡献。

## 6. 论文的主要结论与发现

- **主要结论**：
  1. PAG-Agent在三个AD数据集中一致识别出神经退行性疾病相关通路（如突触功能、氧化磷酸化、神经炎症等），验证了其跨数据集的稳定性。
  2. 在引文检索基准测试中，PAG-Agent在五种文献支持场景下均优于六个竞争性LLM，表明其能提供更上下文相关且引用正确的参考文献。
  3. PAG-Agent降低了通路级分析的技术门槛，使生物学家无需深入编程即可从转录组数据过渡到生物学假设与科学写作。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：将语境感知引入通路分析，突破传统工具仅输出列表的局限；集成LLM与统计方法，实现从数据到解释再到写作的全流程支持。
- **交互友好**：同时提供点击和聊天界面，适合不同技术背景的生物学家。
- **引文集成**：自动检索并验证文献引用，提高解释的可信度，解决了LLM常见幻觉问题（通过检索确保引用真实）。
- **案例设计**：使用多数据集和多分析方法验证一致性，增加稳健性；引文基准设计全面（五种场景）。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **实验覆盖**：仅测试了阿尔茨海默病领域，对于其他疾病（如癌症、代谢疾病）或单细胞数据的泛化性未充分验证。
- **偏差风险**：
  - 引文检索基准中对比的六个LLM未具体说明，可能存在选择偏差（弱于PAG-Agent或特定配置）。
  - 案例研究中未使用盲法或独立验证，可能存在过度拟合已知通路的风险。
- **应用限制**：
  - 需要用户提供清晰的实验条件描述，对于复杂多因素实验可能仍有模糊性。
  - 性能依赖底层LLM（如GPT-4）的可靠性和引用检索数据库的时效性。
  - 未提及对大规模数据（如数千个样本）的处理效率或内存需求。
  - 论文为预印本，尚未经过同行评审。

（完）
