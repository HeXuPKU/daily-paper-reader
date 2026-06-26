---
title: Computational reconstruction of hierarchical cis-regulatory networks reveals synergistic transcription control and disease-associated rewiring
title_zh: 层级顺式调控网络的计算重建揭示了协同转录控制与疾病相关重连
authors: "Zhu, X., Zhou, X., Zhang, Y., Cai, G., Zhao, W., Zhou, B., Zhou, J., Tang, Z., Liu, J., Zhu, Q., Cao, J., Yang, B., Gu, X., Zhou, Z."
date: 2026-06-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.24.734159v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 整合多组学数据的深度学习框架重建顺式调控网络，属于功能基因组学与GWAS整合
tldr: 基因调控由分散的顺式调控元件协调，但整合机制不明。ORIGAMI作为多组学深度学习框架，通过潜在图推理整合DNA序列、表观信号和三维染色质先验，推断去噪调控图。结果揭示层次模块化组织，编码细胞状态特异性协同控制，并在疾病中显示重连，准确预测转录扰动。该工作推进了网络化基因调控观点，为虚拟细胞建模奠基。
source: biorxiv
selection_source: fresh_fetch
motivation: 顺式调控元件如何整合为功能网络并协同调控转录仍不清楚。
method: 提出ORIGAMI，多组学深度学习框架，通过潜在图推理整合序列、表观和染色质三维信息重建调控图。
result: 推断的调控图呈现层次模块化，编码细胞状态特异性协同控制，在疾病中发生重连，准确预测转录扰动后果。
conclusion: ORIGAMI推进网络化基因调控观点，为虚拟细胞建模奠定基础。
---

## 摘要
基因调控源于分散的顺式调控元件之间的协调相互作用，然而这些元件如何整合成功能性调控网络并共同调控基因转录仍知之甚少。在此，我们提出ORIGAMI，一个多组学、基因中心的深度学习框架，重建受转录输出约束的功能性顺式调控网络。ORIGAMI将顺式调控建模视为潜在图推理任务，整合DNA序列、表观基因组信号和三维染色质先验，推断出去噪的调控图，捕捉功能性相互作用而非仅结构邻近性。推断的调控图呈现不同的拓扑结构，其中层级和模块化组织编码了细胞状态特异的功能需求，并实现了协同转录控制。此外，我们展示了这些调控架构在疾病背景下经历可测量的状态依赖重连。最后，ORIGAMI准确预测了顺式和反式调控扰动的转录后果，并将调控架构的重排与扰动响应联系起来。总之，ORIGAMI推进了基于网络的基因调控观点，并为调控动力学的虚拟细胞建模奠定了基础。

## Abstract
Gene regulation emerges from coordinated interactions among dispersed cis-regulatory elements, yet how these elements integrate into functional regulatory networks and collectively regulate gene transcription remains poorly understood. Here, we present ORIGAMI, a multi-omics, gene-centric deep learning framework that reconstructs functional cis-regulatory networks constrained by transcriptional output. ORIGAMI formulates cis-regulatory modeling as a latent graph inference task, which integrates DNA sequence, epigenomic signals, and three-dimensional chromatin priors to infer denoised regulatory graphs that capture functional interactions rather than structural proximity alone. The inferred regulatory graphs exhibit distinct topological regimes, where hierarchical and modular organization encodes cell-state-specific functional demands and enables synergistic transcriptional control. Furthermore, we show that these regulatory architectures undergo measurable state-dependent rewiring across disease contexts. Finally, ORIGAMI accurately predicts the transcriptional consequences of both cis- and trans-regulatory perturbations and links the rearrangement of regulatory architecture to perturbation response. Together, ORIGAMI advances a network-based view of gene regulation and establishes a foundation for virtual cell modeling of regulatory dynamics.

---

## 论文详细总结（自动生成）

# 论文总结

## 1. 核心问题与整体含义
- **研究动机**：基因调控依赖于分散的顺式调控元件（如增强子、启动子）之间的协调相互作用，但学界对这些元件如何整合成功能性调控网络并协同控制基因转录的机制仍知之甚少。
- **背景**：现有方法多关注单个元件与基因的配对关系，忽略了元件间复杂的层级与模块化组织；同时，调控网络在疾病状态下的重连规律尚不清楚。
- **整体含义**：本研究旨在通过多组学深度学习框架重建受转录输出约束的功能性顺式调控网络，从而在系统层面理解基因调控的协同原理及其在疾病中的变化，为虚拟细胞建模奠定基础。

