---
title: A Long-Context Generative Foundation Model Deciphers RNA Design Principles
title_zh: 一个长上下文生成式基础模型破译 RNA 设计原理
authors: "Huang, Y., Lv, G., Cheng, A., Xie, W., Chen, M., Ma, X., Tang, Y., Shi, Q., Wang, J., Wang, Z., Yunpeng, X., Zhao, L., Cai, Y., Chen, J. X., Zheng, S."
date: 2026-03-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.17.712398v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 在1.14亿个序列上训练的长上下文生成式RNA基础模型
tldr: "针对现有RNA生成模型在可控设计和长序列建模方面的局限，本研究推出了EVA（Evolutionary Versatile Architect）。EVA是一个基于1.14亿条全长RNA序列训练的长上下文生成式基础模型，采用混合专家（MoE）架构，支持高达8,192个token的上下文窗口。它能捕捉RNA的全局结构与精细功能，在突变适应性预测、序列工程及多种RNA（如tRNA、mRNA、环状RNA）的从头设计中表现卓越，在多个基准测试中达到SOTA水平，为RNA设计提供了统一的开源框架。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-17-712398-v2/fig-001.webp\", \"caption\": \"Figure 2: Zero-shot fitness prediction across RNA, DNA, and protein. (a) Conceptual overview of using EVA’s zero-shot sequence likelihood to approximate fitness landscapes and mutation effects for RNA, gene regions, and proteins. (b)(c) Benchmark results for zero-shot fitness prediction on ncRNA (b) and mRNA (c) sequences, evaluating the correlation between EVA likelihood scores and experimentally measured fitness across a diverse collection of deep mutational scanning (DMS) assays. Performance is reported as Spearman’s rank correlation (ρ); points indicate individual assays. (d)(e) Benchmark results on eukaryotic (d) and prokaryotic (e) gene essentiality prediction by inserting premature stop codons near the 5′ end of coding sequences and quantifying the EVA log-likelihood drop to infer essentiality. (f) Benchmark results for zero-shot fitness prediction on protein, evaluating the correlation between likelihood scores and experimentally measured fitness. Nucleotide-input EVA predictions are compared against protein language model baselines.\", \"page\": 6, \"index\": 1, \"width\": 944, \"height\": 998}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-17-712398-v2/fig-002.webp\", \"caption\": \"Figure 5: mRNA and circRNA vaccine design with EVA. (a) Conceptual overview of mRNA codon optimization with EVA. (b) Benchmark on five mRNA vaccine systems (SARS-CoV-2 Spike, Influenza PR8 HA, VZV gE, RABV-G, HIV) comparing CDS optimization in terms of MFE and CAI against Evo2-1B, CodonFM-1B, and a Random (MFE-only) baseline, all conditioned on the mRNA type and Homo sapiens. (c) Conceptual overview of circRNA vaccine design with EVA: ORF codon optimization via species-conditioned autoregressive generation (left), and de novo IRES redesign via EVA GLM where the IRES region is masked and regenerated conditioned on flanking sequences (right). (d) Benchmark on four circRNA vaccine systems (SARS: Group-I, SARS: T4 ligase, rabies, CAR-T) for ORF codon optimization, same baselines and species conditioning as (b). (e)(f) Biophysical properties of EVA-redesigned IRES sequences versus the original CVB3 IRES for SARS and rabies circRNA vaccines, including ribosome accessibility and inhibitory long-range interactions.\", \"page\": 11, \"index\": 2, \"width\": 958, \"height\": 939}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-17-712398-v2/fig-003.webp\", \"caption\": \"Figure 1: Overview of EVA data, model, and training. (a) Overview of the EVA model capabilities, and representative applications. (b) OpenRNA v1 comprises 114M curated full-length RNA sequences spanning all domains of life; Phylogenetic tree construction of training data. (c) Comparison of training data scale with prior work (left), and sequence-length distributions together with the number of full-length RNAs covered by different context windows (right). (d) RNA type distribution in OpenRNA v1. (e) EVA model architecture and key differences from prior RNA language models: Mixture-of-Experts (MoE) architecture, support for both CLM and GLM generation, and conditioning on RNA type and taxonomic labels. (f) Illustration of the unstructured global distribution learned by conventional RNA LMs versus the controllable fine-grained latent space learned by EVA. (g) Comparison of context window lengths between EVA (8,192 nt) and prior RNA language models (1,024 nt), highlighting broader RNA design coverage enabled by long context. (h) Long-context “needle-in-a-haystack” evaluation demonstrating EVA’s ability to recall long-range dependencies under an 8,192-token context window. (i) Scaling behavior showing decreasing perplexity with increasing model size, indicating that larger models better capture RNA sequence grammar.\", \"page\": 3, \"index\": 3, \"width\": 976, \"height\": 850}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-17-712398-v2/fig-004.webp\", \"caption\": \"Figure 6: Interpretability analysis revealing hierarchical RNA features learned by EVA. (a) Schematic illustrating how model neurons are mapped to biological concepts using sparse autoencoders, revealing that EVA can learn structure- and function-related biological knowledge from sequence alone. (b) Activations of features associated with IRES, ORF, and related functional elements in circRNA vaccines (left: RABV-G; right: SARS-CoV-2). (c) Activations of features associated with 5′UTR, CDS, and 3′UTR in mRNA vaccines (HIV, PR8 HA, RABV-G, and VZV gE).\", \"page\": 13, \"index\": 4, \"width\": 959, \"height\": 462}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-17-712398-v2/fig-005.webp\", \"caption\": \"Figure 3: Controllable RNA generation with EVA across diverse RNA families and species. (a) Sequence similarity between generated sequences and their closest natural neighbours for unconditional CLM, and reconstruction similarity for GLM; CLM produces both high-similarity and more divergent sequences, whereas GLM achieves higher reconstruction via richer flanking context. (b) GLM infilling similarity between generated and masked fragments across 11 RNA classes. (c) Schematic of conditional generation controlled by RNA-type tags. (d) KL divergence comparison between EVA and GenerRNA across 11 RNA classes, evaluated over three secondary-structure feature groups (GC content & MFE, loop & helix composition, and base-pairing & stem statistics); EVA achieves >13-fold lower KL divergence. (e) Distributional comparisons of RNA-type conditioned samples vs. natural RNAs across UMAP embedding, length, MFE, GC content, and secondarystructure features. (f) Schematic of conditional generation controlled by taxonomic (species) tags. (g) KL divergence comparison between EVA and GenerRNA across six representative mRNA species; EVA achieves >30-fold lower KL divergence, reflecting accurate modeling of organism-specific RNA landscapes. (h) Distributional comparisons of species-conditioned mRNAs vs. natural sequences across sequence, biophysical, and structural metrics; extended results in Figure S7.\", \"page\": 8, \"index\": 5, \"width\": 964, \"height\": 908}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-17-712398-v2/fig-006.webp\", \"caption\": \"Figure 4: De novo design of tRNAs, RNA aptamers, and CRISPR gRNAs. (a) Zero-shot de novo generation of tRNAs showing high structural similarity to natural tRNAs, quantified by TM-score, while maintaining sequence novelty relative to known tRNAs. (b) Representative structural alignments between AlphaFold3-predicted structures of generated tRNAs and experimentally resolved natural tRNAs, illustrating preservation of the canonical L-shaped fold despite low sequence identity. (c) Prediction of fluorescence intensity for RNA aptamers after low-data fine-tuning (n = 30). Left: binding to HBC530; right: binding to HBC620. Model log-likelihood scores are compared against experimentally measured fluorescence. (d) Structural comparison between de novo generated aptamers (blue) and wildtype structures, showing preservation of the ligand-binding pocket and overall fold despite sequence mutations, consistent with learned mutational-structural relationships. (e,f) Prediction of editing efficiency for IscB omegaRNAs after fine-tuning on m16 (n = 42) and m17 (n = 44) sequence sets, respectively. (g) AlphaFold3-predicted complex structure of IscB protein, de novo designed m16 omegaRNA, and target DNA. Success is defined by satisfying a set of domain-level structural criteria relative to wildtype (see Methods). (h,i) Violin plots showing sequence similarity distributions between de novo generated omegaRNAs and the corresponding wildtype sequences for m17 (h) and m16 (i). Generated sequences span a biologically reasonable range of divergence while remaining structurally plausible.\", \"page\": 9, \"index\": 6, \"width\": 949, \"height\": 823}]"
motivation: 现有RNA生成模型因上下文窗口短且缺乏鲁棒的可控设计能力，难以有效模拟全长转录本的复杂进化特征。
method: "开发了基于混合专家架构的EVA模型，利用8,192个token的长上下文窗口在1.14亿条全长RNA序列上进行预训练。"
result: EVA在七项基准测试中取得SOTA性能，显著提升了结构建模精度，并成功实现了从tRNA到mRNA等多种RNA的定向优化与设计。
conclusion: EVA作为一个功能全面的开源RNA基础模型，为解码RNA设计原则及开发新型RNA疗法提供了强有力的工具。
---

