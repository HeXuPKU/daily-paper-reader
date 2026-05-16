---
title: A novel matrix multiplication framework for modeling genotype-by-environment interaction in genomic prediction
title_zh: 一种用于基因组预测中基因型与环境互作建模的新型矩阵乘法框架
authors: "Montesinos-Lopez, O. A., Montesinos-Lopez, A., Montesinos-Lopez, J. C., Crossa, J., Dreisigacker, S., Hernandez-Suarez, C. M., Ortiz, R."
date: 2026-05-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.11.724414v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 基因组预测中的基因与环境交互建模
tldr: 本研究针对植物育种中基因型与环境（GE）交互作用建模的复杂性，提出了一种基于矩阵乘法的新型协方差框架。不同于传统的哈达玛积方法，该框架通过基因型与环境核矩阵的乘积并分解为对称分量来捕捉交互作用。在11个小麦和水稻数据集上的评估显示，该方法显著提升了预测准确率和顶级品种选择效果，为基因组选择提供了更灵活、可解释且高效的建模工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的哈达玛积模型在捕捉复杂的基因型与环境交互结构方面存在局限，难以充分表征其复杂性。
method: 提出一种利用基因型和环境核矩阵乘法推导协方差结构的新框架，并将其分解为对称分量作为混合模型中的随机效应。
result: "在多个小麦和水稻数据集中，该方法比传统模型提升了高达13.2%的预测准确率，并增强了顶级品种的选择精度。"
conclusion: 该框架为建模GE交互提供了灵活、可解释且计算可行的扩展方案，能显著增强多样环境下的基因组预测效能。
---

## 摘要
准确建模基因型与环境（GE）互作对于植物育种中的基因组预测至关重要，但由于复杂的互作结构，这仍然具有挑战性。传统模型通常使用基因型和环境协方差矩阵的 Hadamard 积来捕捉联合相似性，这可能无法充分表征 GE 的复杂性。在此，我们提出了一种新型框架，该框架通过基因型和环境核函数的矩阵乘法推导协方差结构，并将其分解为对称分量，作为随机效应纳入混合模型中。通过对 11 个小麦和水稻多环境数据集的评估，该方法始终优于传统的基于 Hadamard 积的模型，在 Pearson 相关系数方面将预测准确度提高了高达 13.2%，并增强了顶端选择准确度。结合这两种方法可获得最佳性能，表明两者捕捉到了互补的信息。该框架为 GE 互作建模提供了一种灵活、可解释且计算可行的扩展，有望增强在不同环境条件下基因组选择的有效性。

## Abstract
Accurate modeling of genotype-by-environment (GE) interaction is critical for genomic prediction in plant breeding but remains challenging due to complex interaction structures. Conventional models often use the Hadamard product of genotype and environment covariance matrices to capture joint similarity, which may not fully represent GE complexity. Here we propose a novel framework that derives covariance structures from the matrix multiplication of genotype and environment kernels, decomposing these into symmetric components incorporated as random effects in mixed models. Evaluated for 11 wheat and rice multi-environment datasets and across, this approach consistently outperformed the traditional Hadamard-based model, improving prediction accuracy by up to 13.2% in Pearson's correlation and enhancing top-selection accuracy. Combining both methods yielded the highest performance, indicating complementary information capture. This framework offers a flexible, interpretable, and computationally feasible extension for modeling GE interaction, potentially enhancing genomic selection effectiveness under diverse environmental conditions.

---

## 论文详细总结（自动生成）

这篇论文提出了一种在基因组预测中建模基因型与环境（GE）互作的新型数学框架。以下是对该研究的深度总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：在植物育种中，同一基因型在不同环境下的表现存在差异（即 GE 互作）。准确预测这种互作对于选育广适性或环境特异性品种至关重要。
*   **研究动机**：传统的基因组最佳线性无偏预测（GBLUP）模型通常使用基因型协方差矩阵（G）和环境协方差矩阵（E）的 **Hadamard 积（逐元素相乘，$\odot$）** 来建模互作。然而，Hadamard 积假设互作仅发生在对应的元素之间，这种结构过于简单，可能无法捕捉复杂的、非线性的 GE 互作关系。
*   **整体含义**：本研究旨在引入**矩阵乘法（Matrix Multiplication, MM）**框架，通过更复杂的代数结构来表征 G 和 E 之间的联系，从而提高基因组选择的预测精度。

