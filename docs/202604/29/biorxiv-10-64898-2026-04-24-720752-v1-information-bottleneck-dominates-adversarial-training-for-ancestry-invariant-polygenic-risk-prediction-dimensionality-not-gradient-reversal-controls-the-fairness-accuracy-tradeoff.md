---
title: "Information Bottleneck Dominates Adversarial Training for Ancestry-Invariant Polygenic Risk Prediction: Dimensionality, Not Gradient Reversal, Controls the Fairness-Accuracy Tradeoff"
title_zh: 信息瓶颈在祖先不变的多基因风险预测中主导对抗训练：维度而非梯度反转控制着公平性与准确性的权衡
authors: "Tran, P. P., Do, A. T."
date: 2026-04-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720752v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 跨族裔多基因风险评分（PRS）预测
tldr: 本研究挑战了对抗性公平预测中“梯度反转系数是控制敏感属性不变性主导因素”的传统假设。通过在跨族裔多基因风险评分（PRS）预测中使用双流架构，研究发现潜在维度（信息瓶颈）对祖先信息泄露的影响比对抗强度高出8-27倍。实验涵盖基因组和EEG数据，证明了维度控制在实现公平性方面的决定性作用。研究建议在优化公平性-准确性权衡时，应优先考虑容量控制而非复杂的对抗工程。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究在公平预测的对抗性表示学习中，究竟是梯度反转系数还是潜在维度（信息瓶颈）在控制敏感属性的不变性。
method: 采用双流架构进行跨族裔多基因风险评分预测，通过在基因组和EEG领域对比不同潜在维度与对抗强度下的信息泄露情况进行验证。
result: 实验表明潜在维度对祖先信息泄露的影响远超对抗强度，且在极低维度下无需对抗训练即可通过瓶颈效应实现近乎不变性。
conclusion: 潜在维度是控制公平性权衡的核心变量，开发者应优先通过调整潜在维度来设定信息预算，而非过度依赖复杂的对抗性工程。
---

## 摘要
在用于公平预测的对抗表示学习中，梯度反转系数被广泛视为控制敏感属性不变性的主要手段。我们证明这一假设是错误的。通过使用双流架构进行跨祖先多基因风险评分（PRS）预测，我们证明了潜在维度（即信息瓶颈）对祖先信息泄漏方差的影响是对抗强度的 8 到 27 倍。在 20 倍范围内改变 lambda 仅使泄漏改变 2.2 个百分点；而在 16 倍范围内改变维度则使其改变 46.6 个百分点。在维度为 8 且没有对抗训练（lambda = 0）的情况下，祖先泄漏为 32.9%（随机概率为 20%）：仅靠瓶颈就实现了近乎不变性。对抗网络架构（线性 vs 深层 MLP）同样无关紧要（影响范围仅 0.6 个百分点）。我们在两个不相关的领域验证了这一发现——基因组祖先不变性（6 种临床性状，1000 Genomes 数据集，n = 2,504）和 EEG 受试者不变性（预训练 HFTP + Braindecode 双域模型，20 名受试者），并观察到一致的维度主导地位（EEG 中的比例为 12.7:1）。对于基因组应用，流 1 通过 DCT-II 频域特征（136 个系数）对群体结构进行编码；流 2 对来自顶级 PRS SNP 的表型信号进行编码（PCA 降至 128 维）。该架构在使用标准基因组 PCA 作为祖先流时表现同样出色（R2 = 0.217 vs 0.222），证实了其贡献在于架构而非特定的编码方式。非洲裔 PRS 重建的 R2 在所有六种性状上均有提高（例如，冠心病提高了 5.1 个百分点）。线性模型实现了更高的总 R2，但在跨祖先迁移中表现极差（非洲裔冠心病的 R2 = -12.45）。我们强调，我们预测的是 PRS（一种计算出的评分），而非疾病表型；在生物样本库规模的表型数据上的验证正在进行中。这些结果表明，相对于简单的容量控制，对抗公平性研究社区在对抗网络工程上的投入过多。从业者应首先选择潜在维度以设定公平性-准确性权衡的信息预算，然后根据需要选择性地使用对抗训练进行边际优化。

## Abstract
In adversarial representation learning for fair prediction, the gradient reversal coefficient is widely treated as the primary control for sensitive-attribute invariance. We show this assumption is wrong. Using a dual-stream architecture for cross-ancestry polygenic risk score (PRS) prediction, we demonstrate that latent dimensionality -- the information bottleneck -- accounts for 8-27x more variance in ancestry leakage than adversarial strength. Varying lambda across a 20x range changes leakage by only 2.2 percentage points; varying dimensionality across a 16x range changes it by 46.6 pp. At dimension 8 with no adversarial training (lambda = 0), ancestry leakage is 32.9% (chance = 20%): the bottleneck alone achieves near-invariance. The adversary architecture (linear vs deep MLP) is equally irrelevant (0.6 pp range). We validate this finding across two unrelated domains -- genomic ancestry invariance (6 clinical traits, 1000 Genomes, n = 2,504) and EEG subject invariance (pretrained HFTP + Braindecode dual-domain model, 20 subjects) -- observing consistent dimensionality dominance (12.7:1 ratio in EEG). For the genomic application, Stream 1 encodes population structure via DCT-II frequency-domain features (136 coefficients); Stream 2 encodes phenotype signal from top PRS SNPs (PCA to 128 dimensions). The architecture works equally well with standard genomic PCA as the ancestry stream (R2 = 0.217 vs 0.222), confirming the contribution is architectural, not encoding-specific. African-ancestry PRS reconstruction R2 improves on all six traits (e.g., +5.1 pp for coronary artery disease). Linear models achieve higher aggregate R2 but fail catastrophically on cross-ancestry transfer (R2 = -12.45 for African-ancestry CAD). We emphasize that we predict PRS (a computed score), not disease phenotypes; validation on biobank-scale phenotype data is ongoing. These results suggest the adversarial fairness community has been over-investing in adversary engineering relative to simple capacity control. Practitioners should select latent dimensionality first to set the information budget for the fairness-accuracy tradeoff, then optionally use adversarial training for marginal refinement.

