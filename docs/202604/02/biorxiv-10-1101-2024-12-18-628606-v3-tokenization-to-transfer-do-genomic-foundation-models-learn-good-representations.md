---
title: "Tokenization to Transfer: Do Genomic Foundation Models Learn Good Representations?"
title_zh: 从分词到迁移：基因组基础模型是否学习到了良好的表示？
authors: "Vishniakov, K., Viswanathan, K., Medvedev, A., Kanithi, P., Pimentel, M. A., Rajan, R., Khan, S."
date: 2026-03-25
pdf: "https://www.biorxiv.org/content/10.1101/2024.12.18.628606v3.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 基因组基础模型评估与预训练有效性研究
tldr: 本研究通过在52个基因组任务上评估7种基因组基础模型（GFMs），发现随机初始化的模型是极强的基准，而分词器和架构选择显著影响预训练增益。研究指出，现有模型在捕捉临床基因突变方面能力有限，表明当前的NLP式预训练策略在基因组领域提升有限，亟需开发更具生物学意义的分词和训练目标。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-001.webp\", \"caption\": \"Figure 1: Tokenizer choice determines random baseline quality, while pretraining gains are more complex. A comparison of an averaged performance of identical models with random initialization (x-axis) versus pretrained (y-axis) across (A) NT Benchmark (12 histone and enhancer tasks), (B) GUE (7 task categories), and (C) Genomic Benchmarks (8 tasks). Points above the diagonal indicate a benefit from pretraining. Finding: The random baseline performance is strongly determined by the tokenizer, with character models (Orange) consistently outperforming subword models (Blue, Green). In contrast, the performance gains from pretraining are largest for subword models (NT-500M ∆+ 0.242 MCC on GUE) but are highly variable for character models. Marker size is scaled with the number of model parameters.\", \"page\": 2, \"index\": 1, \"width\": 827, \"height\": 297}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-002.webp\", \"caption\": \"Figure 2: Overview of the experiments. (A) Finetuning: we finetune models on different functional element classification tasks. (B) Feature Extraction: For biotype classification, we extract embeddings from frozen models and train a simple classifier to predict gene types using these embeddings. (C) Genomic Variation: We evaluate models’ ability to capture genetic variations through: (1) Mutation sensitivity analysis measures how well models distinguish between original and mutated sequences by computing embedding similarities, and (2) Ancestry prediction uses model embeddings with XGBoost to classify population groups based on genomic variants.\", \"page\": 2, \"index\": 2, \"width\": 660, \"height\": 218}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-003.webp\", \"caption\": \"Table 1: Description of models evaluated in this study. The analyzed models differ in architecture, pretraining objective, tokenizer, model size, and pretraining dataset. We analyze the pretrained models and their randomly initialized counterparts. #Tokens refers to the number of tokens seen by the model during the pretraining. Data refers to the pretraining dataset source.\", \"page\": 3, \"index\": 3, \"width\": 830, \"height\": 262}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-004.webp\", \"caption\": \"Figure 9: GUE performance for each model. Solid bars indicate pretrained model, dashed bars indicate random. Horizontal red dashed line indicates the performance of the best random model. The best rand. init. model is consistently competitive with pretrained models.\", \"page\": 18, \"index\": 4, \"width\": 817, \"height\": 376}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-005.webp\", \"caption\": \"Figure 10: Genomic Benchmarks performance for each model. Solid bars indicate pretrained model, dashed bars indicate randomly initialized. Horizontal red dashed line indicates the performance of the best random model.\", \"page\": 18, \"index\": 5, \"width\": 826, \"height\": 380}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-006.webp\", \"caption\": \"Table 13: Feature Extraction on Histone Tasks from GUE. Embeddings extracted from pretrained and randomly initialized models were used to train an XGBoost classifier. Randomly initialized HyenaDNA with embed dim 2048 outperforms every pretrained model on every task except H3K14ac. MCC on test set is reported.\", \"page\": 19, \"index\": 6, \"width\": 814, \"height\": 260}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-007.webp\", \"caption\": \"Table 10: Statistics of biotype genes.\", \"page\": 19, \"index\": 7, \"width\": 648, \"height\": 256}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-008.webp\", \"caption\": \"Figure 8: NT Benchmark performance per subgroup. Pretrained models (clear bars) vs randomly initialized (dashed bars). Random models are competitive across all subgroups, with random Caduceus outperforming five pretrained models on challenging histone tasks. Red dashed line shows best random model score.\", \"page\": 17, \"index\": 8, \"width\": 826, \"height\": 193}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-009.webp\", \"caption\": \"Table 16: Mutation Data Distribution by Gene and Chunk. Distribution of benign and pathogenic mutations across different chunks for TP53, BRCA2, and CFTR genes.\", \"page\": 20, \"index\": 9, \"width\": 776, \"height\": 181}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-010.webp\", \"caption\": \"Figure 3: Pretraining benefit in low-resource regimes depends on tokenization. Performance curves for H3K4me1 and Enhancers at 1%, 5%, 10%, and 50% data fractions. Subword models (DNABERT-2, GENA-LM) show consistent gains from pretraining (solid / pretrained vs dashed / random lines), while the char-level model (HyenaDNA) often shows smaller benefits.\", \"page\": 5, \"index\": 10, \"width\": 813, \"height\": 212}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-1101-2024-12-18-628606-v3/fig-011.webp\", \"caption\": \"Figure 7: Pretraining provides limited or no advantage over randomly initialized models across diverse genomic tasks. We plot the performance difference (∆ MCC or ∆ Accuracy) between seven pretrained GFMs and the best-performing randomly initialized model for each task. Red bars indicate tasks where the randomly initialized model outperformed, whereas green bars indicate tasks where the pretrained model performed better. The predominance of red bars provides strong evidence that current pretraining paradigms, adapted from NLP, offer minimal benefit for genomics tasks. Notably, smaller randomly initialized models (e.g., Caduceus) frequently achieve the best performance, challenging the assumption that larger pretrained models are inherently superior.\", \"page\": 16, \"index\": 11, \"width\": 827, \"height\": 901}]"
motivation: 旨在探究基因组基础模型的预训练性能与下游任务效果之间的关系，并评估其预训练的成本效益。
method: 在52个多样化的基因组任务中，对比了7种主流GFMs与其随机初始化版本在表示学习上的差异。
result: 发现随机初始化模型表现强劲，且分词器选择决定了预训练收益，但现有模型对临床相关变异的敏感度普遍较低。
conclusion: 目前的NLP式预训练策略对基因组任务改进有限，未来研究应关注生物学启发的分词方式和变异感知目标。
---

