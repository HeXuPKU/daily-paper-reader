---
title: Joint Variable Selection for Omic Biomarkers in Time-to-Event Data
title_zh: 事件发生时间数据中组学标志物的联合变量选择
authors: "Bajzik, J., Depope, A., Zolfimoselo, Y., Sharipov, A., Lesayova, A., Klein, H., Richmond, A., Vernardis, S., Grauslys, A., Andrejev, S., Zelezniak, A., Ralser, M., Marioni, R., Mondelli, M., Robinson, M. R."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721585v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 将电子健康记录诊断时间与多组学及贝叶斯计算方法联系起来
tldr: 该研究针对大规模生物库中多组学数据与疾病发病时间关联分析的挑战，提出了一种名为vampW的贝叶斯计算方法。该方法基于向量近似消息传递框架和Weibull模型，实现了对相关特征的联合建模。相比传统的边际测试和Cox比例风险模型，vampW显著降低了假阳性率，在英国生物库数据中识别出大量蛋白质与疾病的关联，并在预测疾病发病时间方面表现优异，为解析复杂疾病的基因架构提供了强有力的工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的边际测试在处理高维多组学数据时会忽略变量间的相关结构，导致假阳性率高且预测性能受限。
method: 提出了一种名为vampW的参数化贝叶斯方法，利用向量近似消息传递（VAMP）框架结合Weibull生存模型进行联合变量选择。
result: "在UK Biobank数据中识别出大量疾病相关的蛋白质标志物，且在预测发病时间上比CoxPH和DeepSurv分别提升了32%和26%的准确度。"
conclusion: vampW在单一计算框架内实现了准确的变量选择和高效的生存预测，是剖析复杂疾病基因架构的强大工具。
---

## 摘要
绝大多数神经退行性疾病、癌症和代谢性疾病的发病率通常随年龄呈指数级增长。在大规模生物样本库中，将电子健康记录中的诊断时间信息与多种基因组（“多组学”）测量数据相结合，有可能揭示参与疾病发生和进展的基因及生物通路。迄今为止，关联性测试通常使用半参数 Cox 比例风险 (CoxPH) 模型逐个测试变量，这忽略了相关性结构并增加了假阳性发现的风险。为了解决这些问题，我们引入了一种新型的全参数贝叶斯计算方法 vampW，该方法基于应用于 Weibull 模型的向量近似消息传递 (Vector Approximate Message Passing) 框架。vampW 对相关特征进行联合建模，同时提供可解释的风险结构，生成连续的生存曲线，并整合先验知识。在广泛的模拟研究中，我们证明了使用 vampW 对组学数据和事件发生时间结果进行联合建模，与边际测试和其他形式的联合 CoxPH 模型相比，显著减少了假阳性发现。在来自英国生物样本库 (UK Biobank) 的 53,018 名个体中，vampW 识别出 219 种蛋白质与 24 种疾病结果的关联，其中大多数不在边际发现的前列。我们进一步针对指数年龄效应校正了蛋白质水平，识别出 1,308 项关联，并强调了分析对年龄校正方法的敏感性。我们的发现在使用不同测量技术的独立队列中得到了验证，包括来自冰岛的数据和一个新型的 Generation Scotland 蛋白质组学数据集。vampW 在疾病发病时间预测方面也取得了显著改进：在 14 种结果中，与 CoxPH 变体和深度学习方法 DeepSurv 相比，其均方根误差分别降低了 32% 以上和 26% 以上，同时在少数族裔群体中保持了预测效用。总之，vampW 在单一计算框架内提供了准确且可解释的变量选择和样本外预测，使其成为剖析常见复杂疾病发病基因组结构的强大工具。

