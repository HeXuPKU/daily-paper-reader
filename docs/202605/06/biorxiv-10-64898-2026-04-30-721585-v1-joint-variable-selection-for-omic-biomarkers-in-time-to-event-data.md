---
title: Joint Variable Selection for Omic Biomarkers in Time-to-Event Data
title_zh: 事件发生时间数据中组学标志物的联合变量选择
authors: "Bajzik, J., Depope, A., Zolfimoselo, Y., Sharipov, A., Lesayova, A., Klein, H., Richmond, A., Vernardis, S., Grauslys, A., Andrejev, S., Zelezniak, A., Ralser, M., Marioni, R., Mondelli, M., Robinson, M. R."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721585v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用贝叶斯计算方法将EHR诊断时间与多组学联系起来
tldr: 本研究针对大规模生物库中多组学数据与疾病发病时间关联分析的挑战，提出了一种名为 vampW 的新型全参数贝叶斯计算方法。该方法基于向量近似消息传递框架和 Weibull 模型，能够同时对相关特征进行建模并结合先验知识。相比传统的单变量 CoxPH 模型，vampW 显著降低了假阳性率，在 UK Biobank 数据中识别出大量新的蛋白质-疾病关联，并在疾病发病时间预测精度上大幅超越现有方法，为解析复杂疾病的基因架构提供了高效工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的单变量 CoxPH 模型在处理高维多组学数据时，因忽略变量间相关性而导致高假阳性率且预测能力有限。
method: 提出基于向量近似消息传递（VAMP）框架和 Weibull 模型的全参数贝叶斯方法 vampW，实现联合变量选择。
result: "vampW 在 UK Biobank 中识别出 219 个蛋白质关联，且在 14 种疾病预测中将均方根误差较 DeepSurv 降低了 26% 以上。"
conclusion: vampW 整合了准确的变量选择与出色的样本外预测功能，是研究常见复杂疾病发病机制的强有力框架。
---

## 摘要
绝大多数神经退行性疾病、癌症和代谢疾病的发病率通常随年龄呈指数级增长。在大型生物样本库中，将电子健康记录中的诊断时间信息与多种基因组（“多组学”）测量数据联系起来，具有揭示参与疾病发生和进展的基因及生物学通路的潜力。迄今为止，关联性测试通常使用半参数 Cox 比例风险（CoxPH）模型逐个测试变量，这忽略了相关性结构并增加了假阳性发现的风险。为了解决这些问题，我们引入了一种新型的全参数贝叶斯计算方法 vampW，该方法基于应用于 Weibull 模型的向量近似消息传递（Vector Approximate Message Passing）框架。vampW 对相关特征进行联合建模，同时提供可解释的风险结构，生成连续的生存曲线，并整合先验知识。在广泛的模拟研究中，我们证明了使用 vampW 对组学数据和事件发生时间结果进行联合建模，与边际测试和其他形式的联合 CoxPH 模型相比，显著减少了假阳性发现。在来自英国生物样本库（UK Biobank）的 53,018 名个体中，vampW 识别出 219 种蛋白质与 24 种疾病结果的关联，其中大多数不在顶级的边际发现之列。我们进一步针对指数年龄效应校正了蛋白质水平，识别出 1,308 项关联，并突显了分析对年龄校正方法的敏感性。我们的发现在使用不同测量技术的独立队列中得到了验证，包括来自冰岛的数据和一个新的 Generation Scotland 蛋白质组学数据集。vampW 在预测疾病发病时间方面也取得了显著改进：在 14 种结果中，与 CoxPH 变体和深度学习方法 DeepSurv 相比，其均方根误差分别降低了 32% 以上和 26% 以上，同时在少数族裔群体中保持了预测效用。总之，vampW 在单一计算框架内提供了准确且可解释的变量选择和样本外预测，使其成为剖析常见复杂疾病发病基因组结构的强大工具。

