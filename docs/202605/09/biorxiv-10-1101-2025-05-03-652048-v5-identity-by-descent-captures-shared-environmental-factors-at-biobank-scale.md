---
title: Identity-by-descent captures Shared Environmental Factors at Biobank Scale
title_zh: 血缘同源性在生物样本库规模下捕捉共享环境因素
authors: "Marsico, F., Buonaiuto, S., Amos-Abanyie, E., Chinthala, L., Mohammed, A., Zahr, R., Regeneron Genetics Center,, Rooney, R., Williams, R. W., Davis, R. L., Finkel, T. H., Brown, C. W., Vacca, M., Prins, P., Colonna, V."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.1101/2025.05.03.652048v5.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 整合基因组和EHR数据以捕捉共享环境因素和人口结构
tldr: "该研究利用13,143名个体的基因组和电子健康记录数据，通过同源染色体片段（IBD）共享比例进行分层社区检测，将人群划分为精细的子社区。研究发现，IBD聚类不仅能揭示比传统祖先分类更细致的人口结构，还能有效捕捉共享的环境压力因素及其对健康的影响。这种方法超越了传统的种族分类，为精准医疗提供了一个可扩展的框架，能将生物库数据转化为揭示社会健康决定因素的见解。"
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的祖先分类难以捕捉影响健康的复杂环境和文化因素，需要一种更精细的方法来识别共享的环境暴露和社会健康决定因素。
method: "利用13,143名个体的基因组数据，基于同源染色体片段（IBD）共享比例，采用分层社区检测算法将人群划分为不同的社区和子社区。"
result: IBD定义的子社区在环境压力暴露和健康状况上存在显著差异，且这种差异在调整自述种族后依然存在，显示出其捕捉未测量环境因素的能力。
conclusion: IBD聚类能够同时捕捉遗传和环境健康决定因素，是比传统人口统计类别更有效的社会健康决定因素代理指标，有助于实现精准医疗。
---

## 摘要
谱系联系留下的痕迹不仅限于共享的遗传物质：亲属往往共享跨代持续的环境暴露和文化习俗。利用来自综合基因组学生物库（Biorepository for Integrative Genomics）的 13,143 名个体的基因组和电子健康记录数据，我们应用了一种层次化社区检测算法，根据基因组中血缘同源（IBD）共享的比例，将个体分为 4 个主要社区和 17 个子社区。这种方法捕捉到了超越传统祖先分类的精细人口结构。通过整合邻里级的地理数据与基于普查的环境指标，我们揭示了子社区之间环境压力暴露的不平等，这与健康状况的差异率相关，包括在污染负担较重的子社区中呼吸系统疾病患病率升高。通过干预性中介分析，我们发现子社区层面的超额风险大大超过了仅靠已测量的环境因素所能解释的范围，从而展示了基于 IBD 的分组所捕捉到的未测量共享暴露的贡献。在调整了自我报告种族的敏感性分析中，子社区层面的差异依然存在，这表明基于 IBD 的聚类捕捉到了超越通常作为健康社会决定因素代理指标的人口统计学类别的健康相关信息。我们实现了一个开源仪表板，用于交互式探索 IBD 定义的社区、疾病患病率和环境暴露。总之，我们证明了基于 IBD 的聚类共同捕捉了健康的遗传和环境决定因素，为精准健康和群体遗传学提供了一个可扩展的框架，将生物样本库数据转化为可操作的见解。

## Abstract
Genealogical ties leave traces beyond shared genetic material: relatives tend to share environmental exposures and cultural practices that persist across generations. Using genomic and electronic health record data from 13,143 individuals in the Biorepository for Integrative Genomics, we applied a hierarchical community detection algorithm to group individuals into four major communities and 17 subcommunities based on the proportion of their genome shared identical by descent (IBD). This approach captured a fine-scale demographic structure beyond traditional ancestry classifications. By integrating neighborhood-level geographic data with census-derived environmental metrics, we revealed unequal exposure to environmental stressors between subcommunities, which correlated with differential rates of health conditions, including elevated respiratory condition prevalence in subcommunities under greater pollution burden. Through an interventional mediation analysis we found that excess risk at the subcommunity-level substantially exceeded what measured environmental factors alone could explain. thus showing the contribution of unmeasured shared exposures that IBD-based grouping captures. Subcommunity-level disparities persisted in sensitivity analyses adjusting for self-reported race, indicating that IBD-based clustering captures health-relevant information beyond demographic categories commonly used as proxies for social determinants of health. We implemented an open-source dashboard for interactive exploration of IBD-defined communities, disease prevalence, and environmental exposures. Together, we demonstrate that IBD-based clustering jointly captures genetic and environmental determinants of health, offering a scalable framework for precision health and population genetics that translates biobank data into actionable insights.

---

## 论文详细总结（自动生成）

