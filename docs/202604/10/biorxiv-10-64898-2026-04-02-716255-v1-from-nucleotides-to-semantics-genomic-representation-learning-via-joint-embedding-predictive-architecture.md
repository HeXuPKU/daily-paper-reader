---
title: "From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture"
title_zh: 从核苷酸到语义：通过联合嵌入预测架构进行基因组表示学习
authors: "Wang, C., Qi, Q., Sun, H., Zhuang, Z., He, B., Liu, S., Liao, J., Wang, J."
date: 2026-04-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.02.716255v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 通过联合嵌入预测架构进行基因组表示学习
tldr: 针对现有基因组基础模型将DNA类比语言进行核苷酸级重建导致的计算开销大、语义表达弱等问题，本文提出了GenoJEPA框架。该方法采用联合嵌入预测架构，通过连续分块和潜在空间语义对齐，将优化目标从局部碱基重建转向语义对齐。在55项下游任务中，GenoJEPA以更少的参数和计算成本实现了强大的表征能力，支持冻结参数下的轻量级分类，为高效训练大规模基因组模型提供了新路径。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-001.webp\", \"caption\": \"Fig. 3 GenoJEPA achieves competitive performance with end-to-end finetuning. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the overall performance of GenoJEPA and the baselines across all benchmarks. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show the critical difference diagrams for finetuning and probing performance across all benchmarks. Statistical significance is summarized with the Friedman test at p = 0.05 followed by the Nemenyi post-hoc test at p = 0.05 on the task-level representative scores. The average rank and significance are reported from these mean scores. Black horizontal lines indicate no significant difference between methods. (d), (e), and (f) show finetuning performance for each task within the three benchmarks. Blue circles denote the mean score for each task, and red diamonds denote the average performance across all tasks within each benchmark.\", \"page\": 7, \"index\": 1, \"width\": 813, \"height\": 570}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-002.webp\", \"caption\": \"Fig. 5 GenoJEPA exhibits strong few-shot capabilities and feature versatility. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows probing performance for GenoJEPA and the baselines at different training-data scales across all benchmarks. Within each fold, the training and validation sets are stratified at proportions from 10% to 50% for each label while the test set is kept unchanged. Logistic regression with average pooling is used to assess the data efficiency of each method. The average performance across 55 tasks from three benchmarks is reported from these mean scores. (b) and (c) show probing performance under different pooling strategies and classifiers across all benchmarks. The boxplots summarize the distribution of representative scores across 55 tasks from all benchmarks. The center line denotes the median. The box limits denote the first and third quartiles. The whiskers denote the full data range.\", \"page\": 10, \"index\": 2, \"width\": 812, \"height\": 428}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-003.webp\", \"caption\": \"Fig. 4 GenoJEPA demonstrates favourable computational and memory efficiency. (a), (c), (e), and (g) report training time in ms, training memory in MB, inference time in ms, and inference memory in MB, respectively, for GenoJEPA and baselines with fewer than 10M parameters across different sequence lengths. (b), (d), (f), and (h) report the same metrics for GenoJEPA and baselines with more than 50M parameters. Experiments are conducted with a batch size of 1 on an A800 80 GB GPU. Each experiment is repeated for 10 epochs, and mean values are reported. In each epoch, the first 10 steps are excluded to remove cold-start effects. Average metrics are then computed over the next 100 steps. Both axes are shown on a logarithmic scale. Vertical dashed lines indicate sequence lengths that exceed model support or require memory beyond GPU capacity.\", \"page\": 8, \"index\": 3, \"width\": 815, \"height\": 574}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-004.webp\", \"caption\": \"Fig. 1 GenoJEPA learns genomic representations via joint-embedding prediction. (a) shows the pretraining framework. The input DNA sequence is split into non-overlapping patches, linearly projected into dense embeddings, and processed by a Transformer encoder. Token embeddings are then averaged to obtain a sequence representation. Following the LeJEPA formulation, the sequence is augmented into multiple local and global views through random cropping. GenoJEPA is optimized with an invariance loss that aligns semantic features across views together with a SIGReg loss that prevents representation collapse. (b) shows the downstream adaptation strategies for genomic tasks such as functional element identification. In resourcelimited settings, the pretrained encoder is frozen and the resulting sequence embeddings are passed to a lightweight task head for probing. In accuracy-sensitive settings, the entire GenoJEPA model is finetuned end to end together with a task head.\", \"page\": 4, \"index\": 4, \"width\": 815, \"height\": 469}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-02-716255-v1/fig-005.webp\", \"caption\": \"Fig. 2 GenoJEPA maintains highly discriminative features under probing evaluation. Each task is evaluated through 10-fold cross-validation, and the mean test score is used as the representative result. (a) shows the probing win-loss comparison between GenoJEPA and the baselines across all benchmarks. A paired Wilcoxon signed-rank test at p = 0.05 is applied to the fold-wise test scores as a stability-aware paired comparison. The number of wins, ties, and losses is reported across 55 tasks from three benchmarks. (b) shows probing performance for each benchmark. The average and median performance across all tasks within each benchmark are reported from the representative scores. (c) shows task-level probing performance. On the horizontal axis, blue labels denote the Genomic Benchmarks, red labels denote the GUE Benchmarks, and green labels denote the Nucleotide Transformer Tasks.\", \"page\": 5, \"index\": 5, \"width\": 815, \"height\": 645}]"
motivation: 传统基于NLP的DNA预训练模型因缺乏语义边界和核苷酸级重建开销，导致表征能力受限且微调成本高。
method: 提出GenoJEPA框架，利用联合嵌入预测架构结合连续分块技术，在潜在空间中进行语义对齐而非局部重建。
result: 在55个下游任务中表现出卓越的表征能力和泛化性，且显著降低了参数量和计算成本，支持无GPU环境下的轻量级分类。
conclusion: GenoJEPA证明了在潜在空间进行语义学习是构建高效、可扩展且易于应用的基因组基础模型的有效途径。
---