## 摘要
大语言模型的成功启发了通过类似的预训练技术开发基因组基础模型（GFMs）。然而，预训练性能与下游基因组任务有效性之间的关系仍不明确。此外，预训练的高计算成本引发了对其成本效益的质疑。为了评估预训练在基因组学中的效用，我们在 52 个不同的基因组任务中评估了七种不同的 GFM，并将其与具有随机初始化权重的对应模型进行了比较。在各项基准测试中，我们发现随机初始化的模型提供了令人惊讶的强基准，且分词器（tokenizer）和架构的选择强烈影响了这些基准以及预训练带来的收益。具体而言，基于字符分词（character-token）的模型通常能达到或超过规模更大的预训练 k-mer 或 BPE 模型的性能，而子词（subword）模型似乎能从预训练中获益。我们还发现，所评估的 GFM 未能捕捉到临床相关的遗传突变，其嵌入（embeddings）和对数似然比对已标注变异的敏感性有限。对于我们研究的任务，这些结果表明，当前的 NLP 式预训练策略在强大的随机基准之上仅提供了适度的、受分词器限制的改进，并促使人们探索更具生物学启发的分词方式和变异感知目标。我们的代码可在 github.com/m42-health/gfm-random-eval 获取。

## Abstract
AO_SCPLOWBSTRACTC_SCPLOWThe success of Large Language Models has inspired the development of Genomic Foundation Models (GFMs) through similar pretraining techniques. However, the relationship between pretraining performance and effectiveness in downstream genomic tasks remains unclear. Additionally, the high computational cost of pretraining raises questions about its cost-efficiency. To assess the usefulness of pretraining in genomics, we evaluated seven different GFMs across 52 diverse genomic tasks, comparing them to their counterparts with randomly initialized weights. Across benchmarks, we find that randomly initialized models provide surprisingly strong baselines and tokenizer and architecture choices strongly shape both these baselines and the gains from pretraining. Specifically, character-token models often match or exceed the performance of larger pretrained k-mer or BPE models, whereas subword models appear to benefit from pretraining. We also find that the evaluated GFMs fail to capture clinically relevant genetic mutations, with embeddings and log-likelihood ratios showing limited sensitivity to annotated variants. For the tasks we study, these results suggest that current NLP-style pretraining strategies provide modest, tokenizer-gated improvements over strong random baselines and motivate more biologically informed tokenization and variant-aware objectives. Our code is available at github.com/m42-health/gfm-random-eval.

---

## 论文详细总结（自动生成）

这篇论文对基因组基础模型（Genomic Foundation Models, GFMs）的预训练有效性进行了系统且深入的评估。以下是详细的结构化总结：

