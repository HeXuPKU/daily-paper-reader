---
title: "Tokenization to Transfer: Do Genomic Foundation Models Learn Good Representations?"
title_zh: 从分词到迁移：基因组基础模型是否学习到了良好的表示？
authors: "Vishniakov, K., Viswanathan, K., Medvedev, A., Kanithi, P., Pimentel, M. A., Rajan, R., Khan, S."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.1101/2024.12.18.628606v3.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 在基因组任务中评估基因组基础模型 (GFM)
tldr: 本研究系统评估了基因组基础模型（GFM）预训练的实际效用。通过在52个基因组任务上对比7种GFM与其随机初始化版本，发现随机初始化模型表现出乎意料地强，且分词器和架构选择对性能有决定性影响。研究揭示了现有模型在捕捉临床遗传变异方面的不足，为未来开发更具生物学意义的预训练策略提供了重要参考。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-001.webp\", \"caption\": \"Figure 1: Tokenizer choice determines random baseline quality, while pretraining gains are more complex. A comparison of an averaged performance of identical models with random initialization (x-axis) versus pretrained (y-axis) across (A) NT Benchmark (12 histone and enhancer tasks), (B) GUE (7 task categories), and (C) Genomic Benchmarks (8 tasks). Points above the diagonal indicate a benefit from pretraining. Finding: The random baseline performance is strongly determined by the tokenizer, with character models (Orange) consistently outperforming subword models (Blue, Green). In contrast, the performance gains from pretraining are largest for subword models (NT-500M ∆+ 0.242 MCC on GUE) but are highly variable for character models. Marker size is scaled with the number of model parameters.\", \"page\": 2, \"index\": 1, \"width\": 827, \"height\": 297}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-002.webp\", \"caption\": \"Figure 2: Overview of the experiments. (A) Finetuning: we finetune models on different functional element classification tasks. (B) Feature Extraction: For biotype classification, we extract embeddings from frozen models and train a simple classifier to predict gene types using these embeddings. (C) Genomic Variation: We evaluate models’ ability to capture genetic variations through: (1) Mutation sensitivity analysis measures how well models distinguish between original and mutated sequences by computing embedding similarities, and (2) Ancestry prediction uses model embeddings with XGBoost to classify population groups based on genomic variants.\", \"page\": 2, \"index\": 2, \"width\": 660, \"height\": 218}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-003.webp\", \"caption\": \"Table 1: Description of models evaluated in this study. The analyzed models differ in architecture, pretraining objective, tokenizer, model size, and pretraining dataset. We analyze the pretrained models and their randomly initialized counterparts. #Tokens refers to the number of tokens seen by the model during the pretraining. Data refers to the pretraining dataset source.\", \"page\": 3, \"index\": 3, \"width\": 830, \"height\": 262}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-004.webp\", \"caption\": \"Figure 9: GUE performance for each model. Solid bars indicate pretrained model, dashed bars indicate random. Horizontal red dashed line indicates the performance of the best random model. The best rand. init. model is consistently competitive with pretrained models.\", \"page\": 18, \"index\": 4, \"width\": 817, \"height\": 376}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-005.webp\", \"caption\": \"Figure 10: Genomic Benchmarks performance for each model. Solid bars indicate pretrained model, dashed bars indicate randomly initialized. Horizontal red dashed line indicates the performance of the best random model.\", \"page\": 18, \"index\": 5, \"width\": 826, \"height\": 380}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-006.webp\", \"caption\": \"Table 13: Feature Extraction on Histone Tasks from GUE. Embeddings extracted from pretrained and randomly initialized models were used to train an XGBoost classifier. Randomly initialized HyenaDNA with embed dim 2048 outperforms every pretrained model on every task except H3K14ac. MCC on test set is reported.\", \"page\": 19, \"index\": 6, \"width\": 814, \"height\": 260}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-007.webp\", \"caption\": \"Table 10: Statistics of biotype genes.\", \"page\": 19, \"index\": 7, \"width\": 648, \"height\": 256}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-008.webp\", \"caption\": \"Figure 8: NT Benchmark performance per subgroup. Pretrained models (clear bars) vs randomly initialized (dashed bars). Random models are competitive across all subgroups, with random Caduceus outperforming five pretrained models on challenging histone tasks. Red dashed line shows best random model score.\", \"page\": 17, \"index\": 8, \"width\": 826, \"height\": 193}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-009.webp\", \"caption\": \"Table 16: Mutation Data Distribution by Gene and Chunk. Distribution of benign and pathogenic mutations across different chunks for TP53, BRCA2, and CFTR genes.\", \"page\": 20, \"index\": 9, \"width\": 776, \"height\": 181}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-010.webp\", \"caption\": \"Figure 3: Pretraining benefit in low-resource regimes depends on tokenization. Performance curves for H3K4me1 and Enhancers at 1%, 5%, 10%, and 50% data fractions. Subword models (DNABERT-2, GENA-LM) show consistent gains from pretraining (solid / pretrained vs dashed / random lines), while the char-level model (HyenaDNA) often shows smaller benefits.\", \"page\": 5, \"index\": 10, \"width\": 813, \"height\": 212}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-011.webp\", \"caption\": \"Figure 7: Pretraining provides limited or no advantage over randomly initialized models across diverse genomic tasks. We plot the performance difference (∆ MCC or ∆ Accuracy) between seven pretrained GFMs and the best-performing randomly initialized model for each task. Red bars indicate tasks where the randomly initialized model outperformed, whereas green bars indicate tasks where the pretrained model performed better. The predominance of red bars provides strong evidence that current pretraining paradigms, adapted from NLP, offer minimal benefit for genomics tasks. Notably, smaller randomly initialized models (e.g., Caduceus) frequently achieve the best performance, challenging the assumption that larger pretrained models are inherently superior.\", \"page\": 16, \"index\": 11, \"width\": 827, \"height\": 901}]"
motivation: 探究基因组基础模型预训练性能与下游任务效果之间的关系，并评估其相对于高昂计算成本的有效性。
method: 在52个多样化的基因组任务中，对比评估了7种主流GFM与其对应的随机初始化权重模型的表现。
result: 随机初始化模型提供了极强的基准，分词方式显著影响预训练收益，且现有模型在捕捉临床相关变异方面表现有限。
conclusion: 当前类NLP的预训练策略提升有限，未来研究应转向生物学启发的分词方法和变异感知目标。
---

