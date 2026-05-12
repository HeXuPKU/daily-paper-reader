---
title: Identity-by-descent captures Shared Environmental Factors at Biobank Scale
title_zh: 血缘同源性在生物样本库规模下捕捉共享环境因素
authors: "Marsico, F., Buonaiuto, S., Amos-Abanyie, E., Chinthala, L., Mohammed, A., Zahr, R., Regeneron Genetics Center,, Rooney, R., Williams, R. W., Davis, R. L., Finkel, T. H., Brown, C. W., Vacca, M., Prins, P., Colonna, V."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.1101/2025.05.03.652048v5.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 整合基因组和电子健康档案数据以捕捉基因-环境相互作用
tldr: 该研究利用1.3万余人的基因组和电子健康记录数据，通过同源性状（IBD）比例将人群划分为多层级社区。研究发现，IBD聚类不仅能揭示精细的人口结构，还能有效捕捉共享的环境暴露因素（如污染）及其对呼吸系统等疾病的影响。这种方法超越了传统的种族分类，证明了IBD能同时反映遗传与环境对健康的共同作用，为精准医疗提供了一个可扩展的新框架。
source: biorxiv
selection_source: fresh_fetch
motivation: 探索基因组中的同源性状（IBD）是否能比传统人口统计学分类更有效地捕捉共享的环境暴露和健康差异。
method: 采用层次化社区检测算法基于IBD比例对个体进行分组，并结合地理信息、环境指标及中介分析评估其与健康的关系。
result: IBD定义的子社区在环境压力暴露和疾病流行率上表现出显著差异，且这种差异在调整自报种族后依然显著，揭示了未被测量的环境因素贡献。
conclusion: IBD聚类能够整合遗传与环境健康决定因素，为利用生物样本库数据实现精准健康和群体遗传学研究提供了有力工具。
---

## 摘要
谱系联系留下的痕迹超出了共享的遗传物质：亲属往往共享跨代持续的环境暴露和文化习俗。利用来自综合基因组学生物库（Biorepository for Integrative Genomics）的 13,143 名个体的基因组和电子健康档案数据，我们应用了一种分层社区检测算法，根据基因组中血缘同源（IBD）共享的比例，将个体分为 4 个主要社区和 17 个子社区。这种方法捕捉到了超出传统祖源分类的精细人口结构。通过整合邻里层面的地理数据与基于普查的环境指标，我们揭示了子社区之间环境压力暴露的不平等，这与健康状况的差异率相关，包括在污染负担较重的子社区中呼吸系统疾病患病率升高。通过干预性中介分析，我们发现子社区层面的超额风险大大超过了仅凭已测量的环境因素所能解释的范围，从而展示了基于 IBD 的分组所捕捉到的未测量共享暴露的贡献。在调整了自我报告种族的敏感性分析中，子社区层面的差异依然存在，这表明基于 IBD 的聚类捕捉到了超出通常作为健康社会决定因素代理指标的人口统计学类别的健康相关信息。我们实现了一个开源仪表板，用于交互式探索 IBD 定义的社区、疾病患病率和环境暴露。总之，我们证明了基于 IBD 的聚类共同捕捉了健康的遗传和环境决定因素，为精准健康和群体遗传学提供了一个可扩展的框架，将生物样本库数据转化为可操作的见解。

## Abstract
Genealogical ties leave traces beyond shared genetic material: relatives tend to share environmental exposures and cultural practices that persist across generations. Using genomic and electronic health record data from 13,143 individuals in the Biorepository for Integrative Genomics, we applied a hierarchical community detection algorithm to group individuals into four major communities and 17 subcommunities based on the proportion of their genome shared identical by descent (IBD). This approach captured a fine-scale demographic structure beyond traditional ancestry classifications. By integrating neighborhood-level geographic data with census-derived environmental metrics, we revealed unequal exposure to environmental stressors between subcommunities, which correlated with differential rates of health conditions, including elevated respiratory condition prevalence in subcommunities under greater pollution burden. Through an interventional mediation analysis we found that excess risk at the subcommunity-level substantially exceeded what measured environmental factors alone could explain. thus showing the contribution of unmeasured shared exposures that IBD-based grouping captures. Subcommunity-level disparities persisted in sensitivity analyses adjusting for self-reported race, indicating that IBD-based clustering captures health-relevant information beyond demographic categories commonly used as proxies for social determinants of health. We implemented an open-source dashboard for interactive exploration of IBD-defined communities, disease prevalence, and environmental exposures. Together, we demonstrate that IBD-based clustering jointly captures genetic and environmental determinants of health, offering a scalable framework for precision health and population genetics that translates biobank data into actionable insights.

---

## 论文详细总结（自动生成）

这篇论文探讨了如何利用基因组中的血缘同源性（Identity-by-Descent, IBD）来识别生物样本库中共享的环境和遗传因素，从而超越传统的种族和祖源分类。以下是对该论文的结构化总结：

