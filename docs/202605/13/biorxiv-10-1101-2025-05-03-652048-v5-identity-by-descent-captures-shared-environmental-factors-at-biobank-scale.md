---
title: Identity-by-descent captures Shared Environmental Factors at Biobank Scale
title_zh: 同源后裔在生物样本库规模下捕捉共享环境因素
authors: "Marsico, F., Buonaiuto, S., Amos-Abanyie, E., Chinthala, L., Mohammed, A., Zahr, R., Regeneron Genetics Center,, Rooney, R., Williams, R. W., Davis, R. L., Finkel, T. H., Brown, C. W., Vacca, M., Prins, P., Colonna, V."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.1101/2025.05.03.652048v5.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 整合基因组和电子健康记录数据研究环境因素
tldr: "本研究利用13,143名生物样本库参与者的基因组和电子健康记录数据，通过同源后代（IBD）比例进行层次化社区检测，将人群划分为4个主要社区和17个子社区。该方法捕捉到了超越传统祖先分类的精细人口结构，揭示了不同子社区在环境压力暴露及健康状况（如呼吸系统疾病）上的显著差异。研究表明，IBD聚类能有效捕捉未测量的共享环境因素，为精准医疗和群体遗传学提供了可扩展的框架。"
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在探索基因组中的同源后代（IBD）信息是否能比传统人口统计分类更有效地捕捉共享的环境暴露和健康风险。
method: 利用层次化社区检测算法，根据个体间共享的IBD比例对参与者进行分组，并结合地理环境指标和中介分析评估其对健康的影响。
result: 发现IBD定义的子社区在环境压力暴露和疾病流行率上存在显著差异，且这种差异在调整自报种族后依然存在，显示了其捕捉未测量环境因素的能力。
conclusion: IBD聚类共同捕捉了健康的遗传和环境决定因素，为利用生物样本库数据实现精准健康管理和群体遗传学研究提供了有力工具。
---

## 摘要
谱系联系留下的痕迹不仅限于共享的遗传物质：亲属往往共享跨代存在的环境暴露和文化习俗。利用来自综合基因组学生物样本库（Biorepository for Integrative Genomics）的 13,143 名个体的基因组和电子健康记录数据，我们应用了一种层次化社区检测算法，根据基因组中同源后裔（IBD）共享的比例，将个体分为 4 个主要社区和 17 个子社区。这种方法捕捉到了超越传统祖先分类的细粒度人口结构。通过整合社区级地理数据与基于普查的环境指标，我们揭示了子社区之间环境压力因素暴露的不平等，这与健康状况的差异率相关，包括在污染负担较重的子社区中呼吸系统疾病患病率升高。通过干预性中介分析，我们发现子社区层面的超额风险大大超过了仅靠已测环境因素所能解释的范围，从而展示了基于 IBD 的分组所捕捉到的未测共享暴露的贡献。在调整自述种族的敏感性分析中，子社区层面的差异依然存在，这表明基于 IBD 的聚类捕捉到了超越通常作为健康社会决定因素代理指标的人口统计类别的健康相关信息。我们实现了一个开源仪表板，用于交互式探索 IBD 定义的社区、疾病患病率和环境暴露。总之，我们证明了基于 IBD 的聚类共同捕捉了健康的遗传和环境决定因素，为精准健康和群体遗传学提供了一个可扩展的框架，将生物样本库数据转化为可操作的见解。

## Abstract
Genealogical ties leave traces beyond shared genetic material: relatives tend to share environmental exposures and cultural practices that persist across generations. Using genomic and electronic health record data from 13,143 individuals in the Biorepository for Integrative Genomics, we applied a hierarchical community detection algorithm to group individuals into four major communities and 17 subcommunities based on the proportion of their genome shared identical by descent (IBD). This approach captured a fine-scale demographic structure beyond traditional ancestry classifications. By integrating neighborhood-level geographic data with census-derived environmental metrics, we revealed unequal exposure to environmental stressors between subcommunities, which correlated with differential rates of health conditions, including elevated respiratory condition prevalence in subcommunities under greater pollution burden. Through an interventional mediation analysis we found that excess risk at the subcommunity-level substantially exceeded what measured environmental factors alone could explain. thus showing the contribution of unmeasured shared exposures that IBD-based grouping captures. Subcommunity-level disparities persisted in sensitivity analyses adjusting for self-reported race, indicating that IBD-based clustering captures health-relevant information beyond demographic categories commonly used as proxies for social determinants of health. We implemented an open-source dashboard for interactive exploration of IBD-defined communities, disease prevalence, and environmental exposures. Together, we demonstrate that IBD-based clustering jointly captures genetic and environmental determinants of health, offering a scalable framework for precision health and population genetics that translates biobank data into actionable insights.

---

## 论文详细总结（自动生成）

