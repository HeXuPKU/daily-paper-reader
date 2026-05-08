---
title: Joint Variable Selection for Omic Biomarkers in Time-to-Event Data
title_zh: 事件发生时间数据中组学标志物的联合变量选择
authors: "Bajzik, J., Depope, A., Zolfimoselo, Y., Sharipov, A., Lesayova, A., Klein, H., Richmond, A., Vernardis, S., Grauslys, A., Andrejev, S., Zelezniak, A., Ralser, M., Marioni, R., Mondelli, M., Robinson, M. R."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721585v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 将电子健康档案诊断时间与生物库多组学联系起来
tldr: 该研究针对大规模生物库中多组学数据与疾病发病时间关联分析的挑战，提出了一种名为vampW的贝叶斯计算方法。该方法基于向量近似消息传递框架和Weibull模型，实现了对相关特征的联合建模。相比传统的边际测试和Cox比例风险模型，vampW显著降低了假阳性率，在英国生物库数据中识别出大量蛋白质与疾病的关联，并在预测疾病发病时间方面表现优异，为解析复杂疾病的基因架构提供了有力工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的边际测试方法在处理高维多组学数据时会忽略特征间的相关结构，从而增加假阳性风险并限制预测精度。
method: 开发了基于向量近似消息传递（VAMP）框架和Weibull分布的参数化贝叶斯联合变量选择方法vampW。
result: "vampW在识别蛋白质关联方面更具灵敏度，且在疾病发病时间预测的均方根误差上比CoxPH和DeepSurv分别降低了32%和26%以上。"
conclusion: vampW通过单一计算框架实现了准确、可解释的变量选择和高效的生存预测，是剖析复杂疾病基因架构的强大工具。
---

## 摘要
绝大多数神经退行性疾病、癌症和代谢性疾病的发病率通常随年龄呈指数级增长。在大规模生物样本库中，将电子健康记录中的诊断时间信息与多种基因组（“多组学”）测量数据相结合，有可能揭示参与疾病发生和进展的基因及生物学通路。迄今为止，关联性测试通常使用半参数 Cox 比例风险 (CoxPH) 模型逐个测试变量，这忽略了相关性结构并增加了假阳性发现的风险。为了解决这些问题，我们引入了一种新型的全参数贝叶斯计算方法 vampW，该方法基于应用于 Weibull 模型的向量近似消息传递 (Vector Approximate Message Passing) 框架。vampW 对相关特征进行联合建模，同时提供可解释的风险结构，生成连续的生存曲线，并整合先验知识。在广泛的模拟研究中，我们证明了与边际测试和其他形式的联合 CoxPH 模型相比，使用 vampW 对组学数据和事件发生时间结果进行联合建模显著减少了假阳性发现。在来自英国生物样本库 (UK Biobank) 的 53,018 名个体中，vampW 识别出 219 种蛋白质与 24 种疾病结果的关联，其中大多数不在顶级的边际发现之列。我们进一步针对指数年龄效应校正了蛋白质水平，识别出 1,308 项关联，并突显了分析对年龄校正方法的敏感性。我们的发现在使用不同测量技术的独立队列中得到了验证，包括来自冰岛的数据和一个新型的 Generation Scotland 蛋白质组学数据集。vampW 在疾病发病时间预测方面也取得了显著改进：在 14 种结果中，与 CoxPH 变体和深度学习方法 DeepSurv 相比，它分别将均方根误差降低了 32% 以上和 26% 以上，同时在少数族裔群体中保持了预测效用。总之，vampW 在单一计算框架内提供了准确且可解释的变量选择和样本外预测，使其成为剖析常见复杂疾病发病基因组结构的强大工具。

