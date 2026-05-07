---
title: Joint Variable Selection for Omic Biomarkers in Time-to-Event Data
title_zh: 事件发生时间数据中组学标志物的联合变量选择
authors: "Bajzik, J., Depope, A., Zolfimoselo, Y., Sharipov, A., Lesayova, A., Klein, H., Richmond, A., Vernardis, S., Grauslys, A., Andrejev, S., Zelezniak, A., Ralser, M., Marioni, R., Mondelli, M., Robinson, M. R."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721585v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 利用贝叶斯变量选择将电子健康记录诊断时间与多组学指标联系起来
tldr: 针对多组学数据与疾病发病时间关联分析中，传统边际Cox模型忽略特征相关性且假阳性率高的问题，本文提出了一种基于Weibull模型的贝叶斯计算方法vampW。该方法利用向量近似消息传递框架实现联合变量选择，能有效处理高维相关特征并提供可解释的生存曲线。在UK Biobank等大规模数据集上的实验证明，vampW在降低假阳性、发现新生物标志物及预测发病时间方面显著优于现有方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的边际Cox比例风险模型在处理多组学数据时忽略了特征间的相关结构，导致较高的假阳性发现率。
method: 提出了一种名为vampW的完全参数化贝叶斯方法，将向量近似消息传递（VAMP）框架应用于Weibull生存模型以实现联合变量选择。
result: "在UK Biobank数据中发现了大量新的蛋白质与疾病关联，且在发病时间预测的均方根误差上比DeepSurv等深度学习方法降低了26%以上。"
conclusion: vampW集成了准确的变量选择和出色的样本外预测能力，是解析复杂疾病基因组结构的强有力工具。
---

## 摘要
绝大多数神经退行性疾病、癌症和代谢性疾病的发病率通常随年龄呈指数级增长。在大规模生物样本库中，将电子健康记录中的诊断时间信息与多种基因组（“多组学”）测量数据相关联，有可能揭示参与疾病发生和进展的基因及生物学通路。迄今为止，关联性测试通常使用半参数 Cox 比例风险 (CoxPH) 模型逐个测试变量，这忽略了相关性结构并增加了假阳性发现的风险。为了解决这些问题，我们引入了一种新型的全参数贝叶斯计算方法 vampW，该方法基于应用于 Weibull 模型的向量近似消息传递 (Vector Approximate Message Passing) 框架。vampW 对相关特征进行联合建模，同时提供可解释的风险结构，生成连续的生存曲线，并整合先验知识。在广泛的模拟研究中，我们证明了与边际测试和其他形式的联合 CoxPH 模型相比，使用 vampW 对组学数据和事件发生时间结果进行联合建模显著减少了假阳性发现。在来自英国生物样本库 (UK Biobank) 的 53,018 名个体中，vampW 识别出 219 种蛋白质与 24 种疾病结果的关联，其中大多数不在顶级的边际发现之列。我们进一步针对指数年龄效应校正了蛋白质水平，识别出 1,308 项关联，并强调了分析对年龄校正方法的敏感性。我们的发现在使用不同测量技术的独立队列中得到了验证，包括来自冰岛的数据和一个新型的 Generation Scotland 蛋白质组学数据集。vampW 在疾病发病时间预测方面也取得了显著改进：在 14 种结果中，与 CoxPH 变体和深度学习方法 DeepSurv 相比，它分别将均方根误差降低了 32% 和 26% 以上，同时在少数族裔群体中保持了预测效用。总之，vampW 在单一计算框架内提供了准确且可解释的变量选择和样本外预测，使其成为剖析常见复杂疾病发病基因组结构的强大工具。

## Abstract
The incidence of the vast majority of neurodegenerative, cancer, and metabolic diseases generally increases exponentially with age. In large-scale biobanks, linking time-to-diagnosis information in electronic health records to multiple genomic (``multiomics'') measures has the potential to reveal the genes and biological pathways involved in the disease onset and progression. To date, association testing has commonly been conducted by testing one variable at a time using semiparametric Cox proportional hazards (CoxPH) models, which ignores correlation structure and increases the risk of false discoveries. To address these issues, we introduce a novel fully parametric Bayesian computational method, vampW, based on the Vector Approximate Message Passing framework applied to a Weibull model. vampW jointly models correlated features, while providing an interpretable hazard structure, producing a continuous survival curve, and incorporating prior knowledge. In an extensive simulation study, we demonstrate that joint modeling of omics data and time-to-event outcomes with vampW, substantially reduces false discoveries in comparison to marginal testing and other forms of joint CoxPH models. In 53,018 individuals from the UK Biobank, vampW identifies 219 protein associations with 24 disease outcomes, most of which are not among the top marginal discoveries. We further correct protein levels for exponential age effects, identifying 1,308 associations and highlighting the sensitivity of the analysis to age-correction methodology. Our findings replicate in independent cohorts using different measurement technologies, within data from Iceland and a novel Generation Scotland proteomics dataset. vampW also achieves significant improvement in the prediction of disease onset times: across 14 outcomes, it reduces the root mean squared error by over 32% and 26%, when compared to CoxPH variants and the deep learning approach DeepSurv, respectively, while maintaining predictive utility in minority populations. In summary, vampW offers accurate and interpretable variable selection and out-of-sample prediction within a single computational framework, making it a powerful tool for dissecting the genomic architecture of common complex disease onset.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **vampW** 的新型贝叶斯计算框架，旨在解决多组学数据与疾病发病时间（Time-to-Event）关联分析中的挑战。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
在生物医学研究中，将大规模多组学数据（如蛋白质组学）与电子健康记录（EHR）中的疾病诊断时间联系起来，对于发现疾病生物标志物和预测发病风险至关重要。
*   **研究动机**：现有的主流方法（如半参数 Cox 比例风险模型 CoxPH）通常采用“边际测试”（一次只测一个变量），这忽略了组学特征间普遍存在的相关性，导致极高的假阳性率。
*   **核心挑战**：如何在处理高维相关特征的同时，准确处理生存分析中的“右删失”数据（即研究结束时部分人尚未患病），并提供可解释的绝对发病时间预测。