## Abstract
The incidence of the vast majority of neurodegenerative, cancer, and metabolic diseases generally increases exponentially with age. In large-scale biobanks, linking time-to-diagnosis information in electronic health records to multiple genomic ("multiomics") measures has the potential to reveal the genes and biological pathways involved in the disease onset and progression. To date, association testing has commonly been conducted by testing one variable at a time using semiparametric Cox proportional hazards (CoxPH) models, which ignores correlation structure and increases the risk of false discoveries. To address these issues, we introduce a novel fully parametric Bayesian computational method, vampW, based on the Vector Approximate Message Passing framework applied to a Weibull model. vampW jointly models correlated features, while providing an interpretable hazard structure, producing a continuous survival curve, and incorporating prior knowledge. In an extensive simulation study, we demonstrate that joint modeling of omics data and time-to-event outcomes with vampW, substantially reduces false discoveries in comparison to marginal testing and other forms of joint CoxPH models. In 53,018 individuals from the UK Biobank, vampW identifies 219 protein associations with 24 disease outcomes, most of which are not among the top marginal discoveries. We further correct protein levels for exponential age effects, identifying 1,308 associations and highlighting the sensitivity of the analysis to age-correction methodology. Our findings replicate in independent cohorts using different measurement technologies, within data from Iceland and a novel Generation Scotland proteomics dataset. vampW also achieves significant improvement in the prediction of disease onset times: across 14 outcomes, it reduces the root mean squared error by over 32% and 26%, when compared to CoxPH variants and the deep learning approach DeepSurv, respectively, while maintaining predictive utility in minority populations. In summary, vampW offers accurate and interpretable variable selection and out-of-sample prediction within a single computational framework, making it a powerful tool for dissecting the genomic architecture of common complex disease onset.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **vampW** 的新型贝叶斯计算框架，旨在解决大规模生物样本库中多组学数据与疾病发病时间（事件发生时间）关联分析的挑战。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：大多数慢性疾病的发病风险随年龄呈指数级增长。现有的生存分析方法（如半参数 Cox 比例风险模型）在处理高维多组学数据时存在两个主要缺陷：
    1.  **忽略相关性**：通常采用“一次一个”的边际测试，忽略了生物标志物之间普遍存在的相关结构，导致极高的假阳性率。
    2.  **预测局限性**：Cox 模型仅提供相对风险评分，无法直接预测绝对的发病年龄或具体的事件发生时间。
*   **研究背景**：随着英国生物样本库（UK Biobank）等大规模多组学数据的出现，迫切需要一种能够同时进行**联合变量选择**和**精确时间预测**的计算工具。

### 2. 方法论：核心思想与关键技术
*   **核心思想**：vampW 结合了**全参数 Weibull 生存模型**和**向量近似消息传递（VAMP）**框架，在贝叶斯推断下实现高维特征的联合建模。
*   **关键技术细节**：
    *   **Weibull 模型**：采用全参数 Weibull 分布建模发病时间，通过对数变换将其转化为 Gumbel 分布，从而利用位置-尺度特性。
    *   **VAMP 框架**：利用向量近似消息传递算法处理高维设计矩阵，通过“Onsager 校正”确保估计值的渐近正态性，从而实现稳定的变量选择。
    *   **Spike-and-Slab 先验**：使用自适应的混合高斯分布作为先验，通过期望最大化（EM）过程自动学习信号的稀疏性和效应大小。
    *   **右删失处理**：引入了专门处理右删失（Right-censoring）数据的非线性去噪器和 LMMSE 估计步骤，这是对传统 AMP 算法的重要扩展。
    *   **阻尼自适应（Damping Autotuning）**：为了应对真实数据违反旋转不变性假设的问题，引入了自动调整的阻尼因子以确保算法收敛。

### 3. 实验设计
*   **数据集**：
    *   **主要数据**：英国生物样本库（UK Biobank）蛋白质组学数据（PPP），包含 53,018 名个体和 2,924 种蛋白质。
    *   **验证数据**：冰岛 SomaScan 队列（36,000 人）和 Generation Scotland 质谱蛋白质组学数据。
    *   **基准生存数据集**：METABRIC, GBSG, SUPPORT, SAC3（用于小样本场景测试）。
