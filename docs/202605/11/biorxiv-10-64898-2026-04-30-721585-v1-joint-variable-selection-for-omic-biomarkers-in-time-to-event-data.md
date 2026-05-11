---
title: Joint Variable Selection for Omic Biomarkers in Time-to-Event Data
title_zh: 事件发生时间数据中组学标志物的联合变量选择
authors: "Bajzik, J., Depope, A., Zolfimoselo, Y., Sharipov, A., Lesayova, A., Klein, H., Richmond, A., Vernardis, S., Grauslys, A., Andrejev, S., Zelezniak, A., Ralser, M., Marioni, R., Mondelli, M., Robinson, M. R."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721585v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用贝叶斯计算方法将 EHR 诊断时间与多组学数据联系起来
tldr: 针对大规模生物库中多组学数据与疾病发病时间关联分析中存在的虚假发现和相关性忽略问题，本文提出了一种名为vampW的贝叶斯计算方法。该方法基于向量近似消息传递框架和Weibull模型，实现了对相关特征的联合建模。在UK Biobank等数据集上的实验表明，vampW在降低假阳性率、识别关键蛋白质关联以及提高疾病发病时间预测准确性方面显著优于传统CoxPH模型和深度学习方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的单变量Cox比例风险模型在处理高维多组学数据时容易忽略特征间的相关性，从而导致较高的虚假发现率并限制了预测精度。
method: 提出了一种基于向量近似消息传递（VAMP）框架和Weibull分布的参数化贝叶斯联合建模方法vampW，用于变量选择和生存分析。
result: "在UK Biobank数据中识别出219个蛋白质与24种疾病的关联，且在预测疾病发病时间上比DeepSurv等方法降低了超过26%的均方根误差。"
conclusion: vampW为复杂疾病的基因组架构解析提供了一个准确、可解释且具备强大预测能力的变量选择与预测框架，适用于大规模生物库研究。
---

## 摘要
绝大多数神经退行性疾病、癌症和代谢性疾病的发病率通常随年龄呈指数级增长。在大规模生物样本库中，将电子健康记录中的诊断时间信息与多种基因组（“多组学”）测量数据相结合，有可能揭示参与疾病发生和进展的基因及生物通路。迄今为止，关联性测试通常使用半参数 Cox 比例风险 (CoxPH) 模型逐个测试变量，这忽略了相关性结构并增加了假阳性发现的风险。为了解决这些问题，我们引入了一种新型的全参数贝叶斯计算方法 vampW，该方法基于应用于 Weibull 模型的向量近似消息传递 (Vector Approximate Message Passing) 框架。vampW 对相关特征进行联合建模，同时提供可解释的风险结构，生成连续的生存曲线，并整合先验知识。在广泛的模拟研究中，我们证明了使用 vampW 对组学数据和事件发生时间结果进行联合建模，与边际测试和其他形式的联合 CoxPH 模型相比，显著减少了假阳性发现。在来自英国生物样本库 (UK Biobank) 的 53,018 名个体中，vampW 识别出 219 种蛋白质与 24 种疾病结果的关联，其中大多数不在顶级的边际发现之列。我们进一步针对指数年龄效应校正了蛋白质水平，识别出 1,308 项关联，并强调了分析对年龄校正方法的敏感性。我们的发现在使用不同测量技术的独立队列中得到了验证，包括来自冰岛的数据和一个新型的 Generation Scotland 蛋白质组学数据集。vampW 在疾病发病时间的预测方面也取得了显著改进：在 14 种结果中，与 CoxPH 变体和深度学习方法 DeepSurv 相比，它分别将均方根误差降低了 32% 以上和 26% 以上，同时在少数群体中保持了预测效用。总之，vampW 在单一计算框架内提供了准确且可解释的变量选择和样本外预测，使其成为剖析常见复杂疾病发病基因组结构的强大工具。

## Abstract
The incidence of the vast majority of neurodegenerative, cancer, and metabolic diseases generally increases exponentially with age. In large-scale biobanks, linking time-to-diagnosis information in electronic health records to multiple genomic ("multiomics") measures has the potential to reveal the genes and biological pathways involved in the disease onset and progression. To date, association testing has commonly been conducted by testing one variable at a time using semiparametric Cox proportional hazards (CoxPH) models, which ignores correlation structure and increases the risk of false discoveries. To address these issues, we introduce a novel fully parametric Bayesian computational method, vampW, based on the Vector Approximate Message Passing framework applied to a Weibull model. vampW jointly models correlated features, while providing an interpretable hazard structure, producing a continuous survival curve, and incorporating prior knowledge. In an extensive simulation study, we demonstrate that joint modeling of omics data and time-to-event outcomes with vampW, substantially reduces false discoveries in comparison to marginal testing and other forms of joint CoxPH models. In 53,018 individuals from the UK Biobank, vampW identifies 219 protein associations with 24 disease outcomes, most of which are not among the top marginal discoveries. We further correct protein levels for exponential age effects, identifying 1,308 associations and highlighting the sensitivity of the analysis to age-correction methodology. Our findings replicate in independent cohorts using different measurement technologies, within data from Iceland and a novel Generation Scotland proteomics dataset. vampW also achieves significant improvement in the prediction of disease onset times: across 14 outcomes, it reduces the root mean squared error by over 32% and 26%, when compared to CoxPH variants and the deep learning approach DeepSurv, respectively, while maintaining predictive utility in minority populations. In summary, vampW offers accurate and interpretable variable selection and out-of-sample prediction within a single computational framework, making it a powerful tool for dissecting the genomic architecture of common complex disease onset.

---

## 论文详细总结（自动生成）

