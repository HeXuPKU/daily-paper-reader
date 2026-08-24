---
title: A self-supervised DNA foundation model with collapse-resistant multimodal fusion
title_zh: 一种具有抗坍塌多模态融合的自监督DNA基础模型
authors: "Chen, Y."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.19.745697v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 自监督DNA基础模型与抗坍缩多模态融合，属于大规模基因组模型
tldr: 仅基于DNA序列的基因组基础模型难以全面捕捉染色质调控信息，而现有融合多模态的基因组模型常偏向特定预测任务，并且稀疏峰状信号与稠密序列表示直接融合会导致对齐退化至近零解。为此提出自监督的DNA中心多模态基础模型，在共享编码器中将序列嵌入与局部、全局染色质可及性整合，通过全局归一化显著缓解模态塌缩，生成可复用的窗口级嵌入。该嵌入在调控活性预测、调控信号排序及染色质峰检测等下游评估中全面超越DNA-only基线，峰检测AUPRC提升4.6倍，并在ClinVar、GTEx eQTL和PBMC caQTL外部验证中得到进一步改善。框架易于扩展至更多调控模态，为多模态DNA基础模型提供了方法论支撑。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1696, \"height\": 969}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1633, \"height\": 1476}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1671, \"height\": 1183}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1677, \"height\": 1509}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1684, \"height\": 1337}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1669, \"height\": 1231}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1728, \"height\": 272}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1740, \"height\": 308}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1743, \"height\": 362}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1742, \"height\": 360}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1733, \"height\": 235}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1746, \"height\": 235}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1740, \"height\": 235}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1716, \"height\": 510}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-08-19-745697-v1/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1715, \"height\": 600}]"
motivation: 序列DNA模型无法全面反映调控信息；异质模态统计结构差异大，直接融合易塌缩。
method: 自监督DNA多模态基础模型，共享编码器融合序列嵌入与局部/全局染色质可及性，全局归一化防对齐退化。
result: 峰检测AUPRC较DNA-only提升4.6倍；调控活性预测等任务改善，ClinVar、eQTL和caQTL外部验证更优。
conclusion: 全局归一化有效缓解异质模态塌缩，框架可扩展至更多调控模态，奠定多模态DNA基础模型基础。
---

## 摘要
基于DNA序列预训练的基因组基础模型在多种任务上取得了强劲性能，但仅序列表示无法完全捕捉额外DNA中心模态所反映的调控信息。现有的多模态基因组模型通常针对特定预测任务优化，而非用于学习可跨下游分析复用的嵌入表示。然而，直接融合异质基因组模态具有挑战性，因为稀疏的峰状调控信号和密集的序列表示具有显著不同的统计结构，使得朴素的多模态对齐容易退化为近零解。我们提出了一种自监督的DNA中心多模态基础模型来解决这一缺口，在共享的多模态编码器中整合DNA序列嵌入与局部和全局染色质可及性，产生可复用的窗口级嵌入，同时支持预训练期间的掩码重建和下游预测任务。我们诊断了这种异质模态对齐失败，并表明全局归一化显著缓解了坍塌，实现了跨模态的有效联合学习。生成的嵌入改善了下游多项调控功能评估，包括调控活性预测、调控信号排序和染色质可及性峰检测，在峰检测中相比仅DNA基线实现了4.6倍的AUPRC提升，并进一步改善了在ClinVar、GTEx eQTL和PBMC caQTL数据集上的外部验证。该框架可扩展到其他调控模态，为多模态DNA基础模型提供了方法论基础。

## Abstract
Genomic foundation models pretrained on DNA sequence have achieved strong performance across a range of tasks, but sequence-only representations cannot fully capture regulatory information reflected by additional DNA-centric modalities. Existing multimodal genomic models are often optimized for specific prediction tasks rather than for learning reusable embeddings shared across downstream analyses. However, directly fusing heterogeneous genomic modalities is challenging because sparse, peak-shaped regulatory signals and dense sequence representations have markedly different statistical structures, making naive multimodal alignment prone to degenerate near-zero solutions. We present a self-supervised DNA-centric multimodal foundation model that addresses this gap, integrating DNA sequence embeddings with local and global chromatin accessibility in a shared multimodal encoder to produce reusable window-level embeddings that support both masked reconstruction during pre-training and downstream prediction tasks. We diagnose this heterogeneous-modality alignment failure and show that global normalization substantially alleviates collapse, enabling effective joint learning across modalities. The resulting embeddings improve multiple downstream evaluations of regulatory function, including regulatory activity prediction, regulatory signal ranking and chromatin accessibility peak detection, achieving a 4.6-fold AUPRC improvement over the DNA-only baseline in peak detection, and further improving external validation on ClinVar, GTEx eQTL and PBMC caQTL datasets. The framework is extensible to additional regulatory modalities, providing a methodological basis for multimodal DNA foundation models.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义

