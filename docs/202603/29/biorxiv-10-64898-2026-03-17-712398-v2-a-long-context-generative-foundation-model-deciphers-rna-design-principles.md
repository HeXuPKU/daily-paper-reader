---
title: A Long-Context Generative Foundation Model Deciphers RNA Design Principles
title_zh: 一种长上下文生成式基础模型破译 RNA 设计原理
authors: "Huang, Y., Lv, G., Cheng, A., Xie, W., Chen, M., Ma, X., Tang, Y., Shi, Q., Wang, J., Wang, Z., Yunpeng, X., Zhao, L., Cai, Y., Chen, J. X., Zheng, S."
date: 2026-03-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.17.712398v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 针对大规模RNA序列的长上下文生成式基础模型
tldr: "针对现有RNA生成模型在长序列建模和可控设计方面的局限，本研究推出了EVA（Evolutionary Versatile Architect）。这是一个拥有8,192个token长上下文窗口的生成式基础模型，基于1.14亿条全长RNA序列训练，并采用混合专家（MoE）架构。EVA能够捕捉从全局结构到精细功能元件的进化一致性表征，支持从突变适应性预测到多种RNA（如tRNA、mRNA、环状RNA等）的从头设计。实验证明，EVA在多个基准测试中达到SOTA水平，为RNA生物工程提供了强大的统一设计框架。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-17-712398-v2/fig-001.webp\", \"caption\": \"Figure 2: Zero-shot fitness prediction across RNA, DNA, and protein. (a) Conceptual overview of using EVA’s zero-shot sequence likelihood to approximate fitness landscapes and mutation effects for RNA, gene regions, and proteins. (b)(c) Benchmark results for zero-shot fitness prediction on ncRNA (b) and mRNA (c) sequences, evaluating the correlation between EVA likelihood scores and experimentally measured fitness across a diverse collection of deep mutational scanning (DMS) assays. Performance is reported as Spearman’s rank correlation (ρ); points indicate individual assays. (d)(e) Benchmark results on eukaryotic (d) and prokaryotic (e) gene essentiality prediction by inserting premature stop codons near the 5′ end of coding sequences and quantifying the EVA log-likelihood drop to infer essentiality. (f) Benchmark results for zero-shot fitness prediction on protein, evaluating the correlation between likelihood scores and experimentally measured fitness. Nucleotide-input EVA predictions are compared against protein language model baselines.\", \"page\": 6, \"index\": 1, \"width\": 944, \"height\": 998}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-17-712398-v2/fig-002.webp\", \"caption\": \"Figure 5: mRNA and circRNA vaccine design with EVA. (a) Conceptual overview of mRNA codon optimization with EVA. (b) Benchmark on five mRNA vaccine systems (SARS-CoV-2 Spike, Influenza PR8 HA, VZV gE, RABV-G, HIV) comparing CDS optimization in terms of MFE and CAI against Evo2-1B, CodonFM-1B, and a Random (MFE-only) baseline, all conditioned on the mRNA type and Homo sapiens. (c) Conceptual overview of circRNA vaccine design with EVA: ORF codon optimization via species-conditioned autoregressive generation (left), and de novo IRES redesign via EVA GLM where the IRES region is masked and regenerated conditioned on flanking sequences (right). (d) Benchmark on four circRNA vaccine systems (SARS: Group-I, SARS: T4 ligase, rabies, CAR-T) for ORF codon optimization, same baselines and species conditioning as (b). (e)(f) Biophysical properties of EVA-redesigned IRES sequences versus the original CVB3 IRES for SARS and rabies circRNA vaccines, including ribosome accessibility and inhibitory long-range interactions.\", \"page\": 11, \"index\": 2, \"width\": 958, \"height\": 939}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-17-712398-v2/fig-003.webp\", \"caption\": \"Figure 1: Overview of EVA data, model, and training. (a) Overview of the EVA model capabilities, and representative applications. (b) OpenRNA v1 comprises 114M curated full-length RNA sequences spanning all domains of life; Phylogenetic tree construction of training data. (c) Comparison of training data scale with prior work (left), and sequence-length distributions together with the number of full-length RNAs covered by different context windows (right). (d) RNA type distribution in OpenRNA v1. (e) EVA model architecture and key differences from prior RNA language models: Mixture-of-Experts (MoE) architecture, support for both CLM and GLM generation, and conditioning on RNA type and taxonomic labels. (f) Illustration of the unstructured global distribution learned by conventional RNA LMs versus the controllable fine-grained latent space learned by EVA. (g) Comparison of context window lengths between EVA (8,192 nt) and prior RNA language models (1,024 nt), highlighting broader RNA design coverage enabled by long context. (h) Long-context “needle-in-a-haystack” evaluation demonstrating EVA’s ability to recall long-range dependencies under an 8,192-token context window. (i) Scaling behavior showing decreasing perplexity with increasing model size, indicating that larger models better capture RNA sequence grammar.\", \"page\": 3, \"index\": 3, \"width\": 976, \"height\": 850}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-17-712398-v2/fig-004.webp\", \"caption\": \"Figure 6: Interpretability analysis revealing hierarchical RNA features learned by EVA. (a) Schematic illustrating how model neurons are mapped to biological concepts using sparse autoencoders, revealing that EVA can learn structure- and function-related biological knowledge from sequence alone. (b) Activations of features associated with IRES, ORF, and related functional elements in circRNA vaccines (left: RABV-G; right: SARS-CoV-2). (c) Activations of features associated with 5′UTR, CDS, and 3′UTR in mRNA vaccines (HIV, PR8 HA, RABV-G, and VZV gE).\", \"page\": 13, \"index\": 4, \"width\": 959, \"height\": 462}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-17-712398-v2/fig-005.webp\", \"caption\": \"Figure 3: Controllable RNA generation with EVA across diverse RNA families and species. (a) Sequence similarity between generated sequences and their closest natural neighbours for unconditional CLM, and reconstruction similarity for GLM; CLM produces both high-similarity and more divergent sequences, whereas GLM achieves higher reconstruction via richer flanking context. (b) GLM infilling similarity between generated and masked fragments across 11 RNA classes. (c) Schematic of conditional generation controlled by RNA-type tags. (d) KL divergence comparison between EVA and GenerRNA across 11 RNA classes, evaluated over three secondary-structure feature groups (GC content & MFE, loop & helix composition, and base-pairing & stem statistics); EVA achieves >13-fold lower KL divergence. (e) Distributional comparisons of RNA-type conditioned samples vs. natural RNAs across UMAP embedding, length, MFE, GC content, and secondarystructure features. (f) Schematic of conditional generation controlled by taxonomic (species) tags. (g) KL divergence comparison between EVA and GenerRNA across six representative mRNA species; EVA achieves >30-fold lower KL divergence, reflecting accurate modeling of organism-specific RNA landscapes. (h) Distributional comparisons of species-conditioned mRNAs vs. natural sequences across sequence, biophysical, and structural metrics; extended results in Figure S7.\", \"page\": 8, \"index\": 5, \"width\": 964, \"height\": 908}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-17-712398-v2/fig-006.webp\", \"caption\": \"Figure 4: De novo design of tRNAs, RNA aptamers, and CRISPR gRNAs. (a) Zero-shot de novo generation of tRNAs showing high structural similarity to natural tRNAs, quantified by TM-score, while maintaining sequence novelty relative to known tRNAs. (b) Representative structural alignments between AlphaFold3-predicted structures of generated tRNAs and experimentally resolved natural tRNAs, illustrating preservation of the canonical L-shaped fold despite low sequence identity. (c) Prediction of fluorescence intensity for RNA aptamers after low-data fine-tuning (n = 30). Left: binding to HBC530; right: binding to HBC620. Model log-likelihood scores are compared against experimentally measured fluorescence. (d) Structural comparison between de novo generated aptamers (blue) and wildtype structures, showing preservation of the ligand-binding pocket and overall fold despite sequence mutations, consistent with learned mutational-structural relationships. (e,f) Prediction of editing efficiency for IscB omegaRNAs after fine-tuning on m16 (n = 42) and m17 (n = 44) sequence sets, respectively. (g) AlphaFold3-predicted complex structure of IscB protein, de novo designed m16 omegaRNA, and target DNA. Success is defined by satisfying a set of domain-level structural criteria relative to wildtype (see Methods). (h,i) Violin plots showing sequence similarity distributions between de novo generated omegaRNAs and the corresponding wildtype sequences for m17 (h) and m16 (i). Generated sequences span a biologically reasonable range of divergence while remaining structurally plausible.\", \"page\": 9, \"index\": 6, \"width\": 949, \"height\": 823}]"
motivation: 现有RNA生成模型受限于短上下文窗口且缺乏鲁棒的可控设计能力，难以有效模拟全长转录本的复杂进化流形。
method: 开发了名为EVA的长上下文生成式基础模型，利用混合专家架构在超过1.14亿条全长RNA序列上进行预训练。
result: EVA在九个基准测试中的七个实现了最先进性能，将结构建模精度提升了高达一个数量级，并成功应用于多种RNA类别的从头设计。
conclusion: EVA建立了一个统一且开源的RNA设计框架，能够高效处理从基础序列分析到复杂治疗性RNA开发的广泛任务。
---

