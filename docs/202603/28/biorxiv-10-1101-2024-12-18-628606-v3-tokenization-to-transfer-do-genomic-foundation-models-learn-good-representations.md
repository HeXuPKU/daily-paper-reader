---
title: "Tokenization to Transfer: Do Genomic Foundation Models Learn Good Representations?"
title_zh: 从分词到迁移：基因组基础模型是否学习到了良好的表示？
authors: "Vishniakov, K., Viswanathan, K., Medvedev, A., Kanithi, P., Pimentel, M. A., Rajan, R., Khan, S."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.1101/2024.12.18.628606v3.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 在多种基因组任务中评估基因组基础模型
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
大语言模型的成功启发了通过类似的预训练技术开发基因组基础模型（GFMs）。然而，预训练性能与下游基因组任务有效性之间的关系仍不明确。此外，预训练的高昂计算成本也引发了对其成本效益的质疑。为了评估预训练在基因组学中的实用性，我们在 52 个不同的基因组任务中评估了七种不同的 GFM，并将其与具有随机初始化权重的对应模型进行了比较。在各项基准测试中，我们发现随机初始化的模型提供了出人意料的强大基准，而分词器（tokenizer）和架构的选择极大地影响了这些基准以及预训练带来的收益。具体而言，基于字符分词（character-token）的模型通常能达到或超过更大规模的预训练 k-mer 或 BPE 模型的性能，而子词（subword）模型似乎能从预训练中获益。我们还发现，所评估的 GFM 未能捕捉到临床相关的遗传突变，其嵌入（embeddings）和对数似然比对已标注变异的敏感性有限。对于我们研究的任务，这些结果表明，当前的 NLP 式预训练策略在强大的随机基准之上仅提供了适度的、受分词器限制的改进，并促使人们探索更具生物学意义的分词方式和变异感知目标。我们的代码可在 github.com/m42-health/gfm-random-eval 获取。

## Abstract
AO_SCPLOWBSTRACTC_SCPLOWThe success of Large Language Models has inspired the development of Genomic Foundation Models (GFMs) through similar pretraining techniques. However, the relationship between pretraining performance and effectiveness in downstream genomic tasks remains unclear. Additionally, the high computational cost of pretraining raises questions about its cost-efficiency. To assess the usefulness of pretraining in genomics, we evaluated seven different GFMs across 52 diverse genomic tasks, comparing them to their counterparts with randomly initialized weights. Across benchmarks, we find that randomly initialized models provide surprisingly strong baselines and tokenizer and architecture choices strongly shape both these baselines and the gains from pretraining. Specifically, character-token models often match or exceed the performance of larger pretrained k-mer or BPE models, whereas subword models appear to benefit from pretraining. We also find that the evaluated GFMs fail to capture clinically relevant genetic mutations, with embeddings and log-likelihood ratios showing limited sensitivity to annotated variants. For the tasks we study, these results suggest that current NLP-style pretraining strategies provide modest, tokenizer-gated improvements over strong random baselines and motivate more biologically informed tokenization and variant-aware objectives. Our code is available at github.com/m42-health/gfm-random-eval.

---

## 论文详细总结（自动生成）

以下是对论文《Tokenization to Transfer: Do Genomic Foundation Models Learn Good Representations?》的结构化深入总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **研究动机**：受大语言模型（LLM）启发，基因组基础模型（GFM）通过在大规模基因组序列上进行无监督预训练（如掩码语言建模或下一标记预测）而兴起。然而，预训练的高昂计算成本与其在下游任务中带来的实际收益之间的关系并不透明。
*   **核心问题**：当前的基因组预训练策略是否真的学习到了优于随机初始化的生物学表示？预训练在不同分词策略和架构下的有效性如何？

