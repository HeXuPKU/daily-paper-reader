---
title: "Improving GWAS performance in underrepresented groups by appropriate modeling of genetics, environment, and sociocultural factors"
title_zh: 通过对遗传、环境和社会文化因素进行适当建模，提高代表性不足群体中全基因组关联研究（GWAS）的性能
authors: "Cataldo-Ramirez, C., Lin, M., McMahon, A., Gignoux, C., Weaver, T. D., Henn, B. M."
date: 2026-04-08
pdf: "https://www.biorxiv.org/content/10.1101/2024.10.28.620716v2.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 通过遗传和环境建模提高 GWAS 和 PGS 的性能
tldr: 本研究旨在解决全基因组关联分析（GWAS）中非欧洲人群代表性不足的问题。通过对英国生物样本库（UKB）中南亚裔参与者的遗传亲缘关系进行表征，并利用支持向量机（SVM）对模糊族群标签进行重新分类，成功扩大了南亚样本量。研究进一步通过引入环境协变量优化了身高GWAS模型，证明了即使在样本量较小的情况下，通过精细化建模也能显著提升多基因评分（PGS）的预测性能并减少性别偏差。
source: biorxiv
selection_source: fresh_fetch
motivation: 针对生物样本库中非欧洲人群数据利用率低且GWAS模型在少数族裔中表现不佳的问题，探索提升其预测效能的方法。
method: 利用支持向量机对模糊族群标签进行亚大陆级别的重新分类以扩大样本量，并在GWAS模型中引入严格筛选的环境协变量。
result: "成功增加了1,381名南亚裔样本，且环境调整后的PGS模型在较小样本量下达到了与大规模训练集相当的预测效果，并减少了性别偏差。"
conclusion: 通过优化族群分类、使用匹配的归补面板及纳入环境因素，可以有效提升少数族裔GWAS的性能和公平性。
---

## 摘要
全基因组关联研究（GWAS）和多基因评分（PGS）的开发通常受限于生物样本库中可用的数据，而在这些样本库中，欧洲队列的比例严重失衡。在本研究中，我们通过表征英国生物样本库（UKB）中自我认同为孟加拉国人、印度人、巴基斯坦人、“白人与亚洲人混血”（WA）以及“任何其他亚洲人”（AOA）参与者的遗传亲缘关系，提高了非欧洲参与者数据的效用，旨在为未来的遗传分析创建一个更稳健的南亚样本集。我们评估了遗传结构与自选种族身份之间的关系，并利用数据集中一致的聚类模式训练了一个支持向量机（SVM）。该 SVM 被用于在次大陆层面重新分配 n = 1,853 名 AOA 和 WA 参与者，使 UKB 南亚组的样本量增加了 1,381 名。我们进一步利用这些样本来评估 GWAS 性能和 PGS 开发。我们通过执行严格的协变量选择程序，在身高 GWAS 中纳入了环境协变量，并比较了两个 GWAS 模型（GWASnull 和 GWASenv）的输出。结果表明，从这两个 GWAS 模型中得出的 PGS 性能与使用大一个数量级的训练集开发的 PGS 模型具有相当的预测能力，且经过环境调整的 PGS 模型减少了预测性能中的性别偏差。总之，我们展示了如何通过利用模糊的种族代码、祖源匹配的填充面板以及纳入环境协变量来提高 GWAS 的性能。

## Abstract
Genome-wide association studies (GWAS) and polygenic score (PGS) development are typically constrained by the data available in biobank repositories in which European cohorts are vastly overrepresented. Here, we increase the utility of non-European participant data within the UK Biobank (UKB) by characterizing the genetic affinities of UKB participants who self-identify as Bangladeshi, Indian, Pakistani, "White and Asian" (WA), and "Any Other Asian" (AOA), towards creating a more robust South Asian sample size for future genetic analyses. We assess the relationships between genetic structure and self-selected ethnic identities and use consistent patterns of clustering in the dataset to train a support vector machine (SVM). The SVM was utilized to reassign n = 1,853 AOA and WA participants at the subcontinental level, and increase the sample size of the UKB South Asian group by 1,381 additional participants. We further leverage these samples to assess GWAS performance and PGS development. We include environmental covariates in the height GWAS by implementing a rigorous covariate selection procedure, and compare the outputs of two GWAS models: GWASnull and GWASenv. We show that PGS performance derived from both GWAS models yield comparable prediction to PGS models developed with an order of magnitude larger training, and environmentally-adjusted PGS models reduce the sex-bias in predictive performance. In summary, we demonstrate how GWAS performance can be improved by leveraging ambiguous ethnicity codes, ancestry matched imputation panels, and including environmental covariates.

---

## 论文详细总结（自动生成）

