---
title: Sex-specific associations between education-related genetic factors and fertility extend beyond educational attainment
title_zh: 教育相关遗传因素与生育力之间的性别特异性关联超出了受教育程度的影响
authors: "Kuznetsov, I. A., Giannelis, A., Estonian Biobank Research Team,, Lehto, K., Laisk, T., Rietveld, C. A., Vainik, U., Pankratov, V."
date: 2026-05-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.29.721701v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 受教育程度多基因评分与生育力
tldr: 本研究利用爱沙尼亚生物库约5万名受试者数据，探讨了受教育程度（EA）相关的遗传因素与生育力之间的性别差异化关联。研究区分了认知与非认知遗传成分，并结合家系分析评估直接遗传效应。结果发现，女性的EA多基因评分与生育力呈负相关，且该关联独立于实际受教育程度，受首次怀孕年龄调节；而男性关联较弱。这揭示了遗传因素通过多种独立于教育的机制影响生育。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究受教育程度相关的遗传变异是否在教育水平之外独立影响生育力，并分析其在不同性别和文化背景下的表现。
method: 基于爱沙尼亚生物库数据，利用多基因评分（区分认知与非认知成分）及家系模型，分析遗传因素与生育力的关联。
result: 女性EA多基因评分与生育力显著负相关（非认知成分影响更大），且受首次怀孕年龄调节，而男性关联较弱或呈微弱正相关。
conclusion: 受教育程度相关的遗传因素通过独立于教育水平的路径影响生育，且其作用机制在性别和生殖时机上存在显著差异。
---

## 摘要
人口生育模式与社会经济不平等密切相关，其中受教育程度（EA）是终身生育力的关键预测指标。虽然 EA 具有部分遗传性，但与 EA 相关的遗传变异在多大程度上独立于教育而与生育力相关仍不清楚，特别是在西欧和北美以外的人群中。利用爱沙尼亚生物样本库（Estonian Biobank）中约 40,000 名女性和 10,000 名男性的数据，我们研究了 EA 多基因评分（EA PGS）与终身生育力之间的性别特异性关联。我们通过区分认知和非认知 EA 成分、考虑初次怀孕年龄（AFP）以及应用家系内分析来评估直接遗传效应的作用，扩展了先前的研究。在女性中，EA PGS 与生育力呈负相关，且非认知 EA 多基因评分的相关性显著强于认知评分。EA PGS 与生育力之间的关联受 EA 的调节，并在不同的 AFP 阶层中发生符号变化：在 AFP 较早的女性中呈负相关，而在 AFP 较晚的女性中呈正相关。重要的是，这种关联在家系内模型中并未减弱，这与直接遗传效应起主导作用的观点一致。在男性中，这种关联较弱或呈微弱的正相关，并且在不同教育群体中保持稳定。总之，与 EA 相关的遗传变异通过似乎在很大程度上独立于受教育程度的途径与生育力相关，这表明共同的遗传影响通过多种机制发挥作用，而这些机制因性别和生育时机而异。

## Abstract
Population fertility patterns are closely linked to socioeconomic inequality, with educational attainment (EA) being a key predictor of completed fertility. While EA is partially heritable, the extent to which EA-associated genetic variation relates to fertility independently of education remains unclear, particularly outside Western European and North American populations. Using data from ~40,000 women and ~10,000 men in the Estonian Biobank, we examine sex-specific associations between EA polygenic scores (EA PGS) and completed fertility. We extend prior work by distinguishing cognitive and non-cognitive EA components, accounting for age at first pregnancy (AFP), and applying within-family analyses to assess the role of direct genetic effects. Among women, EA PGS is negatively associated with fertility, with a significantly stronger association for the non-cognitive than the cognitive EA polygenic score. The association between EA PGS and fertility is moderated by EA and changes sign across AFP strata, from negative among women with earlier AFP to positive among those with later AFP. Importantly, this association is not attenuated in within-family models, consistent with a predominant role of direct genetic effects. Among men, associations are weak or slightly positive and stable across education groups. Overall, EA-related genetic variation is associated with fertility through pathways that appear largely independent of educational attainment, suggesting that shared genetic influences operate through multiple mechanisms that differ by sex and reproductive timing.

---

## 论文详细总结（自动生成）