### 2. 论文提出的方法论
*   **核心思想**：利用矩阵乘法算子替代或补充传统的 Hadamard 积算子，以推导出新的协方差结构。
*   **关键技术细节**：
    *   **构建核矩阵**：首先分别构建基因型核矩阵 $K_G$ 和环境核矩阵 $K_E$。
    *   **矩阵乘法算子**：计算 $K_{GE} = K_G K_E$。由于 $K_{GE}$ 通常不是对称矩阵，无法直接作为混合模型的协方差矩阵。
    *   **对称化处理**：提出将乘积分解为对称分量，最常用的形式是 $M_{sym} = \frac{1}{2}(K_G K_E + K_E K_G)$。
    *   **模型集成**：将 $M_{sym}$ 作为随机效应的协方差矩阵纳入线性混合模型中。
*   **算法流程**：
    1.  输入标记数据和环境协变量。
    2.  计算 $K_G$ 和 $K_E$。
    3.  计算 MM 框架下的对称交互矩阵。
    4.  使用贝叶斯或频率论方法估计随机效应参数。
    5.  对比 MM 模型、传统 Hadamard 模型以及两者的组合模型。

### 3. 实验设计
*   **数据集**：使用了 **11 个多环境数据集**，涵盖了**小麦（Wheat）**和**水稻（Rice）**两种主要作物，涉及产量、株高等多种农艺性状。
*   **Benchmark（基准）**：
    *   **Model 1 (G+E)**：仅包含基因型和环境主效应的模型。
    *   **Model 2 (G+E+G$\odot$E)**：传统的使用 Hadamard 积建模 GE 互作的模型。
*   **对比方法**：
    *   **Model 3 (G+E+MM)**：使用本研究提出的矩阵乘法框架建模 GE 互作。
    *   **Model 4 (G+E+G$\odot$E+MM)**：同时包含 Hadamard 积和矩阵乘法项的组合模型。
*   **评估指标**：Pearson 相关系数（预测准确率）和顶级品种选择准确率（Top 10% 和 20%）。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号、数量或具体的训练时长。
*   **实现工具**：通常此类研究使用 R 语言环境下的统计遗传学包（如 BGLR 或 sommer），计算压力主要集中在大型矩阵的求逆和迭代采样上。

### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了 11 个不同的数据集，每个数据集包含多个环境和成百上千个品系，实验样本量充足。
*   **充分性评价**：
    *   **多场景验证**：通过跨物种（小麦、水稻）和跨性状验证，证明了方法的普适性。
    *   **对比公平**：所有模型在相同的交叉验证框架下运行，确保了对比的客观性。
    *   **深度分析**：不仅关注整体相关性，还分析了育种中实际关心的“顶级品种筛选”准确率，具有很强的实战参考价值。

### 6. 主要结论与发现
*   **性能提升**：MM 框架在大多数数据集中显著优于传统的 Hadamard 积模型，Pearson 相关系数提升最高达 **13.2%**。
*   **互补性**：组合模型（Hadamard + MM）通常表现最好，这表明矩阵乘法捕捉到了 Hadamard 积所忽略的、不同维度的互作信息。
*   **选择优势**：在筛选表现最好的前 10% 或 20% 品种时，MM 框架表现出更高的稳定性和准确性。
*   **结论**：矩阵乘法为 GE 互作建模提供了一个强大且灵活的新工具，能够显著增强复杂环境下的基因组预测效能。

### 7. 优点
*   **数学创新**：打破了 GE 建模中长期依赖 Hadamard 积的局限，引入了更具表达力的矩阵运算。
*   **灵活性高**：该框架易于扩展，可以根据需要调整对称化处理的方式。
*   **实用性强**：在不改变现有混合模型基本架构的前提下，仅通过更换协方差矩阵即可实现性能提升。

### 8. 不足与局限
*   **生物学解释性**：虽然数学上表现优异，但矩阵乘法项（$K_G K_E$）在生物学上的直观含义（例如：它代表了什么样的基因-环境生理级联反应）相比 Hadamard 积（代表相似性的重合）较难解释。
*   **计算开销**：对于超大规模数据集（如数万个品系），矩阵乘法及对称化操作的内存消耗和计算复杂度会高于简单的逐元素积。
*   **参数调优**：引入更多随机效应项可能会增加模型过拟合的风险，需要更精细的正则化或先验分布设置。

（完）
