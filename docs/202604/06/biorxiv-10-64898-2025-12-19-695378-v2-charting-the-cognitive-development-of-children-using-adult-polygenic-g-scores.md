---
title: "Charting the cognitive development of children using adult 'polygenic g scores'"
title_zh: 利用成年人“多基因g分数”描绘儿童认知发展的轨迹
authors: "Lin, Y., Plomin, R."
date: 2026-04-05
pdf: "https://www.biorxiv.org/content/10.64898/2025.12.19.695378v2.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 利用源自GWAS的多基因评分预测认知发育
tldr: "本研究利用成人一般认知能力（g）和受教育程度的多基因评分（PGS），对1万名英国儿童从幼儿期到成年早期的认知发展进行了追踪研究。通过整合回归分析、潜增长曲线和验证性因子分析，发现多基因评分对认知能力的预测力随年龄增长而显著提升，最高可解释12%的方差，并与更快的认知增长速度相关。该研究为理解遗传因素如何随时间塑造认知轨迹提供了重要工具。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-19-695378-v2/fig-001.webp\", \"caption\": \"Figure 1. Correlations between polygenic g score, g-PGS, EA-PGS, and general cognitive ability (g) across ages.\", \"page\": 9, \"index\": 1, \"width\": 943, \"height\": 943}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-19-695378-v2/fig-002.webp\", \"caption\": \"Figure 2. Polygenic g score prediction of cognitive abilities, educational achievement, and behaviour problems across development.\", \"page\": 16, \"index\": 2, \"width\": 943, \"height\": 1318}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2025-12-19-695378-v2/fig-003.webp\", \"caption\": \"Figure 4. Mean developmental trajectories for individuals with the highest and lowest polygenic g scores. Mean trajectories across development for individuals with polygenic g scores >145 and <55. Panel a: General cognitive ability (g) composite and domain-specific composites (nonverbal and verbal ability). Panel b: educational achievement outcomes including English, mathematics, science, and core-subject composite (sum of English, mathematics, and science). Panel c: Strengths and Difficulties Questionnaire (SDQ) five subscales and total problem score. All measures\", \"page\": 24, \"index\": 3, \"width\": 943, \"height\": 566}]"
motivation: 旨在利用成人多基因评分探索遗传因素在儿童至成年早期认知发展过程中的动态预测作用。
method: 结合成人认知能力和受教育程度的基因数据构建“多基因g评分”，并对1万名英国儿童进行跨时段的结构方程模型分析。
result: "多基因评分的预测力随年龄增长从幼儿期的极低水平上升至成年早期的12%，且能解释15%的跨时间潜认知因子方差。"
conclusion: 成人多基因g评分是追踪认知特质发展的有效工具，揭示了遗传影响随发育过程不断增强的趋势。
---

## 摘要
行为科学中预测力最强的多基因分数是针对认知特征的，尤其是一般认知能力（g）和受教育程度。我们结合了源自成年人g和受教育程度全基因组关联研究的多基因分数，创建了成年人“多基因g分数”，并利用该分数描绘了10,000名英国白人儿童从幼儿期到成年早期的认知发展历程。我们整合了横截面回归、潜增长曲线和验证性因子分析，以系统地表征认知发展。多基因g分数在幼儿期的预测力极小，在童年期具有中等预测力，到成年早期则具有显著的预测力，解释了12%的方差。在潜增长模型中，较高的多基因g分数与更快的认知增长相关。对跨时间潜认知因子（捕捉整个发展过程中的认知能力）的预测力最强（15%）。通过将多基因预测直接整合到结构方程模型框架中，我们提供了在最小测量误差下遗传对g影响的理论上限。我们还考察了多基因g分数对学业成就、行为问题和人体测量指标的预测作用，并发现对学业成就的预测也呈现出类似的随发育增长的趋势。总之，我们的研究结果表明，成年人多基因g分数可以作为描绘认知特征发展的一个有用工具。

## Abstract
The most highly predictive polygenic scores in the behavioural sciences are for cognitive traits, especially general cognitive ability (g) and educational attainment. We combined polygenic scores derived from genome-wide association studies of adult g and educational attainment to create adult 'polygenic g scores' which we used to chart the course of cognitive development of 10,000 white British children from toddlerhood through early adulthood. We integrated cross-sectional regression, latent growth curve, and confirmatory factor analysis to systematically characterise cognitive development. Polygenic g score showed minimal prediction in toddlerhood, modest prediction in childhood, and substantial prediction by early adulthood accounting for 12% of the variance. Higher polygenic g scores were associated with faster cognitive growth in latent growth models. Prediction was strongest for a cross-time latent cognitive factor (15%) capturing cognitive ability across development. By integrating polygenic prediction directly into a structural equation model framework, we provided a theoretical upper bound of genetic influences on g under minimal measurement error. We also examined the polygenic g score's prediction of educational achievement, behaviour problems, and anthropometric outcomes and found similar developmental increases in prediction for educational achievement. Together, our findings demonstrate that adult polygenic g scores can be a useful tool for charting the development of cognitive traits.

---

## 论文详细总结（自动生成）

