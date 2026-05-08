---
title: A high-resolution atlas of cattle regulatory variants and their cross-species activity in matched human cells
title_zh: 牛调控变异的高分辨率图谱及其在匹配人类细胞中的跨物种活性
authors: "Zhao, R., Plenderleith, L., Debnath, T., Owen, R., Pagie, L., Bisht, V., Metheringham, C., Marr, M., Powell, J., Talenti, A., Zhu, C., Paxton, E., Jensen, K., van Arensbergen, J., Connelley, T., Morrison, L., Hassan, M., Prendergast, J. G."
date: 2026-05-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.06.723179v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 将宽泛的关联信号细化为候选功能调节变异
tldr: 本研究利用MPRA和图基因组学技术，在牛及人类细胞中评估了超过1500万个变异，构建了牛调控变异的高分辨率图谱。研究鉴定了15万个表达调节变异，并开发了预测启动子活性的深度学习模型。通过跨物种对比，揭示了牛与人类调控语法的广泛保守性及物种特异性差异。该成果为识别牛性状改良的非编码因果变异提供了关键框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 由于缺乏高分辨率的功能图谱，识别影响牛复杂性状的非编码区因果变异具有挑战性。
method: 结合大规模并行报告基因检测（MPRA）与图基因组学，在牛和人类原代细胞中测量了超过15亿个DNA片段的转录活性。
result: 鉴定了超过15万个表达调节变异，并开发了能预测启动子活性的深度学习模型，同时揭示了跨物种间调控语法的广泛保守性。
conclusion: 该研究提供了牛调控变异的高分辨率图谱，为优先筛选和鉴定改善牛性状的非编码因果变异提供了重要框架。
---

## 摘要
识别牛复杂性状背后的因果非编码变异仍然具有挑战性，因为缺乏调控变异的高分辨率功能图谱。在本研究中，我们将大规模并行报告基因检测（MPRA）与图基因组学相结合，测量了跨越两个牛亚种的超过 15 亿个 DNA 片段的自主转录活性。在牛原代细胞中，我们检测了超过 1500 万个变异，并鉴定了超过 15 万个在牛 eQTL 和 GWAS 位点富集的表达调节变异。这使得能够将广泛的关联信号细化为一小部分候选功能性调控变异。我们的单倍型感知框架捕获了传统 eQTL 研究难以解析的罕见、多等位基因和紧密连锁的变异，并量化了较大变异对转录的不成比例影响。此外，我们利用这些数据训练了一个深度学习模型，该模型能直接从序列成功预测牛启动子活性。在匹配的人类原代细胞中对相同的牛 DNA 进行分析，揭示了启动子和增强子活性、等位基因效应以及调控语法的广泛保守性，支持了跨物种的注释和模型迁移。然而，物种依赖性效应在进化上较年轻的序列和 p53 家族基序中富集，突显了简单跨物种外推的局限性。总之，这些数据提供了牛调控变异的高分辨率图谱，并为优先排序用于牛性状改良的因果非编码变异提供了一个框架。

## Abstract
Identifying causal noncoding variants underlying complex traits in cattle remains challenging because high-resolution functional maps of regulatory variation are lacking. Here we combine massively parallel reporter assays with graph genomics to measure autonomous transcriptional activity from >1.5 billion DNA fragments spanning both cattle subspecies. In primary bovine cells, we assay >15 million variants and identify >150,000 expression-modulating variants enriched at cattle eQTL and GWAS loci. This enables the refinement of broad association signals to small sets of candidate functional regulatory variants. Our haplotype-aware framework captures rare, multi-allelic and tightly linked variants poorly resolved by conventional eQTL studies, and quantifies the disproportionate impact of larger variants on transcription. Furthermore, we use these data to train a deep-learning model that successfully predicts bovine promoter activity directly from sequence. Profiling the same cattle DNA in matched primary human cells reveals widespread conservation of promoter and enhancer activity, allelic effects and regulatory grammar, supporting the transfer of annotations and models across species. However, species-dependent effects are enriched in evolutionarily young sequences and p53-family motifs, highlighting the limits to simple cross-species extrapolation. Together, these data provide a high-resolution atlas of cattle regulatory variation and a framework for prioritising causal noncoding variants for cattle trait improvement.

---

## 论文详细总结（自动生成）

以下是对该论文的深度结构化总结：

