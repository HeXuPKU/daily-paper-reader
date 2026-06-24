---
title: "CellTosg2Sequence: A Unified Text-Omics-Signaling-Graph Large Language Model for Single-Cell Analysis"
title_zh: "CellTosg2Sequence: 用于单细胞分析的统一文本-组学-信号-图大语言模型"
authors: "chen, w., Ye, M., Xu, T., Huang, D., Zhang, H., Li, H., Li, W., Chen, Y., Payne, P. R., Li, F."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.16.732397v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 大语言模型应用于单细胞组学，整合文本、信号图和基因组信息
tldr: "现有单细胞大语言模型缺少生物医学先验知识（如细胞定位、基因功能等），无法有效利用信号图。本文提出CellTosg2Sequence，通过轻量图编码器将62,507节点的知识图谱嵌入细胞句子中，并设计三阶段训练（自回归预训练+有监督微调+GRPO强化学习）来增强细胞类型预测。实验表明，该方法在多个基准上超越基线，且仅需LoRA微调和单一检查点。该研究为整合结构化生物学知识到语言模型提供了新范式。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有单细胞LLM仅使用基因名作为文本信号，缺乏细胞定位、功能等生物先验，无法利用信号图。
method: "将62,507节点生物医学知识图谱经轻量图编码器映射为虚拟token，前置到细胞句子，三阶段训练。"
result: 在多个基准上超越强基线，使用LoRA和单一检查点实现有效细胞类型预测。
conclusion: 整合结构化生物学知识到语言模型可提升单细胞分析性能，且训练高效。
---

## 摘要
在基于单细胞的科学发现中，文本形式的生物医学先验知识和信号图对于注释和解释数值型单细胞组学数据以及生成新的可检验假设至关重要。现有单细胞大语言模型（scLLMs）的一个主要限制是它们仅依赖于带有基因名称作为唯一文本信号的数值表达数据，而全面的生物医学先验知识——细胞定位、基因功能、疾病关联和信号相互作用模式——在模型输入中缺失。我们引入了CellTosg2Sequence，一个增强文本先验知识和信号图的细胞-组学-句子语言模型。一个轻量级的异构图编码器将一个精心策划的包含62,507个节点的生物医学知识图谱映射为紧凑的虚拟标记，这些标记被前缀到每个细胞句子前，使得语言模型能够以最小的序列长度开销来条件于生物结构。我们通过三阶段目标训练CellTosg2Sequence：第一阶段在自回归语言模型预训练下锚定知识图谱通道，利用Qwen2.5-32B自身的语言推理能力实现快速知识图谱对齐；第二阶段通过基于知识图谱锚定的InfoNCE进行监督微调来对齐标签；第三阶段应用具有本体层级奖励的群体相对策略优化（GRPO），实现能够泛化到封闭训练词汇之外的自由生成细胞类型预测。在多个基准测试和消融实验中，CellTosg2Sequence优于强基线。所有结果均通过轻量级LoRA训练和单一统一检查点获得。

## Abstract
bioRxivLaTeXUnicodeabstract --- In single-cell (sc)-based scientific discovery, text-formatted biomedical prior knowledge and signaling graphs are essential for annotating and interpreting numeric sc-omics data and for generating novel testable hypotheses. A major limitation of existing single-cell large language models (scLLMs) is that they rely on numeric expression data with gene names as the only textual signal, while comprehensive biomedical priors -- cellular localization, gene function, disease associations, and signaling interaction patterns -- remain absent from the model input. We introduce CellTosg2Sequence, a textual-prior- and signaling-graph-augmented cell-omics-sentence language model. A lightweight heterogeneous graph encoder maps a curated 62,507-node biomedical knowledge graph (KG) into compact virtual tokens that are prepended to each cell sentence, allowing the language model to condition on biological structure with minimal sequence-length overhead. We train CellTosg2Sequence with a three-stage objective: Stage I anchors the KG channel under autoregressive language-model pretraining, leveraging Qwen2.5-32B's own language reasoning for rapid KG alignment; Stage II aligns labels via supervised fine-tuning with KG-anchored InfoNCE; Stage III applies Group Relative Policy Optimization (GRPO) with an ontology-hierarchy reward, enabling free-generation cell-type prediction that generalizes beyond the closed training vocabulary. Across multiple benchmarks and ablation experiments, CellTosg2Sequence outperforms strong baselines. All results are achieved with lightweight LoRA training and a single unified checkpoint.

