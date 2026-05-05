---
title: Joint Variable Selection for Omic Biomarkers in Time-to-Event Data
title_zh: 事件发生时间数据中组学标志物的联合变量选择
authors: "Bajzik, J., Depope, A., Zolfimoselo, Y., Sharipov, A., Lesayova, A., Klein, H., Richmond, A., Vernardis, S., Grauslys, A., Andrejev, S., Zelezniak, A., Ralser, M., Marioni, R., Mondelli, M., Robinson, M. R."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721585v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 利用贝叶斯计算方法将电子健康记录诊断时间与多组学联系起来
tldr: 本研究针对大规模生物库中多组学数据与疾病发病时间关联分析中的高假阳性率和相关性忽略问题，提出了一种名为vampW的新型贝叶斯计算方法。该方法基于Weibull模型和向量近似消息传递框架，实现了对相关特征的联合建模。通过对英国生物库5万余人的蛋白质组学数据分析，vampW不仅显著降低了假阳性，还发现了数百个与疾病相关的蛋白质，并在预测疾病发病时间上优于传统的CoxPH和深度学习模型，为复杂疾病的基因组架构解析提供了强有力的工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的单变量Cox比例风险模型在处理多组学数据时容易忽略特征间的相关性，导致较高的假阳性率且无法提供连续生存曲线。
method: 提出了一种基于Weibull模型和向量近似消息传递（VAMP）框架的参数化贝叶斯联合变量选择方法vampW。
result: "在英国生物库数据中识别出大量疾病相关蛋白，且在预测准确度上比CoxPH和DeepSurv分别提升了32%和26%以上。"
conclusion: vampW集成了准确的变量选择和出色的样本外预测能力，是研究复杂疾病发病机制和生物标志物的有效工具。
---

## 摘要
绝大多数神经退行性疾病、癌症和代谢性疾病的发病率通常随年龄呈指数级增长。在大规模生物样本库中，将电子健康记录中的诊断时间信息与多种基因组（“多组学”）测量数据相结合，有可能揭示参与疾病发生和进展的基因及生物通路。迄今为止，关联性测试通常使用半参数 Cox 比例风险（CoxPH）模型逐个测试变量，这忽略了相关性结构并增加了假阳性发现的风险。为了解决这些问题，我们引入了一种新型的全参数贝叶斯计算方法 vampW，该方法基于应用于 Weibull 模型的向量近似消息传递（Vector Approximate Message Passing）框架。vampW 对相关特征进行联合建模，同时提供可解释的风险结构，生成连续的生存曲线，并整合先验知识。在广泛的模拟研究中，我们证明了与边际测试和其他形式的联合 CoxPH 模型相比，使用 vampW 对组学数据和事件发生时间结果进行联合建模显著减少了假阳性发现。在来自英国生物样本库（UK Biobank）的 53,018 名个体中，vampW 识别出 219 种蛋白质与 24 种疾病结局的关联，其中大多数不在顶级的边际发现之列。我们进一步针对指数年龄效应校正了蛋白质水平，识别出 1,308 项关联，并突显了分析对年龄校正方法的敏感性。我们的发现在使用不同测量技术的独立队列中得到了验证，包括来自冰岛的数据和一个新型的 Generation Scotland 蛋白质组学数据集。vampW 在疾病发病时间的预测方面也取得了显著改进：在 14 种结局中，与 CoxPH 变体和深度学习方法 DeepSurv 相比，它分别将均方根误差降低了 32% 和 26% 以上，同时在少数族裔群体中保持了预测效用。总之，vampW 在单一计算框架内提供了准确且可解释的变量选择和样本外预测，使其成为剖析常见复杂疾病发病基因结构的强大工具。

## Abstract
The incidence of the vast majority of neurodegenerative, cancer, and metabolic diseases generally increases exponentially with age. In large-scale biobanks, linking time-to-diagnosis information in electronic health records to multiple genomic (``multiomics'') measures has the potential to reveal the genes and biological pathways involved in the disease onset and progression. To date, association testing has commonly been conducted by testing one variable at a time using semiparametric Cox proportional hazards (CoxPH) models, which ignores correlation structure and increases the risk of false discoveries. To address these issues, we introduce a novel fully parametric Bayesian computational method, vampW, based on the Vector Approximate Message Passing framework applied to a Weibull model. vampW jointly models correlated features, while providing an interpretable hazard structure, producing a continuous survival curve, and incorporating prior knowledge. In an extensive simulation study, we demonstrate that joint modeling of omics data and time-to-event outcomes with vampW, substantially reduces false discoveries in comparison to marginal testing and other forms of joint CoxPH models. In 53,018 individuals from the UK Biobank, vampW identifies 219 protein associations with 24 disease outcomes, most of which are not among the top marginal discoveries. We further correct protein levels for exponential age effects, identifying 1,308 associations and highlighting the sensitivity of the analysis to age-correction methodology. Our findings replicate in independent cohorts using different measurement technologies, within data from Iceland and a novel Generation Scotland proteomics dataset. vampW also achieves significant improvement in the prediction of disease onset times: across 14 outcomes, it reduces the root mean squared error by over 32% and 26%, when compared to CoxPH variants and the deep learning approach DeepSurv, respectively, while maintaining predictive utility in minority populations. In summary, vampW offers accurate and interpretable variable selection and out-of-sample prediction within a single computational framework, making it a powerful tool for dissecting the genomic architecture of common complex disease onset.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **vampW** 的新型贝叶斯计算框架，旨在解决大规模生物样本库中多组学数据与疾病发病时间（Time-to-Event）关联分析中的挑战。以下是对该论文的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **研究背景**：随着年龄增长，许多复杂疾病（如癌症、神经退行性疾病）的发病率呈指数级上升。通过电子健康记录（EHR）结合多组学数据，可以识别疾病预测标志物。
*   **核心问题**：目前主流的分析方法是半参数 **Cox 比例风险模型（CoxPH）**。但该模型存在三大缺陷：
    1.  **边际测试局限性**：通常一次只测试一个变量，忽略了组学特征间的复杂相关性，导致极高的假阳性率。
    2.  **统计效率低**：CoxPH 仅依赖事件排序而非绝对时间，无法直接预测具体的发病年龄。
    3.  **缺乏连续性**：无法提供完整的参数化生存曲线。
