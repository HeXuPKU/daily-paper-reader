---
title: "Multi-Stage Graph Attention Networks for Interpretable Alzheimer's Disease Classification from Genome-Wide Association Data"
title_zh: 基于全基因组关联数据的可解释性阿尔茨海默病分类多阶段图注意力网络
authors: "Saxena, A., Gaiteri, C., Faraone, S. V."
date: 2026-04-09
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.06.716790v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 利用图注意力网络对GWAS数据进行阿尔茨海默病分类
tldr: 本研究针对多基因风险评分（PRS）在捕捉基因间上位性相互作用及生物学解释力方面的局限，提出了一种多阶段图注意力网络（GAT）框架。该方法利用GWAS数据构建基因图谱，结合双线性上下文模块、非编码SNP的PRS注入及对抗性去偏技术。实验表明，该模型在阿尔茨海默病分类中优于传统PRS，并能通过可解释性分析揭示关键的生物学信号，为复杂遗传结构的解析提供了新工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-06-716790-v1/fig-001.webp\", \"caption\": \"Figure 1b: Multi-stage GNN architecture with adversarial ancestry debiasing\", \"page\": 47, \"index\": 1, \"width\": 1079, \"height\": 473}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-06-716790-v1/fig-002.webp\", \"caption\": \"Figure 4: Correlation Between GNN and PRS Logits Across Training Stages\\\"\", \"page\": 50, \"index\": 2, \"width\": 1094, \"height\": 333}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-06-716790-v1/fig-003.webp\", \"caption\": \"Table 1a: Stage 1 and Stage 2 AUROC for AD Classification Across GNN Model Configuration\", \"page\": 40, \"index\": 3, \"width\": 1351, \"height\": 387}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-06-716790-v1/fig-004.webp\", \"caption\": \"Figure 3: Ablation Study: Impact of Node and Edge Removal on AD Classification Performance\", \"page\": 49, \"index\": 4, \"width\": 956, \"height\": 958}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-06-716790-v1/fig-005.webp\", \"caption\": \"Table 4b: Connectivity Characteristics of Top, Bottom, and Random Node Subsets\", \"page\": 44, \"index\": 5, \"width\": 1351, \"height\": 667}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-06-716790-v1/fig-006.webp\", \"caption\": \"Figure 2: Explainability Analysis: Importance Distribution and Cross-Sample Stability\", \"page\": 48, \"index\": 6, \"width\": 1027, \"height\": 310}]"
motivation: 旨在克服传统多基因风险评分无法捕捉基因间复杂相互作用且缺乏生物学解释性的问题，提升阿尔茨海默病的分类精度。
method: 开发了一个三阶段图注意力网络，整合基因风险评分、通路图结构、双线性上下文模块及对抗性训练，并与全基因组PRS进行集成。
result: 集成模型在阿尔茨海默病分类中达到了0.82的AUROC，显著优于单一的PRS模型（0.80），并识别出具有生物学意义的基因网络。
conclusion: 多阶段GAT框架能有效捕捉互补的非加性遗传信号，在提高疾病分类准确性的同时增强了遗传研究的可解释性。
---

## 摘要
背景：全基因组关联研究（GWAS）已鉴定出许多与神经精神疾病相关的变异。尽管某些显著位点（如在阿尔茨海默病中）具有重大风险，但其余的遗传变异分布在许多小效应位点上。多基因风险评分（PRS）汇总了这些风险，但未能捕捉上位性相互作用，且生物学可解释性和预测准确性有限。计算基因层面的风险评分并整合已知或经统计验证的基因-基因关联，具有提高可解释性和/或准确性的潜力。图神经网络（GNN）可以利用模拟潜在上位性相互作用的图结构遗传数据来实现这些目标。方法：我们开发了一个三阶段图注意力网络（GAT）分类器，使用了来自七个阿尔茨海默病中心队列的 7,358 名参与者的个体级 GWAS 数据。节点被定义为基因，以来自 AD 和 11 种遗传相关表型的风险评分作为特征。我们评估了两种图构建策略：源自海马转录组数据的基因共表达网络和基于人工策展通路的图。此外，还引入了一个双线性上下文模块，以捕捉图拓扑结构之外的全局基因-基因相互作用。在第一阶段，在图上训练 GNN 编码器；第二阶段在编码器后注入非编码 SNP 的 PRS，通过迁移学习更好地捕捉遗传风险；第三阶段应用带有梯度反转的对抗性训练进行祖先去偏。GNN 预测结果与全基因组 PRS 通过弹性网络回归进行集成。结果：表现最好的 GNN 模型——在通路图上运行的带有双线性上下文的 GAT——实现了 0.78 的 AUROC（95% CI: 0.75-0.80）。将第二阶段或第三阶段的 GNN 对数几率（logits）与全基因组 PRS 相结合的集成模型实现了 0.82 的 AUROC（0.79-0.84），优于单独的 PRS（0.80）。GxI 归因和额外的可解释性分析揭示了阶段特异性的生物信号，其中一些重现了已知的基因-表型关联，另一些则可能反映了潜在的新研究领域。结论：多阶段 GAT 框架捕捉了互补的非加性遗传信号，当与 PRS 集成时，提高了 AD 分类的准确性。事后可解释性分析产生了具有生物学解释性的基因网络，支持了基于图的深度学习在剖析复杂遗传结构中的效用。

