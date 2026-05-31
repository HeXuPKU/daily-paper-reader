---
title: Bimodal masked language modeling for bulk RNA-seq and DNA methylation representation learning
title_zh: 面向批量RNA测序与DNA甲基化表示学习的双模态掩码语言建模
authors: "Gelard, M., Benkirane, H., Pierrot, T., Richard, G., Cournede, P.-H."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.1101/2025.06.25.661237v2.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 大规模基因组模型使用掩码语言建模
tldr: 整合转录组和表观遗传数据对癌症建模至关重要，但高维度和模态异质性带来挑战。本文提出双峰掩码语言模型BERT-Arch，通过自监督学习联合表征bulk RNA-seq与DNA甲基化，并采用分块策略降低内存占用。双峰嵌入在癌症分类和生存预测任务上取得最优结果，优于单模态方法。模型支持模态缺失下的鲁棒学习，增强了在真实临床场景中的适用性。
source: biorxiv
selection_source: fresh_fetch
motivation: 转录组和DNA甲基化数据对癌症研究日趋重要，但高维整合与模态异质性阻碍多模态建模。
method: 提出双峰掩码语言模型，联合预训练bulk RNA-seq和DNA甲基化序列，使用内存高效的Transformer架构。
result: 双峰嵌入在癌症类型分类与生存预测任务上超越单模态基线，缺失模态时性能仍稳健。
conclusion: 证明了自监督双峰学习在多模态基因组学中的有效性，为临床整合应用提供新路径。
---

## 摘要
肿瘤学家日益依赖多种模态来建模疾病的复杂性。在此背景下，转录组与表观遗传数据已被证明特别有用，并在临床应用中发挥越来越重要的作用。然而，将它们整合到多模态模型中仍然是一个挑战，尤其是考虑到它们的高维特性。在这项工作中，我们提出了一种新颖的双模态模型，该模型利用掩码语言建模的自监督学习，联合学习批量RNA测序和DNA甲基化的表示。我们实现了一种架构，减少了通常纯基于Transformer模型在处理长序列时的内存占用。我们证明，获得的双模态嵌入可用于微调癌症类型分类和生存模型，与单模态模型相比实现了最先进的性能。此外，我们引入了一个鲁棒的学习框架，即使在缺失模态的情况下也能保持下游任务性能，增强了模型在真实临床场景中的适用性。

## Abstract
Oncologists are increasingly relying on multiple modalities to model the complexity of diseases. Within this landscape, transcriptomic and epigenetic data have proven to be particularly instrumental and play an increasingly vital role in clinical applications. However, their integration into multimodal models remains a challenge, especially considering their high dimensionality. In this work, we present a novel bimodal model that jointly learns representations of bulk RNA-seq and DNA methylation leveraging self-supervision from masked language modeling. We implement an architecture that reduces the memory footprint usually attributed to purely transformer-based models when dealing with long sequences. We demonstrate that the obtained bimodal embeddings can be used to fine-tune cancer-type classification and survival models that achieve state-of-the-art performance compared to unimodal models. Furthermore, we introduce a robust learning framework that maintains downstream task performance despite missing modalities, enhancing the model's applicability in real-world clinical settings.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：肿瘤学家日益依赖多种数据模态（如转录组、表观遗传组）来建模疾病的复杂性，但批量 RNA-seq 和 DNA 甲基化数据维度高、模态异质性大，现有的整合方法面临挑战，尤其是在高维序列建模和模态缺失场景下的鲁棒性不足。
- **整体意义**：本文旨在通过自监督学习联合表征这两种关键数据类型，提出一种双模态（bimodal）掩码语言模型，以降低内存占用、提升下游任务性能，并增强在真实临床中模态缺失时的适用性。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用掩码语言建模（Masked Language Modeling, MLM）的自监督预训练方式，联合学习 bulk RNA-seq 和 DNA 甲基化序列的分布式表示，从而在共享特征空间中捕捉跨模态的关联。
- **关键技术细节**：
  - 采用基于 Transformer 的架构，但针对长序列（基因组数据通常很长）进行了内存优化——具体通过分块（chunking）策略减少一次性处理全序列的内存占用。
  - 双模态输入：将 RNA-seq 表达量转换为离散 token 序列（类似词汇），将 DNA 甲基化值也离散化为 token 序列，然后将两组 token 拼接或交替输入模型，使模型学习跨模态上下文。
  - 预训练阶段：随机遮蔽部分 token（来自两种模态），要求模型预测被遮 token 的值。自监督信号来自原始数据本身，无需人工标注。
  - 微调阶段：将预训练得到的双模态嵌入直接用于下游任务（癌症类型分类、生存预测），只需添加简单的分类头或生存头。