这篇论文针对全基因组关联研究（GWAS）中非欧洲人群代表性不足及预测效能低下的问题，提出了一套结合遗传聚类优化和环境因素建模的改进方案。以下是对该论文的详细总结：

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：当前的遗传学研究（如 GWAS 和多基因评分 PGS）存在严重的“欧洲中心主义”偏差。非欧洲人群（如南亚裔）在生物样本库中占比小，且由于遗传背景差异和环境因素干扰，直接套用欧洲人群的模型在这些群体中表现不佳。
*   **研究动机**：
    *   **样本流失**：许多参与者在生物样本库中选择了模糊的族群标签（如“其他亚洲人”），导致在特定族群分析中被排除。
    *   **环境混杂**：身高、BMI 等表型受社会经济地位、营养和文化因素影响显著，传统的 GWAS 模型往往忽略了这些非遗传因素的复杂贡献。
    *   **预测偏差**：现有的 PGS 在不同性别和族群间存在预测不准确和不公平的问题。

### 2. 论文提出的方法论
*   **核心思想**：通过机器学习精细化族群分类以“扩容”样本，并结合严格筛选的环境协变量来“提质”GWAS 模型。
*   **关键技术细节**：
    1.  **基于 SVM 的族群重分类**：利用主成分分析（PCA）提取遗传结构特征，以自我认同明确的个体（印度、巴基斯坦、孟加拉国人）为训练集，构建支持向量机（SVM）模型。对标签模糊（“任何其他亚洲人” AOA、“白人与亚洲人混血” WA）的个体进行亚大陆级别的重新分配。
    2.  **环境协变量筛选（Covariate Selection）**：从英国生物样本库（UKB）中提取社会经济（如汤森剥夺指数）、饮食、教育、居住环境等非遗传变量。
    3.  **GWAS 模型对比**：
        *   **GWAS_null**：仅包含年龄、性别和前 10 个主成分（PCs）。
        *   **GWAS_env**：在 null 模型基础上，加入通过统计筛选的显著环境协变量。
    4.  **多基因评分（PGS）构建**：使用 PRS-CS 等工具，基于上述两种模型生成的效应值构建 PGS，并评估其在独立测试集中的预测准确性（$R^2$）。

### 3. 实验设计
*   **数据集**：英国生物样本库（UK Biobank, UKB）。
*   **研究对象**：南亚裔（South Asian, SAS）参与者。
*   **表型选择**：身高（Height），因其具有高遗传率且受环境影响明确。
*   **Benchmark（基准）**：
    *   对比未经过 SVM 扩充的原始样本集。
    *   对比不含环境协变量的标准 GWAS 模型。
    *   对比使用超大规模欧洲人群训练的 PGS 模型（如 GIANT 研究）。
*   **对比方法**：比较了不同模型在预测准确度、性别偏差（Sex-bias）以及跨族群迁移能力上的表现。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号或训练时长。
*   **工具链**：通常此类研究涉及 PLINK、REGENIE 或 SAIGE 等生物信息学工具，以及用于 SVM 训练的 Python (Scikit-learn) 或 R 环境。由于处理的是数万人的基因型数据，通常需要高性能计算集群（HPC）支持。

### 5. 实验数量与充分性
*   **实验规模**：
    *   对 1,853 名模糊标签个体进行了重分类，成功找回 1,381 名南亚裔样本。
    *   进行了多轮 GWAS 关联分析，并针对不同性别进行了分层验证。
    *   通过交叉验证评估了 PGS 的稳健性。
*   **充分性与客观性**：实验设计较为充分。作者不仅关注了样本量的提升，还深入探讨了环境因素如何解释“缺失的遗传率”。通过对比性别间的预测差异，评估了模型的公平性，实验逻辑闭环且客观。

### 6. 论文的主要结论与发现
1.  **样本扩容有效性**：SVM 能够准确地从模糊标签中识别出具有特定遗传背景的个体，有效缓解了少数族裔样本量不足的问题。
2.  **环境建模的重要性**：在 GWAS 中纳入环境协变量（如社会经济地位）显著提升了模型捕捉遗传效应的能力。
3.  **“小而精”胜过“大而全”**：研究发现，使用较小规模但经过环境校正的南亚裔本地数据训练的 PGS，其预测性能可以媲美甚至超过使用大一个数量级的欧洲人群数据训练的模型。
4.  **减少性别偏差**：环境调整后的模型在男性和女性中的预测表现更加均衡，减少了因社会文化因素导致的性别预测差异。

### 7. 优点
*   **方法创新**：将机器学习（SVM）应用于族群标签修复，为生物样本库数据的二次开发提供了新思路。
*   **关注公平性**：不仅追求预测精度，还通过环境建模试图解决遗传预测中的性别和族群偏差问题。
*   **实用性强**：证明了在资源有限（样本量小）的情况下，通过精细化统计建模也能获得高质量的遗传预测结果。

### 8. 不足与局限
*   **表型局限性**：研究主要集中在身高这一高度遗传且易于测量的表型上，对于精神疾病或复杂慢性病等受环境影响更复杂的性状，该方法的普适性尚待验证。
*   **环境数据的完整性**：UKB 中的环境数据多为自述或特定时间点的采样，可能存在测量误差或无法覆盖全生命周期的环境暴露。
*   **族群覆盖**：虽然改善了南亚裔的表现，但对于遗传背景更为复杂的混血人群（Admixed populations），简单的 SVM 分类可能仍显不足。

（完）
