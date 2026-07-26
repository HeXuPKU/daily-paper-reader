---
title: "BioReason-Pro: Advancing Protein Function Prediction with Multimodal Biological Reasoning"
title_zh: BioReason-Pro：通过多模态生物学推理推进蛋白质功能预测
authors: "Fallahpour, A., Seyed-Ahmadi, A., Idehpour, P., Ibrahim, O., Choi, B. M. H., Gupta, P., Naimer, J., Zhu, K., Shah, A., Ma, S., Adduri, A., Güloglu, T., Liu, N., Cui, H., Jain, A., de Castro, M., Cembellin-Prieto, A., Stiles, J. S., Nemcko, F., Nevue, A. A., Moon, H. C., Sosnick, L., Markham, O., Duan, H., Lee, M. Y. Y., Salvador, A. F. M., Maddison, C. J., Thaiss, C. A., Ricci-Tam, C., Plosky, B. S., Burke, D. P., Hsu, P. D., Goodarzi, H., Wang, B."
date: 2026-07-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.19.712954v2.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 用于蛋白质功能预测的多模态推理大语言模型，与大规模基因组模型和医疗AI相关
tldr: "蛋白质功能注释依赖于序列相似性或独立分类任务，缺乏专家推理的多模态整合。本文提出BioReason-Pro，首个多模态推理大模型，结合GO-GPT的层次化GO预测与生物上下文，生成结构化推理轨迹。在GO预测上达73.6%，LLM评分8/10，专家在79%情况下偏好其注释胜过UniProt。实验验证了肾癌标志物RCDG1的新相互作用伙伴，为可解释蛋白质功能预测建立新框架。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1691, \"height\": 1907, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1712, \"height\": 1572, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1722, \"height\": 1589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1701, \"height\": 1594, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1684, \"height\": 1954, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1668, \"height\": 1305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1686, \"height\": 2029, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1682, \"height\": 2060, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1699, \"height\": 1319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 1956, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1263, \"height\": 1065, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1160, \"height\": 1059, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1515, \"height\": 1176, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1682, \"height\": 815, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 857, \"height\": 1147, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 479, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1257, \"height\": 304, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1686, \"height\": 1876, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1710, \"height\": 555, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1730, \"height\": 1024, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1401, \"height\": 635, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1358, \"height\": 634, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1400, \"height\": 637, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1429, \"height\": 1065, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1428, \"height\": 1071, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1432, \"height\": 1063, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1432, \"height\": 1071, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1720, \"height\": 396, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1723, \"height\": 403, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1722, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1722, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1725, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1727, \"height\": 481, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1725, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1723, \"height\": 1917, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1724, \"height\": 2176, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1720, \"height\": 2191, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-03-19-712954-v2/table-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1716, \"height\": 734, \"label\": \"Table\"}]"
motivation: 现有方法无法模拟专家对序列、结构、域和交互的整合推理，蛋白功能预测缺乏多模态推理能力。
method: 构建多模态推理LLM BioReason-Pro，集成GO-GPT的GO预测，通过GPT-5生成百万级推理轨迹进行SFT，并采用强化学习优化。
result: "GO预测Fmax达73.6%，LLM评估8/10，79%案例专家偏好其注释；预测肾癌标志物新交互并经co-IP实验验证。"
conclusion: 结合精确GO建模与可解释推理，BioReason-Pro建立了蛋白质功能预测的新范式，优于现有方法。
---