## 摘要
解码基因组序列中编码的调控语法是计算生物学的一个核心目标。大多数现有的基因组基础模型将 DNA 视为一种语言，并采用自然语言处理中的预训练目标。然而，DNA 序列缺乏明确的语义边界，并包含大量的进化噪声。因此，在低维输入空间中进行核苷酸级重构会增加计算开销，并可能产生判别能力有限的表示。下游任务通常依赖于昂贵的微调，这限制了其在许多生物实验室中的实际应用。在这里，我们提出了 GenoJEPA，这是一个基于联合嵌入预测架构（joint-embedding predictive architecture）的基因组表示学习框架。GenoJEPA 将连续分块（continuous patching）与语义对齐相结合，将优化目标从局部碱基重构转向潜在空间中的语义对齐。在 55 个下游任务中，GenoJEPA 在减少参数数量和计算成本的同时，展现了强大的表示能力和鲁棒的泛化性能。来自冻结的 GenoJEPA 的语义向量支持轻量级、无需 GPU 的分类器，从而实现具有竞争力的准确率。这些结果为大规模基因组基础模型的高效训练和广泛应用提供了一条切实可行的路径。

## Abstract
Decoding the regulatory syntax encoded in genomic sequences is a central objective in computational biology. Most existing genomic foundation models treat DNA as a language and adopt pretraining objectives from natural language processing. DNA sequences, however, lack explicit semantic boundaries and contain substantial evolutionary noise. Nucleotide-level reconstruction in a low-dimensional input space can therefore increase computational overhead and may yield representations with limited discriminative capacity. Downstream tasks often depend on expensive finetuning, which restricts practical use in many biology laboratories. Here we present GenoJEPA, a genomic representation learning framework based on joint-embedding predictive architecture. GenoJEPA combines continuous patching with semantic alignment, shifting the optimization from local base reconstruction to semantic alignment in latent space. Across 55 downstream tasks, GenoJEPA shows strong representational capacity and robust generalization while reducing parameter count and computational cost. The resulting semantic vectors from frozen GenoJEPA support lightweight GPU-free classifiers to achieve competitive accuracy. These results suggest a practical route towards efficient training and broad application of larger-scale genomic foundation models.

---

## 论文详细总结（自动生成）

这是一份关于论文《From nucleotides to semantics: genomic representation learning via joint-embedding predictive architecture》的结构化深度总结：

### 1. 论文的核心问题与整体含义
*   **研究动机：** 现有的基因组基础模型（如 DNABERT, Nucleotide Transformer）大多将 DNA 类比为自然语言，采用掩码语言模型（MLM）或下一 Token 预测（NTP）进行预训练。
*   **核心挑战：** 
    *   **语义差异：** DNA 序列与人类语言不同，缺乏明确的词汇边界，且包含大量非编码的“进化噪声”。
    *   **重建瓶颈：** 传统的核苷酸级重建（类似于图像中的像素级重建）会导致模型过度关注低级物理细节和噪声，而非高级生物语义。
    *   **资源限制：** 现有模型通常需要昂贵的全参数微调才能在下游任务中生效，这限制了资源有限的生物实验室的应用。
*   **整体含义：** 本文提出了 **GenoJEPA** 框架，旨在通过在潜在空间（Latent Space）进行语义对齐，而非在输入空间进行碱基重建，从而学习更具判别力和通用性的基因组表示。

