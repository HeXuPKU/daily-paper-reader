---
title: "OmicsNavigator: An auditable scientific partner for scalable hypothesis validation in spatial omics"
title_zh: OmicsNavigator：一个可审计的科学伙伴，用于空间组学中可扩展的假设验证
authors: "Li, Y., Vakharia, N., Liang, W., Mayer, A. T., Luo, R., Trevino, A. E., Wu, Z."
date: 2026-06-14
pdf: "https://www.biorxiv.org/content/10.1101/2025.07.21.665821v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 基于大语言模型的自主系统用于空间组学数据分析，实现零样本生物标志物检索
tldr: 空间组学高维数据难以转化为可验证的生物学发现。OmicsNavigator是一个基于大语言模型的自主系统，直接推理视觉和分子多模态数据，进行知识引导的结构注释。其可将高维数据转为文本解释，实现零样本语义检索与患者级疾病特征重建，并通过预注册蓝图进行客观假设验证。在多种病理数据集上验证后，系统能生成可读的循证洞察，有望加速空间生物学发现。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决空间组学高维数据难以转化为可测试生物学假设的瓶颈。
method: 构建基于大语言模型的OmicsNavigator，直接处理空间组学的视觉与分子模态，进行知识引导注释和预注册假设验证。
result: 实现零样本语义检索、组织标志物重建，在糖尿病肾病等数据集上生成循证可读洞察。
conclusion: OmicsNavigator作为可审计的科研工具，能有效加速空间组学中的假设验证与生物学发现。
---

## 摘要
将高维、空间分辨的分子数据集转化为可验证的生物学发现仍然是研究的主要瓶颈。这里，我们提出了OmicsNavigator，一个由大型语言模型驱动的自主系统，用于空间组学数据的端到端数据探索和假设验证。OmicsNavigator直接对空间组学数据的多模态输入（包括视觉和分子特征）进行推理，以执行空间结构的知识引导注释。我们表明，通过将高维数据转化为文本解释，OmicsNavigator能够实现组织生物标志物的零样本语义检索，并从原始组学观察中重建患者水平的疾病概况。此外，OmicsNavigator具有一个由预注册、人工审计蓝图控制的目标假设验证引擎。通过跨多种病理条件（包括糖尿病肾病、肾移植排斥反应和COVID-19肺部病理）的数据集验证该系统，我们证明OmicsNavigator能够从空间组学数据中生成基于证据、人类可读的见解，具有加速空间生物学发现的潜力。

## Abstract
Translating high-dimensional, spatially resolved molecular datasets into testable biological findings remains a major research bottleneck. Here, we present Omic-sNavigator, an autonomous large language model-powered system for end-to-end data exploration and hypothesis validation on spatial omics data. OmicsNaviga-tor reasons directly over the multi-modal inputs of spatial omics data, including visual and molecular signatures, to perform knowledge-guided annotation of spatial structures. We show that by transforming high-dimensional data into textual interpretations, OmicsNavigator enables zero-shot semantic retrieval of tissue biomarkers and the reconstruction of patient-level disease profiles from raw omics observations. Furthermore, OmicsNavigator features an objective hypothesis validation engine governed by pre-registered, human-audited blueprints. By validating the system across datasets spanning diverse pathological conditions including diabetic kidney disease, kidney transplant rejection, and COVID-19 pulmonary pathology, we demonstrate that OmicsNavigator generates evidence-based, human-readable insights from spatial omics data, with potential to accelerate spatial biology discoveries.

---

## 论文详细总结（自动生成）

好的，遵照您的要求，以下是基于给定论文摘要和元数据生成的详细中文总结。

### 1. 论文的核心问题与整体含义
- **研究动机与背景**：空间组学技术能够生成高维度、空间分辨的分子数据，但将这些复杂数据转化为可验证的生物学发现是当前的主要瓶颈。传统分析方法往往难以直接处理视觉和分子多模态信息，且缺乏可审计的假设验证流程。
- **核心问题**：如何构建一个能够自主探索、解释空间组学数据，并进行客观、可重复假设验证的智能系统。
- **整体含义**：提出一个名为 **OmicsNavigator** 的、由大型语言模型（LLM）驱动的自主系统，旨在加速空间生物学发现。它通过将高维数据转化为文本解释，实现零样本检索与患者级特征重建，并通过预注册蓝图实现可审计的假设验证。