## 摘要
蛋白质功能注释是理解生物机制、设计疗法以及推进生物医学研究的基础。当前的计算方法要么依赖于浅层的序列相似性，要么将功能预测视为孤立的分类任务，未能捕捉专家生物学家在推断功能时所进行的跨序列、结构、结构域和相互作用的整合推理。我们引入了BioReason-Pro，这是首个用于蛋白质功能预测的多模态推理大语言模型（LLM），它将蛋白质嵌入与生物学上下文相结合以生成结构化的推理轨迹。BioReason-Pro的一个关键输入是GO-GPT（我们的自回归变换器）生成的GO术语预测集，该模型捕获了GO术语的层次结构和跨方面依赖关系。BioReason-Pro通过在GPT-5为超过13万种蛋白质生成的合成推理轨迹上进行监督微调来训练，并通过强化学习进一步优化。它在GO术语预测上达到了73.6%的最高分，在功能摘要上获得了LLM评判者8/10的分数，显著优于之前的方法。与人类蛋白质专家的评估显示，在79%的情况下，BioReason-Pro的注释比真实的UniProt注释更受青睐。值得注意的是，BioReason-Pro预测了肾癌生物标志物RCDG1的一个新的相互作用伙伴，我们通过免疫共沉淀实验在实验室中证实了这一预测。在其他结合伙伴预测中，其逐残基注意力定位到了冷冻电镜结构中解析的确切接触残基。总之，GO-GPT和BioReason-Pro建立了一个结合了精确本体建模与可解释生物学推理的蛋白质功能预测框架。

## Abstract
Protein function annotation is fundamental to understanding biological mechanisms, designing therapeutics, and advancing biomedical research. Current computational methods either rely on shallow sequence similarity or treat function prediction as isolated classification tasks, failing to capture the integrative reasoning across sequence, structure, domains, and interactions that expert biologists perform to infer function. We introduce BioReason-Pro, the first multimodal reasoning large language model (LLM) for protein function prediction that integrates protein embeddings with biological context to generate structured reasoning traces. A key input into BioReason-Pro is the set of GO term predictions made by GO-GPT, our autoregressive transformer that captures hierarchical and cross-aspect dependencies of GO terms. BioReason-Pro is trained via supervised fine-tuning on synthetic reasoning traces generated by GPT-5 for over 130K proteins and further optimized through reinforcement learning. It achieves 73.6% max on GO term prediction and an LLM judge score of 8/10 on functional summaries, substantially outperforming previous methods. Evaluations with human protein experts show that BioReason-Pro annotations are preferred over ground truth UniProt annotations in 79% of cases. Remarkably, BioReason-Pro predicted a novel interaction partner for the renal cancer biomarker RCDG1, which we confirmed in the lab by co-immunoprecipitation. In other binding-partner predictions, its per-residue attention localized to the exact contact residues resolved in cryo-EM structures. Together, GO-GPT and BioReason-Pro establish a framework for protein function prediction that combines precise ontology modeling with interpretable biological reasoning.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：蛋白质功能注释是理解生物机制和药物开发的基础，但实验验证昂贵且低通量，导致已知蛋白质中仅不到 0.1% 拥有实验验证的注释（注释鸿沟）。
- **现有局限**：当前计算预测方法要么依赖浅层序列相似性（如 BLAST），要么将功能预测视为独立的分类任务，无法模拟专家在推断功能时对序列、结构、结构域和相互作用的整合推理。
- **研究意义**：本文首次将多模态推理大语言模型引入蛋白质功能预测，旨在实现 **可解释、结构化、专家级别的蛋白质功能自动注释**，填补大规模功能预测中推理能力的空白。

## 2. 方法论

### 核心思想
构建一个多模态推理 LLM（BioReason-Pro），它整合蛋白质嵌入、基因本体图结构信息和生物学上下文，生成类似于人类专家的推理轨迹。同时配套构建了一个自回归变压器模型 GO-GPT，用于生成可靠的 GO 术语初始预测。

### 关键技术细节
- **GO-GPT**：
  - 基于 ESM2（3B）的残基嵌入 + 12 层 GPT 解码器，使用前缀-因果注意力（prefix-causal attention）。
  - 将 GO 预测建模为序列生成任务：依次生成 MF、BP、CC 方面的 GO 术语，捕获层次和跨方面依赖。
  - 使用温度采样生成多个轨迹，取频率作为概率估计。
