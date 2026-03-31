---
title: "Tokenization to Transfer: Do Genomic Foundation Models Learn Good Representations?"
title_zh: 从分词到迁移：基因组基础模型是否学习到了良好的表示？
authors: "Vishniakov, K., Viswanathan, K., Medvedev, A., Kanithi, P., Pimentel, M. A., Rajan, R., Khan, S."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.1101/2024.12.18.628606v3.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 在多种基因组任务中评估基因组基础模型 (GFM)
tldr: 本研究评估了基因组基础模型（GFM）的预训练有效性。通过在52个多样化任务中对比7种GFM及其随机初始化版本，发现随机权重模型是极强的基准。研究指出分词器和架构选择对性能影响巨大，且现有模型难以捕捉临床相关的基因突变。这表明当前的类NLP预训练策略提升有限，呼吁开发更具生物学启发的分词和训练目标。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-001.webp\", \"caption\": \"Figure 1: Tokenizer choice determines random baseline quality, while pretraining gains are more complex. A comparison of an averaged performance of identical models with random initialization (x-axis) versus pretrained (y-axis) across (A) NT Benchmark (12 histone and enhancer tasks), (B) GUE (7 task categories), and (C) Genomic Benchmarks (8 tasks). Points above the diagonal indicate a benefit from pretraining. Finding: The random baseline performance is strongly determined by the tokenizer, with character models (Orange) consistently outperforming subword models (Blue, Green). In contrast, the performance gains from pretraining are largest for subword models (NT-500M ∆+ 0.242 MCC on GUE) but are highly variable for character models. Marker size is scaled with the number of model parameters.\", \"page\": 2, \"index\": 1, \"width\": 827, \"height\": 297}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-002.webp\", \"caption\": \"Figure 2: Overview of the experiments. (A) Finetuning: we finetune models on different functional element classification tasks. (B) Feature Extraction: For biotype classification, we extract embeddings from frozen models and train a simple classifier to predict gene types using these embeddings. (C) Genomic Variation: We evaluate models’ ability to capture genetic variations through: (1) Mutation sensitivity analysis measures how well models distinguish between original and mutated sequences by computing embedding similarities, and (2) Ancestry prediction uses model embeddings with XGBoost to classify population groups based on genomic variants.\", \"page\": 2, \"index\": 2, \"width\": 660, \"height\": 218}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-003.webp\", \"caption\": \"Table 1: Description of models evaluated in this study. The analyzed models differ in architecture, pretraining objective, tokenizer, model size, and pretraining dataset. We analyze the pretrained models and their randomly initialized counterparts. #Tokens refers to the number of tokens seen by the model during the pretraining. Data refers to the pretraining dataset source.\", \"page\": 3, \"index\": 3, \"width\": 830, \"height\": 262}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-004.webp\", \"caption\": \"Figure 9: GUE performance for each model. Solid bars indicate pretrained model, dashed bars indicate random. Horizontal red dashed line indicates the performance of the best random model. The best rand. init. model is consistently competitive with pretrained models.\", \"page\": 18, \"index\": 4, \"width\": 817, \"height\": 376}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-005.webp\", \"caption\": \"Figure 10: Genomic Benchmarks performance for each model. Solid bars indicate pretrained model, dashed bars indicate randomly initialized. Horizontal red dashed line indicates the performance of the best random model.\", \"page\": 18, \"index\": 5, \"width\": 826, \"height\": 380}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-006.webp\", \"caption\": \"Table 13: Feature Extraction on Histone Tasks from GUE. Embeddings extracted from pretrained and randomly initialized models were used to train an XGBoost classifier. Randomly initialized HyenaDNA with embed dim 2048 outperforms every pretrained model on every task except H3K14ac. MCC on test set is reported.\", \"page\": 19, \"index\": 6, \"width\": 814, \"height\": 260}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-007.webp\", \"caption\": \"Table 10: Statistics of biotype genes.\", \"page\": 19, \"index\": 7, \"width\": 648, \"height\": 256}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-008.webp\", \"caption\": \"Figure 8: NT Benchmark performance per subgroup. Pretrained models (clear bars) vs randomly initialized (dashed bars). Random models are competitive across all subgroups, with random Caduceus outperforming five pretrained models on challenging histone tasks. Red dashed line shows best random model score.\", \"page\": 17, \"index\": 8, \"width\": 826, \"height\": 193}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-009.webp\", \"caption\": \"Table 16: Mutation Data Distribution by Gene and Chunk. Distribution of benign and pathogenic mutations across different chunks for TP53, BRCA2, and CFTR genes.\", \"page\": 20, \"index\": 9, \"width\": 776, \"height\": 181}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-010.webp\", \"caption\": \"Figure 3: Pretraining benefit in low-resource regimes depends on tokenization. Performance curves for H3K4me1 and Enhancers at 1%, 5%, 10%, and 50% data fractions. Subword models (DNABERT-2, GENA-LM) show consistent gains from pretraining (solid / pretrained vs dashed / random lines), while the char-level model (HyenaDNA) often shows smaller benefits.\", \"page\": 5, \"index\": 10, \"width\": 813, \"height\": 212}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-011.webp\", \"caption\": \"Figure 7: Pretraining provides limited or no advantage over randomly initialized models across diverse genomic tasks. We plot the performance difference (∆ MCC or ∆ Accuracy) between seven pretrained GFMs and the best-performing randomly initialized model for each task. Red bars indicate tasks where the randomly initialized model outperformed, whereas green bars indicate tasks where the pretrained model performed better. The predominance of red bars provides strong evidence that current pretraining paradigms, adapted from NLP, offer minimal benefit for genomics tasks. Notably, smaller randomly initialized models (e.g., Caduceus) frequently achieve the best performance, challenging the assumption that larger pretrained models are inherently superior.\", \"page\": 16, \"index\": 11, \"width\": 827, \"height\": 901}]"
motivation: 旨在探究基因组基础模型的预训练性能如何转化为下游任务效果，并评估其高昂计算成本的合理性。
method: 通过在52个基因组任务上对比7种主流GFM与其随机初始化版本的表现，系统评估预训练的实际增益。
result: 随机初始化模型表现出人意料地强，且分词器选择决定了性能基准，而现有模型在识别临床变异方面能力不足。
conclusion: 现有的类NLP预训练策略在基因组领域仅提供有限改进，未来研究应转向生物学知情的分词和变异感知目标。
---