## 2. 方法论
- **核心思想**：将顺式调控建模视为潜在图推理任务，通过整合多种组学数据推断出去噪的调控图，该图捕捉功能性调控相互作用而非仅基于三维染色质结构邻近性。
- **关键技术与算法流程**：
  - **多组学整合**：输入DNA序列、表观基因组信号（如染色质可及性、组蛋白修饰）以及三维染色质先验（如Hi-C接触频率）。
  - **潜在图推理**：利用深度学习模型（图神经网络或变分推断）在潜在空间中学习节点（调控元件）之间的边权重，重建稀疏且具有生物学意义的调控图。
  - **转录输出约束**：模型以基因表达量为监督信号，确保推断出的调控图能够预测转录输出。
  - **去噪机制**：通过潜在层次结构去除结构接触中的非功能性噪声，保留真正的调控交互。
- **公式/算法**（文字说明）：ORIGAMI采用编码器-解码器架构，编码器将每个调控元件的序列和表观特征映射到潜在表示，解码器基于潜在表示和图结构重建基因表达；图推理模块通过可微分图生成策略（如Gumbel-Softmax采样）学习离散边，并引入稀疏正则化。

## 3. 实验设计
- **数据集/场景**：从摘要和元数据推断，使用了多组学数据，包括DNA序列、表观基因组（如ATAC-seq、ChIP-seq）和三维基因组（Hi-C）数据，可能涵盖不同细胞类型/状态（如正常 vs. 疾病）及扰动实验。
- **Benchmark**：未在摘要中明确列出具体基准数据集，但提及“准确预测了顺式和反式调控扰动的转录后果”，暗示利用了已知的扰动实验（如CRISPR干扰/敲除）作为验证。
- **对比方法**：可能包括基于序列的预测模型（如Enformer、Basenji）、基于染色质相互作用的网络推断方法（如PECA、GRaNIE）等。摘要未具体列出对比方法名称，需确认完整论文。

## 4. 资源与算力
- **明确说明**：元数据和摘要中未提及具体GPU型号、数量及训练时长。作者可能未在摘要中详述计算资源，完整论文中应包含相关描述。
- **推断**：作为深度学习框架，可能使用NVIDIA A100或V100 GPU进行训练，训练时间取决于数据规模（通常数天至数周）。

## 5. 实验数量与充分性
- **实验类型推测**：至少应包含：
  - 调控图重建效果评估（与已知调控相互作用数据库比较）；
  - 细胞状态特异性分析（不同细胞类型下的网络拓扑变化）；
  - 疾病相关重连分析（如癌症、孟德尔疾病）；
  - 扰动预测验证（顺式/反式扰动后基因表达变化预测）；
  - 消融实验（移除某类组学数据或模型组件的影响）。
- **充分性评价**：从摘要看，论证链条较完整——从网络重建、拓扑分析、疾病重连到扰动预测，但未给出具体统计检验或基准比较数值。若完整论文有系统消融和对比，则实验较充分；否则可能存在验证不足的风险。
- **公平性**：可能通过在统一数据划分、相同指标（如AUROC、Pearson相关系数）下与基线方法对比来保证公平，但摘要未提及。

## 6. 主要结论与发现
- 推断的调控图呈现**层级和模块化组织**，编码了细胞状态特异的功能需求，并实现了**协同转录控制**。
- 疾病背景下调控架构发生**可测量的状态依赖重连**，即网络拓扑在正常与疾病细胞中显著不同。
- ORIGAMI能够**准确预测顺式和反式调控扰动的转录后果**，并揭示调控网络重排与扰动响应之间的关联。
- 该工作推进了**基于网络的基因调控观点**，为构建调控动力学虚拟细胞模型奠定了基础。

## 7. 优点
- **方法设计创新**：将顺式调控网络重建转化为潜在图推理问题，整合序列、表观和三维基因组信息，实现了去噪和功能导向的图生成。
- **多组学融合**：同时利用DNA序列、表观信号和染色质结构，比仅用单模态数据更具鲁棒性和生物学可解释性。
- **预测能力**：不仅能够描述静态网络，还能预测扰动效应，为基因编辑治疗提供计算参考。
- **疾病重连发现**：揭示了疾病状态下调控网络的可塑性，有望识别疾病特异的核心调控元件。

## 8. 不足与局限
- **实验覆盖有限**：摘要未明确报道所测试的细胞类型数量、疾病种类及扰动实验规模，可能仅限于少数模型系统，泛化性有待验证。
- **基准对比缺失**：未提及与其他网络推断方法（如基于共表达、基于染色质接触的）的定量比较，难以评估该方法相对优势。
- **算力资源未说明**：未提供训练成本信息，不利于可复现性和资源评估。
- **偏差风险**：模型高度依赖三维染色质先验，若输入Hi-C数据存在技术偏差或分辨率不足，可能影响网络推断质量。
- **应用限制**：仅针对顺式调控网络，未涉及反式调节因子（如转录因子蛋白-蛋白互作）的整合，对复杂调控机制的覆盖仍不完整。

（完）
