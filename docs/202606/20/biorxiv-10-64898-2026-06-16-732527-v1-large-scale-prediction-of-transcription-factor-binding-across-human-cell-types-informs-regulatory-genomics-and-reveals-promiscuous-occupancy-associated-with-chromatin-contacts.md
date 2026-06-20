---
title: Large-scale prediction of transcription factor binding across human cell types informs regulatory genomics and reveals promiscuous occupancy associated with chromatin contacts
title_zh: 跨人类细胞类型的转录因子结合大规模预测为调控基因组学提供信息，并揭示与染色质接触相关的混杂占据
authors: "Sonder, E., Aymergen, I. G., Sun, J., Feuvrier, A., Schratt, G., Gapp, K., Bohacek, J., Robinson, M. D., Germain, P.-L."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.16.732527v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 使用ATAC-seq大规模预测转录因子结合的平台，为GWAS解释提供调控基因组学信息
tldr: 转录因子结合具有高度细胞类型特异性，实验测定所有TF在多种细胞类型中不可行。为此开发TFBlearner平台，基于ATAC-seq数据和生物动机特征工程，利用TF协同性和结合相似性预测未见过细胞类型中的结合。预测了1108个染色质相关蛋白在43种人类细胞类型中的结合，发现高占用率（HOT）区域与更多3D染色质接触相关，揭示了TF占用的混杂性和细胞类型特异性。
source: biorxiv
selection_source: fresh_fetch
motivation: 实验测定所有1600多种TF在数百种细胞类型中的结合不切实际，亟需可扩展的计算预测方法。
method: 开发TFBlearner平台，基于ATAC-seq数据，通过生物动机特征工程并利用TF协同性和跨细胞类型结合相似性进行预测。
result: 预测1108个染色质相关蛋白在43种人类细胞类型中的结合，观察到高占用率（HOT）区域具有细胞类型特异性且与更多3D染色质接触相关。
conclusion: 为调控基因组学提供大规模预测资源，并揭示TF占用的混杂性及其与染色质接触的联系。
---

## 摘要
我们对基因表达调控机制的理解受到我们对哪些转录因子在基因组何处结合的有限知识的阻碍，而这具有高度细胞类型特异性。虽然可以通过实验在全基因组范围内检测单个细胞类型中的单个转录因子的结合，但在数百种细胞类型中分析超过1600种转录因子的完整组合超出了实际可行性。在这项工作中，我们开发了一个简化平台TFBlearner，用于训练转录因子特异性模型并基于ATAC-seq数据预测结合。我们专注于生物学驱动的特征工程，并利用转录因子协同性和跨细胞类型的结合相似性，以可扩展的方式在未知细胞类型中实现最先进的结合预测。这使我们能够生成1108种染色质相关蛋白（其中960种为转录因子）在43种人类细胞类型（包括广泛使用的细胞系和代表所有主要人类细胞谱系的36种生理细胞类型）中的结合预测汇编。我们展示了模型如何额外提供对转录因子的生物学见解，以及如何将结合预测用于下游任务（如转录因子活性推断）。我们的研究还观察到转录因子占据的高度混杂性。为了探究非特异性占据，我们描述了跨细胞类型的拥挤或高占据区域，提供了其功能性的证据，并报告了重要的细胞类型特异性。最后，我们表明，跨细胞类型，拥挤区域参与更多的3D接触，并且拥挤启动子处的大部分转录因子占据可以解释为来自远端调控元件的束缚结合。

## Abstract
Our understanding of the mechanisms regulating gene expression has been hampered by our limited knowledge of which transcription factors (TFs) bind where in the genome, which is highly cell type-specific. While genome-wide TF binding can be experimentally assayed for individual TFs in individual cell types, profiling the full combinations of over 1600 TFs in hundreds of cell types is beyond practical reach. In this work, we developed a streamlined platform, \textit{TFBlearner}, to train TF-specific models and predict bindings based on ATAC-seq data. We focused on biologically-motivated feature engineering and harnessed TF cooperativity and binding similarity across cell types to achieve state of the art binding predictions in unseen cell types in a scalable fashion. This enabled us to generate a compendium of binding predictions for 1108 Chromatin-associated proteins, of which 960 TFs, across 43 human cell types including widely-used cell lines and 36 physiological cell types representing all major human cell lineages. We show how the models additionally provide biological insights on the TFs, and show how the binding predictions can be used in downstream tasks such as TF activity inference. Our study additionally led to the observation of high promiscuity in TF occupancy. To investigate aspecific occupancy, we characterized crowded or high-occupancy (HOT) regions across cell types, providing evidence of their functionality, and reporting important cell type-specificity. Finally, we show that, across cell types, crowded regions engage in more 3D contacts, and that most TF occupancy at crowded promoters can be explained as tethered bindings from distal regulatory elements.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：基因表达调控机制研究受限于对转录因子（TF）在基因组中结合位点的认知不足，而TF结合具有高度细胞类型特异性。实验测定所有1600多种TF在数百种细胞类型中的完整结合谱不切实际，亟需可扩展的计算预测方法。
- **整体含义**：开发一个基于ATAC-seq数据的预测平台TFBlearner，大规模预测跨细胞类型的TF结合，为调控基因组学提供资源，并揭示与染色质3D接触相关的混杂占据（HOT区域）的功能意义。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：利用ATAC-seq数据作为输入，通过生物学驱动的特征工程，并利用TF协同性与跨细胞类型的结合相似性，训练TF特异性模型，从而在未见过的细胞类型中实现结合预测。
- **关键技术细节**：
  - 特征工程：基于生物动机设计特征（如序列motif、染色质可及性、TF协同性等）。
  - 模型训练：为每个TF训练独立模型，利用跨细胞类型的共享信息（结合相似性）增强泛化能力。
  - 预测流程：输入ATAC-seq数据→提取特征→应用训练好的TF模型→输出全基因组结合预测。
  - 扩展性：可同时预测1108种染色质相关蛋白（含960种TF）在43种细胞类型中的结合。