- **BioReason-Pro**：
  - 基座 LLM：Qwen3-4B-Thinking。
  - 蛋白质嵌入：冻结的 ESM3-1B（第38层），经两层 MLP 投影到 LLM 隐藏维度。
  - GO 图编码器：基于 GAT（3层，8头）的层次图神经网络，压缩为 200 个固定长度嵌入，通过交叉注意力模块（类似 Perceiver）整合。
  - 输入上下文：InterPro 域、STRING PPI 列表、GO-GPT 初始 GO 预测、生物体信息。
  - **训练流程**：
    - 第一阶段（模态对齐）：仅训练投影层和 GO 编码器，LLM 冻结（1 epoch）。
    - 第二阶段（LLM 微调）：训练整个模型，LLM 使用 LoRA（rank=128, alpha=256），10 epoch，最佳在 epoch 8。
    - 强化学习（RL）：基于 GSPO（Group Sequence Policy Optimization）变体，使用加权 Fmax 作为奖励，每蛋白质生成 24 个采样，训练 1200 步。
- **推理轨迹生成**：使用 GPT-5 为 130K 训练蛋白质生成合成推理轨迹（平均 1100 tokens），用于监督微调。

### 公式或算法流程（文字说明）
- 前缀-因果注意力：蛋白质残基之间双向注意，GO 令牌因果注意前缀残基和先前 GO 令牌。
- 模态组装：`X_LLM = [h_prot_1...h_prot_L, h_go_1...h_go_200, E_ctx]`，放入 LLM 输入。
- 强化学习损失：`L = -1/(B*G*L_max) * sum( min( s_i * A_hat_i, clip(s_i,1-ε_low,1+ε_high)*A_hat_i ) )`，其中 s_i 是序列级重要性比率，A_hat_i 是批次归一化后的优势。

## 3. 实验设计

### 数据集
- **来源**：UniProt（2023年1月）、GOA（2022年11月）、InterPro、STRING v12.0、PDB。
- **规模**：133,492 个蛋白质，覆盖 3,135 个生物体。仅保留实验性 GO 注释。
- **划分**：按 CAFA 时间分割：训练/验证数据截止 2022 年 11 月；测试集为 2023年3月至2024年2月间获得新实验注释的蛋白质（8,630个独特蛋白）。
- **推理数据**：130,492 条 GPT-5 生成的合成推理轨迹。

### 基准对比
- **GO 预测**：GO-GPT vs InterLabelGO+（CAFA5 公开方法）、ProtBoost。
- **功能摘要/推理**：BioReason-Pro (SFT/RL) vs Prot2Text-v2、BLAST（同源转移，含罚分和不含罚分版本）。
- **评估指标**：
  - 加权/未加权 Fmax（CAFA 标准）。
  - LLM-as-Judge：GPT-5.1 在 5 个轴上评分（分子功能、生物过程、细胞组分、特异性、可靠性），1-10。
  - 人类专家评估：27 名分子生物学家，对 162 个蛋白质进行配对偏好比较（模型 vs UniProt 真值），以及 7 个轴上的 1-10 评分。

### 实验充分性
- 包含 GO 预测性能比较、退化分析（BLAST 相似性分箱、蛋白长度、域数目等）、泛化性（跨物种、跨序列相似性）。
- 进行了 RL 训练过程分析、因果注意力分析（eEFSec、CFAP61、RCDG1）。
- 案例研究包括：eEFSec（SECIS 结合蛋白预测）、CFAP61（非酶支架推理）、RCDG1（新相互作用伙伴的 co-IP 验证）。
- 消融探索（附录 B.4）：LLM 骨干、LoRA 秩、GO 编码器必要性、推理轨迹格式。
- 极限测试：短肽（<50 aa）和 AI 生成蛋白（EvoAcr1/2）。
- 总体上实验数量较多，覆盖主流任务和深度分析，但人类专家评估样本 162 相对有限。

## 4. 资源与算力

- **GO-GPT**：4 × NVIDIA H100 GPU，有效 batch size 160，训练最多 100 epoch（early stopping）。
- **BioReason-Pro SFT**：8 × NVIDIA H100（2 节点 × 4），每设备 batch size 4，有效 batch size 32。Stage 1 训练 1 epoch，Stage 2 训练 10 epoch（最佳在 epoch 8）。
- **BioReason-Pro RL**：8 × NVIDIA H100，有效 batch size 192，训练 1,200 步，约 32 小时，消耗约 619M tokens。
- 论文未给出 SFT 总训练时长，但 RL 约 32 小时。

## 5. 实验数量与充分性