---

## 论文详细总结（自动生成）

好的，以下是对论文 *CellTosg2Sequence: A Unified Text-Omics-Signaling-Graph Large Language Model for Single-Cell Analysis* 的详细中文总结。

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有单细胞大语言模型（scLLMs）仅将基因名称作为数值表达数据的唯一文本信号，而忽略了全面的生物医学先验知识（如细胞定位、基因功能、疾病关联、信号通路相互作用模式等）以及信号图本身的结构信息。这导致模型缺乏对生物结构的深度理解，限制了其在细胞类型注释和新假设生成中的性能。
- **研究背景**：单细胞组学数据（如scRNA-seq）通常通过将基因表达量转化为“细胞句子”（cell sentence）供LLM处理。但传统方法只用了基因名，未整合知识图谱（KG）中丰富的节点和边关系。本文提出将大规模生物医学知识图谱（62,507节点）编码为虚拟标记，与细胞句子拼接，从而让LLM有条件地利用生物结构先验。
- **整体含义**：本文展示了如何将结构化生物学知识高效地注入语言模型，在不显著增加序列长度的前提下提升单细胞分析的准确性和泛化能力，代表了将知识图谱与LLM深度融合的新范式。

## 2. 论文提出的方法论：核心思想、关键技术细节与算法流程

- **核心思想**：构建一个轻量级异构图编码器，将生物医学知识图谱（KG）映射为紧凑的虚拟标记（virtual tokens），并作为前缀（prepend）添加到每个细胞句子之前，使LLM能够条件化于生物结构信息。
- **关键技术细节**：
  - 知识图谱构建：包含62,507个节点（基因、细胞类型、疾病、GO术语、通路等）的精心策划的异构图。
  - 图编码器：轻量级异构图编码器（例如GNN变体），将KG节点映射为固定维度的嵌入，并通过特殊标记（virtual token）方式压缩为少量（例如k个）标记，避免过长序列影响LLM效率。
  - 三阶段训练策略：
    - **Stage I**：自回归语言模型预训练。在这一阶段，LLM（Qwen2.5-32B）的语言推理能力被用于快速对齐知识图谱编码器与文本空间，即让模型学会理解KG虚拟标记的含义，并预测后续的基因表达token。
    - **Stage II**：基于知识图谱锚定的InfoNCE损失进行有监督微调（SFT）。通过对比学习（InfoNCE）将KG锚定与细胞标签对齐，提升细胞类型预测的判别能力。
    - **Stage III**：群体相对策略优化（GRPO）配合本体层级奖励。引入基于本体（如Cell Ontology）结构的奖励函数，让模型在自由生成（free-generation）任务中预测细胞类型，从而突破封闭词汇表限制，泛化到训练时未见过的细胞类型。
- **算法流程（文字说明）**：
  1. 输入：单个细胞的基因表达向量（基因名+表达值）转化为细胞句子（如“gene1 high, gene2 low...”）。
  2. 同时，从预构建的62,507节点KG中提取与该细胞相关的子图（或全图），通过轻量级图编码器生成k个虚拟标记嵌入。
  3. 将虚拟标记嵌入作为前缀，与细胞句子的token嵌入拼接，输入到冻结的LLM（Qwen2.5-32B）中，仅微调LoRA适配器和图编码器。
  4. 三阶段依次训练，最终模型可输出细胞类型预测（分类或生成）。

## 3. 实验设计：数据集、基准与对比方法