## Abstract
Background: Genome-wide association studies have identified numerous variants associated with neuropsychiatric disorders. Although some significant loci can carry substantial risk, as in Alzheimer's Disease, the remaining genetic variance is distributed across many small-effect loci. Polygenic risk scores (PRS) aggregate this risk but do not capture epistatic interactions, and offer limited biological interpretability and predictive accuracy. Computing gene level risk scores and integrating known or statistically validated gene-gene associations has the potential to increase interpretability and/or accuracy. Graph Neural Networks (GNNs) can leverage graph structured genetic data that models potential epistatic interactions to achieve these goals. Methods: We developed a three-stage Graph Attention Network (GAT) classifier using individual-level GWAS data from 7,358 participants across seven Alzheimer's Disease Center cohorts. Nodes were defined as genes, with risk scores from AD and 11 genetically correlated phenotypes serving as features. We evaluated two graph construction strategies: gene co-expression networks derived from hippocampal transcriptomic data and curated pathway-based graphs. Additionally, a bilinear context module was incorporated to capture global gene-gene interactions beyond the graph topology. In Stage 1, a GNN encoder was trained on the graphs; Stage 2 injected PRS for non-coding SNPs after the encoder to better capture genetic risk via transfer learning, and Stage 3 applied adversarial training with gradient reversal for ancestry debiasing. GNN predictions were ensembled with whole-genome PRS using elastic net regression. Results: The best-performing GNN model - a GAT with bilinear context operating on the pathway graph - achieved an AUROC of 0.78 (95% CI: 0.75-0.80). Ensemble models combining Stage 2 or 3 GNN logits with whole-genome PRS achieved an AUROC of 0.82 (0.79-0.84), outperforming PRS alone (0.80). GxI attribution and additional explainability analyses revealed stage-specific biological signals, some of which re-capitulated known gene-phenotype associations and others which may reflect potential new areas of inquiry. Conclusion: A multi-stage GAT framework captures complementary, non-additive genetic signal that, when ensembled with PRS, improves the accuracy of AD classification. Post-hoc explainability analyses yield biologically interpretable gene networks, supporting the utility of graph-based deep learning for dissecting complex genetic architectures.

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为多阶段图注意力网络（GAT）的框架，旨在通过全基因组关联研究（GWAS）数据对阿尔茨海默病（AD）进行更精准且具可解释性的分类。以下是对该论文的深度总结：

### 1. 核心问题与整体含义
*   **研究动机**：尽管 GWAS 识别了大量与 AD 相关的遗传变异，但传统的**多基因风险评分（PRS）**存在两大缺陷：一是它是线性加和模型，无法捕捉基因间的**上位性（Epistasis，即非线性相互作用）**；二是缺乏生物学解释性，无法揭示致病的分子网络。
*   **核心目标**：利用图神经网络（GNN）处理非欧几里得数据的能力，整合已知的生物通路信息，捕捉基因间的复杂相互作用，从而提升 AD 的分类准确率并提供生物学洞察。

