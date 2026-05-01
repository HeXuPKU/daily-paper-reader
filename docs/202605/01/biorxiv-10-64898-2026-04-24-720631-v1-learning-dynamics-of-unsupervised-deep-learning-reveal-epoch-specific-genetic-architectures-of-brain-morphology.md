---
title: Learning dynamics of unsupervised deep learning reveal epoch-specific genetic architectures of brain morphology
title_zh: 无监督深度学习的学习动力学揭示了大脑形态学中特定轮次的遗传架构
authors: "ISLAM, S. M. S., Xia, T., Zhao, X., Xie, Z., Zhi, D."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720631v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 深度学习用于推导遗传发现的表型
tldr: 本研究探讨了无监督深度学习在脑形态遗传发现中的学习动力学。通过对英国生物银行的3D脑部MRI进行卷积自编码器训练，研究发现不同训练阶段（epoch）的表征能捕捉到截然不同的遗传架构。通过集成多个训练检查点，研究者识别出了比传统单检查点方法更多的基因风险位点，揭示了学习过程与生物学特征演变之间的联系，为利用深度学习进行遗传研究提供了新视角。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在探究深度神经网络在训练过程中表征的演变如何影响从复杂影像数据中发现遗传关联的能力。
method: 利用3D卷积自编码器对英国生物银行的脑部MRI进行训练，并系统分析不同训练轮次下表征的遗传力及其对应的基因位点。
result: 研究发现不同训练阶段捕捉到具有相似遗传力但遗传架构各异的特征，且集成多个检查点能比单一检查点识别出更多显著的基因风险位点。
conclusion: 学习动力学是无监督深度学习进行遗传发现的一个重要维度，利用训练过程中的多个检查点可显著增强对生物学特征的挖掘能力。
---

## 摘要
表示学习是一种从复杂测量（如影像）中提取表型以进行遗传发现的新兴范式。然而，深度神经网络的学习动力学，特别是训练过程中表示的演变，虽然在表示学习中备受关注，但在遗传发现的背景下尚未得到充分研究。在本研究中，我们利用在英国生物样本库（UK Biobank）参与者的 T1 加权大脑 MRI 上训练的 3D 卷积自编码器，证明了其学习轨迹形成了一个按轮次分层的大脑形态遗传力景观。不同的训练轮次在相当的遗传力水平上捕捉到了截然不同的遗传架构。总体而言，跨信息丰富的检查点进行集成，比传统的单检查点方法能识别出更多的基因组风险位点。可解释性分析表明，包括 MAPT 和 MCPH1 在内的轮次特异性位点，映射到了在训练过程不同阶段识别出的、具有生物学一致性且各异的神经解剖特征上。我们的结果将学习动力学确立为利用无监督深度学习进行遗传发现的一个新维度，并对任何在训练期间保存多个检查点的架构具有实际意义。

## Abstract
Representation learning is an emerging paradigm for deriving phenotypes from complex measurements (e.g., imaging) for genetic discovery. However, the learning dynamics of deep neural networks, especially the evolution of representations during training, while of interest in representation learning, were insufficiently investigated in the context of genetic discovery. In this study, using a 3D convolutional autoencoder trained on T1-weighted brain MRIs UK Biobank participants, we show that its learning trajectory forms an epoch-stratified landscape of brain morphology heritability. Different training epochs capture distinct genetic architectures at comparable heritability levels. Overall, ensembling across informative checkpoints identifies more genomic risk loci than the conventional single-checkpoint approach. Interpretability analysis reveals that epoch-specific loci, including MAPT and MCPH1, map onto biologically coherent and distinct neuroanatomical signatures, identified at different stages of the training process. Our results establish learning dynamics as a novel axis for genetic discovery using unsupervised deep learning and have practical implications for any architecture that saves multiple checkpoints during training.

---

## 论文详细总结（自动生成）

这篇论文探讨了无监督深度学习在神经影像遗传学中的应用，重点研究了模型训练过程中的“学习动力学”如何影响遗传关联的发现。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：在利用深度学习（如自编码器）从脑部 MRI 中提取表型进行全基因组关联分析（GWAS）时，研究者通常只选择验证集损失最低的单一检查点（Checkpoint）。论文质疑这一惯例：**模型在训练过程中的动态演变是否会捕捉到不同的遗传信号？**
*   **研究动机**：传统的影像衍生表型（IDP）依赖预定义图谱，可能遗漏复杂的形态模式。无监督学习虽能提取数据驱动特征，但其训练轨迹（Learning Trajectory）与遗传敏感性之间的关系此前未被探索。