这篇论文由伦敦国王学院的 Yujing Lin 和 Robert Plomin 发表，探讨了如何利用基于成年人全基因组关联研究（GWAS）构建的遗传指标来追踪儿童的认知发育轨迹。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：虽然个体的 DNA 在出生时就已固定，但遗传对认知能力的影响是否在整个发育过程中保持一致？研究旨在探索利用成年人的“多基因 g 分数”（polygenic g scores）能否有效预测儿童从幼儿期（2岁）到成年早期（26岁）的认知水平变化及增长速度。
*   **研究背景**：认知能力的遗传力随年龄增长而增加（即 Wilson 效应）。目前预测力最强的多基因评分（PGS）源自成年人的智力（g）和受教育程度（EA）。本研究试图通过这些“成年标准”来描绘儿童发育的遗传蓝图。

### 2. 论文提出的方法论
*   **核心思想**：构建一个复合的“多基因 g 分数”，并将其应用于长达 25 年的纵向表型数据中，通过结构方程模型（SEM）区分遗传对认知状态（截距）和增长率（斜率）的影响。
*   **关键技术细节**：
    *   **多基因评分构建**：使用 **LDpred2-auto** 处理 GWAS 汇总统计数据。
    *   **复合分数（SMTPred）**：利用 **SMTPred** 算法将受教育程度（EA-PGS）和智力（g-PGS）加权合并。在本研究中，EA-PGS 权重为 0.91，g-PGS 为 0.31，以最大化对一般认知能力的预测力。
    *   **统计模型**：
        *   **横截面回归**：计算各年龄点的方差解释量（$R^2$）。
        *   **潜增长曲线模型（LGCM）**：分析遗传分数如何预测认知的初始水平和随时间变化的斜率。
        *   **验证性因子分析（CFA）**：提取跨时间的潜因子，以消除测量误差，获取遗传影响的理论上限。

### 3. 实验设计
*   **数据集**：使用了**双生子早期发育研究（TEDS）**队列，包含约 10,000 名英国白人儿童。
*   **时间跨度**：从 2 岁、3 岁、4 岁一直追踪到 25/26 岁，涵盖幼儿期、童年期、青少年期和成年早期。
*   **评估指标（Outcomes）**：
    *   认知能力（言语、非言语、一般认知 g）。
    *   学业成就（7 岁至 16 岁的各科成绩及 GCSE 分数）。
    *   行为问题（SDQ 量表、多方评价）。
    *   人体测量（身高、BMI）。
*   **对比方法（Benchmark）**：将复合的“多基因 g 分数”与单一的 EA-PGS 和 g-PGS 进行对比，验证复合分数的增量预测效力。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的硬件配置（如 GPU 型号）。
*   **软件环境**：使用了 RStudio (2023.09.1) 进行统计分析，涉及 LDpred2 等生物信息学工具。此类研究通常依赖 CPU 集群进行基因型数据的清洗和评分计算，而非深度学习所需的 GPU 算力。

### 5. 实验数量与充分性
*   **实验规模**：样本量达 10,000 人，且拥有长达 20 多年的多次重复测量，数据量在同类发育遗传学研究中属于顶尖水平。
*   **充分性与公平性**：
    *   进行了**性别分层分析**（未发现显著性别差异）。
    *   进行了**合子类型（MZ/DZ）敏感性测试**。
    *   进行了**非线性测试**（加入二次项验证预测是否呈线性）。
    *   使用了**错误发现率（FDR）**进行多重比较校正。
    *   实验设计非常系统且客观，充分考虑了群体分层和测量误差。

### 6. 论文的主要结论与发现
*   **预测力随年龄增长**：多基因 g 分数在幼儿期预测力极低，但随年龄稳步上升。在 25 岁时，对认知能力的解释力达到 **12%**。
*   **潜因子预测上限**：在消除测量误差的 SEM 模型中，该分数对跨时间认知潜因子的预测力高达 **15%**。
*   **预测增长速度**：高多基因分数不仅预示着更高的起点，还预示着**更快的认知增长率**（斜率显著为正）。
*   **学业成就**：对 16 岁 GCSE 成绩的预测力最强，可解释 **18%** 的方差。
*   **线性关系**：遗传分数与认知表现之间呈纯线性关系，极端高分者和低分者在性质上并无不同，仅是程度上的差异。

### 7. 优点
*   **纵向深度**：极少数能从 2 岁追踪到 26 岁并结合基因组数据的研究。
*   **方法论严谨**：通过 SEM 和 CFA 提取潜因子，提供了遗传影响的“理论上限”，比单纯的横截面回归更具科学性。
*   **复合预测因子**：证明了结合 EA 和智力两种 PGS 能显著提升预测精度。

### 8. 不足与局限
*   **族群局限性**：样本仅限于**英国白人（欧洲裔）**，由于遗传背景和环境差异，结论无法直接推广到其他族裔。
*   **言语偏差**：由于复合分数中 EA-PGS 权重较高，该分数对言语能力的预测优于非言语能力（如空间、数学），存在一定的“言语偏向”。
*   **预测 vs 解释**：论文强调这是一种“预测工具”，而非“因果解释”。目前的 PGS 仍包含环境相关性（如基因-环境相关），不能简单等同于纯生物学因果。
*   **早期预测力弱**：在 7 岁之前，该分数的实用预测价值仍然有限。

（完）
