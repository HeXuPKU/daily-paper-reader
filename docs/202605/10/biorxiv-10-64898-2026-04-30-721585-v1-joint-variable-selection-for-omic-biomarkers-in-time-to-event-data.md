---
title: Joint Variable Selection for Omic Biomarkers in Time-to-Event Data
title_zh: 事件发生时间数据中组学标志物的联合变量选择
authors: "Bajzik, J., Depope, A., Zolfimoselo, Y., Sharipov, A., Lesayova, A., Klein, H., Richmond, A., Vernardis, S., Grauslys, A., Andrejev, S., Zelezniak, A., Ralser, M., Marioni, R., Mondelli, M., Robinson, M. R."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721585v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 利用贝叶斯计算方法将电子健康记录与多组学关联进行关联测试
tldr: 本研究针对大规模生物库中多组学数据与疾病发病时间关联分析的挑战，提出了一种名为vampW的新型贝叶斯计算框架。该方法结合了Weibull模型与向量近似消息传递技术，能够同时处理高度相关的组学特征并提供可解释的风险结构。相比传统的Cox比例风险模型，vampW显著降低了假阳性率，在UK Biobank等大型数据集上识别出更多关键生物标志物，并大幅提升了疾病发病时间的预测精度，为复杂疾病的基因架构研究提供了高效工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的Cox比例风险模型在处理多组学数据时常采用单变量测试，容易忽略特征间的相关性并导致较高的假阳性率。
method: 提出vampW方法，这是一种基于向量近似消息传递（VAMP）框架和Weibull模型的全参数贝叶斯计算方法，支持联合变量选择。
result: "在UK Biobank数据中识别出数百个蛋白质关联，且在预测疾病发病时间上的均方根误差比CoxPH和DeepSurv分别降低了32%和26%。"
conclusion: vampW在变量选择的准确性和预测性能上均优于现有方法，是解析复杂疾病基因架构和生物标志物发现的强大工具。
---

## 摘要
绝大多数神经退行性疾病、癌症和代谢性疾病的发病率通常随年龄呈指数级增长。在大规模生物样本库中，将电子健康记录中的诊断时间信息与多种基因组（“多组学”）测量数据相结合，有可能揭示参与疾病发生和进展的基因及生物学通路。迄今为止，关联性测试通常使用半参数 Cox 比例风险 (CoxPH) 模型逐个测试变量，这忽略了相关性结构并增加了假阳性发现的风险。为了解决这些问题，我们引入了一种新型的全参数贝叶斯计算方法 vampW，该方法基于应用于 Weibull 模型的向量近似消息传递 (Vector Approximate Message Passing) 框架。vampW 对相关特征进行联合建模，同时提供可解释的风险结构，生成连续的生存曲线，并整合先验知识。在广泛的模拟研究中，我们证明了与边际测试和其他形式的联合 CoxPH 模型相比，使用 vampW 对组学数据和事件发生时间结果进行联合建模显著减少了假阳性发现。在来自英国生物样本库 (UK Biobank) 的 53,018 名个体中，vampW 识别出 219 种蛋白质与 24 种疾病结果的关联，其中大多数不在顶级的边际发现之列。我们进一步针对指数年龄效应校正了蛋白质水平，识别出 1,308 项关联，并强调了分析对年龄校正方法的敏感性。我们的发现在使用不同测量技术的独立队列中得到了验证，包括来自冰岛的数据和一个新的 Generation Scotland 蛋白质组学数据集。vampW 在疾病发病时间的预测方面也取得了显著改进：在 14 种结果中，与 CoxPH 变体和深度学习方法 DeepSurv 相比，它分别将均方根误差降低了 32% 和 26% 以上，同时在少数群体中保持了预测效用。总之，vampW 在单一计算框架内提供了准确且可解释的变量选择和样本外预测，使其成为剖析常见复杂疾病发病基因组结构的强大工具。

## Abstract
The incidence of the vast majority of neurodegenerative, cancer, and metabolic diseases generally increases exponentially with age. In large-scale biobanks, linking time-to-diagnosis information in electronic health records to multiple genomic ("multiomics") measures has the potential to reveal the genes and biological pathways involved in the disease onset and progression. To date, association testing has commonly been conducted by testing one variable at a time using semiparametric Cox proportional hazards (CoxPH) models, which ignores correlation structure and increases the risk of false discoveries. To address these issues, we introduce a novel fully parametric Bayesian computational method, vampW, based on the Vector Approximate Message Passing framework applied to a Weibull model. vampW jointly models correlated features, while providing an interpretable hazard structure, producing a continuous survival curve, and incorporating prior knowledge. In an extensive simulation study, we demonstrate that joint modeling of omics data and time-to-event outcomes with vampW, substantially reduces false discoveries in comparison to marginal testing and other forms of joint CoxPH models. In 53,018 individuals from the UK Biobank, vampW identifies 219 protein associations with 24 disease outcomes, most of which are not among the top marginal discoveries. We further correct protein levels for exponential age effects, identifying 1,308 associations and highlighting the sensitivity of the analysis to age-correction methodology. Our findings replicate in independent cohorts using different measurement technologies, within data from Iceland and a novel Generation Scotland proteomics dataset. vampW also achieves significant improvement in the prediction of disease onset times: across 14 outcomes, it reduces the root mean squared error by over 32% and 26%, when compared to CoxPH variants and the deep learning approach DeepSurv, respectively, while maintaining predictive utility in minority populations. In summary, vampW offers accurate and interpretable variable selection and out-of-sample prediction within a single computational framework, making it a powerful tool for dissecting the genomic architecture of common complex disease onset.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **vampW** 的新型贝叶斯计算框架，旨在解决大规模生物库中多组学数据与疾病发病时间（Time-to-Event）关联分析中的变量选择与预测难题。