### 1. 核心问题与研究动机
*   **核心问题**：传统的人口学分类（如自报种族、大陆级祖源）在医学研究中往往被用作社会和环境因素的代理指标，但这些分类过于粗糙，且容易强化生物学偏见。
*   **研究动机**：亲属之间不仅共享遗传物质，还共享跨代持续的环境暴露、文化习俗和社会经济条件。研究者希望探索基于基因组推断的 IBD 关系是否能更精准地捕捉这些“基因-环境”共存的复杂结构，并将其应用于精准医疗和公共卫生。

### 2. 方法论
*   **核心思想**：利用个体间共享的长片段 DNA（IBD）构建亲缘网络，通过社区检测算法识别具有相似背景的群体。
*   **关键技术流程**：
    1.  **IBD 计算**：使用 `hap-ibd` 软件在 13,143 名个体的全外显子组数据中检测 ≥2 cM 的共享片段。
    2.  **网络构建**：以个体为节点，以总共享 IBD 长度为边权重构建遗传网络。
    3.  **层次化社区检测**：应用 **Leiden 算法**进行两轮迭代，将人群划分为 4 个主要社区和 17 个精细子社区。
    4.  **环境整合**：通过参与者的邮政编码（ZIP code）链接邻里层面的社会决定因素（SDoH），如 PM2.5 污染、贫困率、社会脆弱性指数（SVI）等。
    5.  **中介分析**：采用**干预性中介分析（Interventional Mediation Analysis）**，将子社区身份作为暴露因素，将已测量的环境指标作为中介变量，将健康状况作为结果，分解出“环境介导效应”和“独立因素（包含遗传和未测量环境）”。

### 3. 实验设计
*   **数据集**：综合基因组学生物库（BIG）队列，包含 13,143 名参与者（87% 为儿童）的基因组数据和电子健康档案（EHR）。
*   **Benchmark 与对比**：
    *   对比了基于主成分分析（PCA）的连续祖源分布。
    *   对比了自报种族（SIRE）和民族（Hispanic/Latino）。
    *   使用了 HGDP-1kGP 全球参考面板来验证子社区的遗传背景。
*   **健康指标**：将 ICD-9/10 编码映射为 PheCodes，重点分析了哮喘、皮炎、癫痫和流感四种疾病。

### 4. 资源与算力
*   **测序平台**：使用 Illumina NovaSeq 6000 进行全外显子组测序。
*   **软件工具**：BWA-MEM, DeepVariant, GLnexus, ShapeIT v5, PLINK 等。
*   **算力说明**：文中未明确说明具体的 GPU/CPU 核心数或总训练时长，但提到使用了大规模并行处理工具来应对生物库级别的计算需求。

### 5. 实验数量与充分性
*   **实验规模**：分析了 1.3 万余人的数据，并额外引入 4,091 名 HGDP-1kGP 样本进行敏感性分析，验证了社区结构的稳定性。
*   **充分性**：研究涵盖了地理距离与遗传距离的相关性分析、SDoH 相似性分析、疾病流行率回归以及复杂的中介分析。
*   **客观性**：通过 E-value 敏感性分析评估了未测量混杂因素的影响，并调整了自报种族进行验证，实验设计较为严谨、客观。

### 6. 主要结论与发现
*   **精细结构**：IBD 聚类能发现比传统祖源分析更细微的人口结构（如波多黎各与秘鲁人群的区分）。
*   **环境共振**：遗传上接近的子社区在地理上也高度聚集，且面临相似的环境压力（如 C2 社区普遍暴露于高 PM2.5 污染）。
*   **健康差异**：环境暴露差异解释了约 1/3 的子社区间健康风险差异（如哮喘），而剩下的 2/3 风险由 IBD 捕捉到的未测量共享因素（包括遗传和特定文化/生活方式）解释。
*   **超越种族**：在调整种族因素后，IBD 定义的子社区依然能显著预测健康风险，证明其捕捉到了传统分类遗漏的临床相关信息。

### 7. 优点
*   **无需参考面板**：基于 IBD 的方法是“参考自由”的，避免了预设参考人群带来的偏差。
*   **整合性强**：成功将抽象的遗传网络与具体的地理环境、社会经济指标及临床结果整合在一起。
*   **开源贡献**：提供了交互式仪表板，增强了数据的透明度和公共卫生应用潜力。

### 8. 不足与局限
*   **地理局限性**：样本主要集中在田纳西州（孟菲斯等地），其结论在其他地理区域的普适性有待验证。
*   **生态学谬误风险**：环境数据是在邻里层面（邮编）而非个体层面测量的，可能无法完全反映个体的实际暴露。
*   **未测量混杂**：尽管进行了中介分析，但仍有大量风险无法明确区分是归因于遗传还是未测量的社会文化因素。
*   **样本偏差**：该队列以儿科患者为主，可能无法完全代表成年人群的健康模式。

（完）