### 2. 论文提出的方法论
- **核心思想**：利用LLM直接对空间组学的多模态输入（视觉特征和分子特征）进行推理，执行知识引导的结构注释和端到端的假设验证。
- **关键技术细节**：
    - **知识引导的结构注释**：系统直接处理空间组学的视觉与分子特征，进行空间结构的自动标注。
    - **零样本语义检索**：通过将高维数据转化为文本解释，系统无需训练即可实现组织生物标志物的语义搜索。
    - **患者级疾病特征重建**：能够从原始组学数据中重建患者层面的疾病概况。
    - **目标假设验证引擎**：核心创新点。该引擎由**预注册（pre-registered）**、**人工审计（human-audited）**的蓝图（blueprints）控制，确保假设验证过程的客观性和可复现性。
- **公式或算法流程**：论文中无明确公式。流程可概括为：多模态输入 → LLM推理与知识引导注释 → 文本转化与语义检索 → 预注册蓝图控制下的假设验证 → 生成循证、人类可读的洞察。

### 3. 实验设计
- **使用了哪些数据集/场景**：
    - 糖尿病肾病（Diabetic Kidney Disease）
    - 肾移植排斥反应（Kidney Transplant Rejection）
    - COVID-19肺部病理（COVID-19 Pulmonary Pathology）
- **Benchmark与对比方法**：论文摘要中未提及具体的基准测试（benchmark）或被对比的其他方法。表明该研究可能以定性/案例验证为主，或尚未在公开基准上进行大规模定量比较。

### 4. 资源与算力
- **文中未明确说明**：摘要和元数据中未提及使用的GPU型号、数量、训练时长或任何算力资源信息。

### 5. 实验数量与充分性
- **实验组数**：在三个不同的病理数据集上进行了验证（糖尿病肾病、肾移植排斥、COVID-19肺部病理）。
- **充分性与客观性**：
    - **覆盖范围**：覆盖了三种不同的病理条件，具有一定多样性，但样本量（数据集规模）未知。
    - **消融实验**：未提及任何消融实验（如去除预注册蓝图、替换LLM等）来验证各组件的贡献。
    - **对比实验**：未进行与其他现有方法（如传统统计建模、其他AI工具）的公平对比。
    - **结论客观性**：实验设计依赖于预注册蓝图，这一机制增强了客观性，但实验结果本身仅为“生成基于证据、人类可读的洞察”，缺乏定量指标（如准确率、F1分数、检索精确率等）的支撑。

### 6. 论文的主要结论与发现
- OmicsNavigator能够有效处理空间组学的高维、多模态数据，实现**零样本语义检索**和**组织标志物重建**。
- 系统能够生成**循证、人类可读的洞察**，有助于加速空间生物学发现。
- 其**可审计的假设验证**引擎（基于预注册蓝图）是区别于其他黑箱方法的关键优势。

### 7. 优点
- **方法创新性**：将LLM应用于空间组学的端到端分析，并引入**预注册蓝图**进行假设验证，增强了可复现性和可信度。
- **零样本能力**：无需针对特定组织或疾病重新训练即可进行语义检索，节省了标注成本。
- **可解释性**：输出为人类可读的文本洞察，而非简单的预测标签，便于领域专家理解与审阅。
- **多模态处理**：能够同时推理视觉和分子特征，贴近空间组学的数据本质。

### 8. 不足与局限
- **实验验证不充分**：
    - 缺乏**定量基准对比**，未能展示在标准指标（如检索精度、分类准确率）上的性能。
    - **无消融实验**，难以验证各模块（尤其是LLM推理、蓝图验证）的具体贡献。
    - 数据集数量（3个）虽有一定广度，但缺乏深度（每个数据集的具体规模、样本量不详）。
- **偏差风险**：
    - LLM本身可能引入知识偏差或幻觉（hallucination），论文未明确评估或缓解这一问题。
    - 预注册蓝图虽然增强了客观性，但其设计是否覆盖所有可能的假设空间仍存疑。
- **应用限制**：
    - **算力与成本**：未讨论LLM推理所需的计算成本，在大型空间组学数据集上可能效率较低。
    - **可扩展性**：未说明系统如何处理百万级细胞或斑点的超大规模数据。
- **资源描述缺失**：未提供任何算力信息，不利于后续复现和效率评估。

（完）