## 摘要
大语言模型的成功启发了通过类似的预训练技术开发基因组基础模型（GFMs）。然而，预训练性能与下游基因组任务有效性之间的关系仍不明确。此外，预训练的高计算成本引发了对其成本效益的质疑。为了评估预训练在基因组学中的效用，我们在 52 个不同的基因组任务中评估了七种不同的 GFM，并将其与具有随机初始化权重的对应模型进行了比较。在各项基准测试中，我们发现随机初始化的模型提供了出人意料的强大基准，而分词器和架构的选择极大地影响了这些基准以及预训练带来的收益。具体而言，基于字符分词的模型通常能达到或超过更大的预训练 k-mer 或 BPE 模型的性能，而子词模型似乎能从预训练中获益。我们还发现，所评估的 GFM 未能捕捉到临床相关的遗传突变，其嵌入和对数似然比对已标注变异的敏感性有限。对于我们研究的任务，这些结果表明，当前的 NLP 风格预训练策略在强大的随机基准之上仅提供了适度的、受分词器限制的改进，并促使人们探索更具生物学启发的分词方式和变异感知目标。我们的代码可在 github.com/m42-health/gfm-random-eval 获取。

## Abstract
AO_SCPLOWBSTRACTC_SCPLOWThe success of Large Language Models has inspired the development of Genomic Foundation Models (GFMs) through similar pretraining techniques. However, the relationship between pretraining performance and effectiveness in downstream genomic tasks remains unclear. Additionally, the high computational cost of pretraining raises questions about its cost-efficiency. To assess the usefulness of pretraining in genomics, we evaluated seven different GFMs across 52 diverse genomic tasks, comparing them to their counterparts with randomly initialized weights. Across benchmarks, we find that randomly initialized models provide surprisingly strong baselines and tokenizer and architecture choices strongly shape both these baselines and the gains from pretraining. Specifically, character-token models often match or exceed the performance of larger pretrained k-mer or BPE models, whereas subword models appear to benefit from pretraining. We also find that the evaluated GFMs fail to capture clinically relevant genetic mutations, with embeddings and log-likelihood ratios showing limited sensitivity to annotated variants. For the tasks we study, these results suggest that current NLP-style pretraining strategies provide modest, tokenizer-gated improvements over strong random baselines and motivate more biologically informed tokenization and variant-aware objectives. Our code is available at github.com/m42-health/gfm-random-eval.

---

## 论文详细总结（自动生成）

这篇论文对基因组基础模型（Genomic Foundation Models, GFMs）的预训练有效性进行了系统且深入的反思性评估。以下是该论文的结构化总结：