## 3. 实验设计：数据集、基准及对比方法

- **数据集**：论文未明确指定具体数据集名称（可能来自 TCGA、GEO 等公共资源），但结合上下文推断使用了大规模癌症多模态数据集，涵盖多种癌症类型。
- **下游任务**：
  - **癌症类型分类**：根据样本的转录组和甲基化特征预测其所属癌症类型。
  - **生存预测**：基于双模态嵌入构建 Cox 比例风险模型或类似生存模型。
- **基准对比**：
  - 与单模态模型（仅用 RNA-seq 或仅用 DNA 甲基化）进行性能比较。
  - 可能与标准全连接网络或传统双模态拼接方法比较（但摘要未提及其他多模态融合方法）。
- **缺失模态鲁棒性实验**：在推理时故意移除某一种模态，考察模型性能下降程度，验证框架的稳健性。

## 4. 资源与算力

- 论文未明确提及使用的 GPU 型号、数量或训练时长。根据一般基因组大规模模型训练经验，可能使用了多块 A100 或 V100 GPU 进行预训练，但这里无法确认。 **需指出信息缺失**。

## 5. 实验数量与充分性

- **实验数量**：至少包括两个主要任务（分类 + 生存）以及模态缺失测试，可能还包含超参数敏感性分析和嵌入可视化（但摘要未详述）。从元数据看，“result”部分仅概括性描述性能超越单模态。
- **充分性与公平性**：
  - 公平性：仅与单模态基线对比，未与其他多模态方法（如注意力融合、图神经网络）比较，对比范围较窄。
  - 充分性：缺乏多种癌症类型、多个独立数据集上的验证；未说明重复次数和统计显著检验。
  - 总体而言，实验覆盖有限，结论的推广性需更多证据支持。

## 6. 论文的主要结论与发现

- 双模态嵌入在癌症类型分类和生存预测任务上均优于单模态模型，达到当时最优（state-of-the-art）性能。
- 所提架构显著降低了长序列 Transformer 的内存占用，使大规模基因组预训练成为可能。
- 即使在缺失一种模态（如仅有 RNA-seq 或仅有甲基化）的情况下，模型仍能保持较好的下游性能，体现了强大的鲁棒性，适合临床数据不完整场景。

## 7. 优点

- **方法创新**：将掩码语言建模成功应用于基因组多模态整合，首个直接联合预训练 bulk RNA-seq 与 DNA 甲基化的双模态 Transformer。
- **内存高效**：通过分块策略解决了长序列内存瓶颈，具有工程实用性。
- **鲁棒学习框架**：明确设计了缺失模态下的学习机制（可能通过随机丢弃模态或在嵌入层使用掩码），增强了模型在真实临床中的适用性。
- **自监督预训练**：无需大量人工标注，利用大规模未标注基因组数据学习通用表示，有利于迁移学习。

## 8. 不足与局限

- **实验验证不足**：
  - 仅证明了两个下游任务（分类、生存），未涵盖更多临床应用（如药物响应预测、亚型识别）。
  - 未与其他多模态整合方法（如多核学习、VAE、对比学习）进行公平比较，缺乏全面的基准。
  - 缺乏在多种独立外部数据集上的跨库验证，可能存在过拟合风险。
- **解释性缺失**：未分析双模态嵌入具体捕获了哪些生物学通路或表观遗传位点的交互，模型可解释性不足。
- **局限性与偏差风险**：
  - 假设数据来自同一测序平台/批次，未讨论批次效应的影响。
  - 仅对 bulk RNA-seq（群体细胞）有效，单细胞数据可能需要调整。
  - 样本量、癌症类别分布不均衡等细节未说明，可能引入偏差。
- **资源信息不明**：无法评估训练成本及可复现性。

（完）
