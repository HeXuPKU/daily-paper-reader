---
title: "CellTosg2Sequence: A Unified Text-Omics-Signaling-Graph Large Language Model for Single-Cell Analysis"
title_zh: CellTosg2Sequence：用于单细胞分析的统一文本-组学-信号-图大语言模型
authors: "chen, w., Ye, M., Xu, T., Huang, D., Zhang, H., Li, H., Li, W., Chen, Y., Payne, P. R., Li, F."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.16.732397v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 单细胞大语言模型，属于基因组大模型和医学LLM范畴
tldr: 现有单细胞大语言模型仅以基因名作为文本信号，缺失细胞定位、功能、疾病关联和信号交互等生物先验知识。本文提出CellTosg2Sequence，通过轻量异构图编码器将包含6.2万个节点的生物知识图谱压缩为虚拟token注入细胞句子，并采用三阶段训练（自回归预训练、监督微调、GRPO）实现开放词汇的细胞类型预测。实验表明该方法在多个基准上超越基线，且仅需轻量LoRA训练和单一检查点。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有scLLM忽略生物先验知识和信号图，限制了对单细胞数据的理解和可解释性。
method: 异构知识图谱编码器生成虚拟token注入语言模型，三阶段训练：自回归预训练对齐KG、InfoNCE监督微调、GRPO优化层次化奖励。
result: 在多个基准测试中，CellTosg2Sequence显著优于现有强基线方法。
conclusion: 融合知识图谱先验可显著提升单细胞大语言模型的泛化能力和生物学解释性。
---

## 摘要
在基于单细胞（sc）的科学发现中，文本格式的生物医学先验知识和信号图对于注释和解释数值型单细胞组学数据以及生成新的可检验假设至关重要。现有单细胞大语言模型（scLLMs）的一个主要局限是它们仅依赖以基因名称为唯一文本信号的数值表达数据，而模型输入中缺乏全面的生物医学先验——细胞定位、基因功能、疾病关联和信号相互作用模式。我们引入了CellTosg2Sequence，一种增强文本先验和信号图的细胞-组学-句子语言模型。一个轻量级异构图编码器将精心整理的62,507节点生物医学知识图谱（KG）映射为紧凑的虚拟标记，这些标记被前置到每个细胞句子的开头，使语言模型能够以最小的序列长度开销适应生物结构。我们通过三阶段目标训练CellTosg2Sequence：第一阶段在自回归语言模型预训练下锚定KG通道，利用Qwen2.5-32B自身的语言推理实现快速KG对齐；第二阶段通过基于KG锚定的InfoNCE进行监督微调以对齐标签；第三阶段应用具有本体层次奖励的群体相对策略优化（GRPO），实现能够泛化到封闭训练词汇之外的自由生成细胞类型预测。在多个基准测试和消融实验中，CellTosg2Sequence优于强基线方法。所有结果均通过轻量级LoRA训练和单一统一检查点实现。

## Abstract
bioRxivLaTeXUnicodeabstract --- In single-cell (sc)-based scientific discovery, text-formatted biomedical prior knowledge and signaling graphs are essential for annotating and interpreting numeric sc-omics data and for generating novel testable hypotheses. A major limitation of existing single-cell large language models (scLLMs) is that they rely on numeric expression data with gene names as the only textual signal, while comprehensive biomedical priors -- cellular localization, gene function, disease associations, and signaling interaction patterns -- remain absent from the model input. We introduce CellTosg2Sequence, a textual-prior- and signaling-graph-augmented cell-omics-sentence language model. A lightweight heterogeneous graph encoder maps a curated 62,507-node biomedical knowledge graph (KG) into compact virtual tokens that are prepended to each cell sentence, allowing the language model to condition on biological structure with minimal sequence-length overhead. We train CellTosg2Sequence with a three-stage objective: Stage I anchors the KG channel under autoregressive language-model pretraining, leveraging Qwen2.5-32B's own language reasoning for rapid KG alignment; Stage II aligns labels via supervised fine-tuning with KG-anchored InfoNCE; Stage III applies Group Relative Policy Optimization (GRPO) with an ontology-hierarchy reward, enabling free-generation cell-type prediction that generalizes beyond the closed training vocabulary. Across multiple benchmarks and ablation experiments, CellTosg2Sequence outperforms strong baselines. All results are achieved with lightweight LoRA training and a single unified checkpoint.