## Abstract
The incidence of the vast majority of neurodegenerative, cancer, and metabolic diseases generally increases exponentially with age. In large-scale biobanks, linking time-to-diagnosis information in electronic health records to multiple genomic (``multiomics'') measures has the potential to reveal the genes and biological pathways involved in the disease onset and progression. To date, association testing has commonly been conducted by testing one variable at a time using semiparametric Cox proportional hazards (CoxPH) models, which ignores correlation structure and increases the risk of false discoveries. To address these issues, we introduce a novel fully parametric Bayesian computational method, vampW, based on the Vector Approximate Message Passing framework applied to a Weibull model. vampW jointly models correlated features, while providing an interpretable hazard structure, producing a continuous survival curve, and incorporating prior knowledge. In an extensive simulation study, we demonstrate that joint modeling of omics data and time-to-event outcomes with vampW, substantially reduces false discoveries in comparison to marginal testing and other forms of joint CoxPH models. In 53,018 individuals from the UK Biobank, vampW identifies 219 protein associations with 24 disease outcomes, most of which are not among the top marginal discoveries. We further correct protein levels for exponential age effects, identifying 1,308 associations and highlighting the sensitivity of the analysis to age-correction methodology. Our findings replicate in independent cohorts using different measurement technologies, within data from Iceland and a novel Generation Scotland proteomics dataset. vampW also achieves significant improvement in the prediction of disease onset times: across 14 outcomes, it reduces the root mean squared error by over 32% and 26%, when compared to CoxPH variants and the deep learning approach DeepSurv, respectively, while maintaining predictive utility in minority populations. In summary, vampW offers accurate and interpretable variable selection and out-of-sample prediction within a single computational framework, making it a powerful tool for dissecting the genomic architecture of common complex disease onset.

---

## 论文详细总结（自动生成）

这是一份关于论文《Joint Variable Selection for Omic Biomarkers in Time-to-Event Data》的深度结构化总结：

### 1. 核心问题与整体含义
*   **研究动机**：随着年龄增长，许多慢性病的发病风险呈指数级上升。在大规模生物样本库中，将多组学数据（如蛋白质组学）与电子健康记录（EHR）中的诊断时间（Time-to-Event）联系起来，对于揭示疾病机制和预测发病年龄至关重要。
*   **核心挑战**：目前主流的半参数 Cox 比例风险模型（CoxPH）存在三大缺陷：
    1.  **边际测试缺陷**：逐一测试变量会忽略变量间的相关性，导致极高的假阳性率。
    2.  **统计效率低**：CoxPH 仅依赖事件排序而非绝对时间，无法直接预测具体的发病年龄。
    3.  **高维处理难**：在处理数千个组学特征时，缺乏高效的联合建模和变量选择框架。
*   **整体含义**：论文提出了一种名为 **vampW** 的新框架，旨在通过全参数贝叶斯方法，在单一计算流程中同时实现准确的变量选择和高精度的发病时间预测。

### 2. 方法论
*   **核心思想**：将 **Weibull 生存模型** 与 **向量近似消息传递（VAMP）** 框架相结合。
*   **关键技术细节**：
    *   **Weibull 模型**：采用全参数 Weibull 分布建模发病时间，其对数空间符合 Gumbel 分布，允许直接估计均值和方差。
    *   **变量选择先验**：使用自适应的 **Spike-and-Slab 先验**（混合高斯分布），通过后验包含概率（PIP）识别关键生物标志物。
    *   **右删失处理**：引入了专门处理右删失（Right-censoring）数据的非线性 LMMSE 估计器，这是对传统 AMP 算法的重要改进。
    *   **参数估计**：利用期望最大化（EM）过程自适应地学习先验参数和 Weibull 形状参数。
    *   **稳定性增强**：引入阻尼（Damping）自动调节机制，以应对真实组学数据中设计矩阵不满足旋转不变性假设导致的收敛问题。

### 3. 实验设计
*   **数据集**：
    *   **主数据集**：英国生物样本库（UK Biobank）PPP 项目，包含 53,018 名个体和 2,924 种蛋白质。
    *   **验证数据集**：冰岛 SomaScan 队列（36,000人）和 Generation Scotland 质谱蛋白质组学数据集。