### 2. 方法论
*   **核心思想**：将遗传风险建模为图结构，节点为基因，边为基因间的生物学关联，通过多阶段训练整合不同类型的遗传信号并消除群体偏见。
*   **关键技术细节**：
    *   **特征工程**：节点特征不仅包含 AD 的基因级风险评分，还整合了 11 种遗传相关表型（如脑容量、流体智力、精神分裂症等）的评分。
    *   **图构建**：对比了基于海马体转录组的“共表达网络”和基于 KEGG/Reactome 的“策展通路图”。利用 Ricci 曲率进行图剪枝和重连，以优化信息流动并防止过度平滑。
    *   **双线性上下文模块 (BLC)**：在 GAT 层后引入 BLC，通过计算全局图表示与局部节点表示的交互，捕捉超越图拓扑结构的全局基因关联。
    *   **三阶段架构**：
        1.  **Stage 1**：训练基础 GNN 编码器。
        2.  **Stage 2**：通过迁移学习注入非编码区（间质）的 PRS 信号，捕捉调控元件的遗传风险。
        3.  **Stage 3**：引入对抗性训练和**梯度反转层 (GRL)**，强制模型学习与祖先成分（Ancestry PCs）无关的特征，实现祖先去偏。
    *   **集成模型**：最终使用弹性网络（Elastic Net）回归将 GNN 的预测概率与全基因组 PRS 进行集成。

### 3. 实验设计
*   **数据集**：使用了来自 7 个阿尔茨海默病中心（ADC）队列的 7,358 名参与者的个体级 GWAS 数据。
*   **Benchmark（基准）**：
    *   传统的全基因组 PRS 模型（基于逻辑回归）。
    *   **Deep Sets 模型**：作为消融对照，该模型忽略图结构，仅处理节点特征。
*   **对比实验**：对比了不同密度的图结构、有无 BLC 模块、以及不同阶段的性能差异。

### 4. 资源与算力
*   **算力说明**：文中提到使用了 PyTorch 和 PyTorch Geometric 库，并在容器化环境中使用 **DistributedDataParallel (DDP)** 进行多 GPU 并行训练。
*   **优化技术**：应用了自动混合精度（AMP）和梯度检查点（Gradient Checkpointing）以降低显存占用。
*   **缺失信息**：论文**未明确说明**具体的 GPU 型号（如 A100 或 V100）、使用的 GPU 数量以及训练所需的总时长。

### 5. 实验数量与充分性
*   **实验规模**：测试了 10 种不同的 GNN 配置（Table 1a），并进行了详尽的消融实验。
*   **消融实验**：包括节点消融、边消融（移除 Top 10% 重要节点/边 vs 随机移除）、特征通道消融等，验证了模型对图结构和特定表型特征的依赖性。
*   **充分性评价**：实验设计较为客观，通过 Optuna 进行了系统的超参数搜索，并使用自助法（Bootstrapping）计算置信区间，确保了统计学上的严谨性。

### 6. 主要结论与发现
*   **性能优越性**：最佳 GNN 模型（通路图 + BLC）AUROC 为 0.78。当与 PRS 集成后，AUROC 提升至 **0.82**，显著优于纯 PRS 模型（0.80）。
*   **图结构价值**：通路图的表现优于共表达图，说明先验的生物学知识对模型至关重要。
*   **生物学解释**：
    *   识别出 *APOE*, *TOMM40*, *APOA2* 等关键基因。
    *   发现 AD 遗传风险在深层抑制性神经元和 VIP 神经元中显著富集。
    *   提取的子图揭示了淀粉样蛋白形成、铁硫簇转移和金属稳态等致病通路。

### 7. 优点
*   **多阶段融合**：成功将基因区风险、非编码区风险和祖先去偏整合在一个框架内。
*   **全局与局部结合**：BLC 模块有效弥补了 GNN 难以捕捉长程基因交互的短板。
*   **深度可解释性**：不仅提升了预测率，还通过事后归因分析（GxI）提供了可验证的生物学假设。

### 8. 不足与局限
*   **样本量瓶颈**：对于深度学习而言，7,000 余例样本规模仍然偏小，可能存在过拟合风险。
*   **输入简化**：输入特征是预先计算的基因级加性评分，这可能在进入模型前就丢失了部分原始 SNP 间的非线性信息。
*   **计算成本**：相比于秒级计算的 PRS，该模型的训练和超参调优需要巨大的算力支持。
*   **缺乏外部独立验证**：虽然使用了内部测试集，但未在如 UK Biobank 等完全独立的外部大规模数据集上验证泛化性。

（完）
