---
title: Identity-by-descent captures Shared Environmental Factors at Biobank Scale
title_zh: 血缘同源性在生物样本库规模下捕捉共享环境因素
authors: "Marsico, F., Buonaiuto, S., Amos-Abanyie, E., Chinthala, L., Mohammed, A., Zahr, R., Regeneron Genetics Center,, Rooney, R., Williams, R. W., Davis, R. L., Finkel, T. H., Brown, C. W., Vacca, M., Prins, P., Colonna, V."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.1101/2025.05.03.652048v5.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 在生物样本库规模上整合基因组和电子健康记录数据
tldr: "本研究利用13,143名生物样本库参与者的基因组和电子病历数据，通过同源后裔（IBD）比例进行层次社区检测，将人群划分为4个主要社区和17个子社区。研究发现，这种基于IBD的聚类方法能捕捉到比传统祖先分类更细致的人口结构，并揭示了不同子社区在环境压力暴露及健康状况（如呼吸系统疾病）上的显著差异。即使在调整自报种族后，这些差异依然存在，表明IBD聚类能有效整合遗传与未测量的环境暴露因素，为精准健康研究提供了可扩展的新框架。"
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的祖先分类和种族标签难以充分捕捉影响健康状况的复杂环境暴露和代际文化实践。
method: "基于13,143名个体的基因组同源后裔（IBD）比例，应用层次社区检测算法进行精细的人口结构划分。"
result: 识别出的子社区在环境压力暴露上存在显著差异，且这些差异与呼吸系统疾病等健康状况的患病率高度相关。
conclusion: IBD聚类能够同时捕捉遗传和环境的健康决定因素，为超越传统人口统计学分类的精准医疗提供了有力工具。
---

## 摘要
宗谱联系留下的痕迹超出了共享的遗传物质：亲属往往共享跨代持续的环境暴露和文化习俗。利用来自综合基因组学生物样本库（Biorepository for Integrative Genomics）的 13,143 名个体的基因组和电子健康记录数据，我们应用了一种层次化社区检测算法，根据其基因组中血缘同源（IBD）共享的比例，将个体分为 4 个主要社区和 17 个子社区。这种方法捕捉到了超出传统祖先分类的精细人口结构。通过整合社区层面的地理数据与基于普查的环境指标，我们揭示了子社区之间环境压力暴露的不平等，这与健康状况的差异率相关，包括在污染负担较重的子社区中呼吸系统疾病患病率升高。通过干预性中介分析，我们发现子社区层面的超额风险大大超过了仅凭已测量的环境因素所能解释的范围，从而展示了基于 IBD 的分组所捕捉到的未测量共享暴露的贡献。在调整了自我报告种族的敏感性分析中，子社区层面的差异依然存在，这表明基于 IBD 的聚类捕捉到了超出通常作为健康社会决定因素代理指标的人口统计学类别的健康相关信息。我们实现了一个开源仪表板，用于交互式探索 IBD 定义的社区、疾病患病率和环境暴露。总之，我们证明了基于 IBD 的聚类共同捕捉了健康的遗传和环境决定因素，为精准健康和群体遗传学提供了一个可扩展的框架，将生物样本库数据转化为可操作的见解。

## Abstract
Genealogical ties leave traces beyond shared genetic material: relatives tend to share environmental exposures and cultural practices that persist across generations. Using genomic and electronic health record data from 13,143 individuals in the Biorepository for Integrative Genomics, we applied a hierarchical community detection algorithm to group individuals into four major communities and 17 subcommunities based on the proportion of their genome shared identical by descent (IBD). This approach captured a fine-scale demographic structure beyond traditional ancestry classifications. By integrating neighborhood-level geographic data with census-derived environmental metrics, we revealed unequal exposure to environmental stressors between subcommunities, which correlated with differential rates of health conditions, including elevated respiratory condition prevalence in subcommunities under greater pollution burden. Through an interventional mediation analysis we found that excess risk at the subcommunity-level substantially exceeded what measured environmental factors alone could explain. thus showing the contribution of unmeasured shared exposures that IBD-based grouping captures. Subcommunity-level disparities persisted in sensitivity analyses adjusting for self-reported race, indicating that IBD-based clustering captures health-relevant information beyond demographic categories commonly used as proxies for social determinants of health. We implemented an open-source dashboard for interactive exploration of IBD-defined communities, disease prevalence, and environmental exposures. Together, we demonstrate that IBD-based clustering jointly captures genetic and environmental determinants of health, offering a scalable framework for precision health and population genetics that translates biobank data into actionable insights.

---

## 论文详细总结（自动生成）