## 摘要
具有特定功能 RNA 序列的可编程设计仍然是生物学中的一个核心挑战。尽管最近取得了进展，但现有的 RNA 生成模型缺乏鲁棒的可控设计能力，并受限于较短的上下文窗口，限制了它们对全长转录本复杂进化流形进行建模的能力。在此，我们介绍了 EVA（Evolutionary Versatile Architect），这是一个长上下文生成式 RNA 基础模型，在涵盖整个进化多样性的超过 1.14 亿条全长 RNA 序列上进行了训练。通过将混合专家（Mixture-of-Experts）架构与 8,192 个 token 的上下文窗口相结合，EVA 学习了 RNA 序列空间的一种统一且进化一致的表示，捕捉了全局转录本结构和细粒度的功能元件。EVA 在单一架构内为广泛的 RNA 设计任务建立了一个统一框架，涵盖从突变适应性预测到上下文感知序列工程的各种任务。我们通过对多种 RNA 类别（包括 tRNA、适配体和 CRISPR 引导 RNA，以及 mRNA 和环状 RNA 疗法）的从头设计和靶向优化，展示了 EVA 的多功能性。在系统评估中，EVA 在九个既定基准测试中的七个上实现了最先进的性能，与现有方法相比，结构建模精度提高了一个数量级。EVA 已在以下仓库完全开源：https://github.com/GENTEL-lab/EVA。

