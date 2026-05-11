---
title: Identity-by-descent captures Shared Environmental Factors at Biobank Scale
title_zh: 同源后裔在生物样本库规模下捕捉共享环境因素
authors: "Marsico, F., Buonaiuto, S., Amos-Abanyie, E., Chinthala, L., Mohammed, A., Zahr, R., Regeneron Genetics Center,, Rooney, R., Williams, R. W., Davis, R. L., Finkel, T. H., Brown, C. W., Vacca, M., Prins, P., Colonna, V."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.1101/2025.05.03.652048v5.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 整合基因组和电子健康记录数据以捕捉环境因素
tldr: 该研究利用生物样本库中1.3万余人的基因组和电子健康记录数据，通过同源性状（IBD）比例将人群划分为不同层级的社区。研究发现，IBD聚类不仅能揭示比传统祖先分类更精细的人口结构，还能有效捕捉共享的环境暴露因素（如污染）及其对健康（如呼吸系统疾病）的影响。这种方法超越了传统的种族分类，为精准医疗和群体遗传学提供了一个整合遗传与环境因素的可扩展框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在探索基因组中的同源性状（IBD）是否能比传统的人口统计学分类更有效地捕捉共享的环境暴露和健康差异。
method: "利用层次化社区检测算法，基于13,143名个体的IBD比例将其分组，并结合地理数据和人口普查环境指标进行中介分析。"
result: IBD定义的子社区在环境压力暴露和疾病流行率上存在显著差异，且这种差异在调整自报种族后依然存在，显示出其捕捉未测量暴露的能力。
conclusion: IBD聚类能够同时捕捉遗传和环境健康决定因素，为精准医疗提供了一个超越传统人口统计学分类的可扩展分析框架。
---

## 摘要
谱系联系留下的痕迹不仅限于共享的遗传物质：亲属往往共享跨代存在的环境暴露和文化习俗。利用来自综合基因组学生物库（Biorepository for Integrative Genomics）的 13,143 名个体的基因组和电子健康记录数据，我们应用了一种层次化社区检测算法，根据基因组中同源后裔（IBD）共享的比例，将个体分为 4 个主要社区和 17 个子社区。这种方法捕捉到了超越传统祖先分类的细粒度人口结构。通过整合社区级地理数据与基于普查的环境指标，我们揭示了子社区之间环境压力因素暴露的不平等，这与健康状况的差异率相关，包括在污染负担较重的子社区中呼吸系统疾病患病率升高。通过干预性中介分析，我们发现子社区层面的超额风险大大超过了仅靠已测环境因素所能解释的范围，从而展示了基于 IBD 的分组所捕捉到的未测共享暴露的贡献。在调整自报种族的敏感性分析中，子社区层面的差异依然存在，这表明基于 IBD 的聚类捕捉到了超越通常作为健康社会决定因素代理指标的人口统计类别的健康相关信息。我们实现了一个开源仪表板，用于交互式探索 IBD 定义的社区、疾病患病率和环境暴露。总之，我们证明了基于 IBD 的聚类共同捕捉了健康的遗传和环境决定因素，为精准健康和群体遗传学提供了一个可扩展的框架，将生物样本库数据转化为可操作的见解。

## Abstract
Genealogical ties leave traces beyond shared genetic material: relatives tend to share environmental exposures and cultural practices that persist across generations. Using genomic and electronic health record data from 13,143 individuals in the Biorepository for Integrative Genomics, we applied a hierarchical community detection algorithm to group individuals into four major communities and 17 subcommunities based on the proportion of their genome shared identical by descent (IBD). This approach captured a fine-scale demographic structure beyond traditional ancestry classifications. By integrating neighborhood-level geographic data with census-derived environmental metrics, we revealed unequal exposure to environmental stressors between subcommunities, which correlated with differential rates of health conditions, including elevated respiratory condition prevalence in subcommunities under greater pollution burden. Through an interventional mediation analysis we found that excess risk at the subcommunity-level substantially exceeded what measured environmental factors alone could explain. thus showing the contribution of unmeasured shared exposures that IBD-based grouping captures. Subcommunity-level disparities persisted in sensitivity analyses adjusting for self-reported race, indicating that IBD-based clustering captures health-relevant information beyond demographic categories commonly used as proxies for social determinants of health. We implemented an open-source dashboard for interactive exploration of IBD-defined communities, disease prevalence, and environmental exposures. Together, we demonstrate that IBD-based clustering jointly captures genetic and environmental determinants of health, offering a scalable framework for precision health and population genetics that translates biobank data into actionable insights.

---

## 论文详细总结（自动生成）