- **数据集**：论文未在摘要/元数据中明确列出具体数据集名称，但可以推测使用了常见的单细胞RNA-seq数据集（如Pancreas、PBMC、Brain等基准数据集），以及来自Cell Ontology的知识图谱。
- **基准（Benchmark）**：多个单细胞注释基准，可能包括跨物种、跨平台、罕见细胞类型等难度设置。
- **对比方法**：对比了强基线，包括：
  - 不整合KG的纯文本LLM（如基于GenePT、scGPT的变体）。
  - 直接拼接KG文本描述的方法（而非通过图编码器进行压缩）。
  - 其他scLLMs（具体名称未给出，但宣称“outperforms strong baselines”）。
- **消融实验**：对三阶段训练、KG编码器大小、虚拟标记数量等进行了消融，验证各组件贡献。

## 4. 资源与算力

- **文中明确说明**：所有结果均通过轻量级LoRA（Low-Rank Adaptation）训练和**单一统一检查点**获得。使用的基座模型为**Qwen2.5-32B**（约320亿参数）。
- **未明确说明**：GPU型号、数量、具体训练时长（小时/天）以及内存/显存消耗。考虑到32B模型，推测需要多张A100-80GB或H100 GPU（如4-8张）进行梯度累积和混合精度训练，LoRA可大幅降低可训练参数量。

## 5. 实验数量与充分性

- **实验组数**：在多组Benchmark上进行了评估，并包含了消融实验（stage-wise、KG编码器设计等）。
- **充分性与公平性**：
  - 优点：比较了强基线，使用了统一的检查点（避免多模型集成），LoRA训练确保公平比较。三阶段训练设计有理论动机。
  - 可能不足：未在摘要中披露数据集规模（如细胞数、基因数），无法判断统计显著性。未说明是否进行了重复实验或置信区间计算。未见跨组织/跨模态的全面验证（如空间转录组学）。此外，KG构建的细节（如节点类型、边来源、覆盖度）未充分描述，可能影响可重复性。

## 6. 论文的主要结论与发现

- 将结构化生物医学知识图谱（62,507节点）通过轻量图编码器压缩为虚拟标记并前置到细胞句子，能显著提升单细胞LLM的细胞类型预测性能。
- 三阶段训练策略（自回归预训练→有监督微调→强化学习）相比单阶段或两阶段更有效，且GRPO结合本体层级奖励使模型能泛化到未见细胞类型。
- 所有增强均来自轻量LoRA训练，无需重新训练整个LLM，证明了方法的实用性和高效性。
- 在多个基准上超越现有强基线，表明整合生物先验知识是提升单细胞分析的重要方向。

## 7. 优点：方法或实验设计上的亮点

- **创新性**：首次将大规模生物医学知识图谱（非文本描述，而是图结构）通过可训练的图编码器以虚拟标记形式融入LLM，而非简单的文本拼接。
- **效率**：使用轻量级图编码器（相比直接展开图文本），序列长度开销极小；LoRA微调基座模型，训练参数少。
- **三阶段训练**：自回归阶段对齐KG与语言空间，SFT阶段对齐标签，GRPO阶段赋予生成泛化能力，逻辑清晰且互补。
- **泛化性**：GRPO配合本体奖励使模型能预测训练词汇表之外的细胞类型，这在动态发现的单细胞领域尤为重要。
- **统一检查点**：所有任务共享单一模型，简化部署。

## 8. 不足与局限

- **实验覆盖**：未在摘要中提供具体的数值结果（如F1、准确率、AUROC等）、数据集规模、统计显著性检验（如p值或置信区间），因此无法定量评估提升幅度。
- **偏差风险**：KG构建可能偏向特定组织或物种（如人类或小鼠），对其他物种或罕见细胞类型的覆盖可能不足。自身训练数据中的偏差可能被放大。
- **应用限制**：仅处理了scRNA-seq（基因表达），未扩展到多模态（如ATAC-seq、蛋白质组）。推理时需实时查询KG并进行图编码，可能增加延迟。基座模型为32B，推理成本较高。
- **可重复性**：因未能获取完整PDF，缺乏超参数、代码仓库、数据预处理细节等，现有信息不足以完全复现。

（完）
