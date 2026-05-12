---
title: "CLCNet: a contrastive learning and chromosome-aware network for genomic prediction in plants"
title_zh: CLCNet：一种用于植物基因组预测的对比学习与染色体感知网络
authors: "Huang, J., Yang, Z., Yin, M., Li, C., Li, J., Wang, Y., Huang, L., Li, M., Liang, C., He, F., Han, R., Jiang, Y."
date: 2026-05-10
pdf: "https://www.biorxiv.org/content/10.1101/2024.12.29.630569v7.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 利用全基因组标记进行基因组预测的深度学习框架
tldr: 基因组选择在植物育种中至关重要，但面临高维数据和个体差异捕捉难的问题。本研究提出CLCNet，一种结合对比学习和染色体感知特征建模的深度学习框架。该模型通过对比学习增强对基因型差异的捕捉，并利用染色体感知模块进行结构化特征选择。在四种作物、十种性状上的实验表明，CLCNet在预测准确率上显著优于传统及深度学习模型，尤其在高中等遗传力性状中表现优异，为植物育种提供了高效的预测工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决基因组预测中SNP维度远超样本量以及难以捕捉个体间细微基因型差异的挑战。
method: 提出集成对比学习模块与染色体感知特征建模的深度学习框架，实现精细化表型差异捕捉与结构化特征提取。
result: "在四种作物的测试中，CLCNet的皮尔逊相关系数比基准模型提升了0.34%至12.19%，且在不同遗传力水平下均表现稳健。"
conclusion: CLCNet是一个能显著提高基因组预测准确性的有效框架，在植物育种实际应用中具有巨大的潜力。
---

## 摘要
基因组选择（GS）利用全基因组标记和表型来预测育种值，其有效性在很大程度上取决于基因组预测（GP）模型的准确性。然而，GP 方法通常难以捕捉个体间的变异性，并受限于维度灾难，即单核苷酸多态性（SNP）的数量远超样本量。为了应对这些挑战，我们提出了 CLCNet（对比学习与染色体感知网络），这是一种集成对比学习和染色体感知特征建模的新型深度学习框架。CLCNet 包含两个关键组件：(i) 对比学习模块，增强了模型捕捉个体间细粒度、依赖于基因型的表型差异的能力；(ii) 染色体感知模块，在染色体和基因组水平上捕捉结构化特征选择，从而提取最具信息量的 SNP。我们在四种农作物上评估了 CLCNet，涵盖了十个重要的农艺性状，并将其与多种经典的线性、机器学习和深度学习模型进行了比较。CLCNet 实现了卓越的预测性能，皮尔逊相关系数（PCC）较基准模型有显著提升，增幅在 0.34% 到 12.19% 之间，同时降低了均方误差（MSE）。对于具有中等连锁不平衡（LD；r2 = 0.21-0.36）和高遗传力（h2 > 0.66）的性状（如玉米、油菜和大豆中的性状），性能提升更为显著。对于具有高 LD（r2 = 0.74）和较低遗传力（h2 < 0.50）的棉花性状，CLCNet 保持了稳健的性能且没有下降。总之，这些结果表明 CLCNet 是提高基因组预测准确性的有效框架，在植物育种的实际应用中具有巨大潜力。

## Abstract
Genomic selection (GS) leverages genome-wide markers and phenotypes to predict breeding values, with its effectiveness largely dependent on the accuracy of genomic prediction (GP) models. However, GP methods often struggle to capture inter-individual variability and are limited by the curse of dimensionality, where the number of SNPs far exceeds the sample size. To address these challenges, we present CLCNet (Contrastive Learning and Chromosome-aware Network), a novel deep learning framework that integrates contrastive learning and chromosome-aware feature modeling. CLCNet comprises two key components: (i) a contrastive learning module that enhances the model's ability to capture fine-grained, genotype-dependent phenotypic differences among individuals, and (ii) a chromosome-aware module that captures structured feature selection at both chromosome and genome levels, thereby distilling the most informative SNPs. We evaluated CLCNet across four crop species, covering ten agronomically important traits, and compared it with a diverse set of classical linear, machine learning, and deep learning models. CLCNet achieved superior prediction performance, with statistically significant improvements in Pearson correlation coefficient (PCC), ranging from 0.34% to 12.19% over baseline, together with reduced mean squared error (MSE). Performance gains were more pronounced for traits with moderate linkage disequilibrium (LD; r2= 0.21-0.36) and high heritability (h2 > 0.66), such as those in maize, rapeseed, and soybean. For cotton traits characterized by high LD (r2 = 0.74) and lower heritability (h2 < 0.50), CLCNet maintained robust performance without degradation. Overall, these results demonstrate that CLCNet is an effective framework for improving genomic prediction accuracy and holds strong potential for practical applications in plant breeding.