## 摘要
大语言模型的成功启发了通过类似的预训练技术开发基因组基础模型（GFMs）。然而，预训练性能与下游基因组任务有效性之间的关系仍不明确。此外，预训练的高计算成本引发了对其成本效益的质疑。为了评估预训练在基因组学中的效用，我们在 52 个不同的基因组任务中评估了七种不同的 GFM，并将其与具有随机初始化权重的对应模型进行了比较。在各项基准测试中，我们发现随机初始化的模型提供了出人意料的强大基准，而分词器和架构的选择极大地影响了这些基准以及预训练带来的收益。具体而言，基于字符分词的模型通常能达到或超过更大的预训练 k-mer 或 BPE 模型的性能，而子词模型似乎能从预训练中获益。我们还发现，所评估的 GFM 未能捕捉到临床相关的遗传突变，其嵌入和对数似然比对已标注变异的敏感性有限。对于我们研究的任务，这些结果表明，当前的 NLP 风格预训练策略在强大的随机基准之上仅提供了适度的、受分词器限制的改进，并促使人们探索更具生物学启发的分词方式和变异感知目标。我们的代码可在 github.com/m42-health/gfm-random-eval 获取。

## Abstract
AO_SCPLOWBSTRACTC_SCPLOWThe success of Large Language Models has inspired the development of Genomic Foundation Models (GFMs) through similar pretraining techniques. However, the relationship between pretraining performance and effectiveness in downstream genomic tasks remains unclear. Additionally, the high computational cost of pretraining raises questions about its cost-efficiency. To assess the usefulness of pretraining in genomics, we evaluated seven different GFMs across 52 diverse genomic tasks, comparing them to their counterparts with randomly initialized weights. Across benchmarks, we find that randomly initialized models provide surprisingly strong baselines and tokenizer and architecture choices strongly shape both these baselines and the gains from pretraining. Specifically, character-token models often match or exceed the performance of larger pretrained k-mer or BPE models, whereas subword models appear to benefit from pretraining. We also find that the evaluated GFMs fail to capture clinically relevant genetic mutations, with embeddings and log-likelihood ratios showing limited sensitivity to annotated variants. For the tasks we study, these results suggest that current NLP-style pretraining strategies provide modest, tokenizer-gated improvements over strong random baselines and motivate more biologically informed tokenization and variant-aware objectives. Our code is available at github.com/m42-health/gfm-random-eval.

---

## 论文详细总结（自动生成）

这篇论文对当前基因组基础模型（GFM）的有效性进行了系统性评估，以下是详细的结构化总结：