- **背景**：基于DNA序列预训练的基因组基础模型在多种基因组学任务上表现出色，但序列本身只承载了一部分生物学信息。染色质可及性、组蛋白修饰等调控活性是以DNA为中心的重要调控模态，这些信息难以由序列表示完整推断出来。
- **问题1（信息缺口）**：仅依赖序列表示无法全面捕捉真实调控环境，例如开放染色质区域、增强子/启动子活性和峰状信号的分布等。
- **问题2（现有方案不足）**：已有的多模态基因组模型大多针对特定预测任务进行监督优化，主要服务于任务精度，而非学习可用于多种下游分析的通用嵌入；此外，异质模态（稀疏峰状信号 vs. 密集序列信号）在统计结构上差异巨大，直接融合极易发生对齐退化——即模型退化为接近零解，各模态丧失有效交互。
- **问题3（方法论缺口）**：如何在不塌缩的情况下实现异构调控模态与DNA序列的自监督联合表征学习，是实现多模态基因组基础模型的关键挑战。
- **论文含义**：该研究提出一种**DNA中心的自监督多模态基础模型**——将DNA序列嵌入与局部/全局染色质可及性在共享多模态编码器中融合，产生**窗口级可复用嵌入**，同时支持预训练中的掩码重建与下游预测任务，从而为多模态DNA基础模型奠定方法论基础。

## 2. 方法论

- **核心思想**：在共享编码器中同时输入DNA序列与染色质可及性信息，使模型学习既包含序列语法、又包含染色质调控信号的联合表示；不同下游任务直接从该窗口级嵌入出发，无需重新训练或任务特化表示。
- **关键技术细节**：
  - **模态融合**：在共享多模态编码器中，将DNA序列嵌入与两种形式的染色质可及性信号（局部信号和全局信号）进行整合；局部信号捕捉短距离调控信息，全局信号提供更宽泛的开放染色质背景。
  - **自监督预训练任务**：嵌入表示同时支持掩码重建目标，即在预训练期间通过被掩码的序列或可及性信号进行重构，使模型不依赖标注就能从多模态数据中学习。
  - **抗坍塌机制——全局归一化**：论文明确提出，直接拼接/融合稀疏峰状信号和密集序列表示时，对齐过程容易收敛到近零解。引入**全局归一化**能够有效防止这种退化，保持各模态的信息流动与联合学习稳定性。
- **算法流程**（以文字描述）：
  1. 输入DNA序列，经序列编码器得到序列嵌入；
  2. 输入局部和全局染色质可及性信号；
  3. 在共享多模态编码器中对序列嵌入与可及性信号进行融合；
  4. 对融合后的联合表示进行全局归一化，以规避异质模态对齐坍缩；
  5. 预训练时对掩码区域进行序列重建/信号重建，学习窗口级嵌入；
  6. 下游使用时，将训练好的窗口级嵌入直接接入各类预测头（调控活性、信号排序、峰检测等）。

## 3. 实验设计

- **下游评估任务与基准（benchmark）**：
  1. 调控活性预测；
  2. 调控信号排序（regulatory signal ranking）；
  3. 染色质可及性峰检测（chromatin accessibility peak detection）。
- **对比方法**：以**仅DNA序列的基线模型**作为主要对照（即DNA-only baseline），用于检验多模态融合带来的增益；同时隐含对比已有的任务特定多模态模型——但论文强调自身目标是可复用嵌入而非任务优化。
- **外部验证数据集**：
  - ClinVar（临床变异注释）；
  - GTEx eQTL（表达数量性状位点）；
  - PBMC caQTL（染色质可及性数量性状位点）。
- **关键实验结果**：
  - 峰检测中，AUPRC 相比DNA-only基线提升了**4.6倍**；
  - 调控活性预测和调控信号排序均有显著改善；
  - 外部数据验证显示，多模态嵌入在多个独立数据集上进一步增强了预测能力。