### 1. 核心问题与整体含义
*   **研究动机**：大多数慢性病（如癌症、神经退行性疾病）的发病风险随年龄呈指数级增长。现有的生存分析主流方法（如 Cox 比例风险模型）存在两个主要缺陷：
    1.  **关联测试局限性**：通常采用单变量（边际）测试，忽略了组学特征间复杂的相关性，导致极高的假阳性率。
    2.  **预测能力不足**：作为半参数模型，CoxPH 仅能预测相对风险评分，难以直接给出绝对的发病时间预测。
*   **核心目标**：开发一种能够同时进行高维变量联合选择、处理相关性结构、并准确预测绝对发病时间的计算框架。

### 2. 方法论
*   **核心思想**：将**全参数 Weibull 生存模型**与**向量近似消息传递（VAMP）**框架相结合。
*   **关键技术细节**：
    *   **Weibull 模型**：采用全参数 Weibull 分布建模发病时间，利用其位置-尺度特性处理对数时间域的线性关系。
    *   **Spike-and-Slab 先验**：对效应量 $\beta$ 使用自适应的“尖峰-平板”先验，实现稀疏变量选择。
    *   **VAMP 框架**：利用近似消息传递算法处理高维设计矩阵，通过 Onsager 校正确保估计值的渐近正态性。
    *   **右删失处理**：创新性地将生存函数整合进 VAMP 的去噪步骤中，以处理未观察到发病事件的删失数据。
    *   **参数估计**：通过期望最大化（EM）算法自适应地学习先验分布参数和 Weibull 形状参数。

### 3. 实验设计
*   **数据集**：
    *   **主数据集**：英国生物样本库（UK Biobank）蛋白质组学数据（53,018 人，2,924 种蛋白）。
    *   **验证数据集**：冰岛队列（SomaScan 技术）、Generation Scotland 队列（质谱技术）。
*   **Benchmark 与对比方法**：
    *   **边际测试**：Marginal CoxPH（逐个蛋白测试）。
    *   **联合模型**：标准 Joint CoxPH、LASSO-penalized CoxPH（带稳定性选择）。
    *   **深度学习**：DeepSurv（基于神经网络的生存分析）。
*   **场景**：24 种模拟场景（改变信号强度、删失率、分布误设等）以及 24 种真实人类疾病。

### 4. 资源与算力
*   **硬件环境**：使用 AMD EPYC 9654 处理器。
*   **算力消耗**：
    *   **内存**：单个性状分析约需 **64 GB RAM**。
    *   **时长**：平均每个性状耗时 **12.7 CPU 小时**。
    *   **成本**：在 DNAnexus 云平台上约合 7.3 英镑/性状。
*   **对比**：计算效率高于带稳定性选择的 LASSO-CoxPH（约 60.8 CPU 小时）。

### 5. 实验数量与充分性
*   **模拟实验**：进行了 24 种不同参数配置的模拟，每种配置重复 50 次，充分验证了模型在不同删失率和分布偏离情况下的鲁棒性。
*   **真实数据实验**：涵盖了 24 种主要疾病（癌症、心血管、神经系统疾病等），并进行了跨技术平台（Olink vs. 质谱）和跨队列（英国 vs. 冰岛 vs. 苏格兰）的验证。
*   **公平性与消融**：专门测试了不同遗传背景（非洲裔、南亚裔）的迁移性，并对比了线性与指数年龄校正对结果的影响。实验设计客观且覆盖面广。

### 6. 主要结论与发现
*   **变量选择更精准**：vampW 显著降低了边际测试带来的假阳性。在 UKB 中识别出 219 个蛋白关联，且这些发现具有高度的生物学可解释性。
*   **预测精度大幅提升**：在预测绝对发病时间方面，vampW 的均方根误差（RMSE）比 CoxPH 降低了 **32%**，比 DeepSurv 降低了 **26%**。
*   **年龄校正的重要性**：研究发现许多蛋白关联（如 CGA 蛋白）实际上是由年龄的指数效应驱动的，通过非线性年龄校正可以揭示更真实的生物标志物（如抑郁症相关的 CXCL17）。
*   **跨人群迁移性**：在少数族裔群体中，vampW 生成的风险评分依然保持了良好的预测效用。

### 7. 优点
*   **全能型框架**：在同一个贝叶斯框架内完成了变量选择、效应估计和绝对时间预测。
*   **处理相关性**：相比边际测试，联合建模能更有效地识别出真正的驱动基因，而非相关的“乘客”特征。
*   **小样本优势**：在数据稀缺场景下，表现优于复杂的深度学习模型。
*   **参数可解释性**：Weibull 形状参数提供了关于疾病风险随时间变化的直观生物学理解。

### 8. 不足与局限
*   **分布依赖**：模型假设数据服从 Weibull 分布，对于分布极度不规则的疾病（如文中提到的精神分裂症）效果不佳。
*   **混杂因素限制**：虽然校正了年龄和性别，但尚未全面整合生活方式、药物史等动态混杂因素。
*   **计算扩展性**：虽然在数千个特征上表现良好，但若扩展到数百万个基因组变异，仍面临内存和计算效率的挑战。

（完）