这篇论文题为《同源后裔在生物样本库规模下捕捉共享环境因素》，由来自田纳西大学健康科学中心（UTHSC）和再生元遗传学中心（RGC）等机构的研究团队完成。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：传统的遗传学研究通常依赖于粗略的“祖先分类”或“自报种族”来研究健康差异，但这些类别往往无法捕捉到精细的人口结构以及亲属间共享的复杂环境暴露。
*   **研究动机**：谱系联系不仅意味着共享基因，还意味着共享文化、社会规范和地理环境。研究者旨在探索利用**同源后裔（Identity-by-Descent, IBD）**——即由于共同祖先而共享的DNA片段——能否在生物样本库规模下，直接从基因组数据中提取出比传统分类更精细、且能同时反映遗传与环境影响的群体结构。

### 2. 论文提出的方法论
*   **核心思想**：构建一个基于IBD共享量的个体关联网络，并利用社区检测算法进行分层聚类。
*   **关键技术细节**：
    *   **IBD检测**：使用 `hap-ibd` 软件在 13,143 名个体的全外显子组测序数据中检测共享片段（最小阈值 2 cM）。
    *   **网络构建**：以个体为节点，以成对共享的IBD总长度为边权重，构建遗传关联网络。
    *   **分层社区检测**：应用 **Leiden 算法**进行两轮迭代。第一轮识别出 4 个主要社区（对应大洲级祖先），第二轮在社区内部识别出 17 个子社区。
    *   **中介分析（Mediation Analysis）**：采用干预性中介分析框架，将子社区成员身份作为暴露因素，将测得的环境指标（如 PM2.5、贫困率）作为中介变量，将健康结果（如哮喘、流感）作为结局，从而分解出“环境介导效应”和“独立于已知环境的社区效应”。

### 3. 实验设计
*   **数据集**：主要使用 **BIG (Biorepository for Integrative Genomics)** 队列，包含 13,143 名参与者（主要是孟菲斯地区的儿科患者），关联了电子健康记录（EHR）和基于邮政编码的社会决定因素（SDoH）数据。
*   **Benchmark 与对比**：
    *   对比了基于主成分分析（PCA）的连续遗传变异分类。
    *   对比了自报种族（SIRE）和民族。
    *   引入 **HGDP-1kGP** 全球参考面板进行验证，观察 BIG 子社区与全球群体的遗传亲缘关系。
*   **评估场景**：分析了呼吸系统、皮肤、神经系统、感染等 6 大类疾病的患病率差异。

### 4. 资源与算力
*   **测序平台**：使用 Illumina NovaSeq 6000 进行全外显子组测序。
*   **计算资源**：文中未明确说明具体的 GPU/CPU 核心数量或总训练时长。但提到了使用 `GLnexus` 进行联合变异调用，以及 `RFMix` 进行祖先推断，这些通常需要高性能计算集群（HPC）支持。

### 5. 实验数量与充分性
*   **实验规模**：分析了超过 1.3 万名个体的基因组，涵盖了 17 个子社区。
*   **充分性验证**：
    *   进行了**敏感性分析**：在调整自报种族后，观察子社区间的健康差异是否依然显著。
    *   **E-value 分析**：评估未观测到的混杂因素对中介分析结果的影响强度。
    *   **稳定性测试**：加入 4,091 名外部参考样本后，原有社区结构保持稳定，证明了算法的鲁棒性。
    *   实验设计较为客观，通过多维度（遗传、地理、社会环境、临床）的交叉验证，论证了 IBD 聚类的有效性。

### 6. 论文的主要结论与发现
*   **精细结构**：IBD 聚类能发现比传统祖先推断更细致的人口结构（如波多黎各裔与秘鲁裔的区分）。
*   **环境共振**：IBD 共享量与地理距离、社会环境相似性（SDoH）高度相关。近一半的近亲居住在同一社区。
*   **健康差异**：不同子社区在环境驱动型疾病（如呼吸系统疾病）上的患病率差异显著，且 PM2.5 暴露量能解释呼吸系统疾病 90% 的社区间变异。
*   **未测暴露**：中介分析显示，已测环境因素仅能解释约 1/3 的超额风险，剩余 2/3 的风险由 IBD 社区捕捉到的未测共享暴露（如室内空气质量、饮食、文化习俗等）解释。

### 7. 优点
*   **无需参考面板**：该方法是“参考无关”的，直接从样本内部关系出发，避免了预设种族标签带来的偏差。
*   **整合性强**：成功将抽象的遗传亲缘关系与具体的地理环境、社会不平等和临床结局联系起来。
*   **临床应用价值**：开发了开源仪表板，为精准公共卫生干预（如针对高风险子社区的污染治理）提供了工具。

### 8. 不足与局限
*   **生态学谬误风险**：环境数据是基于邮政编码（社区级）而非个体级的，可能无法完全反映个体的真实暴露。
*   **地理局限性**：样本主要集中在孟菲斯地区，其发现的社会环境模式可能具有地域特殊性，需在其他城市或国家验证。
*   **因果推断限制**：虽然使用了中介分析，但作为观察性研究，仍难以完全排除所有未观测到的遗传或环境混杂因素。
*   **样本量限制**：部分较小的子社区（如 C4 亚洲社区）因样本量不足无法进行深入的拓扑和中介分析。

（完）