## 摘要
具有特定功能 RNA 序列的可编程设计仍然是生物学中的一个核心挑战。尽管最近取得了进展，但现有的 RNA 生成模型缺乏鲁棒的可控设计能力，并受限于短上下文窗口，限制了它们对全长转录本复杂进化流形进行建模的能力。在此，我们介绍了 EVA（Evolutionary Versatile Architect），这是一个长上下文生成式 RNA 基础模型，在涵盖整个进化多样性的超过 1.14 亿条全长 RNA 序列上进行了训练。通过将混合专家（Mixture-of-Experts）架构与 8,192 个 token 的上下文窗口相结合，EVA 学习了 RNA 序列空间的统一且进化一致的表示，能够同时捕捉全局转录本结构和细粒度的功能元件。EVA 在单一架构内为广泛的 RNA 设计任务建立了一个统一框架，涵盖从突变适应性预测到上下文感知序列工程。我们通过对多种 RNA 类别（包括 tRNA、适配体和 CRISPR 引导 RNA，以及 mRNA 和环状 RNA 疗法）的从头设计和靶向优化，展示了 EVA 的多功能性。在系统评估中，EVA 在九个既定基准中的七个上实现了最先进的性能，与现有方法相比，结构建模精度提高了一个数量级。EVA 已在以下仓库完全开源：https://github.com/GENTEL-lab/EVA。