*   **研究意义**：开发一种能够同时进行高维变量选择和精确发病时间预测的联合建模工具。

### 2. 方法论：核心思想与关键技术
*   **核心思想**：将**向量近似消息传递（VAMP）**框架应用于全参数 **Weibull 生存模型**，实现对数千个特征的联合贝叶斯推断。
*   **关键技术细节**：
    *   **Weibull 模型**：采用全参数 Weibull 分布建模发病时间，其对数空间符合 Gumbel 分布，允许模型捕捉随时间变化的风险率。
    *   **右删失处理（Right-Censoring）**：论文创新性地在 VAMP 框架中引入了处理右删失数据的机制，通过修改似然项来处理未观察到发病事件的个体。
    *   **先验分布**：使用**自适应“尖峰与平板”（Spike-and-Slab）先验**，通过混合高斯分布来模拟不同强度的效应，并实现特征稀疏性。
    *   **算法流程**：利用期望最大化（EM）算法自适应估计先验参数和 Weibull 超参数。通过去噪步（Denoising）和线性最小均方误差（LMMSE）步交替迭代，并引入阻尼（Damping）技术确保在非旋转不变数据上的收敛性。

### 3. 实验设计
*   **数据集**：
    *   **主要数据**：英国生物样本库（UK Biobank）蛋白质组学数据（PPP），包含 53,018 名个体和 2,924 种蛋白质。
    *   **验证数据**：冰岛 SomaScan v4 队列（3.6 万人）和苏格兰 Generation Scotland 质谱蛋白质组学数据集。
*   **场景与结局**：分析了 24 种疾病结局（如阿尔茨海默症、高血压、各类癌症等）。
*   **Benchmark 方法**：
    *   边际 CoxPH 测试（Marginal CoxPH）。
    *   联合 CoxPH 模型（Joint CoxPH）。
    *   带稳定性选择的 LASSO 惩罚 CoxPH（CoxPH LASSO）。
    *   深度学习生存分析方法 **DeepSurv**。

### 4. 资源与算力
*   **算力需求**：在 AMD EPYC 9654 处理器上，单个性状分析平均需要 **12.7 CPU 小时**。
*   **内存消耗**：每个性状分析约需 **64 GB RAM**。
*   **成本参考**：在云端（DNAnexus）运行单个性状的成本约为 7.3 英镑。

### 5. 实验数量与充分性
*   **模拟实验**：设计了 **24 种模拟场景**（涵盖不同信号强度、删失比例、分布误设定等），每种场景重复 50 次，共计 1200 组模拟实验。
*   **真实数据实验**：对 24 种真实疾病进行了全面分析，并进行了**年龄校正消融实验**（线性 vs 指数校正）。
*   **充分性评价**：实验设计非常充分且严谨。不仅对比了传统统计模型，还对比了最先进的深度学习模型，并通过两个独立队列（使用不同检测技术）进行了外部验证，确保了结果的客观性和公平性。

### 6. 主要结论与发现
*   **变量选择更准**：在模拟中，vampW 的假发现率（FDR）控制良好，且真阳性率（TPR）显著高于 CoxPH 变体。
*   **预测精度更高**：在 14 种高流行率疾病中，vampW 的预测均方根误差（RMSE）比 CoxPH 变体降低了 **32%**，比 DeepSurv 降低了 **26%**。
*   **生物学发现**：识别出 219 个（未校正年龄）和 1308 个（指数校正年龄）蛋白-疾病关联。发现了如 *CXCL17* 与抑郁症关联等新生物标志物，并证实了 *APOE*、*PSA* 等已知标志物。
*   **跨人群迁移性**：生成的蛋白质风险评分在不同遗传背景（如非洲裔、南亚裔）人群中表现出良好的迁移性和预测效用。

### 7. 优点
*   **联合建模能力**：能够同时处理数千个相关特征，有效区分直接效应和相关性导致的虚假关联。
*   **全参数化优势**：相比半参数模型，能提供绝对发病时间的预测，且生存曲线更具解释性。
*   **鲁棒性**：在数据稀缺场景下（如小样本生存基准测试），表现优于复杂的深度学习模型。
*   **不确定性量化**：作为贝叶斯方法，能提供后验包含概率（PIP）和置信区间。

### 8. 不足与局限
*   **混杂因素挑战**：虽然考虑了年龄和性别，但蛋白质水平受药物使用等其他复杂混杂因素影响，需更广泛的协变量调整。
*   **计算开销**：尽管比某些并行化 LASSO 方法更高效，但处理数百万个基因组标记时仍面临内存和计算时间的挑战。
*   **模型假设**：Weibull 分布虽然通用，但对于某些发病风险不随年龄指数增长的疾病（如哮喘），拟合度可能略逊。
*   **数据依赖**：目前主要依赖单次采样数据，无法捕捉蛋白质随时间变化的动态信息。

（完）