## Abstract
The incidence of the vast majority of neurodegenerative, cancer, and metabolic diseases generally increases exponentially with age. In large-scale biobanks, linking time-to-diagnosis information in electronic health records to multiple genomic ("multiomics") measures has the potential to reveal the genes and biological pathways involved in the disease onset and progression. To date, association testing has commonly been conducted by testing one variable at a time using semiparametric Cox proportional hazards (CoxPH) models, which ignores correlation structure and increases the risk of false discoveries. To address these issues, we introduce a novel fully parametric Bayesian computational method, vampW, based on the Vector Approximate Message Passing framework applied to a Weibull model. vampW jointly models correlated features, while providing an interpretable hazard structure, producing a continuous survival curve, and incorporating prior knowledge. In an extensive simulation study, we demonstrate that joint modeling of omics data and time-to-event outcomes with vampW, substantially reduces false discoveries in comparison to marginal testing and other forms of joint CoxPH models. In 53,018 individuals from the UK Biobank, vampW identifies 219 protein associations with 24 disease outcomes, most of which are not among the top marginal discoveries. We further correct protein levels for exponential age effects, identifying 1,308 associations and highlighting the sensitivity of the analysis to age-correction methodology. Our findings replicate in independent cohorts using different measurement technologies, within data from Iceland and a novel Generation Scotland proteomics dataset. vampW also achieves significant improvement in the prediction of disease onset times: across 14 outcomes, it reduces the root mean squared error by over 32% and 26%, when compared to CoxPH variants and the deep learning approach DeepSurv, respectively, while maintaining predictive utility in minority populations. In summary, vampW offers accurate and interpretable variable selection and out-of-sample prediction within a single computational framework, making it a powerful tool for dissecting the genomic architecture of common complex disease onset.

---

## 论文详细总结（自动生成）

这是一份关于论文《Joint Variable Selection for Omic Biomarkers in Time-to-Event Data》的结构化深度总结：

### 1. 核心问题与整体含义（研究动机和背景）
该研究聚焦于大规模生物样本库中**多组学数据与疾病发病时间（Time-to-Event）的关联分析**。
*   **研究动机**：大多数慢性病的发病风险随年龄呈指数级增长。传统的关联分析（如 Cox 比例风险模型）通常采用“边际测试”（一次只测一个变量），这忽略了生物标志物之间复杂的相互关联，导致极高的假阳性率。
*   **核心挑战**：如何在处理高维、高度相关的组学数据时，既能准确识别真正的生物标志物（变量选择），又能精确预测个体的绝对发病时间，同时处理生存分析中常见的“右删失”（即研究结束时部分人尚未发病）问题。

### 2. 方法论：vampW 算法
论文提出了一种名为 **vampW** 的全参数贝叶斯计算框架。
*   **核心思想**：将**向量近似消息传递（VAMP）**框架应用于 **Weibull 生存模型**。
*   **关键技术细节**：
    *   **Weibull 模型**：采用全参数 Weibull 分布建模发病时间，相比半参数的 Cox 模型，它能利用绝对时间信息，生成连续生存曲线并预测具体发病年龄。
    *   **Spike-and-Slab 先验**：对标志物效应量 $\beta$ 使用自适应的“峰谷先验”，通过期望最大化（EM）算法自动估计信号的稀疏性和效应分布。
    *   **右删失处理**：引入了专门处理右删失数据的 MAP（最大后验概率）估计器，将其整合进 VAMP 的迭代过程中。
    *   **双重去噪与 LMMSE**：算法通过两个去噪步骤（考虑先验）和两个线性最小均方误差（LMMSE）步骤（考虑特征相关性）交替迭代，并加入 Onsager 校正项以确保估计的渐近正态性。
    *   **阻尼自适应（Damping Autotuning）**：为应对真实组学数据违反旋转不变性假设导致的收敛问题，引入了自动调节的阻尼机制。

### 3. 实验设计
*   **数据集**：
    *   **UK Biobank (UKB)**：53,018 名个体的 2,924 种蛋白质测量数据，涵盖 24 种疾病（如阿尔茨海默症、糖尿病、癌症等）。
    *   **独立验证集**：冰岛 SomaScan 蛋白质组学队列（约 36,000 人）和 Generation Scotland (GS) 质谱蛋白质组学数据集。