### 2. 方法论
*   **核心思想：** 借鉴计算机视觉中的联合嵌入预测架构（JEPA），通过对同一 DNA 序列的不同增强视图（View）进行潜在空间特征对齐，捕捉序列的结构化语义。
*   **关键技术细节：**
    1.  **连续分块（Continuous Patching）：** 放弃传统的 k-mer 或 BPE 分词，将 DNA 序列切分为非重叠的固定长度块（如 16bp），通过线性投影映射为连续向量。这避免了词表膨胀，并保留了局部生化依赖性。
    2.  **骨干架构：** 采用 **ModernBERT** 架构，引入旋转位置嵌入（RoPE）、预归一化（Pre-norm）和无偏置设计，提升了长序列处理效率。
    3.  **多视图增强：** 对同一序列进行随机裁剪，生成 2 个全局视图（覆盖 65%-80%）和 6 个局部视图（覆盖 35%-40%）。
    4.  **优化目标（损失函数）：**
        *   **不变性损失（Invariance Loss）：** 强制所有视图的表示向全局视图的平均表示靠拢。
        *   **SIGReg 损失（正则化）：** 采用“素描各向同性高斯正则化”，通过随机投影和经验特征函数测试，引导特征分布符合标准高斯分布，防止表征崩溃（Representation Collapse）。

### 3. 实验设计
*   **预训练数据：** 涵盖 850 个代表性物种（细菌、真菌、无脊椎动物、脊椎动物等）的基因组语料库，总计约 1930 亿个核苷酸。
*   **Benchmark：** 在 3 个主流基准上进行了 55 个子任务的评估：
    *   **Genomic Benchmarks (9项)：** 跨物种序列分类、调控元件识别。
    *   **GUE Benchmarks (28项)：** 病毒变体分类、酵母组蛋白修饰、人类/小鼠转录因子结合预测。
    *   **Nucleotide Transformer Tasks (18项)：** 人类表观遗传标记、剪接位点识别。
*   **对比方法：** HyenaDNA (7M), CaduceusPh (8M), GROVER (87M), DNABERT-2 (117M), NT-v2 (494M)。

### 4. 资源与算力
*   **GenoJEPA-T (6M 参数)：** 使用 **1 张 NVIDIA RTX 3090 (24GB)**，训练 10 万步，耗时约 **12 小时**。
*   **GenoJEPA-B (52M 参数)：** 使用 **1 张 NVIDIA A800 (80GB)**，训练 50 万步，耗时约 **150 小时**。
*   **效率优势：** 相比于参数量大 10 倍的 NT-v2，GenoJEPA 在更短的时间内达到了更优的性能。

### 5. 实验数量与充分性
*   **实验规模：** 论文进行了极其详尽的实验，包括 55 个任务的 **Probing（冻结权重探测）** 和 **Finetuning（全参数微调）**。
*   **消融实验：** 附录中包含了 **23 组消融实验**，涵盖了数据增强策略、Patch 大小、嵌入维度、损失函数超参数、学习率调度等各个方面。
*   **客观性：** 采用了 10 折交叉验证，并使用马修斯相关系数（MCC）作为主要指标以应对生物数据的不平衡性。对比实验在统一的硬件和协议下进行，确保了公平性。

### 6. 主要结论与发现
*   **语义表征极强：** 在冻结模型参数的 Probing 评估中，52M 的 GenoJEPA-B 显著优于 494M 的 NT-v2，证明其学习到的原始特征具有极高的判别力。
*   **微调性能领先：** 在全参数微调下，GenoJEPA 依然保持了最高或极具竞争力的平均排名。
*   **计算效率极高：** 连续分块技术显著降低了内存占用和运行时间，在 8192bp 长度下的表现优于专门针对长序列设计的 Mamba/Hyena 架构模型。
*   **数据效率：** 在仅使用 10% 标注数据的情况下，GenoJEPA 的表现即可接近其他模型使用 50% 数据的结果。

### 7. 优点（亮点）
*   **范式创新：** 首次将 JEPA 架构成功应用于基因组学，证明了“对齐优于重建”在处理高噪声生物序列时的优越性。
*   **实用性强：** 强大的 Probing 能力意味着研究人员可以使用廉价的 CPU 环境（如逻辑回归分类器）直接利用预训练特征，降低了门槛。
*   **架构稳健：** 连续分块策略解决了离散词表对单核苷酸突变敏感的问题，增强了模型的鲁棒性。

### 8. 不足与局限
*   **序列长度限制：** 预训练序列长度上限为 4096bp，虽然覆盖了大多数基因级任务，但对于需要超长程依赖的任务（如 TAD 边界识别）尚显不足。
*   **模型规模：** 目前最大模型仅为 52M，尚未探索在亿级（Billion-scale）参数下的扩展定律（Scaling Laws）。
*   **任务覆盖：** 实验主要集中在分类任务上，对于生成式任务（如序列设计）的适用性尚未验证。

（完）