### 3. 实验设计
- **数据集/场景**：
  - 使用ATAC-seq数据作为主要输入，覆盖43种人类细胞类型，包括广泛使用的细胞系以及代表所有主要人类细胞谱系的36种生理细胞类型。
  - 预测目标：1108种染色质相关蛋白（TF为主）的结合。
- **Benchmark**：摘要提及“state of the art binding predictions”，但未明确列出对比方法或基线。推测可能对比了ChIP-seq实验数据或其他计算方法（如基于motif的预测、深度学习模型等），但原文未详细说明。
- **对比方法**：未具体说明，可能隐含与现有基于序列或染色质可及性的预测方法比较。

### 4. 资源与算力
- **未明确说明**：论文摘要及元数据中未提及使用的GPU型号、数量或训练时长等具体算力信息。仅从可扩展性推断可能使用了高效计算框架，但缺乏细节。

### 5. 实验数量与充分性
- **实验数量**：
  - 主要实验：构建并评估了1108个蛋白的预测模型，覆盖43种细胞类型。
  - 下游分析：包括TF活性推断、HOT区域特征描述、与3D染色质接触的关联分析。
  - 可能包含消融实验（如特征重要性分析）或交叉验证，但摘要未详细列出。
- **充分性与客观性**：
  - 充分性：覆盖细胞类型和蛋白数量较大，具有一定代表性；但对模型性能的严格定量评估（如与ChIP-seq实验的精度/召回率对比）未在摘要中体现，削弱了结论的客观性。
  - 公平性：由于未提供对比方法的具体结果，难以判断是否公平比较。

### 6. 论文的主要结论与发现
- **主要结论**：
  1. 成功构建TFBlearner平台，基于ATAC-seq数据实现大规模、细胞类型特异的TF结合预测，达到先进水平。
  2. 观察到TF占用的高度混杂性（promiscuity），即多个TF在相同区域密集结合。
  3. 高占用率区域（HOT区域）具有细胞类型特异性，且与更多3D染色质接触相关，提示其功能性（如作为调控枢纽）。
  4. 拥挤启动子上的大部分TF占据可解释为来自远端调控元件的束缚结合（tethered binding）。
- **发现**：
  - 模型可用于TF活性推断等下游任务。
  - 提供了调控基因组学的大规模资源（预测谱汇编）。

### 7. 优点
- **方法亮点**：
  - 聚焦生物学驱动的特征工程，利用TF协同性和跨细胞类型相似性，提升预测的生物学可解释性和泛化能力。
  - 可扩展性强，能够一次性预测数百种蛋白在多种细胞类型中的结合，突破实验瓶颈。
  - 不仅输出预测，还提供生物学见解（如HOT区域功能、染色质接触关联）。
- **实验亮点**：
  - 覆盖细胞类型广泛（包括原代生理细胞），增加了结果的生态效度。

### 8. 不足与局限
- **实验覆盖**：
  - 预测性能的定量验证不足：未在摘要中展示与ChIP-seq等实验数据的直接精度/召回率对比，缺乏严格基准评估。
  - 对比方法不明确：无法判断是否与现有最优方法进行了公平比较。
- **偏差风险**：
  - 依赖ATAC-seq数据，而ATAC-seq本身存在偏好（如对开放染色质区域敏感），可能影响预测覆盖度。
  - 预测模型可能无法完全替代实验验证，尤其对于低表达或条件特异性TF。
- **应用限制**：
  - 仅覆盖43种人类细胞类型，远少于实际存在的数百种，迁移到其他细胞类型或物种需重新训练。
  - 算力资源未公开，其他研究者难以复现大规模预测过程。

（完）