*   **Benchmark（对比方法）**：
    *   **边际 CoxPH**：传统的单变量测试。
    *   **联合 CoxPH**：全变量不加惩罚的联合建模。
    *   **LASSO-CoxPH**：带稳定性选择（Stability Selection）的惩罚回归。
    *   **DeepSurv**：基于深度学习的生存分析前沿方法。
*   **评估指标**：变量选择的假阳性率（FDR）与真阳性率（TPR）；预测性能的 C-index（一致性指数）与 RMSE（均方根误差）。

### 4. 资源与算力
*   **算力消耗**：
    *   使用 **AMD EPYC 9654 处理器**。
    *   **vampW**：单个性状分析平均耗时 **12.7 CPU 小时**，内存需求约 **64 GB RAM**。
    *   **对比**：LASSO-CoxPH 平均耗时 60.8 CPU 小时（需 160 GB RAM）。
*   **成本评估**：在 DNAnexus 云平台上，vampW 单个性状分析成本约为 7.3 英镑，具有较好的计算经济性。

### 5. 实验数量与充分性
*   **模拟实验**：设计了 **24 种模拟场景**（涵盖不同信号强度、删失率、分布误设等），每种场景重复 **50 次**。这充分验证了算法在各种极端情况下的鲁棒性。
*   **真实数据实验**：对 **24 种真实疾病** 进行了全面分析，并进行了**跨族裔（非洲裔、南亚裔）的迁移性测试**。
*   **充分性评价**：实验设计非常严谨，不仅有模拟验证，还有跨技术平台（Olink vs 质谱）、跨地域队列的独立外部验证，客观性极高。

### 6. 主要结论与发现
*   **变量选择更精准**：在模拟中，边际测试的假阳性率超过 80%，而 vampW 能保持极低的 FDR 且 TPR 显著高于 LASSO-CoxPH。
*   **预测精度大幅提升**：在 14 种主要疾病中，vampW 的预测误差（RMSE）比 CoxPH 变体降低了 **32%**，比深度学习方法 DeepSurv 降低了 **26%**。
*   **生物学新发现**：识别出 1,308 个（经年龄校正后）蛋白与疾病的关联。例如，识别出 *CXCL17* 与抑郁症的相关性，以及 *COL9A1* 与 2 型糖尿病的潜在关联。
*   **年龄校正的重要性**：研究发现许多蛋白关联（如 *CGA*）实际上是由蛋白水平随年龄指数变化引起的，强调了非线性年龄校正在组学研究中的必要性。

### 7. 优点
*   **联合建模能力**：有效处理了组学特征间的高度相关性，显著减少了统计学上的“虚假关联”。
*   **全参数优势**：相比 Cox 模型只能给出相对风险排名，vampW 能给出具体的发病时间预测，更具临床参考价值。
*   **贝叶斯框架**：能够自动学习数据先验，无需像 LASSO 那样进行繁琐的交叉验证来调节超参数。
*   **跨人群通用性**：证明了在欧洲人群训练的模型在少数族裔中仍具有良好的预测效用。

### 8. 不足与局限
*   **分布假设限制**：Weibull 分布虽然通用，但不能完美拟合所有疾病（如哮喘和炎症性肠病的发病分布偏离较大），这可能影响某些特定疾病的效力。
*   **混杂因素处理**：目前主要校正了年龄和性别，尚未深入整合药物使用、生活方式等更复杂的动态混杂因素。
*   **计算扩展性**：虽然比 LASSO 快，但面对未来数百万量级的基因组标志物时，仍需进一步优化内存管理和并行化效率。
*   **前瞻性验证**：研究主要基于历史回顾性电子病历数据，蛋白水平与疾病的因果关系（是预测因子还是疾病结果）仍需进一步探讨。

（完）