### 1. 核心问题与整体含义
*   **研究背景**：牛（Cattle）的复杂性状（如产奶量、肉质、抗病性）受大量非编码区变异的影响。然而，传统的表达定量性状位点（eQTL）分析受限于连锁不平衡（LD），难以从成百上千个关联变异中精准识别出真正的因果调控变异。
*   **核心问题**：如何构建高分辨率的牛调控变异图谱，并理解这些调控逻辑在哺乳动物进化过程中（如牛与人之间）的保守性与差异？
*   **整体含义**：本研究通过大规模实验手段，为牛的基因组改良提供了从“关联信号”到“功能变异”的精准映射框架。

### 2. 方法论
*   **核心思想**：结合**大规模并行报告基因检测（MPRA）**与**图基因组学（Graph Genomics）**，在体外直接测量数千万个 DNA 片段的转录活性。
*   **关键技术细节**：
    *   **SuRE-MPRA 升级版**：利用随机剪切的基因组 DNA 构建文库，不依赖于预定义的候选区域，实现了全基因组覆盖。
    *   **图基因组比对**：为了克服单一参考基因组的偏差，研究者构建了包含两个牛亚种（普通牛 *Bos taurus* 和瘤牛 *Bos indicus*）的图基因组，确保变异检测的准确性。
    *   **单倍型感知框架**：通过捕获长片段 DNA，能够直接区分并测量不同等位基因（Haplotypes）的活性差异。
    *   **深度学习预测**：利用实验产生的海量数据，训练了一个基于卷积神经网络（CNN）的深度学习模型，旨在直接从 DNA 序列预测启动子和增强子的活性。

### 3. 实验设计
*   **细胞模型**：主要使用牛的原代巨噬细胞（Primary Macrophages），并将其与匹配的人类原代巨噬细胞进行对比。
*   **数据集规模**：
    *   测量了超过 **15 亿个** DNA 片段。
    *   涵盖了超过 **1500 万个** 遗传变异。
*   **Benchmark 与对比**：
    *   将 MPRA 鉴定的表达调节变异（EMVs）与已发表的牛 **eQTL** 数据和 **GWAS**（全基因组关联分析）信号进行重叠验证。
    *   对比了牛 DNA 序列在牛细胞环境与人类细胞环境中的活性表现，以评估跨物种调控语法的保守性。

### 4. 资源与算力
*   **算力说明**：论文中未明确列出具体的 GPU 型号（如 A100/V100）或具体的训练总时长。
*   **计算负载暗示**：考虑到处理 15 亿个片段的比对、图基因组的构建以及深度学习模型的训练，该研究显然消耗了极高规模的计算资源（高性能计算集群 HPC）。

### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了两个牛亚种的广泛遗传多样性，检测的变异数量（1500 万）在同类物种研究中处于领先地位。
*   **充分性评价**：
    *   **非常充分**：不仅做了牛内部的变异鉴定，还进行了跨物种的验证实验。
    *   **多维度验证**：通过与实际生物学信号（eQTL/GWAS）的对比，证明了体外实验结果在体内（In vivo）的相关性。
    *   **消融/对比**：分析了不同长度变异（SNVs vs Indels）的影响，实验设计逻辑严密。

### 6. 主要结论与发现
*   **鉴定大量 EMVs**：成功鉴定出超过 **15 万个** 具有表达调节功能的变异。
*   **精细定位能力**：MPRA 信号能显著缩小 GWAS 关联区域，将候选变异范围从数百个缩减至极少数几个。
*   **结构变异的影响**：发现较大的变异（如插入/缺失）对转录活性的影响不成比例地大于单核苷酸变异（SNVs）。
*   **跨物种保守性**：牛和人类在启动子/增强子活性、等位基因效应以及转录因子结合语法上表现出高度保守。
*   **物种特异性**：物种间的差异主要集中在进化上较年轻的序列以及特定的转录因子基序（如 p53 家族）上。

### 7. 优点
*   **高分辨率**：突破了传统遗传学研究中 LD 的限制，能够直接定位到功能位点。
*   **图基因组应用**：有效解决了牛亚种间高度多样性导致的参考基因组偏倚问题。
*   **跨物种迁移性**：证明了在人类中训练的调控模型在很大程度上可以迁移到牛的研究中，反之亦然。

### 8. 不足与局限
*   **组织特异性缺失**：实验主要在巨噬细胞中进行，可能无法捕捉到如乳腺、肌肉或神经系统特异性的调控元件。
*   **体外环境局限**：MPRA 质粒系统缺乏内源性的染色质三维结构（3D Genomics）和表观遗传环境，可能导致部分调控效应被误估。
*   **进化外推风险**：虽然大部分保守，但研究也指出对于进化较快的序列，简单的跨物种模型迁移可能存在偏差。

（完）