以下是对论文《Identity-by-descent captures Shared Environmental Factors at Biobank Scale》（同源后裔在生物样本库规模下捕捉共享环境因素）的深度结构化总结：

### 1. 核心问题与整体含义
*   **研究动机**：传统的医学研究常使用“种族”或“祖先”作为健康社会决定因素（SDoH）的代理指标，但这些分类过于粗糙，无法捕捉到精细的地理、文化和环境暴露差异。
*   **核心问题**：基因组中的**同源后裔（Identity-by-Descent, IBD）**片段不仅反映了遗传联系，还隐含了亲属间共享的跨代环境暴露。研究旨在探索基于 IBD 的社区检测能否比传统分类更有效地识别共享环境压力及其对健康的影响。
*   **整体含义**：该研究证明了 IBD 聚类可以作为一个强大的框架，将遗传背景与未测量的环境因素结合起来，为精准医疗提供比自述种族更精细的视角。

### 2. 方法论
*   **核心思想**：利用个体间共享的 IBD 比例构建遗传网络，通过社区检测算法识别出具有紧密亲缘和地理联系的群体。
*   **关键技术流程**：
    1.  **IBD 检测**：利用基因组数据识别个体间共享的 DNA 片段。
    2.  **层次化社区检测**：应用算法（如基于 IBD 共享比例的网络聚类）将 13,143 名参与者划分为 4 个主要社区和 17 个子社区。
    3.  **多模态数据整合**：将 IBD 社区与电子健康记录（EHR）、居住地普查区（Census Tract）以及环境指标（如 EJScreen 提供的污染数据、社会经济地位指标）进行关联。
    4.  **中介分析（Mediation Analysis）**：采用干预性中介分析模型，评估子社区对健康风险的影响中有多少是由“已测环境因素”解释的，多少是由“未测共享因素”贡献的。

### 3. 实验设计
*   **数据集**：来自综合基因组学生物样本库（BIG）的 **13,143 名个体**的数据，该样本库主要覆盖美国田纳西州孟菲斯地区。
*   **Benchmark（基准）**：以**自述种族（Self-reported Race）**和传统的**主成分分析（PCA）祖先成分**作为对比基准。
*   **对比维度**：
    *   子社区间的环境压力暴露（如空气污染、铅暴露风险）。
    *   子社区间的疾病患病率差异（通过 PheWAS 临床表型关联研究）。
    *   在调整种族因素后，IBD 社区对健康风险的额外解释力。

### 4. 资源与算力
*   **算力说明**：论文中未明确给出具体的 GPU 型号、数量或训练时长。
*   **软件资源**：提到了实现了一个**开源仪表板（Dashboard）**，用于交互式探索 IBD 社区、疾病和环境数据，强调了分析流程的可扩展性和工具的开放性。

### 5. 实验数量与充分性
*   **实验规模**：分析了 17 个子社区在多种环境指标和临床表型上的表现。
*   **充分性评价**：
    *   **敏感性分析**：研究在调整了自述种族后依然观察到子社区间的显著差异，证明了结果的稳健性。
    *   **中介分析**：通过量化已测与未测因素的贡献，增强了结论的客观性。
    *   **局限性**：虽然在孟菲斯人群中表现良好，但样本量（约 1.3 万）相对于英国生物样本库（UK Biobank）等超大规模研究较小，且地理局限性较强。

### 6. 主要结论与发现
*   **精细结构捕捉**：IBD 聚类识别出了比传统祖先分类更细致的人口结构，这些结构与地理上的居住模式高度吻合。
*   **环境暴露不平等**：不同的 IBD 子社区在环境压力（如污染负担）上的暴露存在显著不平等。
*   **健康关联**：环境负担较重的子社区，其呼吸系统疾病等健康问题的患病率显著升高。
*   **超越已知因素**：中介分析显示，子社区层面的健康风险很大程度上源于**未测量的共享暴露**，这表明 IBD 能够捕捉到普查数据无法覆盖的深层社会环境信息。

### 7. 优点
*   **创新视角**：将 IBD 从单纯的遗传学工具扩展为捕捉“遗传+环境”综合信息的传感器。
*   **多维整合**：成功打通了基因组、EHR 和地理环境普查数据，展示了生物样本库数据的深度挖掘潜力。
*   **临床意义**：为识别高风险群体提供了新工具，有助于制定更精准的公共卫生干预措施。

### 8. 不足与局限
*   **地理局限性**：研究集中在单一城市（孟菲斯），其结论在其他地区或更广泛的人群中是否具有普适性仍需验证。
*   **偏差风险**：生物样本库的参与者可能存在招募偏差（Recruitment Bias），不能完全代表总体人群。
*   **因果推断限制**：尽管使用了中介分析，但作为观察性研究，仍难以完全排除所有混杂因素，无法给出绝对的因果定论。
*   **隐私考量**：高精度的 IBD 聚类可能增加个体或特定小群体的再识别风险，需关注伦理隐私保护。

（完）