## Abstract
Programmable design of RNA sequences with defined functions remains a central challenge in biology. Despite recent advances, existing RNA generative models lack robust controllable design capabilities and are constrained by short context windows, limiting their capacity to model the complex evolutionary manifold of full-length transcripts. Here, we introduce EVA (Evolutionary Versatile Architect), a long-context generative RNA foundation model trained on over 114 million full-length RNA sequences spanning the full breadth of evolutionary diversity. By integrating a Mixture-of-Experts architecture with an 8,192-token context window, EVA learns a unified, evolution-consistent representation of RNA sequence space that captures both global transcript structure and fine-grained functional elements. EVA establishes a unified framework for a broad spectrum of RNA design tasks within a single architecture, ranging from mutational fitness prediction to context-aware sequence engineering. We demonstrate EVAs versatility through the de novo design and targeted optimization of diverse RNA classes, including tRNAs, aptamers, and CRISPR guide RNAs, as well as mRNA and circular RNA therapeutics. In systematic evaluations, EVA achieves state-of-the-art performance across seven of nine established benchmarks, improving structural modeling accuracy by up to an order of magnitude compared to existing approaches. EVA is fully open-source at the following repository: https://github.com/GENTEL-lab/EVA.

---

## 论文详细总结（自动生成）

### 论文总结：EVA (Evolutionary Versatile Architect) —— 长上下文生成式 RNA 基础模型

#### 1. 核心问题与整体含义
*   **研究动机**：RNA 在生命过程中具有极其多样的功能（编码、结构、催化、调节），但现有的 RNA 生成模型存在两大瓶颈：一是**上下文窗口短**（通常小于 1024 nt），难以建模全长转录本；二是**缺乏鲁棒的可控设计能力**，难以在不同物种和 RNA 类别间进行精确切换。
*   **核心目标**：开发一个能够捕捉全长 RNA 序列进化流形、支持长上下文且具备多任务统一处理能力的生成式基础模型，以破译 RNA 设计原理并助力药物研发。

#### 2. 方法论
*   **核心思想**：利用大规模进化多样性数据，通过混合专家（MoE）架构和长上下文窗口，构建一个既能进行序列评分（预测）又能进行受控合成（生成）的统一模型。
*   **关键技术细节**：
    *   **架构**：1.4B 参数的 Decoder-only Transformer，引入 **Mixture-of-Experts (MoE)** 骨干网络（8 个专家，每次激活 2 个），显著提升参数效率。
    *   **长上下文**：支持 **8,192 个 token** 的窗口，覆盖了超过 95% 的已知全长转录本。
    *   **训练目标**：结合了**因果语言建模 (CLM)** 和 **广义语言建模 (GLM/Infilling)**。CLM 用于从头生成，GLM 用于局部区域的掩码填充（如 IRES 重新设计）。
    *   **数据策略**：构建了 **OpenRNA v1** 数据集（1.14 亿条全长序列）。采用基于进化保守性的**平方根采样策略**，平衡了常见家族（如 rRNA）与稀有功能家族的权重。
    *   **两阶段训练**：第一阶段进行 RNA 类别标签条件预训练；第二阶段引入分类学（物种）标签进行中后期训练，实现从通用语法到物种特异性特征的解耦。

