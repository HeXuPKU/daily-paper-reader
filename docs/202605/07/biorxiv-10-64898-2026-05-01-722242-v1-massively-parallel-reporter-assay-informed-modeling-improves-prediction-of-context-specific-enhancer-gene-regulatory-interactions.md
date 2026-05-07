---
title: Massively parallel reporter assay-informed modeling improves prediction of context-specific enhancer-gene regulatory interactions
title_zh: 大规模并行报告基因分析引导的建模改进了对特定背景下增强子-基因调控相互作用的预测
authors: "DeGroat, W., Kreimer, A."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.01.722242v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 将MPRA功能基因组学数据与基因组规模的调控模型整合
tldr: 增强子在特定背景下的基因表达调控中起关键作用，但其靶基因预测仍具挑战。本研究提出了MPRabc模型，通过整合大规模并行报告基因检测（MPRA）活性、序列特征、表观基因组信号及3D染色质图谱，并结合CRISPR扰动数据进行训练。该模型在预测增强子-基因（E-G）相互作用方面优于现有方法，成功识别了多种细胞系中的谱系特异性调控程序，为解析非编码变异的功能提供了有力工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的增强子-基因预测框架缺乏捕捉特定细胞背景下相互作用的分辨率，且未能充分整合MPRA提供的顺式调控活性数据。
method: 开发了MPRabc模型，该模型融合了预测的MPRA活性、序列衍生特征、表观遗传信号、3D染色质接触图谱以及CRISPR扰动训练数据。
result: MPRabc在验证的调控相互作用基准测试中优于现有最先进模型，并成功在K562、HepG2和hiPSC细胞系中识别出关键的转录因子驱动因子和调控网络。
conclusion: 整合MPRA信息的建模策略是解码增强子功能并跨细胞背景关联非编码变异与基因调控机制的一种可扩展且高效的方法。
---

## 摘要
增强子是驱动特定背景下基因表达的顺式调控元件，但其靶基因和作用模式在很大程度上仍未得到解决。由于大多数疾病相关变异位于非编码调控 DNA 中，准确的、细胞类型特异性的增强子-基因（E-G）映射对于理解遗传风险至关重要。然而，目前的 E-G 预测框架缺乏捕捉此类特定背景相互作用的分辨率。大规模并行报告基因分析（MPRA）提供了顺式调控活性的测量，但将其整合到全基因组规模的 E-G 模型中一直受到限制。在这里，我们介绍了 MPRabc，这是一种由 MPRA 引导的模型，可改进 E-G 相互作用的预测。MPRabc 将预测的 MPRA 活性、序列衍生的调控特征、表观基因组信号和三维染色质接触图谱与基于 CRISPR 的扰动训练数据相结合。与经过验证的调控相互作用进行的基准测试表明，MPRabc 的性能优于现有最先进的模型。我们为 K562、HepG2 和 hiPSC 细胞系生成了高分辨率的 E-G 网络，并应用基于图的框架来识别调控架构、映射性状相关变异和表达定量性状位点，并解析增强子活性的转录因子驱动因素。在不同背景下，我们准确地恢复了谱系定义的调控程序，包括 K562 中的 GATA1::TAL1、HepG2 中的 HNF1A/B 以及 hiPSC 中的 POU 因子回路。总之，这些结果确立了 MPRA 引导的建模作为一种可扩展的策略，用于解码增强子功能并将非编码变异与跨细胞背景的基因调控机制联系起来。

## Abstract
Enhancers are cis-regulatory elements that drive context-specific gene expression, yet their target genes and modes of action remain largely unresolved. Because most disease-associated variants lie in non-coding regulatory DNA, accurate, cell type-specific enhancer-gene (E-G) mapping is essential for understanding genetic risk. However, current E-G prediction frameworks lack the resolution to capture such context-specific interactions. Massively parallel reporter assays (MPRAs) provide measurement of cis-regulatory activity, but their integration into genome-scale E-G models has been limited.

Here, we introduce MPRabc, an MPRA-informed model that improves E-G interaction prediction. MPRabc integrates predicted MPRA activity, sequence-derived regulatory features, epigenomic signals, and three-dimensional chromatin contact maps with CRISPR-based perturbation training data. Benchmarking against validated regulatory interactions shows that MPRabc outperforms state-of-the-art models. We generated high-resolution E-G networks for K562, HepG2, and hiPSC cell lines and applied a graph-based framework to identify regulatory architecture, map trait-associated variants and expression quantitative trait loci, and resolve transcription factor drivers of enhancer activity. Across contexts, we accurately recovered lineage-defining regulatory programs, including GATA1::TAL1 in K562, HNF1A/B in HepG2, and POU factor circuits in hiPSCs.

Together, these results establish MPRA-informed modeling as a scalable strategy for decoding enhancer function and linking non-coding variants to gene regulatory mechanisms across cellular contexts.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **MPRabc** 的新型计算模型，旨在通过整合大规模并行报告基因分析（MPRA）数据来提高特定细胞背景下增强子-基因（E-G）调控相互作用的预测准确性。

以下是对该论文的结构化总结：

