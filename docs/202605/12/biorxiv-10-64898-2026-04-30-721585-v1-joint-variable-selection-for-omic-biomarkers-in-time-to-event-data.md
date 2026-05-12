---
title: Joint Variable Selection for Omic Biomarkers in Time-to-Event Data
title_zh: 事件发生时间数据中组学生物标志物的联合变量选择
authors: "Bajzik, J., Depope, A., Zolfimoselo, Y., Sharipov, A., Lesayova, A., Klein, H., Richmond, A., Vernardis, S., Grauslys, A., Andrejev, S., Zelezniak, A., Ralser, M., Marioni, R., Mondelli, M., Robinson, M. R."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721585v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用贝叶斯方法将电子健康档案与多组学联系起来
tldr: 针对大规模生物库中多组学数据与疾病发病时间关联分析中存在的虚假发现和相关性忽略问题，本文提出了一种名为vampW的贝叶斯计算方法。该方法基于向量近似消息传递框架和Weibull模型，实现了对相关特征的联合建模。在UK Biobank等数据集上的实验表明，vampW在降低假阳性率、识别关键蛋白质关联以及提高疾病发病时间预测准确性方面显著优于传统CoxPH模型和深度学习方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的单变量Cox比例风险模型在处理高维多组学数据时容易忽略特征间的相关性，从而导致较高的虚假发现率并限制了预测精度。
method: 提出了一种基于向量近似消息传递（VAMP）框架和Weibull分布的参数化贝叶斯联合建模方法vampW，用于变量选择和生存分析。
result: "在UK Biobank数据中识别出219个蛋白质与24种疾病的关联，且在预测疾病发病时间上比DeepSurv等方法降低了超过26%的均方根误差。"
conclusion: vampW为复杂疾病的基因组架构解析提供了一个准确、可解释且具备强大预测能力的变量选择与预测框架，适用于大规模生物库研究。
---

## 摘要
绝大多数神经退行性疾病、癌症和代谢性疾病的发病率通常随年龄呈指数级增长。在大规模生物样本库中，将电子健康记录中的诊断时间信息与多种基因组（“多组学”）测量数据相结合，有可能揭示参与疾病发生和进展的基因及生物通路。迄今为止，关联性测试通常使用半参数 Cox 比例风险（CoxPH）模型，通过一次测试一个变量来进行，这忽略了相关性结构并增加了假阳性发现的风险。为了解决这些问题，我们引入了一种新型的全参数贝叶斯计算方法 vampW，该方法基于应用于 Weibull 模型的向量近似消息传递（Vector Approximate Message Passing）框架。vampW 对相关特征进行联合建模，同时提供可解释的风险结构，生成连续的生存曲线，并整合先验知识。在广泛的模拟研究中，我们证明了使用 vampW 对组学数据和事件发生时间结果进行联合建模，与边际测试和其他形式的联合 CoxPH 模型相比，显著减少了假阳性发现。在来自英国生物样本库（UK Biobank）的 53,018 名个体中，vampW 识别出 219 种蛋白质与 24 种疾病结果的关联，其中大多数不在顶级的边际发现之列。我们进一步针对指数年龄效应校正了蛋白质水平，识别出 1,308 项关联，并强调了分析对年龄校正方法的敏感性。我们的发现在使用不同测量技术的独立队列中得到了验证，包括来自冰岛的数据和一个新的 Generation Scotland 蛋白质组学数据集。vampW 在疾病发病时间预测方面也取得了显著改进：在 14 种结果中，与 CoxPH 变体和深度学习方法 DeepSurv 相比，其均方根误差分别降低了 32% 以上和 26% 以上，同时在少数族裔群体中保持了预测效用。总之，vampW 在单一计算框架内提供了准确且可解释的变量选择和样本外预测，使其成为剖析常见复杂疾病发病基因组结构的强大工具。

## Abstract
The incidence of the vast majority of neurodegenerative, cancer, and metabolic diseases generally increases exponentially with age. In large-scale biobanks, linking time-to-diagnosis information in electronic health records to multiple genomic ("multiomics") measures has the potential to reveal the genes and biological pathways involved in the disease onset and progression. To date, association testing has commonly been conducted by testing one variable at a time using semiparametric Cox proportional hazards (CoxPH) models, which ignores correlation structure and increases the risk of false discoveries. To address these issues, we introduce a novel fully parametric Bayesian computational method, vampW, based on the Vector Approximate Message Passing framework applied to a Weibull model. vampW jointly models correlated features, while providing an interpretable hazard structure, producing a continuous survival curve, and incorporating prior knowledge. In an extensive simulation study, we demonstrate that joint modeling of omics data and time-to-event outcomes with vampW, substantially reduces false discoveries in comparison to marginal testing and other forms of joint CoxPH models. In 53,018 individuals from the UK Biobank, vampW identifies 219 protein associations with 24 disease outcomes, most of which are not among the top marginal discoveries. We further correct protein levels for exponential age effects, identifying 1,308 associations and highlighting the sensitivity of the analysis to age-correction methodology. Our findings replicate in independent cohorts using different measurement technologies, within data from Iceland and a novel Generation Scotland proteomics dataset. vampW also achieves significant improvement in the prediction of disease onset times: across 14 outcomes, it reduces the root mean squared error by over 32% and 26%, when compared to CoxPH variants and the deep learning approach DeepSurv, respectively, while maintaining predictive utility in minority populations. In summary, vampW offers accurate and interpretable variable selection and out-of-sample prediction within a single computational framework, making it a powerful tool for dissecting the genomic architecture of common complex disease onset.

---