### 2. 论文提出的方法论
论文提出了 **TRACE (TRaining-dynamics Analysis via Checkpoint Ensemble)** 框架，核心思想是利用整个训练轨迹而非单一时间点：
*   **3D 卷积自编码器 (CAE)**：构建了一个包含 1.38 亿参数的模型，将全脑 T1 加权 MRI 压缩为 128 维的潜在表示（Latent Representation）。
*   **信息检查点选择**：基于“边际信息增益”准则，筛选出贡献了至少 100 个此前轮次未发现的显著 SNP 的轮次。最终从 85 个轮次中选出 13 个信息丰富的检查点。
*   **集成 GWAS**：对这 13 个检查点的 128 维特征分别进行 GWAS，并使用 minP 方法进行两级聚合（跨维度聚合和跨轮次聚合）。
*   **四阶段位点归因管线**：为了解释特定轮次发现的基因位点（如 *MAPT*），开发了包含“轮次分类器 -> 集成梯度（IG）归因 -> 像素级统计映射 -> 区域富集分析（KS 检验）”的解释方案。

### 3. 实验设计
*   **数据集**：使用英国生物样本库（UK Biobank）数据。
    *   **训练/验证集**：7,663 人（用于自编码器训练）。
    *   **发现集**：22,962 名白人英国后裔（用于 GWAS 发现）。
    *   **复制集**：12,258 人（用于独立验证发现的位点）。
*   **Benchmark 与对比方法**：
    *   **UDIP**：代表传统方法，即仅使用验证集损失最低的单一最佳检查点。
    *   **IDP 预测**：通过预测 139 个已知区域灰质体积来评估表征的解剖学意义。
*   **验证指标**：SNP 遗传力（$h^2$）、显著基因位点数量、解剖学映射的一致性。

### 4. 资源与算力
*   **硬件**：使用了单张 **NVIDIA A100-SXM-80GB GPU**。
*   **训练时长**：总计训练 85 个轮次，每个轮次（含训练与验证）耗时约 **30 分钟**。
*   **计算开销**：论文提到集成梯度（IG）归因分析计算成本极高（30 名受试者 × 24 个检查点），若扩展到数百名受试者将需要约 1,000 GPU 小时。

### 5. 实验数量与充分性
*   **实验规模**：基于超过 4 万名受试者的大规模影像遗传学分析，样本量充足。
*   **充分性**：
    *   进行了 85 个轮次的动态追踪，覆盖了从随机初始化到收敛的全过程。
    *   设置了独立的复制集进行 100% 的方向一致性验证。
    *   针对轮次选择阈值（50, 100, 200 SNPs）进行了**消融/敏感性实验**，证明结论稳健。
*   **客观性**：通过对比相同遗传力水平下的位点发现能力，客观证明了集成方法的优越性。

### 6. 论文的主要结论与发现
*   **遗传景观的分层性**：训练轨迹形成了一个按轮次分层的遗传力景观。不同阶段捕捉到的遗传架构截然不同，例如 *MCPH1* 位点仅在早期轮次出现，而 *MAPT* 位点仅在后期出现。
*   **性能解耦**：重建损失（图像质量）、解剖预测准确度与遗传力这三个指标在训练过程中并不同步。重建质量最好并不代表遗传敏感性最高。
*   **集成优势**：TRACE 集成方法识别出 90 个基因位点，比传统单检查点方法（78 个）多出 15%，且两者的平均遗传力几乎相同（均为 0.585）。
*   **生物学一致性**：通过归因分析发现，后期轮次捕捉到的 *MAPT* 信号精准映射到了与 Tau 蛋白病理相关的颞叶区域，验证了信号的真实性。

### 7. 优点
*   **视角新颖**：首次将深度学习的“学习动力学”引入神经影像遗传学，打破了“单一最佳模型”的思维定式。
*   **可解释性强**：不仅发现了位点，还通过创新的四阶段管线证明了这些位点与特定脑区解剖特征的生物学联系。
*   **实用性高**：该框架不依赖特定架构（VAE、Transformer 等均适用），只需保存训练过程中的多个检查点即可提升发现能力。

### 8. 不足与局限
*   **计算成本**：虽然 GWAS 阶段有加速，但高维特征的归因分析（如 IG）对大规模样本来说依然存在算力瓶颈。
*   **样本单一性**：研究主要集中在英国生物样本库的白人后裔，跨族裔的泛化性有待验证。
*   **模态限制**：目前仅在 T1 加权结构 MRI 上进行了测试，尚未扩展到弥散 MRI 或功能 MRI。
*   **富集分析性质**：KS 富集分析目前主要是描述性的，缺乏针对单个区域的正式显著性检验。

（完）