这篇论文题为《Identity-by-descent captures Shared Environmental Factors at Biobank Scale》，由 Marsico 等人发表。研究探讨了如何利用基因组中的血缘同源性（IBD）来识别共享环境暴露和健康风险的精细人群结构。

以下是对该论文的深度结构化总结：

### 1. 核心问题与整体含义
*   **研究动机**：传统的种族（Race）和祖先（Ancestry）分类在医学研究中常被用作健康社会决定因素（SDoH）的代理指标，但这些分类过于粗糙，无法捕捉复杂的环境暴露、文化习俗和地理聚集性。
*   **核心问题**：亲属不仅共享基因，还往往共享跨代持续的环境压力。研究旨在探索是否可以通过基因组中共享的 IBD 片段，在生物样本库规模下识别出比传统分类更精细的“社区”，并证明这些社区能有效捕捉未被测量的环境健康风险。

### 2. 论文提出的方法论
*   **核心思想**：利用个体间共享的 IBD 片段比例作为亲缘关系的度量，构建人群关联网络，并通过算法将其划分为具有相似遗传和环境背景的子社区。
*   **关键技术流程**：
    1.  **IBD 检测与网络构建**：对 13,143 名个体的基因组数据进行分析，计算两两之间的 IBD 共享比例。
    2.  **层次化社区检测**：应用层次化社区检测算法（Hierarchical Community Detection），将人群划分为 4 个主要社区和 17 个精细子社区。
    3.  **多模态数据整合**：将 IBD 社区与电子健康记录（EHR）、邻里级地理数据（Zip Code）以及基于普查的环境指标（如 EPA 的 EJScreen 污染数据）进行关联。
    4.  **中介分析**：采用干预性中介分析（Interventional Mediation Analysis），量化已测量环境因素（如空气污染）对子社区健康差异的解释程度，从而推断未测量因素的贡献。

### 3. 实验设计
*   **数据集**：来自综合基因组学生物库（Biorepository for Integrative Genomics, BIG）的 13,143 名个体。
*   **Benchmark/对比对象**：
    *   **自述种族（Self-reported Race）**：评估 IBD 聚类是否比种族标签提供更多信息。
    *   **传统祖先成分（PCA）**：对比 IBD 聚类与基于主成分分析的遗传结构。
*   **评估指标**：疾病患病率（如呼吸系统疾病）、环境压力暴露水平（污染、贫困率等）、优势比（OR）。

### 4. 资源与算力
*   **算力说明**：论文中未明确详细说明具体的 GPU 型号、数量或训练时长。考虑到其涉及 1.3 万人的 IBD 计算和社区检测，这类任务通常依赖高性能计算集群（HPC）而非单一 GPU 训练，主要消耗在于基因组数据的预处理和大规模矩阵运算。

### 5. 实验数量与充分性
*   **实验规模**：研究将人群细分为 17 个子社区，并针对每个社区进行了环境暴露和多种疾病患病率的关联分析。
*   **充分性与客观性**：
    *   进行了**敏感性分析**：在调整了自述种族后，子社区间的健康差异依然显著，证明了该方法的独立价值。
    *   **中介分析**：通过量化已知环境因素的贡献，客观地展示了 IBD 捕捉“隐性”环境因素的能力。
    *   **可视化工具**：开发了开源仪表板，增强了结果的可验证性和透明度。

### 6. 论文的主要结论与发现
*   **精细结构发现**：IBD 聚类揭示了远比传统祖先分类更细致的人口结构，能够反映近代的地理迁移和隔离。
*   **环境不平等**：不同子社区在环境压力（如空气污染、重金属暴露）上的暴露存在显著不平等。
*   **健康关联**：环境负担较重的子社区，其呼吸系统疾病等健康问题的患病率显著升高。
*   **超越已知因素**：中介分析显示，子社区的超额健康风险中，很大一部分无法由已测量的环境指标解释，说明 IBD 有效捕捉到了未被记录的共享社会和环境暴露。

### 7. 优点
*   **创新视角**：将 IBD 从单纯的遗传学工具扩展为社会健康决定因素（SDoH）的探测器。
*   **精准医疗框架**：提供了一个可扩展的框架，能将生物库的静态遗传数据转化为动态的、可操作的公共卫生见解。
*   **去种族化潜力**：通过生物学联系而非社会建构的种族类别来识别高风险群体，有助于减少医疗偏见。

### 8. 不足与局限
*   **样本局限性**：研究基于单一生物样本库（1.3 万人），虽然具有代表性，但样本量相比英国生物样本库（UK Biobank）等仍较小，可能存在地理区域偏差。
*   **因果推断难度**：虽然使用了中介分析，但由于是横断面研究，难以完全确定环境暴露与健康结果之间的长期因果链条。
*   **隐私风险**：精细的 IBD 聚类可能增加特定小群体被重新识别的风险，需关注数据隐私保护。

（完）