### 1. 核心问题与研究动机
*   **核心问题**：当前模仿自然语言处理（NLP）的大规模预训练策略，在基因组学任务中是否真的比随机初始化的模型更有效？
*   **研究动机**：尽管基因组基础模型（GFM）在学术界备受关注，但预训练性能与下游任务表现之间的关系尚不明确。考虑到预训练极高的计算成本，研究者质疑这种“NLP风格”的预训练是否具有成本效益，以及模型是否真正捕捉到了生物学意义上的序列特征。

### 2. 方法论
*   **核心思想**：采用“端到端对比”的方法，将 7 种主流预训练 GFM 与其**完全相同架构但随机初始化权重**的对应版本进行对比。
*   **关键技术细节**：
    *   **模型选择**：涵盖了不同架构（Transformer, State-Space Models）、不同分词器（Character, k-mer, BPE）和不同规模（450K 到 580M 参数）的模型，包括 HyenaDNA、Caduceus、DNABERT-2、GENA-LM、NT 系列以及作者自研的 Mistral-DNA。
    *   **评估维度**：分为全参数微调（Finetuning）、冻结特征提取（Feature Extraction）和基因组变异分析（Genomic Variation）三个维度。
    *   **分词器消融**：专门设计实验对比字符分词（Character）与子词分词（k-mer/BPE）对模型性能的影响。

### 3. 实验设计
*   **数据集与基准测试**：
    *   **下游分类任务**：使用了 NT Benchmark、GUE（Genome Understanding Evaluation）和 Genomic Benchmarks，共计 **52 个基因组分类任务**（如组蛋白修饰、增强子预测、剪接位点检测等）。
    *   **特征提取**：使用 Gencode 数据集进行生物类型（Biotype）分类。
    *   **变异分析**：使用 1000 Genomes 项目数据进行祖先预测，并利用 ClinVar 数据评估模型对致病性突变的敏感性。
*   **对比方法**：每个预训练模型都与其随机初始化的版本在完全相同的超参数条件下进行对比。

### 4. 资源与算力
*   **算力投入**：论文明确提到，为了训练自研的 Mistral-DNA 模型，使用了由 **6 个节点组成的 GPU 集群，每个节点配备 8 张 NVIDIA H100 GPU（共 48 张 H100）**。
*   **训练规模**：Mistral 模型在 150B 个 token 上进行了预训练。此外，为了确保公平性，研究团队进行了近 **10,000 次微调实验**，以搜索最佳超参数。

### 5. 实验数量与充分性
*   **实验规模**：涵盖 7 种模型、52 个任务、多种学习率和数据比例（1% 到 50% 的消融），实验总量巨大。
*   **充分性与客观性**：实验设计非常严谨。作者不仅对比了预训练与随机初始化，还进行了超参数搜索、LoRA 与全微调的对比、以及嵌入维度的消融实验。这种大规模的对比研究在当前领域内非常罕见，具有很高的客观性和说服力。

### 6. 主要结论与发现
*   **随机基准极强**：随机初始化的模型表现出人意料地好。在许多任务中，随机初始化的字符分词模型（如 Caduceus）甚至能超过参数量更大的预训练模型。
*   **分词器决定性能**：分词方式是影响性能的关键。字符分词模型在随机状态下表现最强，但从预训练中获益较少；而子词分词（k-mer/BPE）模型虽然随机表现较差，但能从预训练中获得显著提升。
*   **变异敏感性缺失**：现有的 GFM 在捕捉单核苷酸多态性（SNP）等微小变异方面表现极差。无论是嵌入向量的余弦相似度还是对数似然比测试，模型都难以区分参考序列与突变序列（AUROC 接近 0.5）。
*   **预训练收益有限**：在大多数微调任务中，预训练带来的性能提升仅在 2-3% 左右，这与其巨大的计算成本不成正比。

### 7. 优点
*   **批判性视角**：挑战了“规模越大、预训练越久就越好”的固有观念。
*   **严谨的实验控制**：通过确保随机初始化版本与预训练版本在架构和超参数上的完全一致，消除了实验偏差。
*   **揭示了分词器的核心作用**：深入探讨了分词策略如何作为“归纳偏置”影响模型学习。

### 8. 不足与局限
*   **任务类型限制**：主要集中在判别式分类任务上，未深入探讨生成式任务（如序列设计）或超长程依赖任务（如增强子-启动子相互作用）。
*   **上下文窗口限制**：评估的部分模型上下文窗口较短（128-1024 bp），可能限制了其在复杂调控逻辑任务中的表现。
*   **变异评估深度**：虽然使用了 ClinVar，但对于变异效应预测的评估还可以进一步扩展到 eQTL 或 sQTL 等更复杂的生物学场景。

（完）
