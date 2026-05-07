---
title: Identity-by-descent captures Shared Environmental Factors at Biobank Scale
title_zh: 血缘同源性在生物样本库规模下捕捉共享环境因素
authors: "Marsico, F., Buonaiuto, S., Amos-Abanyie, E., Chinthala, L., Mohammed, A., Zahr, R., Regeneron Genetics Center,, Rooney, R., Williams, R. W., Davis, R. L., Finkel, T. H., Brown, C. W., Vacca, M., Prins, P., Colonna, V."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.1101/2025.05.03.652048v5.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 电子健康记录与基因组数据的整合
tldr: "本研究利用13,143名生物样本库参与者的基因组和电子健康记录数据，通过同源染色体片段（IBD）共享比例，应用层次社区检测算法将人群划分为精细的子社区。这种方法不仅揭示了超越传统祖源分类的人口结构，还捕捉到了地理环境压力与健康状况（如呼吸系统疾病）之间的关联。研究发现，IBD聚类能有效识别未被测量的共享环境暴露，为精准医疗和群体遗传学提供了一个可扩展的框架，将生物库数据转化为实际的健康洞察。"
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在探索基因组中的同源共享片段（IBD）是否能比传统祖源分类更有效地捕捉影响健康的共享环境因素。
method: 利用层次社区检测算法基于IBD共享比例对1.3万余名个体进行聚类，并结合地理环境指标和健康记录进行中介分析。
result: 识别出17个具有显著环境暴露差异和健康风险差异的子社区，且这些差异在调整自报种族后依然存在。
conclusion: IBD聚类能够同时捕捉遗传和环境健康决定因素，是超越传统人口统计学分类、实现精准健康管理的新型框架。
---

## 摘要
谱系联系留下的痕迹不仅限于共享的遗传物质：亲属往往共享跨代持续的环境暴露和文化习俗。利用来自综合基因组学生物库（Biorepository for Integrative Genomics）的 13,143 名个体的基因组和电子健康记录数据，我们应用了一种层次化社区检测算法，根据基因组中血缘同源（IBD）共享的比例，将个体分为 4 个主要社区和 17 个子社区。这种方法捕捉到了超越传统祖先分类的精细人口结构。通过整合邻里级的地理数据与基于普查的环境指标，我们揭示了子社区之间环境压力暴露的不平等，这与健康状况的差异率相关，包括在污染负担较重的子社区中呼吸系统疾病患病率升高。通过干预性中介分析，我们发现子社区层面的超额风险大大超过了仅靠已测量的环境因素所能解释的范围，从而展示了基于 IBD 的分组所捕捉到的未测量共享暴露的贡献。在调整了自我报告种族的敏感性分析中，子社区层面的差异依然存在，这表明基于 IBD 的聚类捕捉到了超越通常作为健康社会决定因素代理指标的人口统计学类别的健康相关信息。我们实现了一个开源仪表板，用于交互式探索 IBD 定义的社区、疾病患病率和环境暴露。总之，我们证明了基于 IBD 的聚类共同捕捉了健康的遗传和环境决定因素，为精准健康和群体遗传学提供了一个可扩展的框架，将生物样本库数据转化为可操作的见解。

## Abstract
Genealogical ties leave traces beyond shared genetic material: relatives tend to share environmental exposures and cultural practices that persist across generations. Using genomic and electronic health record data from 13,143 individuals in the Biorepository for Integrative Genomics, we applied a hierarchical community detection algorithm to group individuals into four major communities and 17 subcommunities based on the proportion of their genome shared identical by descent (IBD). This approach captured a fine-scale demographic structure beyond traditional ancestry classifications. By integrating neighborhood-level geographic data with census-derived environmental metrics, we revealed unequal exposure to environmental stressors between subcommunities, which correlated with differential rates of health conditions, including elevated respiratory condition prevalence in subcommunities under greater pollution burden. Through an interventional mediation analysis we found that excess risk at the subcommunity-level substantially exceeded what measured environmental factors alone could explain. thus showing the contribution of unmeasured shared exposures that IBD-based grouping captures. Subcommunity-level disparities persisted in sensitivity analyses adjusting for self-reported race, indicating that IBD-based clustering captures health-relevant information beyond demographic categories commonly used as proxies for social determinants of health. We implemented an open-source dashboard for interactive exploration of IBD-defined communities, disease prevalence, and environmental exposures. Together, we demonstrate that IBD-based clustering jointly captures genetic and environmental determinants of health, offering a scalable framework for precision health and population genetics that translates biobank data into actionable insights.