## 4. 资源与算力

- 论文提供的文本/元数据中**没有明确说明**使用的GPU型号、GPU数量、训练时长等具体算力信息。
- 也未提供模型参数量、训练数据规模、预训练步数或吞吐量等与计算开销相关的细节。
- 若需复现或评估训练成本，需要查阅论文全文或补充材料。

## 5. 实验数量与充分性

- **实验组数**：论文至少包含三类内部下游评估（活性预测、信号排序、峰检测）+ 三类外部验证（ClinVar、GTEx eQTL、PBMC caQTL），并针对模态坍塌问题进行了诊断性分析与归一化策略的对比验证。
- **充分性评估**：
  - 从任务多样性看，覆盖了从峰信号检测到变异/调控位点评分等不同层次的功能评估，较全面地检验了嵌入的生物学可用性；
  - 外部验证为跨数据集泛化提供了证据，增强了结论可信度；
  - 峰检测AUPRC大幅提升，数字化结果清晰且具有说服力。
  - 但受限于摘要/元数据，无法从已给内容确认是否包含多个随机种子统计、显著性检验、若干组任务的表格细节以及所有消融实验（例如不同归一化方案比较、不同融合深度等）。总体来看实验设计是合理且较充分的，但细节层面可能需要全文确认。

## 6. 主要结论与发现

- **异质模态对齐坍缩是可诊断的问题，且可通过全局归一化显著缓解**。这种抗坍缩策略使模型能有效联合学习稀疏调控信号与密集序列表示。
- **多模态联合嵌入全面超越DNA-only基线**：尤其在峰检测任务上，AUPRC提升4.6倍；调控活性预测和调控信号排序也得到改善。
- **嵌入具有通用性和可复用性**：在ClinVar、GTEx eQTL和PBMC caQTL外部数据集中进一步获得更优结果，表明学习到的窗口级表征不局限于特定任务或特定细胞环境。
- **框架具备可扩展性**：设计上不依赖特定模态，可扩展到除染色质可及性之外的其他调控模态（如组蛋白修饰、甲基化、转录因子结合等），为多模态DNA基础模型建立方法学平台。

## 7. 优点

- **精准定位了现有方法的关键空白**：不只是提出新架构，而是指出“任务特定多模态模型”和“序列-only基础模型”之间的断层，并以自监督方式弥合。
- **显式诊断模态坍塌问题并在方法上给出有效解法**：全局归一化作为简洁、可推广的模块，为解决异质基因组模态融合提供了适用性强的思路。
- **强调嵌入复用，而非单一任务精度**：这使得该模型可作为通用基础设施，服务于广泛的基因组下游分析。
- **实验覆盖较全面**：从任务性能到外部独立验证，形成了“内部分析+外部验证”的证据链；峰检测AUPRC提升4.6倍是非常具体的量化信号。
- **方法具备可扩展性**：框架对数据形态（局部与全局可及性信号）的要求灵活，可推广至更多调控模态。

## 8. 不足与局限

- **算力与训练细节未提及**：缺少模型规模、训练资源配置与时间成本的信息，难以为后续研究者提供可复现的训练预算参考。
- **数据模态相对有限**：所融合的调控信息均为染色质可及性（局部+全局），尚未展示在组蛋白修饰、甲基化或转录因子ChIP-seq等其他重要表观遗传模态上的表现。
- **下游任务类型仍有边界**：实验集中在调控功能预测、信号排序和峰检测；未包括变异致病性分类、单细胞分辨率分析、长程调控关系建模等更大范围的应用，因此对“可复用基础模型”的普适性论证仍有限。
- **异质模态覆盖度**：论文主要解决染色质可及性信号与序列的融合问题，对于更多模态的组合灵活性以及新模态加入对模型稳定性的影响，尚未给出更多证据。
- **泛化风险的潜在来源**：外部验证使用了ClinVar、eQTL、caQTL，多集中于常见变异与中等规模样本，对于罕见变异或不同人群/组织中的表现仍需进一步探索。
- **“可扩展至更多模态”当前更多是概念性主张**：框架虽具备扩展潜力，但未给出多模态扩展后的实验证据或更复杂的模态交互分析（如模态缺失、模态冲突等情况）。

（完）