### 2. 方法论：核心思想与关键技术
论文提出了 **vampW**，一种基于 **向量近似消息传递（VAMP）** 框架的全参数贝叶斯 Weibull 生存模型。
*   **核心思想**：将生存分析转化为一个非线性高维回归问题，通过 Weibull 分布对发病时间建模，并利用贝叶斯框架进行联合变量选择。
*   **关键技术细节**：
    *   **Weibull 模型**：采用全参数 Weibull 分布，将对数发病时间表示为线性预测因子、Weibull 形状参数和 Gumbel 噪声的组合。
    *   **先验分布**：使用自适应的 **Spike-and-Slab（脉冲与阶梯）** 先验，通过混合高斯分布模拟不同强度的效应大小，实现稀疏变量选择。
    *   **VAMP 框架**：引入了专门针对 Weibull 似然函数的**通道去噪器（Channel Denoiser）**，并开发了处理**右删失数据**的新机制。
    *   **参数估计**：利用期望最大化（EM）算法自适应地从数据中学习先验参数和 Weibull 分布参数。

### 3. 实验设计
*   **数据集**：
    *   **主数据集**：英国生物样本库（UK Biobank, UKB）PPP 项目，包含 53,018 名个体的 2,924 种蛋白质测量值和 24 种疾病的发病时间。
    *   **验证数据集**：冰岛 SomaScan 队列（36,000 人）和 Generation Scotland 质谱蛋白质组学数据集。
*   **Benchmark（对比方法）**：
    *   边际 CoxPH（Marginal CoxPH）
    *   联合非惩罚 CoxPH
    *   带稳定性选择的 LASSO 惩罚 CoxPH
    *   深度学习方法 DeepSurv
*   **评估指标**：假阳性率（FDR）、真阳性率（TPR）、一致性指数（C-index）和均方根误差（RMSE）。

### 4. 资源与算力
*   **硬件环境**：实验在 AMD EPYC 9654 处理器上运行。
*   **算力消耗**：
    *   **内存**：单个性状分析约需 **64 GB RAM**。
    *   **时长**：单个性状分析平均耗时 **12.7 CPU 小时**。
    *   **成本**：在 DNAnexus 云平台上，单个性状分析成本约为 7.3 英镑。
*   **对比**：其计算效率优于带稳定性选择的 LASSO-CoxPH（后者需 60.8 CPU 小时）。

### 5. 实验数量与充分性
*   **模拟实验**：设计了 **24 种模拟场景**（涵盖不同信噪比、删失率、分布误设和先验分布），每种场景重复 **50 次**。
*   **真实数据实验**：对 **24 种复杂疾病** 进行了全面分析，并进行了跨种族（非洲裔、南亚裔）的迁移性测试。
*   **充分性评价**：实验设计非常充分且严谨。通过模拟验证了算法在模型误设下的鲁棒性，通过跨技术平台（Olink vs. 质谱）和跨队列（英国 vs. 冰岛）的验证，确保了结论的客观性和公平性。

### 6. 主要结论与发现
*   **变量选择更精准**：在模拟中，vampW 的 TPR 显著高于 CoxPH 变体，且 FDR 控制良好。在 UKB 数据中识别出 219-1308 个蛋白质关联，其中许多是传统边际测试无法发现的新标志物（如 CXCL17 与抑郁症）。
*   **预测性能卓越**：在发病时间预测（RMSE）上，vampW 比 DeepSurv 提升了 **26%**，比 CoxPH 变体提升了 **32%**。
*   **年龄校正的重要性**：研究发现蛋白质水平受年龄的指数效应影响巨大，采用非线性年龄校正会显著改变关联分析的结果。
*   **跨族裔迁移性**：在英国白人数据上训练的模型，在非洲裔和南亚裔人群中依然保持了良好的预测效用。

### 7. 优点
*   **联合建模能力**：能够同时处理数千个相关特征，有效区分直接关联和相关性导致的假阳性。
*   **全参数化优势**：不同于 Cox 模型的相对风险评分，vampW 能直接预测绝对发病时间，并生成连续生存曲线。
*   **贝叶斯不确定性**：提供后验包含概率（PIP），为生物标志物的可靠性提供量化依据。
*   **鲁棒性**：在小样本（数据稀缺）场景下表现优于深度学习方法。

### 8. 不足与局限
*   **计算资源需求**：虽然比某些惩罚回归快，但对于包含数百万基因组标志物的大规模分析，仍需进一步优化内存和并行效率。
*   **混杂因素限制**：目前主要校正了年龄和性别，尚未充分利用 EHR 中更复杂的混杂因素（如药物使用、生活方式）。
*   **分布假设**：Weibull 分布虽然通用，但可能无法完美拟合所有疾病的发病模式（如论文中提到的精神分裂症）。
*   **前瞻性验证**：研究主要基于历史数据，蛋白质水平与疾病的因果关系（是预测因子还是疾病状态的产物）仍需进一步探讨。

（完）
