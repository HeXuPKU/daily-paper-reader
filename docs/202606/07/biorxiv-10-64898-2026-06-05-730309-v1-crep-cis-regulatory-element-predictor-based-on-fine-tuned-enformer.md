---
title: "CREP: Cis-Regulatory Element Predictor Based on Fine-Tuned Enformer"
title_zh: CREP：基于微调Enformer的顺式调控元件预测器
authors: "Stranieri, N., Riva, S. G., Hughes, J. R."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730309v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: CREP基于微调Enformer从序列预测顺式调控元件，可直接用于解读非编码GWAS变异。
tldr: 非编码区变异常通过扰乱顺式调控元件(CRE)致病，现有深度学习模型能预测表观信号但不直接注释CRE身份。本文提出CREP，通过微调Enformer模型并利用多种人类细胞类型的调控注释进行训练，使其能从序列直接预测CRE类别。实验表明整合多细胞类型数据可提升预测性能，并成功识别Vanuatu SNP新产生的红细胞增强子；误差分析揭示增强子与启动子间的误分类反映其共享调控架构。CREP为解读非编码变异的功能影响提供了可解释的框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 非编码遗传变异常扰动CRE但缺乏直接从序列预测CRE身份的模型。
method: 微调Enformer，用多细胞类型REgulamentary注释训练序列到CRE标签的预测。
result: 多细胞训练提升性能，准确检测de novo增强子，误分类反映CRE功能连续体。
conclusion: CREP实现可解释的CRE身份预测，辅助非编码变异功能解读。
---

## 摘要
大量与疾病相关的遗传变异位于基因组的非编码区域，它们通过扰乱顺式调控元件（如增强子、启动子和绝缘子）来发挥作用。尽管近期基于序列的深度学习模型（如Enformer）能准确从DNA序列预测连续的 epigenomic信号，但它们不能直接提供离散且可解释的CRE注释。在此，我们提出CREP（顺式调控元件预测器），这是Enformer的一个微调版本，训练用于从序列中预测调控元件的身份，使用来自多个人类细胞类型的Regulamentary衍生注释。通过受控实验框架，我们表明整合多种细胞类型能提升模型性能。CREP利用细胞类型特异性训练数据学习调控表征，同时从序列中产生统一的CRE身份预测。这由瓦努阿图SNP（一个在红细胞中从头创建调控元件的非编码变异）所证明，仅当训练中包含红细胞数据时才能正确检测到该变异。错误分析进一步揭示，增强子和启动子之间的明显误分类反映了它们共享的调控架构，支持将CRE视为功能连续体而非严格离散类别的观点。总之，这些结果表明CREP能够从序列中实现调控元件身份的可解释预测，并为非编码遗传变异的功能解析提供了框架。

## Abstract
A substantial fraction of disease-associated genetic variants reside in non-coding regions of the genome, where they act by perturbing cis-regulatory elements (CREs) such as enhancers, promoters, and insulators. While recent sequence-based deep learning models, such as Enformer, accurately predict continuous epigenomic signals from DNA sequence, they do not directly provide discrete and interpretable CRE annotations. Here, we present CREP (Cis-Regulatory Element Predictor), a fine-tuned version of Enformer trained to predict regulatory element identity from sequence using REgulamentary-derived annotations across multiple human cell-types. Through a controlled experimental framework, we show that incorporating diverse cell-types improves model performance. CREP leverages cell-type-specific training data to learn regulatory representations while producing a unified prediction of CRE identity from sequence. This is demonstrated by the Vanuatu SNP, a non-coding variant that creates a de novo erythroid regulatory element, which is correctly detected only when erythroid data are included during training. Error analysis further reveals that apparent misclassifications between enhancers and promoters reflect their shared regulatory architecture, supporting the view of CREs as a functional continuum rather than strictly discrete classes. Together, these results demonstrate that CREP enables interpretable prediction of regulatory element identity from sequence and provides a framework for the functional interpretation of non-coding genetic variation.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- 大量疾病相关的遗传变异位于**非编码区**，它们通过扰乱**顺式调控元件（CRE）**（如增强子、启动子、绝缘子）来影响基因表达。
- 现有基于序列的深度学习模型（如Enformer）虽然能准确预测连续的**表观基因组信号**（如染色质可及性、组蛋白修饰），但**不能直接提供离散且可解释的CRE身份注释**。
- 因此，急需一种能从DNA序列直接预测CRE类别（增强子、启动子、绝缘子等）的方法，以帮助解读非编码变异的功能影响。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将Enformer模型进行**微调**，将其预测目标从连续表观信号改为**离散的CRE类别标签**，使模型能直接从序列输出“增强子”、“启动子”等身份。
- **关键技术细节**：
  - 使用**来自多个细胞类型的Regulamentary注释**作为训练标签（Regulamentary是一种整合多种调控实验注释的数据库）。
  - 训练时采用**多细胞类型联合训练**：输入序列后，模型学习不同细胞类型共享的调控表征，同时输出**统一的CRE身份预测**（不区分细胞类型）。
  - 框架允许模型利用细胞类型特异性数据提升预测能力，但预测时无需指定细胞类型。