## Abstract
Programmable design of RNA sequences with defined functions remains a central challenge in biology. Despite recent advances, existing RNA generative models lack robust controllable design capabilities and are constrained by short context windows, limiting their capacity to model the complex evolutionary manifold of full-length transcripts. Here, we introduce EVA (Evolutionary Versatile Architect), a long-context generative RNA foundation model trained on over 114 million full-length RNA sequences spanning the full breadth of evolutionary diversity. By integrating a Mixture-of-Experts architecture with an 8,192-token context window, EVA learns a unified, evolution-consistent representation of RNA sequence space that captures both global transcript structure and fine-grained functional elements. EVA establishes a unified framework for a broad spectrum of RNA design tasks within a single architecture, ranging from mutational fitness prediction to context-aware sequence engineering. We demonstrate EVAs versatility through the de novo design and targeted optimization of diverse RNA classes, including tRNAs, aptamers, and CRISPR guide RNAs, as well as mRNA and circular RNA therapeutics. In systematic evaluations, EVA achieves state-of-the-art performance across seven of nine established benchmarks, improving structural modeling accuracy by up to an order of magnitude compared to existing approaches. EVA is fully open-source at the following repository: https://github.com/GENTEL-lab/EVA.

---

## 论文详细总结（自动生成）

### 论文总结：EVA (Evolutionary Versatile Architect) —— 长上下文生成式 RNA 基础模型

#### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：现有的 RNA 生成模型存在两大瓶颈：一是**上下文窗口过短**（通常仅 1024 nt），无法捕捉全长转录本的全局结构和长程相互作用；二是**缺乏鲁棒的可控设计能力**，难以针对特定物种或特定 RNA 类别进行精准生成。
*   **研究背景**：RNA 在生命活动中扮演多重角色（编码、催化、调节），其功能高度依赖于复杂的二级和三级结构。随着合成生物学和 RNA 疗法（如 mRNA 疫苗、环状 RNA）的兴起，迫切需要一个能够理解全长序列进化规律并支持多任务设计的统一基础模型。