---

## 论文详细总结（自动生成）

这是一份关于论文《Information Bottleneck Dominates Adversarial Training for Ancestry-Invariant Polygenic Risk Prediction》的深度结构化总结：

### 1. 论文的核心问题与整体含义
*   **研究动机**：在公平机器学习（Fair ML）中，对抗性表示学习（Adversarial Representation Learning）是实现“敏感属性不变性”的主流方法。传统观点认为，**梯度反转系数（$\lambda$）**是控制公平性与准确性权衡的核心超参数。
*   **核心问题**：本研究挑战了上述假设，提出在跨族裔多基因风险评分（PRS）预测中，**潜在维度（即信息瓶颈的宽度）**才是控制祖先信息泄露的决定性因素，其影响力远超对抗训练的强度。
*   **整体含义**：研究揭示了模型架构中的“容量控制”比复杂的“对抗工程”更有效，为开发更公平、更具泛化性的基因组预测模型提供了新路径。

### 2. 论文提出的方法论
*   **核心思想**：采用**双流架构（Dual-Stream Architecture）**来分离祖先信息和表型信号，并通过控制中间潜在表示 $z$ 的维度来限制信息流。
*   **关键技术细节**：
    *   **流 1（祖先流）**：使用离散余弦变换（DCT-II）提取基因组的频域特征（136个系数）来编码群体结构。
    *   **流 2（表型流）**：将顶级 PRS 相关 SNP 通过 PCA 降维至 128 维，捕捉生物学信号。
    *   **对抗机制**：在潜在表示 $z$ 处接入一个祖先分类器（Adversary），通过梯度反转层（GRL）在训练过程中剔除祖先信息。
    *   **信息瓶颈控制**：系统性地改变 $z$ 的维度（从 8 到 128），观察其对“祖先泄露”和“预测准确度”的影响。

### 3. 实验设计
*   **数据集**：
    1.  **基因组数据**：1000 Genomes Project（n=2,504），涵盖 5 个超级种群（非洲、欧洲、东亚等）。
    2.  **EEG 数据**：用于跨领域验证，包含 20 名受试者的脑电信号。
*   **预测任务**：预测 6 种临床性状的 PRS（冠心病 CAD、2型糖尿病 T2D、乳腺癌、前列腺癌、哮喘、肥胖）。
*   **Benchmark 与对比方法**：
    *   **线性模型（Linear Models）**：作为标准 PRS 的基准。
    *   **消融实验变量**：对抗强度 $\lambda$（0 到 1.0）、潜在维度（8 到 128）、对抗网络架构（线性 vs. 深层 MLP）。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号、数量或总训练时长。但考虑到数据集规模（n=2,504）和模型架构（轻量级 MLP 和双流网络），该实验在单张商用 GPU 或高性能 CPU 集群上即可完成，计算成本相对较低。

### 5. 实验数量与充分性
*   **实验规模**：
    *   涵盖了 6 种不同的临床性状，确保了结果在不同生物学特征下的稳健性。
    *   进行了跨领域的验证（从基因组学到神经科学 EEG），证明了结论的普适性。
    *   **充分性评价**：实验设计非常充分。作者通过多维度的参数扫描（Grid Search）对比了维度与 $\lambda$ 的方差贡献比，这种定量分析有力地支持了其核心论点。

### 6. 论文的主要结论与发现
*   **维度主导论**：潜在维度对祖先信息泄露的影响是 $\lambda$ 的 **8 到 27 倍**。在维度为 8 时，即使不进行对抗训练（$\lambda=0$），模型也能实现近乎完美的祖先不变性。
*   **对抗工程的边际效应**：改变对抗网络的深度（线性 vs. 4层 MLP）对公平性的提升微乎其微（仅 0.6 个百分点）。
*   **跨族裔性能提升**：该架构显著改善了在非洲裔样本上的 PRS 预测准确度（如冠心病 $R^2$ 提升了 5.1%），解决了线性模型在跨族裔迁移时性能崩溃的问题。

### 7. 优点
*   **视角独特**：挑战了对抗学习领域的长期直觉，提出了更简单、更有效的公平性控制手段。
*   **跨领域验证**：结论不仅局限于基因组学，在 EEG 数据上的复现增强了理论的可信度。
*   **实用性强**：为生物信息学研究者提供了一个无需复杂调参即可实现跨族裔公平预测的架构参考。

### 8. 不足与局限
*   **预测目标限制**：目前预测的是**计算出的 PRS 分数**而非原始的疾病表型（Phenotypes），虽然作者提到正在生物样本库（Biobank）规模上进行验证，但本文尚未展示大规模真实表型的结果。
*   **样本量规模**：1000 Genomes 的样本量（约 2.5k）相对于现代大型生物样本库（如 UK Biobank 的 500k）较小，可能存在过拟合特定群体结构的风险。
*   **公平性定义单一**：研究主要关注“不变性”（Invariance），未深入探讨其他公平性指标（如预测平价或机会均等）。

（完）