### 1. 论文的核心问题与整体含义
*   **研究动机**：受大语言模型（LLM）启发，基因组学领域涌现出大量通过大规模无监督预训练构建的基础模型。然而，预训练性能（如困惑度）与下游任务效果之间的关系并不明确，且预训练消耗了巨大的计算资源。
*   **核心问题**：现有的基因组预训练策略是否真的学习到了优于随机初始化的表示？预训练带来的增益是否与其高昂的成本相匹配？

### 2. 论文提出的方法论
*   **核心思想**：通过“端到端对比”实验，将 7 种主流预训练 GFM 与其**完全相同架构但权重随机初始化**的对应版本进行对比。
*   **关键技术细节**：
    *   **微调（Finetuning）**：在 52 个分类任务上进行全参数微调，而非仅使用 LoRA，以确保随机基准能达到其性能上限。
    *   **特征提取（Feature Extraction）**：冻结模型权重，提取嵌入向量（Embeddings），使用 XGBoost 等简单分类器评估特征质量。
    *   **变异敏感性分析**：通过计算原始序列与突变序列（SNP）之间的余弦相似度，以及计算对数似然比（LLR），评估模型对单核苷酸变化的感知能力。
    *   **分词器消融实验**：控制架构不变，仅改变分词方式（如字符 vs. k-mer），探究分词策略对性能的影响。

### 3. 实验设计
*   **数据集与基准（Benchmarks）**：
    *   **NT Benchmark**：包含组蛋白修饰、增强子、启动子和剪接位点预测等任务。
    *   **GUE (Genome Understanding Evaluation)**：涵盖 7 大类、28 个数据集的多物种基准。
    *   **Genomic Benchmarks**：涉及人类、小鼠和线虫的 8 个监管元素分类任务。
    *   **变异分析**：使用 ClinVar 数据集（涉及 TP53, BRCA2, CFTR 基因）和 1000 Genomes Project（用于祖先预测）。
*   **对比方法**：评估了 HyenaDNA, NT-500M, NT-50M, GENA-LM, DNABERT-2, Caduceus 以及作者自训练的 Mistral-DNA。

### 4. 资源与算力
*   **算力投入**：作者训练了自己的 Mistral-DNA 模型，使用了 **6 个节点，每个节点配备 8 张 Nvidia H100 GPU（共 48 张 H100）**。
*   **训练规模**：Mistral 模型在 150B 个 token 上进行了预训练。
*   **微调实验**：为了确保公平性，进行了近 **10,000 次微调实验**，涵盖了广泛的学习率和超参数搜索。

### 5. 实验数量与充分性
*   **实验规模**：涵盖 52 个多样化任务，涉及从 450K 到 580M 参数量的不同架构（Transformer, SSM 等）。
*   **充分性与公平性**：实验设计非常严谨。作者不仅对比了预训练与随机初始化，还考虑了数据稀缺场景（1% 到 50% 标签量）下的表现，并对分词器、嵌入维度等关键变量进行了详尽的消融研究。这种大规模的超参数搜索确保了随机基准不是因为训练不足而表现差，结论具有高度客观性。

### 6. 论文的主要结论与发现
*   **随机基准极强**：随机初始化的模型（尤其是基于字符分词的模型，如 Caduceus）在许多任务上能匹配甚至超过大型预训练模型。
*   **分词器是关键**：分词方式决定了随机基准的起点。**字符级分词（Character-level）**模型在随机状态下表现最好；而**子词/k-mer 分词**模型更依赖预训练来学习词表表示。
*   **预训练增益有限**：在大多数任务中，预训练带来的性能提升仅为 2-3%，在某些字符级模型中甚至出现负迁移。
*   **变异感知力缺失**：现有的 GFM 对单核苷酸多态性（SNP）极不敏感。即使序列中一半的碱基被修改，模型嵌入的余弦相似度仍可能高于 0.99，且在 ClinVar 变异预测上的表现接近随机猜测（AUROC ≈ 0.5）。

### 7. 优点
*   **批判性视角**：挑战了领域内“规模越大、预训练越久就越好”的固有认知。
*   **实验严谨**：通过全参数微调和大规模超参数搜索，消除了“随机基准未充分训练”的偏差。
*   **揭示机制**：深入探讨了分词器归纳偏置（Inductive Bias）与预训练收益之间的因果关系。

### 8. 不足与局限
*   **任务覆盖限制**：主要集中在判别式分类任务，未深入探讨生成式任务（如序列设计）或超长程依赖任务（如增强子-启动子相互作用）。
*   **上下文窗口**：评估的大多数模型上下文窗口较短（128-1024），无法完全代表最新一代超长上下文模型（如 Evo2）的潜力。
*   **变异分析深度**：虽然指出了模型对 SNP 不敏感，但尚未提出能够彻底解决该问题的成熟预训练目标。

（完）