这是一份关于论文《Joint Variable Selection for Omic Biomarkers in Time-to-Event Data》（事件发生时间数据中组学标志物的联合变量选择）的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何在大规模生物样本库（如 UK Biobank）中，准确地将高维、高度相关的多组学数据（如蛋白质组学）与疾病发病时间（Time-to-Event）联系起来。
*   **研究背景**：
    *   大多数慢性病（癌症、神经退行性疾病）的发病率随年龄呈指数增长。
    *   **传统方法局限**：目前主流采用单变量（Marginal）Cox 比例风险模型。这种方法忽略了组学特征间的相关性，容易产生大量虚假关联（假阳性），且在预测个体发病时间方面表现欠佳。
    *   **需求**：需要一种能够同时处理高维特征、考虑特征间相关性、并能提供准确发病时间预测的联合建模框架。

### 2. 论文提出的方法论：vampW
*   **核心思想**：提出一种名为 **vampW** 的全参数贝叶斯联合建模方法。它将**向量近似消息传递（VAMP）**框架与 **Weibull 分布**（用于模拟随年龄增长的风险）相结合。
*   **关键技术细节**：
    *   **Weibull 模型**：不同于 Cox 模型的半参数性质，vampW 使用 Weibull 分布显式建模基准风险，能够生成连续的生存曲线并直接预测发病时间。
    *   **VAMP 框架**：一种高效的近似推理算法，专门用于高维线性模型的贝叶斯推断，能够处理特征间的高度共线性。
    *   **变量选择**：通过“刺与板”（Spike-and-Slab）先验分布实现自动变量选择，识别出对疾病风险有真正贡献的标志物。
    *   **联合建模**：所有组学特征被同时放入模型中，通过惩罚项或先验分布区分直接效应和由相关性引起的间接效应。

### 3. 实验设计
*   **数据集**：
    *   **UK Biobank (UKB)**：主要分析队列，包含 53,018 名个体的 Olink 蛋白质组学数据。
    *   **Generation Scotland (GS)**：独立验证队列，使用不同的蛋白质测量技术。
    *   **冰岛数据**：用于跨研究结果的外部验证。
*   **Benchmark（基准方法）**：
    *   **单变量 CoxPH**：标准的边际关联测试。
    *   **联合 CoxPH 变体**：如 Lasso 和 Elastic Net 惩罚回归。
    *   **DeepSurv**：基于深度学习的生存分析前沿方法。
*   **实验场景**：
    *   **模拟研究**：在已知真实效应的情况下，测试模型在不同相关性结构和稀疏度下的表现。
    *   **真实疾病关联**：针对 24 种常见疾病（如阿尔茨海默症、糖尿病、各类癌症）进行标志物筛选。
    *   **预测性能评估**：评估模型在样本外预测疾病发病时间的准确度。

### 4. 资源与算力
*   **算力说明**：论文中**未明确列出**具体的 GPU 型号、数量或精确的训练时长。
*   **效率提及**：作者强调了 VAMP 框架的计算效率，指出其能够处理数万样本和数千特征的联合建模，这在传统贝叶斯 MCMC 方法中是难以实现的。

### 5. 实验数量与充分性
*   **实验规模**：
    *   **模拟实验**：涵盖了多种参数组合（样本量、特征相关性、效应大小），验证了方法在控制假阳性方面的优越性。
    *   **真实数据应用**：对 24 种疾病进行了详尽分析，识别出 219 个（未校正年龄效应）和 1308 个（校正后）蛋白质关联。
    *   **验证充分性**：通过 Generation Scotland 和冰岛数据的跨队列验证，证明了发现的生物学关联具有稳健性。
    *   **公平性测试**：专门在少数群体（非欧洲裔）中测试了预测效用，确保了模型的泛化能力。
*   **评价**：实验设计非常全面，从理论模拟到多中心实测，再到跨技术平台的验证，逻辑链条完整且客观。

### 6. 主要结论与发现
*   **降低假阳性**：vampW 显著减少了由特征相关性导致的虚假关联。在 UKB 数据中，许多被单变量测试排在首位的蛋白质在联合模型中被证明并非直接相关。
*   **预测精度大幅提升**：在 14 种疾病的预测中，vampW 的均方根误差（RMSE）比 CoxPH 变体降低了 **32% 以上**，比深度学习方法 DeepSurv 降低了 **26% 以上**。
*   **生物学发现**：识别出 219 个与疾病发病直接相关的蛋白质标志物，并揭示了年龄校正方法对组学关联分析结果的巨大影响。
*   **跨平台稳健性**：尽管测量技术不同，但在 UKB 中发现的蛋白质效应在其他队列中得到了高度复制。

### 7. 优点
*   **联合建模能力**：有效解决了组学数据中普遍存在的共线性问题，提供了比单变量分析更纯净的关联列表。
*   **预测与解释并重**：既能像机器学习模型一样提供高精度预测，又能像统计模型一样提供可解释的变量贡献（效应值）。
*   **全参数优势**：利用 Weibull 分布捕捉年龄相关的风险特征，比半参数模型更适合生物学上的衰老相关疾病研究。

### 8. 不足与局限
*   **分布假设限制**：Weibull 分布假设风险随时间单调变化，虽然适用于大多数老年病，但对于风险波动剧烈或非单调的疾病（如某些传染病或急性发作疾病）可能拟合欠佳。
*   **计算门槛**：尽管比 MCMC 快，但相比于简单的单变量 Cox 扫描，联合建模仍需要更高的计算资源和更复杂的算法实现。
*   **数据依赖**：模型的效果高度依赖于电子健康记录（EHR）中诊断时间的准确性，数据缺失或记录偏差会影响参数估计。

（完）