### 1. 核心问题与整体含义
*   **研究动机**：受大语言模型（LLM）启发，基因组学领域涌现了大量通过大规模无监督预训练构建的基础模型。然而，预训练的高昂计算成本是否转化为了下游任务的显著增益？预训练性能（如困惑度）与实际生物学任务效果之间的关系是否明确？
*   **核心问题**：当前的基因组预训练策略是否真的学习到了优于“随机初始化+有监督微调”的表示？

### 2. 方法论
*   **核心思想**：通过“端到端对比”实验，将 7 种主流 GFMs 的**预训练版本**与其**完全相同架构但随机初始化的版本**在相同条件下进行对比。
*   **关键技术细节**：
    *   **微调（Finetuning）**：在 52 个分类任务上进行全参数微调，并进行广泛的超参数搜索（如学习率、权重衰减等），确保对比的公平性。
    *   **特征提取（Feature Extraction）**：冻结模型权重，提取嵌入向量（Embeddings），使用 XGBoost 等简单分类器评估原始表示质量。
    *   **变异敏感性分析**：通过计算参考序列与突变序列（SNP）之间的余弦相似度，以及基于对数似然比（LLR）的 ClinVar 变异预测，评估模型对单核苷酸变化的感知力。
    *   **分词器消融**：对比字符级（Character）、k-mer 和 BPE 分词对模型性能的影响。

### 3. 实验设计
*   **数据集与场景**：
    *   **三大基准测试**：NT Benchmark（组蛋白修饰、增强子等）、GUE（多物种基因组理解）、Genomic Benchmarks。
    *   **变异任务**：1000 Genomes（祖先预测）、ClinVar（致病性变异分析）。
*   **对比方法**：评估了 HyenaDNA、NT-500M、NT-50M、GENA-LM、DNABERT-2、Caduceus 以及作者自研的 Mistral-DNA。
*   **评估指标**：MCC（马修斯相关系数）、Accuracy、F1 分数、AUROC、余弦相似度。

### 4. 资源与算力
*   **算力投入**：
    *   **自研 Mistral 模型**：使用了 6 个节点，每个节点配备 8 张 Nvidia H100 GPU（共 **48 张 H100**）。
    *   **训练规模**：在 1000 Genomes 数据集的 50 个样本上预训练，处理了约 1500 亿个 token。
    *   **微调实验**：进行了近 **10,000 次**微调实验，以确保超参数搜索的完备性。

### 5. 实验数量与充分性
*   **实验规模**：涵盖 52 个任务，跨越不同物种（人、小鼠、果蝇、线虫）和不同生物学功能（启动子、剪接位点、增强子等）。
*   **充分性与客观性**：实验设计非常严谨。作者不仅对比了预训练与随机初始化，还进行了数据缩减实验（1% 到 50% 标签量）和分词器控制变量实验。通过全参数微调而非 LoRA 确保了随机基准能发挥最大潜力，体现了极高的客观性。

### 6. 主要结论与发现
*   **随机基准极强**：随机初始化的模型（尤其是基于字符分词的模型，如 Caduceus）在许多任务上表现优异，甚至超过了参数量更大的预训练模型。
*   **分词器决定增益**：
    *   **字符分词模型**：随机基准很高，预训练带来的提升微乎其微甚至有负面影响。
    *   **子词/k-mer 分词模型**：预训练增益显著，因为预训练帮助模型克服了处理复杂词表（Vocabulary）的难度。
*   **变异感知力缺失**：现有 GFMs 对单核苷酸多态性（SNP）极不敏感。即使序列中一半的碱基被修改，模型嵌入的相似度仍接近 0.99；在 ClinVar 致病性预测任务中，表现接近随机猜测（AUROC 约 0.5）。
*   **预训练损失的误导性**：较低的预训练损失（困惑度）并不一定对应更好的下游任务表现。

### 7. 优点
*   **揭示了行业盲点**：挑战了“预训练规模越大越好”的固有认知，指出了分词器在基因组模型中的核心地位。
*   **严谨的基准测试**：通过大规模超参数搜索，消除了因微调不充分导致的实验偏差。
*   **变异敏感性评估**：首次系统性地指出当前模型在临床相关变异分析上的严重局限。

### 8. 不足与局限
*   **任务覆盖范围**：主要集中在判别式分类任务，未深入探讨生成式任务（如序列设计）或超长程依赖任务（如基因表达预测）。
*   **上下文长度限制**：所评估的大多数模型上下文窗口较短（128-1024 bp），可能限制了对长程调控元件关系的理解。
*   **模型版本更新**：虽然涵盖了主流模型，但基因组 AI 领域发展极快，更新的模型（如 Evo2）未包含在本次深度对比中。

（完）