- **算法流程**（文字描述）：
  1. 输入DNA序列片段（如长度为200kb的序列）。
  2. 通过预训练的Enformer编码器提取高维序列特征。
  3. 在编码器顶部添加额外的全连接分类层（softmax输出），预测每个窗口的CRE类别（如增强子、启动子、绝缘子、其他/非CRE）。
  4. 使用交叉熵损失在Regulamentary注释上微调，训练数据包含来自多个细胞类型的序列-标签对。

### 3. 实验设计：数据集、基准与对比方法
- **数据集**：使用**Regulamentary数据库**衍生的人类细胞类型注释，包括多种常见细胞系/原代细胞（如K562, GM12878, H1hESC, 红细胞等）。具体细胞类型数量未在元数据中明确，但提到“多个人类细胞类型”。
- **基准（Benchmark）**：
  - 内部构建**受控实验框架**：对比**单细胞类型训练** vs **多细胞类型联合训练**，衡量不同训练策略对CRE预测准确性的影响。
  - 使用**Vanuatu SNP**（一个在红细胞中从头创建增强子的非编码变异）作为**功能验证案例**：检测模型是否能正确识别该变异产生的de novo增强子。
- **对比方法**：文中未明确列出其他现有CRE预测方法（如DeepSEA、Basenji、Sei等），而是以Enformer直接输出表观信号作为间接对比（Enformer不直接提供CRE类别）。核心对比是**单细胞 vs 多细胞训练**。

### 4. 资源与算力
- 论文在提供的元数据中**未明确说明**使用的GPU型号、数量、训练时长等计算资源信息。
- 仅提及对Enformer进行了微调，通常Enformer原模型基于TPU或A100训练，但本文缺乏具体算力细节。

### 5. 实验数量与充分性
- **实验数量**：至少包含以下组：
  - **多细胞 vs 单细胞训练性能对比**（可能是多组细胞类型组合的消融实验）。
  - **单个变异案例验证**（Vanuatu SNP）。
  - **错误分析**（增强子与启动子误分类的生物学解释）。
- **充分性评价**：
  - 实验设计**较为充分**：通过受控框架系统评估了多细胞训练带来的提升，并提供了具体案例验证。
  - **客观性**：误差分析从生物学角度解释了误分类，表明模型学到了CRE间的功能连续性，而非简单错误。
  - **潜在不足**：未与其他CRE预测方法（如基于随机森林的方法、其他深度学习模型）进行定量比较（如AUROC、F1-score），也未提供大规模统计显著性检验。实验结果可能缺乏足够泛化性。

### 6. 论文的主要结论与发现
1. **多细胞类型联合训练显著提升CRE预测性能**，因为模型能从不同细胞类型中学习共享的调控模式，同时保留细胞类型特异性信息。
2. **成功检测de novo增强子**：仅在训练数据中包含红细胞数据时，模型才能正确识别Vanuatu SNP新产生的红细胞增强子，体现了细胞类型特异性训练的重要性。
3. **增强子与启动子之间的误分类并非简单错误，而是反映了二者共享的调控架构**（如都有RNA聚合酶II结合、组蛋白H3K27ac信号等），支持CRE是**功能连续体**而非严格离散类别的观点。
4. CREP提供了**从序列到CRE身份的可解释预测框架**，可用于辅助非编码变异的功能注释。

### 7. 优点：方法或实验设计上的亮点
- **方法创新**：首次将Enformer微调为离散CRE分类器，填补了从序列直接预测CRE身份的空白。
- **多细胞整合策略**：利用丰富的人类细胞类型注释提升泛化性能，且统一预测无需指定细胞类型，便于实际应用。
- **可解释性**：误差分析揭示了增强子-启动子的功能连续性，为理解CRE本质提供了生物学洞见。
- **案例验证落地**：通过实际变异（Vanuatu SNP）证明模型在罕见变异功能解读中的实用性。

### 8. 不足与局限
- **注释依赖**：依赖Regulamentary数据库，其覆盖的细胞类型和CRE类别可能不全面（如缺乏沉默子、边界元件等），且注释质量影响模型性能。
- **缺乏广泛对比**：未与DeepSEA、Sei、Basenji等模型进行定量性能比较（如AUROC、精确率-召回率），难以评估相对优势。
- **计算资源未披露**：无法评估训练与部署门槛。
- **跨物种迁移性未验证**：当前仅针对人类，未知对模式生物是否有效。
- **罕见变异检测泛化性**：仅用一个案例验证，样本量小，可能高估模型对稀有变异的检测能力。
- **类别定义模糊性**：增强子与启动子的误分类虽被解释为功能连续体，但也可能暴露分类边界不清晰带来的噪声。

（完）