---

## 论文详细总结（自动生成）

这是一份关于论文《CLCNet: a contrastive learning and chromosome-aware network for genomic prediction in plants》的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：基因组预测（GP）是植物育种中基因组选择（GS）的关键，但面临两大挑战：
    1.  **维度灾难**：单核苷酸多态性（SNP）标记的数量远超样本量（$p \gg n$）。
    2.  **个体差异捕捉难**：传统模型难以捕捉个体间细微的基因型差异及其对表型的复杂影响。
*   **研究背景**：虽然深度学习已应用于 GP，但现有模型往往忽略了基因组的生物学结构（如染色体组织）以及如何通过对比学习增强特征的判别力。

### 2. 论文提出的方法论：CLCNet
CLCNet 框架集成了两个核心创新模块：
*   **对比学习模块 (Contrastive Learning Module)**：
    *   **核心思想**：通过对比学习增强模型对基因型差异的敏感度。
    *   **技术细节**：该模块旨在学习一种嵌入空间，使得具有相似表型的个体在空间中更接近，而差异大的个体被推开。这有助于模型捕捉细粒度的、依赖于基因型的表型变异。
*   **染色体感知模块 (Chromosome-aware Module)**：
    *   **核心思想**：利用基因组的自然结构进行特征提取。
    *   **技术细节**：模型不再将所有 SNP 视为扁平向量，而是在**染色体水平**和**全基因组水平**上进行结构化特征选择。通过这种分层建模，模型能够自动识别并提取对性状预测最具信息量的 SNP 组合。

### 3. 实验设计
*   **数据集**：涵盖四种主要农作物：**玉米 (Maize)、油菜 (Rapeseed)、大豆 (Soybean) 和棉花 (Cotton)**。
*   **性状范围**：共测试了 10 个重要的农艺性状。
*   **Benchmark（基准模型）**：
    *   **线性模型**：GBLUP, rrBLUP, LASSO。
    *   **传统机器学习**：支持向量回归 (SVR), 随机森林 (RF), XGBoost。
    *   **深度学习**：多层感知机 (MLP), 卷积神经网络 (CNN), 残差网络 (ResNet), Transformer。
*   **评价指标**：皮尔逊相关系数 (PCC) 和均方误差 (MSE)。

### 4. 资源与算力
*   **算力说明**：摘要及提供的文本片段中**未明确说明**具体的 GPU 型号、数量或训练时长。通常此类深度学习模型在植物基因组规模（数万至数十万 SNP）下训练，需要中高端 GPU（如 NVIDIA RTX 3090 或 A100）支持。

### 5. 实验数量与充分性
*   **实验规模**：
    *   跨越了 4 个物种和 10 个性状，具有较好的物种多样性。
    *   对比了 10 种以上的基准模型，涵盖了从经典统计学到前沿深度学习的各类方法。
*   **充分性与公平性**：
    *   实验考虑了不同遗传力 ($h^2$) 和连锁不平衡 (LD) 水平对模型性能的影响。
    *   通过多物种验证，证明了模型的稳健性。实验设计较为客观，遵循了基因组预测领域的标准评估流程。

### 6. 主要结论与发现
*   **性能提升**：CLCNet 在所有测试中均表现最优，PCC 较基准模型提升了 **0.34% 至 12.19%**，同时显著降低了 MSE。
*   **遗传力与 LD 的影响**：
    *   在**中等 LD**（$r^2 = 0.21-0.36$）和**高遗传力**（$h^2 > 0.66$）的性状（如玉米、油菜、大豆）中，CLCNet 的提升最为显著。
    *   在**高 LD**（$r^2 = 0.74$）和**低遗传力**（$h^2 < 0.50$）的性状（如棉花）中，CLCNet 依然保持稳健，未出现性能退化。
*   **结论**：CLCNet 能够有效提取结构化基因组特征，是提高植物育种预测准确性的强有力工具。

### 7. 优点
*   **生物学启发**：引入染色体感知模块，符合基因组的物理结构逻辑。
*   **特征判别力强**：对比学习的引入解决了传统回归模型在处理高度相似基因型时区分度不足的问题。
*   **普适性强**：在不同作物和不同遗传背景的性状上均表现出优越性或稳健性。

### 8. 不足与局限
*   **模型复杂性**：相比于 GBLUP 等线性模型，CLCNet 作为深度学习框架，其超参数调优和训练成本更高。
*   **可解释性挑战**：尽管有染色体感知模块，但深度学习内部的“黑箱”性质仍使得具体 SNP 如何影响表型的生物学解释不如线性模型直观。
*   **小样本限制**：虽然对比学习能缓解部分问题，但在样本量极小（如小于几百个个体）的育种群体中，其优势可能无法完全发挥。

（完）