*   **Benchmark 与对比方法**：
    *   **边际 CoxPH**：传统的单变量测试。
    *   **联合 CoxPH**：所有变量同时进入模型。
    *   **LASSO-CoxPH**：带交叉验证和稳定性选择（Stability Selection）的惩罚项模型。
    *   **DeepSurv**：基于深度学习的生存分析前沿方法。
*   **评估指标**：假阳性率（FDR）、真阳性率（TPR）、一致性指数（C-index）以及均方根误差（RMSE）。

### 4. 资源与算力
*   **硬件环境**：AMD EPYC 9654 处理器。
*   **算力消耗**：
    *   **内存**：每个性状分析约需 64 GB RAM。
    *   **时长**：单个预测性状平均耗时 **12.7 CPU 小时**。
    *   **成本**：在 DNAnexus 云平台上，单个分析成本约为 7.3 英镑。
*   **对比**：虽然比边际 CoxPH 慢，但与需要多次迭代的 LASSO-CoxPH（约 60.8 CPU 小时）相比，计算效率更高。

### 5. 实验数量与充分性
*   **实验规模**：
    *   **模拟实验**：设计了 **24 种场景**（涵盖不同信号强度、删失率、分布偏离等），每种场景重复 50 次，共计 1200 组模拟实验。
    *   **真实数据**：对 **24 种常见疾病**（如阿尔茨海默症、2型糖尿病、各类癌症等）进行了全面分析。
    *   **消融/敏感性分析**：对比了线性年龄校正与指数年龄校正对结果的影响。
*   **充分性评价**：实验设计非常充分，不仅在模拟数据中验证了统计性质，还在跨技术平台（Olink vs 质谱）、跨地域（英国 vs 冰岛 vs 苏格兰）和跨族裔（欧洲、非洲、南亚裔）的场景下验证了模型的鲁棒性和迁移性。

### 6. 主要结论与发现
*   **变量选择更准**：在模拟中，vampW 的 TPR 显著高于 CoxPH 变体，且 FDR 控制良好。在 UKB 数据中识别出 219 个（未校正年龄）和 1308 个（校正指数年龄）蛋白关联。
*   **预测精度更高**：在 14 种疾病的绝对发病时间预测中，vampW 的 **RMSE 比 DeepSurv 降低了 26%**，比 CoxPH 变体降低了 32% 以上。
*   **生物学新发现**：识别出如 *CXCL17* 与抑郁症的新关联，并验证了 *APOE*（阿尔茨海默症）、*KLK3*（前列腺癌）等已知标志物。
*   **年龄校正的重要性**：发现许多蛋白（如 *CGA*）与疾病的关联实际上是由蛋白水平随年龄指数变化引起的，强调了非线性年龄校正的必要性。

### 7. 优点
*   **全能性**：在同一个贝叶斯框架内解决了变量选择、参数估计和绝对时间预测三个问题。
*   **统计严谨性**：相比深度学习方法，提供了可解释的 PIP（后验包含概率）和不确定性量化。
*   **处理删失能力**：创新性地在消息传递算法中整合了右删失似然函数。
*   **跨族裔迁移性**：证明了其生成的蛋白质风险评分在少数族裔中依然具有较好的预测效用。

### 8. 不足与局限
*   **分布假设限制**：模型依赖 Weibull 分布假设，对于不符合该分布的疾病（如发病年龄分布极不均匀的精神分裂症）效果受限。
*   **混杂因素处理**：目前主要校正了年龄和性别，尚未充分整合药物使用、生活方式等动态混杂因素。
*   **因果推断缺失**：识别的是关联而非因果，无法确定蛋白变化是疾病的原因还是结果（尽管通过前瞻性分析缓解了此问题）。
*   **计算开销**：虽然优于 LASSO，但面对数百万个基因组标志物时，内存和计算需求仍需进一步优化。

（完）