*   **对比方法（Benchmarks）**：
    *   边际 CoxPH（Marginal CoxPH）
    *   联合 CoxPH（Joint CoxPH）
    *   带稳定性选择的 LASSO-CoxPH
    *   深度学习方法 DeepSurv 及其他 13 种生存分析模型（在小样本基准测试中）。
*   **评估指标**：假发现率（FDR）、真阳性率（TPR）、一致性指数（C-index）和均方根误差（RMSE）。

### 4. 资源与算力
*   **硬件环境**：使用 AMD EPYC 9654 处理器。
*   **算力消耗**：
    *   **内存**：每个性状分析约需 **64 GB RAM**。
    *   **耗时**：单个性状分析平均需要 **12.7 CPU 小时**。
    *   **成本**：在 DNAnexus 云平台上，单个性状的计算成本约为 **7.3 英镑**。
*   **对比**：其计算成本与带交叉验证的 LASSO-CoxPH 相当（后者约 10.5 英镑/性状）。

### 5. 实验数量与充分性
*   **模拟实验**：设计了 **24 种场景**，涵盖不同的信噪比（方差解释度 40%/80%）、删失率（90%/95%）、分布误设（Weibull vs ExpGamma）和先验分布（正态 vs 拉普拉斯）。每种场景重复 50 次。
*   **真实数据实验**：分析了 **24 种常见疾病**（如阿尔茨海默症、2型糖尿病、癌症等）。
*   **充分性评价**：实验设计非常充分。不仅通过模拟验证了统计性质（FDR 控制），还通过独立队列和不同测量技术（Olink vs SomaScan vs 质谱）验证了生物学发现的可靠性。此外，还进行了跨族裔（非洲裔、南亚裔）的迁移性分析和数据稀缺场景下的消融/对比实验。

### 6. 主要结论与发现
*   **变量选择更精准**：在模拟中，vampW 的假阳性率远低于边际测试，且真阳性率优于 LASSO-CoxPH。
*   **预测精度大幅提升**：在 14 种真实疾病预测中，vampW 的 RMSE 比 CoxPH 变体降低了 **32%**，比深度学习方法 DeepSurv 降低了 **26%**。
*   **生物学新发现**：识别出 1,308 个（经年龄校正）和 219 个（未经年龄校正）蛋白-疾病关联。证实了 APOE、GDF15 等已知标志物，并发现了如 CXCL17 与抑郁症关联等潜在新靶点。
*   **年龄校正的重要性**：研究发现，是否进行非线性（指数）年龄校正会显著改变识别出的蛋白质集合，强调了在衰老相关研究中校正方法的重要性。

### 7. 优点
*   **联合建模能力**：能够同时处理数千个相关的生物标志物，有效区分直接效应和相关性导致的间接效应。
*   **全参数优势**：相比半参数模型，能提供更具解释力的生存曲线和绝对时间预测。
*   **鲁棒性**：在模型误设（非 Weibull 分布）和数据稀缺（样本量仅 100）的情况下，依然表现出极强的竞争力。
*   **跨平台验证**：研究结果在不同技术平台（抗体法 vs 质谱法）间具有良好的可重复性。

### 8. 不足与局限
*   **计算开销**：虽然比某些深度学习方法快，但 64GB 的内存需求和十余小时的 CPU 时间在处理数百万个基因组标记时仍面临扩展性挑战。
*   **分布假设**：尽管具有鲁棒性，但其核心基于 Weibull 分布假设，对于某些发病风险不随时间单调变化的疾病（如精神分裂症）可能不适用。
*   **混杂因素**：目前的分析主要校正了年龄和性别，尚未充分整合药物使用、生活方式等更复杂的临床混杂因素。
*   **静态测量**：依赖于单次时间点的蛋白质测量，无法捕捉蛋白质水平随时间动态变化对疾病风险的影响。

（完）