- GO 预测对比：3 种基线 × 3 方面 × 2 指标，附带 bootstrap 显著性检验。
- BioReason-Pro GO 预测：与 GO-GPT、InterLabelGO+ 对比，并通过不同解码策略（greedy、best-of-10）分析。跨序列相似性分箱分析。
- LLM 评判者评估：覆盖完整测试集 8,159 蛋白质，平均分对比和分箱分析。
- 人类专家评估：162 蛋白质 × 2 模型 × 10 轴，并包含自由文本错误分类。
- 案例研究：3 个蛋白的深度注意力和结构对齐，1 个湿实验验证。
- 极限测试：2 个短肽集 + 2 个 EvoAcr 蛋白 × 4 生物体。
- 消融：在附录 B.4 和 B.5 中涉及架构选择、LoRA 秩、GO 编码器消融、上下文设计。
- **评价**：实验相当充分，覆盖主要对比、退化、泛化、可解释性和验证。唯一潜在不足是人类评估样本量 162，但增强了专家判断的可信度。

## 6. 论文的主要结论与发现

- GO-GPT 在加权 Fmax 上达到 0.65-0.70，显著优于 InterLabelGO+ (0.63) 和 ProtBoost，其学习到的嵌入恢复了生物本体结构和进化关系。
- BioReason-Pro 在 GO 预测上达到 Fmax 73.6%（加权 Fmax 0.66 greedy），功能摘要 LLM 评分 8.03/10，远超 Prot2Text-v2 (4.15)。
- **人类专家**：79% 的情况下偏好 BioReason-Pro SFT 注释超过 UniProt 真值，RL 为 73%。
- **实验验证**：预测 RCDG1 与 RAB5A 的相互作用，通过 co-IP 得到确证。
- **结构化推理**：eEFSec 案例中，模型预测 SECIS 结合蛋白 SBP2，且注意力集中在 RIFT 结构域的 SECIS RNA 接触界面；CFAP61 案例中，模型从退化的 Rossmann 域推断出非酶支架功能，注意力集中在被重新利用为 dynein 接触的残基上。
- 强化学习提高了 GO 准确性并减少了幻觉，但可能牺牲了一些机理深度（SFT 在机理深度上略优，RL 在可靠性上更优）。

## 7. 优点

- **创新性**：首次将多模态推理 LLM 用于蛋白质功能预测，生成完整的结构化推理链，实现可解释性。
- **技术集成**：结合了规模化蛋白质基础模型（ESM3）、图神经网络（GO 编码器）和 LLM 推理（Qwen3），以及自回归 GO 预测（GO-GPT）。
- **训练策略**：利用大型语言模型（GPT-5）生成合成推理轨迹，降低对人工标注推理的依赖；采用强化学习直接优化功能预测指标。
- **验证强度**：包含定量评估、人类专家评估和湿实验验证（co-IP），提升可信度。
- **适用范围**：在低序列相似性蛋白质和全新设计的合成蛋白上仍能产生合理假设。
- **开源释放**：公开模型权重、代码、数据集和 web 界面，利于社区复现和应用。

## 8. 不足与局限

- **训练成本**：计算需求高，需串联 ESM3、GO-GPT 和推理 LLM，且依赖有实验注释的蛋白质。
- **数据偏差**：合成推理轨迹由 GPT-5 生成，可能隐含系统误差并传播。
- **短肽表现差**：序列长度 <50 aa 时，性能系统性下降（域缺乏、家族混淆）。
- **对生物体标签敏感**：对于无域蛋白，预测强烈依赖于所输入的生物体，导致不同物种下预测功能差异很大。
- **人类评估样本有限**：仅 162 个蛋白，27 位专家，统计力有限，且可能引入个人偏好偏差。
- **RL 的局限性**：虽提高准确性，但降低了机理深度和创新假设的生成（如 SFT 更富机制洞察）。
- **不可解释性限制**：尽管有推理链，但模型是否学习到真正推理还是模仿仍有争议；注意力分析案例数量偏少。
- **GO 覆盖率**：对于新颖或组合功能，GO 本体词汇可能限制表达（如 eEFSec 的独特功能没有对应 GO 术语）。

（完）