#### 2. 核心方法论
*   **大规模数据集 (OpenRNA v1)**：构建了包含 1.14 亿条全长 RNA 序列的数据库，涵盖了生命的所有领域，确保了模型能学习到广泛的进化多样性。
*   **混合专家架构 (MoE)**：采用 MoE 架构以实现参数规模的高效扩展，在保持计算效率的同时增强模型处理复杂生物信息的能力。
*   **长上下文窗口**：支持 **8,192 个 token** 的上下文长度，比之前的主流模型提升了 8 倍，能够覆盖绝大多数天然 RNA 的全长序列。
*   **双重生成模式**：
    *   **CLM (因果语言模型)**：用于自回归生成，支持从头设计。
    *   **GLM (通用语言模型)**：支持掩码填充（Infilling），用于局部序列优化和编辑。
*   **可控生成机制**：通过引入 **RNA 类型标签**（如 tRNA, mRNA, circRNA）和 **分类学标签**（物种信息）作为条件，实现定向设计。

#### 3. 实验设计
*   **数据集与场景**：
    *   **零样本适应性预测**：在 ncRNA、mRNA 和蛋白质的深度突变扫描 (DMS) 实验数据上评估。
    *   **可控生成评估**：针对 11 种 RNA 类别和 6 个代表性物种进行生成，评估其与天然序列的分布一致性。
    *   **从头设计任务**：包括 tRNA、RNA 适配体（Aptamers）和 CRISPR 引导 RNA（omegaRNA）。
    *   **治疗性应用**：针对 SARS-CoV-2、流感等疫苗的 mRNA 密码子优化及环状 RNA (circRNA) 的 IRES 序列重设计。
*   **Benchmark 与对比方法**：
    *   对比了 **Evo2-1B**、**CodonFM-1B**、**GenerRNA** 等当前最先进的 RNA 或多模态基础模型。
    *   使用了 9 个既定基准测试，涵盖结构建模、生物物理属性预测等。

#### 4. 资源与算力
*   **算力说明**：论文摘要和正文简述中**未明确说明**具体的 GPU 型号、数量及总训练时长。但考虑到其处理 1.14 亿条序列及 MoE 架构的规模，推测其消耗了极大规模的计算资源（通常为数百至数千个 GPU 小时/天级别）。
*   **开源贡献**：作者强调了模型的开源性，提供了 GitHub 仓库以供社区使用。

#### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了从基础的序列似然估计到复杂的生物工程设计，共进行了 9 项基准测试，并在 7 项中达到 SOTA。
*   **充分性与客观性**：
    *   实验设计较为全面，不仅有计算指标（如 KL 散度、困惑度），还结合了结构预测（AlphaFold3）和实验测量数据（DMS 荧光强度等）进行验证。
    *   通过“大海捞针”（Needle-in-a-haystack）实验验证了长上下文的有效性，证明了模型确实能处理长程依赖。

#### 6. 主要结论与发现
*   **性能领先**：EVA 在结构建模精度上比现有方法提升了高达一个数量级。
*   **进化一致性**：模型学习到的潜在空间能够反映生物学功能，通过稀疏自编码器（SAE）分析发现，模型内部神经元能自动对应到 IRES、ORF 等功能元件。
*   **多功能性**：EVA 是一个“全能选手”，既能预测突变影响，也能从头设计具有天然折叠结构的 tRNA，还能优化疫苗序列的稳定性和翻译效率。

#### 7. 优点
*   **长上下文优势**：解决了 RNA 领域长期存在的“短视”问题，使全长转录本建模成为可能。
*   **可控性强**：通过物种和类型标签，极大地降低了生成序列的盲目性，提高了工程化设计的成功率。
*   **统一框架**：将多种零样本预测任务和生成任务整合在单一架构下，展示了基础模型的强大泛化力。

#### 8. 不足与局限
*   **实验验证局限**：虽然使用了大量公开实验数据进行验证，但对于从头设计的序列（如新型 IRES 或 omegaRNA），论文中更多依赖于计算模拟（如 AlphaFold3 预测），缺乏大规模的湿实验（In vitro/In vivo）闭环验证。
*   **计算开销**：MoE 架构虽然推理高效，但训练和部署长上下文模型对显存和算力仍有较高要求，限制了普通实验室的微调能力。
*   **数据偏差风险**：尽管数据集巨大，但天然序列的分布可能存在采样偏差，模型在设计完全超越自然进化流形的“超天然”功能 RNA 时可能仍受限。

（完）
