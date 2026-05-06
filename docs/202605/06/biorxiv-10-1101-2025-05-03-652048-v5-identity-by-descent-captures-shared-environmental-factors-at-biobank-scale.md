---
title: Identity-by-descent captures Shared Environmental Factors at Biobank Scale
title_zh: 血缘同源在生物样本库规模下捕捉共享环境因素
authors: "Marsico, F., Buonaiuto, S., Amos-Abanyie, E., Chinthala, L., Mohammed, A., Zahr, R., Regeneron Genetics Center,, Rooney, R., Williams, R. W., Davis, R. L., Finkel, T. H., Brown, C. W., Vacca, M., Prins, P., Colonna, V."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.1101/2025.05.03.652048v5.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 整合基因组和电子健康记录数据以捕捉人口结构和环境因素
tldr: "本研究利用13,143名个体的基因组和电子健康记录数据，通过同源染色体片段（IBD）比例进行层次化社区检测，将人群划分为4个主要社区和17个子社区。研究发现，这种基于IBD的聚类能捕捉到比传统祖先分类更精细的人口结构，并揭示了子社区间在环境压力暴露（如污染）与健康状况（如呼吸系统疾病）上的显著差异。该方法不仅能识别未测量的共享环境暴露，还能在调整自报种族后依然保持对健康差异的解释力，为精准医疗提供了可扩展的框架。"
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的祖先分类和种族标签难以充分捕捉影响健康状况的复杂共享环境因素和文化习俗。
method: "基于13,143名个体的基因组IBD共享比例，采用层次化社区检测算法将人群划分为具有精细人口结构的子社区。"
result: 子社区间的环境暴露差异与呼吸系统等疾病患病率显著相关，且IBD聚类捕捉到了现有环境指标和自报种族无法解释的健康风险。
conclusion: 基于IBD的聚类框架整合了遗传与环境决定因素，为利用生物样本库数据实现精准健康管理提供了新途径。
---

## 摘要
谱系联系留下的痕迹不仅限于共享的遗传物质：亲属往往倾向于共享跨代持续的环境暴露和文化习俗。利用来自综合基因组学生物样本库（Biorepository for Integrative Genomics）的 13,143 名个体的基因组和电子健康记录数据，我们应用了一种层次化社区检测算法，根据基因组中血缘同源（IBD）共享的比例，将个体分为 4 个主要社区和 17 个子社区。这种方法捕捉到了超越传统祖先分类的精细人口结构。通过整合邻里级的地理数据与基于普查的环境指标，我们揭示了子社区之间环境压力暴露的不平等，这与健康状况的差异率相关，包括在污染负担较重的子社区中呼吸系统疾病患病率升高。通过干预性中介分析，我们发现子社区层面的超额风险大大超过了仅凭已测量的环境因素所能解释的范围，从而展示了基于 IBD 的分组所捕捉到的未测量共享暴露的贡献。在调整了自我报告种族的敏感性分析中，子社区层面的差异依然存在，这表明基于 IBD 的聚类捕捉到了超越通常作为健康社会决定因素代理指标的人口统计学类别的健康相关信息。我们实现了一个开源仪表板，用于交互式探索 IBD 定义的社区、疾病患病率和环境暴露。总之，我们证明了基于 IBD 的聚类共同捕捉了健康的遗传和环境决定因素，为精准健康和群体遗传学提供了一个可扩展的框架，将生物样本库数据转化为可操作的见解。

## Abstract
Genealogical ties leave traces beyond shared genetic material: relatives tend to share environmental exposures and cultural practices that persist across generations. Using genomic and electronic health record data from 13,143 individuals in the Biorepository for Integrative Genomics, we applied a hierarchical community detection algorithm to group individuals into four major communities and 17 subcommunities based on the proportion of their genome shared identical by descent (IBD). This approach captured a fine-scale demographic structure beyond traditional ancestry classifications. By integrating neighborhood-level geographic data with census-derived environmental metrics, we revealed unequal exposure to environmental stressors between subcommunities, which correlated with differential rates of health conditions, including elevated respiratory condition prevalence in subcommunities under greater pollution burden. Through an interventional mediation analysis we found that excess risk at the subcommunity-level substantially exceeded what measured environmental factors alone could explain. thus showing the contribution of unmeasured shared exposures that IBD-based grouping captures. Subcommunity-level disparities persisted in sensitivity analyses adjusting for self-reported race, indicating that IBD-based clustering captures health-relevant information beyond demographic categories commonly used as proxies for social determinants of health. We implemented an open-source dashboard for interactive exploration of IBD-defined communities, disease prevalence, and environmental exposures. Together, we demonstrate that IBD-based clustering jointly captures genetic and environmental determinants of health, offering a scalable framework for precision health and population genetics that translates biobank data into actionable insights.