这篇论文探讨了如何利用基因组中的血缘同源性（Identity-by-Descent, IBD）在生物样本库规模下捕捉共享的环境因素与健康差异。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：传统的遗传学研究通常依赖于离散的种族或祖先分类，这些分类往往是人为定义的，且难以捕捉到亲属间共享的复杂环境暴露、社会经济地位和文化习俗。
*   **研究动机**：血缘关系不仅意味着共享遗传物质，还意味着共享生活环境。研究者希望建立一种无需外部参考面板、直接基于基因组推断宗谱关系的框架，以更精准地揭示遗传与环境对健康差异的共同影响。

### 2. 论文提出的方法论
*   **核心思想**：利用 IBD 共享片段构建个体间的宗谱网络，并通过社区检测算法识别具有相似背景的群体。
*   **关键技术细节**：
    *   **IBD 检测**：使用 `hap-ibd` 软件在 13,143 名个体的全外显子组测序数据中检测共享片段（阈值 $\ge$ 2 cM）。
    *   **网络构建**：以个体为节点，以总 IBD 共享长度为边权重构建遗传网络。
    *   **层次社区检测**：应用 **Leiden 算法**进行两轮迭代，将人群划分为 4 个主要社区（C1-C4）和 17 个子社区。
    *   **环境整合**：通过邮政编码（ZIP code）将个体连接到社区层面的社会健康决定因素（SDoH），如 PM2.5 污染指数、贫困率、社会脆弱性指数（SVI）等。
    *   **中介分析**：采用干预性中介分析（Interventional Mediation Analysis），将风险分解为“环境介导效应（EME）”和“独立因子（IF，代表未测量的共享因素）”。

### 3. 实验设计
*   **数据集**：来自综合基因组学生物样本库（BIG）的 **13,143 名参与者**（主要是田纳西州孟菲斯地区的儿科人群）。
*   **Benchmark 与对比**：
    *   对比了**自报种族/族裔（SIRE）**和**推断的全球祖先（RFMix）**。
    *   使用了 **HGDP-1kGP** 参考面板来验证社区的遗传背景。
    *   分析了 6 大类疾病（呼吸、感染、皮肤、肿瘤、神经、先天性疾病）的患病率。
*   **场景**：重点分析了孟菲斯市内部的地理隔离与环境暴露不平等。

### 4. 资源与算力
*   **测序平台**：使用 Illumina NovaSeq 6000 进行全外显子组测序。
*   **软件栈**：BWA-MEM, DeepVariant, GLnexus, ShapeIT v5, PLINK 等。
*   **算力说明**：文中未明确给出具体的 GPU/CPU 核时或训练时长，但提到处理了超过 1.3 万个样本的基因组数据，并构建了大规模 IBD 网络，这暗示了需要高性能计算集群支持。

### 5. 实验数量与充分性
*   **实验规模**：进行了层次化聚类分析、地理空间关联分析、SDoH 相似性分析、疾病患病率回归分析以及针对四种特定疾病（哮喘、皮炎、癫痫、流感）的中介分析。
*   **充分性**：
    *   **敏感性分析**：通过调整自报种族验证了 IBD 社区的独立信息价值。
    *   **稳定性验证**：加入 4,091 名外部参考样本（HGDP-1kGP）重新运行算法，证明了社区结构的稳定性。
    *   **鲁棒性**：使用 E-value 分析评估了未测量混杂因素的影响。实验设计全面，涵盖了遗传、地理、社会和临床多个维度。

### 6. 主要结论与发现
*   **精细结构**：IBD 聚类能捕捉到比传统祖先分类更细致的人口结构，反映了近期的宗谱联系。
*   **地缘关联**：近亲（1-2 级）约 49% 居住在同一社区；即使是远亲，其地理距离也显著近于随机个体。
*   **环境暴露不平等**：不同子社区在 PM2.5 暴露和贫困率上存在显著差异，这直接解释了呼吸系统疾病患病率的波动（$R^2 = 0.90$）。
*   **风险分解**：已测量的环境因素仅能解释约 1/3 的子社区健康差异，另外 2/3 的风险（独立因子）可能源于未测量的共享暴露（如室内空气、饮食、文化习惯等）。

### 7. 优点
*   **无需参考面板**：完全基于样本内部的遗传关系，避免了传统方法对特定参考人群的偏见。
*   **多维度整合**：成功将电子健康记录（EHR）、高分辨率地理环境数据与基因组学数据无缝对接。
*   **临床转化价值**：开发了开源仪表板，为精准公共卫生干预（如识别高风险污染暴露群体）提供了工具。

### 8. 不足与局限
*   **生态学谬误风险**：环境数据是基于邮政编码的平均值，而非个体层面的精确暴露测量，可能导致环境效应被低估。
*   **人群局限性**：研究对象主要是美国南部的儿科群体，其结论在其他地区或成年人群中的普适性尚需验证。
*   **未测量混杂**：虽然 IBD 捕捉到了“独立因子”，但仍无法具体区分这部分风险究竟是来自微环境、表观遗传还是特定的文化行为。

（完）