这篇论文题为《教育相关遗传因素与生育力之间的性别特异性关联超出了受教育程度的影响》，是一项基于大规模生物库数据的社会科学基因组学研究。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义
*   **研究动机**：在现代社会，受教育程度（EA）与生育力呈负相关，且两者均具有遗传性。以往研究发现，与高教育程度相关的遗传变异在现代人群中正受到负向选择（即高 EA 遗传倾向者生育更少）。
*   **核心问题**：这种遗传关联是否仅仅是因为这些基因让人读了更多书（从而推迟生育），还是存在独立于教育水平之外的生物或心理路径？此外，这种关联在不同性别、不同社会背景（如经历剧变的爱沙尼亚）下是否一致？
*   **整体含义**：研究旨在揭示遗传因素如何通过性别特异性和生命历程特异性的途径影响人类的生殖行为。

### 2. 方法论
*   **核心思想**：利用多基因评分（PGS）作为遗传倾向的代理变量，结合人口统计学数据，通过多维度统计模型拆解遗传、教育与生育的关系。
*   **关键技术细节**：
    *   **准泊松回归（Quasi-Poisson GLM）**：用于处理生育数量（计数数据）的分布，估计预期生育率比（EFR）。
    *   **GWAS-by-subtraction**：将 EA 的遗传效应分解为“认知成分”（Cog）和“非认知成分”（NonCog，如性格、动机等）。
    *   **中介与调节模型**：分析实际受教育程度（EA）和初次怀孕年龄（AFP）如何中介或调节遗传效应。
    *   **家系内设计（Within-family）**：通过同胞对比和父母 PGS 调整，排除家庭环境混杂（如“养育”效应），提取“直接遗传效应”。

### 3. 实验设计
*   **数据集**：爱沙尼亚生物库（Estonian Biobank），样本量约为 40,000 名女性和 10,000 名男性，涵盖了 20 世纪初至 20 世纪末出生的多个队列。
*   **Benchmark/对比维度**：
    *   **性别对比**：分别对男性和女性进行独立建模。
    *   **成分对比**：对比认知 PGS 与非认知 PGS 的效应差异。
    *   **社会背景对比**：对比苏联时期与后苏联时期的效应变化。
    *   **分层对比**：按教育水平（初等、中等、高等）和 AFP 阶段进行分层分析。

### 4. 资源与算力
*   **算力说明**：文中明确提到数据分析是在塔尔图大学的**高性能计算中心（High-Performance Computing Center）**完成的。
*   **具体细节**：未披露具体的 GPU/CPU 型号、核心数或具体的训练/计算时长。此类研究通常侧重于大规模统计推断而非深度学习模型训练，因此对内存和并行计算能力要求较高。

### 5. 实验数量与充分性
*   **实验规模**：研究基于约 5 万人的基因与表型数据，实验组别涵盖了群体关联分析、中介分析、交互分析及家系验证。
*   **充分性评价**：
    *   **非常充分**：研究不仅做了群体水平的关联，还通过家系模型这一“金标准”验证了直接遗传效应，增强了结论的可靠性。
    *   **客观性**：通过调整出生地、参与波次、前 10 个主成分（PC）等变量，有效控制了人口结构混杂。
    *   **多维度验证**：对认知与非认知成分的拆解是该领域较为前沿且深入的尝试。

### 6. 主要结论与发现
*   **性别差异显著**：女性中 EA PGS 与生育力呈显著负相关；而男性中关联极弱甚至在某些模型下呈微弱正相关。
*   **非认知成分主导**：在女性中，非认知遗传成分（与性格、行为倾向相关）对生育力的负面影响比认知成分（智力相关）更强。
*   **独立于教育**：实际受教育程度只能解释女性遗传关联的一小部分（约 30%），说明遗传因素通过教育以外的路径（如职业抱负、价值观）影响生育。
*   **AFP 的调节作用**：在早育女性中，高 EA PGS 预示着更少的子女；但在晚育女性中，高 EA PGS 反而与更多的子女相关，显示出一种“资源保障”效应。

### 7. 优点
*   **精细化拆解**：成功区分了认知与非认知遗传因素，比传统的单一 EA PGS 研究更具深度。
*   **家系验证**：利用家系数据排除了“被动基因-环境相关性”，证明了结论的生物学基础。
*   **背景独特性**：提供了东欧转型社会的证据，补充了以往仅局限于西欧和北美的数据空白。

### 8. 不足与局限
*   **男性样本量不足**：男性的样本量仅为女性的四分之一，导致男性分析的统计效能受限，可能掩盖了一些微弱的关联。
*   **代理指标偏差**：使用“初次怀孕年龄”作为“初次生育年龄”的代理，可能受到流产、引产等因素的干扰。
*   **生存与参与偏差**：生物库参与者通常比一般人群更健康、受教育程度更高，这可能导致对早期出生队列的效应估计存在偏差。
*   **因果路径复杂**：虽然证明了“独立于教育”，但具体的替代路径（如具体的性格特质或经济稳定性）仍需进一步明确。

（完）