### 2. 方法论：核心思想与关键技术细节
*   **核心思想**：通过“端到端对比”评估预训练的价值。研究者将 7 种主流 GFM 的**预训练版本**与其**完全相同架构但随机初始化（Random Init）的版本**在相同条件下进行对比。
*   **关键技术细节**：
    *   **模型选择**：涵盖了编码器（Encoder）和解码器（Decoder）架构，包括 Transformer 和状态空间模型（SSM），参数量从 450K 到 580M 不等。
    *   **分词器对比**：分析了字符级（Character）、k-mer 和字节对编码（BPE）三种分词策略的影响。
    *   **评估维度**：
        1.  **全参数微调（Finetuning）**：在监督任务上更新权重。
        2.  **特征提取（Feature Extraction）**：冻结权重，使用嵌入向量训练简单的分类器（如 XGBoost）。
        3.  **变异敏感性分析**：通过余弦相似度和对数似然比（LLR）评估模型对单核苷酸多态性（SNP）等微小序列变化的感知能力。
    *   **自定义模型**：作者训练了一个基于 Mistral 架构（580M 参数）的基因组模型，采用字符分词和 RoPE 位置编码。

### 3. 实验设计
*   **数据集与基准（Benchmark）**：
    *   **NT Benchmark**：包含组蛋白修饰、增强子、启动子和剪接位点预测（12 个任务）。
    *   **GUE (Genome Understanding Evaluation)**：涵盖 7 个类别、28 个数据集的多物种基准。
    *   **Genomic Benchmarks**：包含人类、小鼠和线虫的 8 个分类任务。
    *   **总计**：52 个基因组分类任务。
*   **对比方法**：对比了 HyenaDNA、Caduceus、NT-500M、NT-50M、GENA-LM、DNABERT-2 以及作者自研的 Mistral 模型。

### 4. 资源与算力
*   **预训练算力**：作者训练 Mistral 模型使用了 **48 张 Nvidia H100 GPU**（6 个节点，每节点 8 张卡），在 150B 个 token 上进行训练。
*   **微调算力**：进行了近 **10,000 次微调实验**，涵盖了不同的学习率、权重衰减、Batch Size 以及 LoRA 与全参数微调的对比。

### 5. 实验数量与充分性
*   **实验规模**：实验设计非常详尽，不仅对比了预训练与随机初始化，还进行了：
    *   **数据稀缺性实验**：在 1%、5%、10% 和 50% 的标签比例下测试预训练收益。
    *   **分词器消融实验**：固定架构，仅改变分词方式（字符 vs k-mer）。
    *   **嵌入维度实验**：测试不同隐藏层维度对随机模型性能的影响。
*   **充分性评价**：实验覆盖了目前主流的所有 GFM 架构和分词策略，通过大规模超参数搜索确保了对比的公平性，结论具有高度的客观性和说服力。

### 6. 主要结论与发现
*   **随机基准极强**：随机初始化的模型（尤其是字符分词模型）表现出惊人的竞争力。例如，随机初始化的 Caduceus 往往能匹配甚至超过比它大得多的预训练模型。
*   **分词器是关键门控**：
    *   **字符分词模型**：随机基准极高，预训练带来的提升微乎其微且不稳定。
    *   **子词/k-mer 模型**：随机基准较低，预训练能带来显著提升（0.05-0.25 MCC），但最终性能往往仍难超越字符模型。
*   **预训练损失的误导性**：消融实验显示，字符模型虽然预训练困惑度（Perplexity）更低，但在下游任务中反而不如 k-mer 模型，说明当前的预训练目标与生物学功能预测之间存在脱节。
*   **变异感知能力缺失**：所有评估的模型在捕捉临床相关突变（如 ClinVar 变异）方面表现极差，AUROC 接近随机猜测（0.5 左右），且嵌入向量对 SNP 极不敏感。

### 7. 优点
*   **批判性视角**：挑战了“预训练规模越大越好”的固有认知，揭示了分词策略在基因组建模中的核心地位。
*   **严谨的实验控制**：通过“随机初始化 vs 预训练”的同架构对比，排除了架构本身带来的性能红利。
*   **实战指导意义**：为研究者提供了实用的建议，即在开发新模型时应优先报告经过良好调优的随机基准。

### 8. 不足与局限
*   **上下文长度限制**：受限于评估模型的默认配置，大多数实验在较短的序列（128-1024 bp）上进行，未能充分测试超长程（如 100kb+）的调控相互作用。
*   **任务类型偏差**：主要集中在判别式分类任务，未深入探讨生成式任务（如序列设计）或回归任务（如基因表达预测）。
*   **变异分析深度**：虽然揭示了敏感性不足，但未进一步探索如何通过特定的目标函数（如对比学习）来修复这一缺陷。

（完）