## 论文详细总结（自动生成）

以下是对论文《Joint Variable Selection for Omic Biomarkers in Time-to-Event Data》的深度结构化总结：

### 1. 核心问题与整体含义
*   **研究动机**：大多数慢性病（如癌症、神经退行性疾病）的发病风险随年龄呈指数级增长。在大规模生物库中，将多组学数据与电子健康档案（EHR）中的发病时间结合，有助于揭示疾病机制。
*   **现有痛点**：
    *   传统的 **Cox比例风险模型（CoxPH）** 多用于单变量（边际）测试，忽略了组学特征间的高度相关性，导致假阳性率高。
    *   半参数模型仅能提供相对风险评分，无法直接预测个体的**绝对发病时间**。
    *   深度学习方法在小样本或数据稀缺场景下表现不佳，且缺乏可解释性。
*   **核心目标**：开发一种能够联合处理高维相关特征、控制假阳性、并准确预测绝对发病时间的贝叶斯全参数建模框架。

### 2. 方法论
*   **核心思想**：提出 **vampW** 算法，将 **向量近似消息传递（VAMP）** 框架应用于全参数 **Weibull 生存模型**。
*   **关键技术细节**：
    *   **Weibull 渠道去噪器**：针对 Weibull 似然函数推导了非线性 MMSE（最小均方误差）估计器，用于处理非线性观测。
    *   **右删失处理机制**：创新性地将生存函数（Survival Function）引入 VAMP 的优化目标中，使算法能够处理未观测到事件发生的删失数据。
    *   **自适应 Spike-and-Slab 先验**：利用混合高斯分布作为先验，通过期望最大化（EM）算法自适应学习特征的稀疏度（$\lambda$）和效应大小。
    *   **算法流程**：通过两个去噪步骤（针对效应量 $\beta$ 和潜在预测因子 $z$）以及两个线性 MMSE 步骤循环迭代，并引入阻尼（Damping）机制确保在违反旋转不变性假设的真实数据上收敛。

### 3. 实验设计
*   **数据集**：
    *   **UK Biobank (UKB)**：53,018 名个体，2,924 种蛋白质（Olink 平台），24 种疾病结果。
    *   **外部验证**：冰岛 SomaScan 队列（36,000 人）、Generation Scotland 质谱蛋白质组数据集。
    *   **标准基准**：METABRIC, SUPPORT, GBSG, SAC3 等生存分析公开数据集。
*   **对比方法 (Benchmarks)**：
    *   边际 CoxPH（单变量测试）。
    *   联合 CoxPH（全变量回归）。
    *   LASSO-CoxPH（带稳定性选择）。
    *   DeepSurv（深度学习生存分析基准）。
*   **评估指标**：假发现率 (FDR)、真阳性率 (TPR)、一致性指数 (C-index)、均方根误差 (RMSE)。

### 4. 资源与算力
*   **硬件环境**：AMD EPYC 9654 处理器。
*   **算力消耗**：
    *   **内存**：每个性状分析约需 **64 GB RAM**。
    *   **时长**：平均每个性状耗时 **12.7 CPU 小时**。
    *   **成本**：在 DNAnexus 云端运行，每个性状约 7.3 英镑（相比之下，LASSO-CoxPH 约 10.5 英镑）。

### 5. 实验数量与充分性
*   **模拟实验**：设计了 **24 种模拟场景**（涵盖不同信噪比、删失率、分布误设定等），每种场景重复 50 次，共计 1200 组实验，验证了算法在各种极端情况下的鲁棒性。
*   **真实数据分析**：覆盖了 24 种主要疾病，并进行了**跨技术平台**（Olink vs 质谱）和**跨人群**（英国、冰岛、非洲裔、南亚裔）的验证。
*   **充分性评价**：实验设计非常充分，不仅有大规模真实数据应用，还包含了针对年龄校正方法的消融研究，以及在数据稀缺场景下与 13 种深度学习/传统方法的对比。

### 6. 主要结论与发现
*   **变量选择更优**：vampW 在保持极低 FDR 的同时，TPR 显著高于 CoxPH 变体。在 UKB 中识别出 219 个（未校正指数年龄）或 1308 个（校正后）显著蛋白关联。
*   **预测精度领先**：在发病时间预测上，vampW 的 RMSE 比 CoxPH 降低了 **32%**，比 DeepSurv 降低了 **26%**。
*   **生物学意义**：发现了 CXCL17 与抑郁症的新关联，并证实了 APOE（阿尔茨海默病）、REN（高血压）等经典标志物。
*   **跨人群迁移**：生成的蛋白质风险评分在少数族裔中表现出良好的迁移性和预测效用。

### 7. 优点
*   **全参数化预测**：相比半参数模型，能直接给出具体的发病年龄预测，具有更高的临床参考价值。
*   **处理相关性**：联合建模有效解决了组学数据中普遍存在的共线性问题，减少了虚假关联。
*   **小样本优势**：在数据稀缺的生存分析基准测试中，表现优于几乎所有深度学习模型。
*   **可解释性**：提供后验包含概率（PIP），方便研究者筛选关键生物标志物。

### 8. 不足与局限
*   **计算压力**：虽然比 LASSO 高效，但面对数百万级别的基因组标记（如全基因组关联研究）时，内存需求仍是挑战。
*   **分布假设限制**：Weibull 分布假设风险随时间单调变化，对于某些风险波动剧烈的疾病（如精神分裂症）可能不完全适用。
*   **混杂因素覆盖**：目前主要校正了年龄和性别，对于药物干预、生活方式等动态混杂因素的整合仍有待加强。

（完）