#### 3. 实验设计
*   **数据集**：OpenRNA v1（包含 mRNA, tRNA, circRNA, miRNA 等 15 类 RNA）。
*   **Benchmark 与对比方法**：
    *   **零样本适应性预测**：在 13 个 ncRNA 突变扫描 (DMS) 任务、5 个 mRNA 任务及 20 个蛋白质 DMS 任务上评估。对比了 Evo/Evo2、CodonFM、ESMC 等模型。
    *   **基因必需性预测**：在 42 种原核生物和 5 种真核生物上对比 Evo 系列模型。
    *   **生成质量**：与 GenerRNA 对比，评估 GC 含量、最小自由能 (MFE)、二级结构特征的 KL 散度。
    *   **应用场景**：tRNA 从头设计（TM-score 评估）、RNA 适配体优化、CRISPR IscB omegaRNA 设计、mRNA/circRNA 疫苗密码子优化。

#### 4. 资源与算力
*   **算力资源**：使用了 **16 台 NVIDIA H200 (141GB) GPU**，分布在 2 个节点上。
*   **并行策略**：采用了混合并行方案，包括专家并行 (EP=4) 和数据并行 (DP=4)。
*   **训练细节**：模型规模从 21M 扩展至 1.4B。虽然未明确给出总训练天数，但详细记录了超参数设置（如 AdamW 优化器、1e-4 学习率、BF16 精度）。

#### 5. 实验数量与充分性
*   **实验规模**：非常充分。涵盖了从分子水平（突变预测）到系统水平（基因必需性），再到应用水平（疫苗设计）的完整链条。
*   **消融实验**：对 MoE 与 Dense 架构、采样策略、两阶段训练课程、上下文长度等关键变量进行了详细的消融研究。
*   **客观性**：使用了大量独立的第三方基准数据集（如 ProteinGym、DEG 数据库），并采用了多种生物物理指标（MFE、CAI、TM-score）进行多维度评估，结果较为客观。

#### 6. 主要结论与发现
*   **统一性**：EVA 在单一架构下实现了 11 类 RNA 的可控生成，且在 9 个基准测试中的 7 个达到 SOTA。
*   **跨模态能力**：尽管仅在 RNA 上训练，EVA 展现了预测 DNA 基因必需性和蛋白质突变效应的惊人能力，证明编码序列蕴含了跨尺度的进化约束。
*   **长上下文优势**：8k 窗口对于捕捉全长转录本的全局结构至关重要，显著提升了结构建模精度（最高达一个数量级）。
*   **可解释性**：通过稀疏自编码器 (SAE) 发现，模型内部神经元能够自动识别 5'UTR、CDS、3'UTR 和 IRES 等功能元件。

#### 7. 优点
*   **架构创新**：首次将 MoE 引入 RNA 基础模型，解决了 RNA 数据异质性带来的建模难题。
*   **长上下文支持**：极大地扩展了可设计的 RNA 空间，使其能够处理复杂的长链非编码 RNA 和全长 mRNA。
*   **开源贡献**：提供了目前最大的开源 RNA 数据集、全系列模型权重及完整的训练/微调流程，对社区贡献巨大。
*   **实用性强**：直接针对疫苗设计和 CRISPR 工具优化等前沿生物工程问题提供了解决方案。

#### 8. 不足与局限
*   **湿实验验证**：论文目前主要基于计算评估（In silico），虽然展示了结构模拟的合理性，但缺乏大规模的湿实验（Wet-lab）最终验证数据。
*   **3D 结构建模**：模型本质上是基于序列的，虽然能捕捉结构约束，但无法像 AlphaFold-multimer 那样直接输出精确的原子级 3D 坐标。
*   **系统级设计限制**：目前仍侧重于单条 RNA 链的设计，对于更复杂的 RNA-蛋白质复合物或多组分 RNA 系统的协同设计仍有提升空间。

（完）