### 1. 核心问题与整体含义
*   **研究动机**：人类基因组中大多数与疾病相关的遗传变异位于非编码区的增强子内。然而，准确识别这些增强子在特定细胞类型中调控哪些靶基因（即 E-G 映射）仍然是一个重大挑战。
*   **核心问题**：现有的预测模型（如 ABC 模型）主要依赖表观基因组信号和 3D 染色质接触数据，但在捕捉特定细胞背景下的调控活性方面分辨率不足。
*   **整体含义**：论文提出将 MPRA 这种能够直接测量 DNA 序列调控活性的功能基因组学数据整合进预测框架，以弥补传统模型在功能活性表征上的短板。

### 2. 方法论
*   **核心思想**：在监督学习框架下，将序列衍生的调控特征（通过深度学习模型预测）与传统的表观遗传和空间结构特征相结合。
*   **关键技术细节**：
    *   **候选元件定义**：利用 DNase-seq 峰值定义候选顺式调控元件（CREs）。
    *   **特征提取**：
        *   **MPRALegNet**：一个卷积神经网络（CNN），用于预测序列在特定细胞系中的 MPRA 活性（log2 RNA/DNA 比值）。
        *   **Sei**：一个深度学习框架，用于预测序列的 21,907 种表观基因组特征（如组蛋白修饰、TF 结合概率）。
    *   **模型构建**：基于 **ENCODE-rE2G** 框架，采用带 L2 正则化的逻辑回归模型。
    *   **整合流程**：将预测的 MPRA 活性、Sei 衍生的调控概率、DNase-seq 信号、H3K27ac 信号以及 Hi-C 接触频率作为输入特征。
    *   **下游分析**：开发了 **E-P-INAnalyzer** 工具包，利用 Louvain 算法进行社区检测，识别调控子结构（模块）。

### 3. 实验设计
*   **数据集/场景**：主要针对 K562（人慢性髓系白血病细胞）、HepG2（人肝癌细胞）和 hiPSC（人诱导多能干细胞）三种细胞系。
*   **Benchmark（基准）**：使用 Gschwind 等人汇总的 **CRISPRi 扰动金标准数据集**（包含 10,356 个经过实验验证的 E-G 对，其中 471 个为正样本）。
*   **对比方法**：
    *   **ABC 模型**（Activity-by-Contact）。
    *   **ENCODE-rE2G**（原版监督学习模型）。
    *   其他 7 种主流 E-G 预测模型（如 GraphReg, DeepSEA 等）。
*   **消融实验**：分别测试了仅添加 Sei 特征、仅添加 MPRALegNet 特征以及全模型（MPRabc）的性能差异。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的硬件配置（如 GPU 型号、数量）或具体的训练时长。
*   **实现细节**：提到使用了预训练的 MPRALegNet 和 Sei 模型权重，这表明推理过程的算力需求主要集中在特征提取阶段。

### 5. 实验数量与充分性
*   **实验规模**：
    *   在 K562 上进行了全面的基准测试和消融实验。
    *   在三种细胞系中生成了全基因组规模的 E-G 网络。
    *   进行了 1,000 次染色体分层置换检验（Permutation Test）以验证变异富集。
    *   对 755 个转录因子基序（TFBM）进行了富集分析。
*   **充分性评价**：实验设计较为充分且客观。通过交叉验证、消融实验以及与独立实验数据（eQTL、GWAS 变异）的关联分析，多维度验证了模型的可靠性。

### 6. 主要结论与发现
*   **性能领先**：MPRabc 的 AUPRC 达到 **0.707**，显著优于 ABC 模型（0.612）和 ENCODE-rE2G（0.634），是目前同类输入条件下性能最优的模型。
*   **特征贡献**：消融实验证明，Sei 提供的特征贡献了主要的预测增益，而 MPRALegNet 提供的单一特征具有极高的信息密度。
*   **生物学发现**：
    *   成功识别了 K562 中的 **GATA1::TAL1**、HepG2 中的 **HNF4A/HNF1A** 以及 hiPSC 中的 **POU2F1::SOX2** 等关键谱系驱动因子。
    *   证明了预测的 E-G 相互作用与血液性状、肝酶水平相关的 GWAS 变异以及组织特异性 eQTL 具有显著的一致性。

### 7. 优点
*   **多模态整合**：成功将“序列-功能”预测模型（MPRA）与“活性-接触”模型（ABC）结合。
*   **高分辨率**：相比传统模型，能更精准地识别特定细胞背景下的功能性增强子。
*   **工具链完整**：不仅提供了预测模型，还配套了用于网络分析和变异解释的工具包（E-P-INAnalyzer）。

### 8. 不足与局限
*   **数据依赖性**：MPRALegNet 目前仅在少数细胞系中有训练数据，限制了 MPRabc 向更多罕见细胞类型的直接迁移。
*   **代理偏差**：在 hiPSC 的研究中，由于缺乏直接数据，使用了 H1 hESC 作为部分特征的代理，可能引入潜在的生物学偏差。
*   **黑盒属性**：虽然使用了逻辑回归提高了一定解释性，但特征提取阶段依赖复杂的深度学习模型，难以直观解释特定碱基变化如何通过 MPRA 活性影响最终的 E-G 评分。
*   **实验验证限制**：虽然在 K562 有大量 CRISPRi 数据验证，但在 HepG2 和 hiPSC 上的验证主要依赖于统计富集（如 eQTL），缺乏同等规模的直接扰动实验支持。

（完）
