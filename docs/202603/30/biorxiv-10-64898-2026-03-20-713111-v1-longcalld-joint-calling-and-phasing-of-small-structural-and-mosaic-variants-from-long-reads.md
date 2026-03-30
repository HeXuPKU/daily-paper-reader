---
title: "LongcallD: joint calling and phasing of small, structural and mosaic variants from long reads"
title_zh: LongcallD：基于长读段的小变异、结构变异和嵌合变异联合检测与定相
authors: "Gao, Y., Liao, W.-W., Qin, Q., Hall, I. M., Li, H."
date: 2026-03-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.20.713111v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 基因组变异的联合调用与定相
tldr: LongcallD是一个针对长读长测序数据的统一分析框架，旨在解决现有工具将小变异、结构变异（SV）和分型（phasing）割裂处理的问题。该工具利用局部多序列比对技术，实现了小变异与SV的同步检测与分型。通过整合生殖系分型和逆转录转座特征，它能高效识别低比例嵌合变异及单读长支持的移动元件插入。该方法在提升SV和嵌合变异检测准确性的同时，保持了极高的小变异检测性能，为复杂遗传结构研究提供了强力支持。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-20-713111-v1/fig-001.webp\", \"caption\": \"Fig. 3 | Accuracy of SV calling. a, FDR and FNR of SVs on HiFi and T2T data. Metrics were 213 calculated using truvari in “refine” mode, with SVs stratified by genomic context (tandem repeats 214 vs. other regions). Dipcall, PAV, cuteSV-asm, and SVIM-asm were applied to long-read assembly 215 alignments, T2T-dipcall and T2T-PAV were applied to T2T assembly alignments. All other callers 216 were applied to long-read alignments. b, FDR and FNR of SVs on ONT data. 217\", \"page\": 11, \"index\": 1, \"width\": 1024, \"height\": 479}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-20-713111-v1/fig-002.webp\", \"caption\": \"Fig. 5 | Haplotype-aware alignment refinement by longcallD. Top, tandem repeat annotation 276 and reference genome sequence. Middle, HG002 raw HiFi long-read alignments displaying 277 fragmented, inconsistent insertions and clippings. Bottom, haplotype-phased and refined 278 alignments produced by longcallD. In this example, longcallD identified three large insertions on 279 both haplotypes, together with other small variants. 280\", \"page\": 15, \"index\": 2, \"width\": 968, \"height\": 548}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-20-713111-v1/fig-003.webp\", \"caption\": \"Fig. 4 | SV- and region-wise genotype and basepair F1 scores. a, SV-wise F1 scores in whole 266 confident and tandem repeat regions on HiFi and T2T data, measured by aardvark. Dipcall, PAV, 267 cuteSV-asm, and SVIM-asm were applied to long-read assembly alignments, T2T-dipcall and 268 T2T-PAV were applied to T2T assembly alignments, all other callers were applied to long-read 269 alignments. b, SV-wise F1 scores on ONT data. c, Region-wise F1 score distribution in tandem 270 repeats on HiFi and T2T data, merged calls are shown for SV-only callers. Curves represent the 271 fraction of tandem repeat regions (y-axis) achieving an F1 score above a given threshold (x-axis). 272 d, Region-wise F1 score distribution in tandem repeats on ONT data. 273\", \"page\": 14, \"index\": 3, \"width\": 967, \"height\": 579}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-20-713111-v1/fig-004.webp\", \"caption\": \"Fig. 6 | Low-VAF mosaic SNV and MEI calling. a, Precision and recall of mosaic SNV calls 354 on COLO829BLT50 in easy regions using HiFi and ONT data. Clair-Mosaic did not report any 355 mosaic SNVs on ONT dataset. b, Alternative allele depth of TP mosaic SNV calls on 356 COLO829BLT50 using HiFi data. LongcallD, detected exclusively by longcallD; DeepSomatic, 357 detected exclusively by DeepSomatic; LC&DS, detected by both longcallD and DeepSomatic 358 but not by Clair-Mosaic; Clair-Mosaic, detected exclusively by Clair-Mosaic; LC&DS&CM, 359 detected by all three callers. Wilcoxon rank-sum tests were used to compare the alternative allele 360\", \"page\": 19, \"index\": 4, \"width\": 1168, \"height\": 1013}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-20-713111-v1/fig-005.webp\", \"caption\": \"Fig. 2 | Characterization of noisy regions and small-variant calling accuracy. a, Fractions of 184 haplotype-aware and haplotype-agnostic noisy regions identified by longcallD on HG002. b, 185 Length distribution of noisy regions identified by longcallD on HG002. c, False positives per 186 million bases (FPPM) and false-negative rates (FNR) for SNPs on HG002 HiFi data and 187 corresponding T2T assemblies, evaluated using hap.py. Variants are stratified into all regions, 188 homopolymer regions, and non-homopolymer regions. LongcallD, DeepVariant, and Clair3 were 189 applied to long-read alignments, dipcall and PAV were applied to alignments of long-read 190 assemblies, T2T-dipcall and T2T-PAV were applied to alignments of T2T assemblies. d, FPPM 191 and FNR for indels on HG002 HiFi data. e, FPPM and FNR for SNPs on HG002 ONT data. f, 192 FPPM and FNR for indels on HG002 ONT data. 193\", \"page\": 9, \"index\": 5, \"width\": 768, \"height\": 686}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-20-713111-v1/fig-006.webp\", \"caption\": \"Fig. 1 | Illustration of the longcallD variant calling workflow. a, Classification of candidate 98 regions into clean and noisy categories. b, Local haplotagging of long reads using heterozygous 99\", \"page\": 5, \"index\": 6, \"width\": 987, \"height\": 516}]"
motivation: 现有长读长分析工具通常将小变异检测、结构变异识别和分型视为独立任务，未能充分利用长读长数据的关联信息。
method: 提出LongcallD框架，采用局部多序列比对（MSA）技术，并结合生殖系分型与逆转录转座特征来同步处理多种变异。
result: 实验表明，该方法显著提升了结构变异和嵌合变异的检测精度，且在小变异检测方面表现出极强的竞争力。
conclusion: LongcallD为临床和进化应用中解析复杂遗传架构提供了一个稳健且高效的统一分析基础。
---

## 摘要
长读段测序是一种强大的技术，能够在单个连续读段中捕捉多个变异。这种长度使得单个读段能够跨越小变异和结构变异，同时携带关键的定相信息。然而，目前的计算工具在很大程度上将小变异检测、结构变异（SV）检测和定相视为相互独立的问题，未能充分发挥长读段的潜力。在这里，我们提出了 longcallD，这是一个利用局部多序列比对同时检测和定相小变异及结构变异的统一框架。通过整合生殖系定相和逆转录转座特征，longcallD 还能识别低比例的嵌合变异，并检测由单个读段支持的可移动元件插入。与现有方法相比，我们的统一方法在保持具有竞争力的小变异检测性能的同时，显著提高了 SV 发现和嵌合变异的准确性。我们预见 longcallD 将为临床和进化应用中解析复杂的遗传结构提供坚实的基础。

## Abstract
Long-read sequencing is a powerful technique capturing multiple variants within single continuous reads. This length allows individual reads to bridge small and structural variants while carrying crucial phasing information. However, current computational tools treat small variant calling, structural variant (SV) detection and phasing as largely disconnected problems, failing to unleash the full potential of long reads. Here, we present longcallD, a unified framework utilizing local multiple-sequence alignment to simultaneously call and phase small and structural variants. By integrating germline phasing and retrotransposition hallmarks, longcallD also identifies low-fraction mosaic variants and detects mobile element insertions supported by a single read. Compared to existing methods, our unified approach substantially improves SV discovery and mosaic variants accuracy while maintaining competitive small variant calling. We anticipate that longcallD will provide a robust foundation for resolving complex genetic architectures in clinical and evolutionary applications.

---

## 论文详细总结（自动生成）

### LongcallD：基于长读段的小变异、结构变异和嵌合变异联合检测与定相

#### 1. 核心问题与研究动机
*   **核心问题**：现有的长读段（Long-read）分析工具通常将小变异（SNPs/Indels）检测、结构变异（SV）识别和单倍型定相（Phasing）视为三个独立的计算问题。
*   **研究动机**：
    *   **信息浪费**：单个长读段实际上可以跨越多个变异位点并天然携带定相信息，但现有工具未能充分利用这种关联性。
    *   **对齐干扰**：在低复杂度区域（LCR）或SV周围，不一致的读段比对会导致小变异检测出现大量假阳性或漏检。
    *   **嵌合变异挑战**：低等位基因分值（VAF）的嵌合变异（Mosaic variants）极难与测序错误区分。
*   **整体含义**：LongcallD 旨在建立一个统一的框架，通过局部多序列比对（MSA）和迭代定相，同步解决上述问题，提升变异检测的全面性和准确性。

#### 2. 方法论
*   **核心思想**：将基因组划分为“清洁区域”和“噪声区域”，对不同区域采用差异化策略，并利用定相信息相互校准。
*   **关键技术细节**：
    *   **区域分类**：
        *   **清洁区域**：比对准确度高，直接通过等位基因计数调用高置信度生殖系变异。
        *   **噪声区域**：包括同聚物、短串联重复（STR）、变数串联重复（VNTR）及SV边界。
    *   **局部单倍型感知 MSA**：
        *   利用清洁区域的杂合变异对读段进行局部定相（Haplotagging）。
        *   对噪声区域提取特定单倍型的子序列，使用 **abPOA** 算法生成单倍型解析的共识序列（Consensus）。
        *   使用 **WFA** 算法将共识序列比对回参考基因组以调用变异。
    *   **迭代定相流程**：构建读段-变异兼容性矩阵，通过多数投票法在变异单倍型分配和读段单倍型分配之间交替迭代，直至收敛。
    *   **低 VAF 嵌合变异检测**：
        *   利用已建立的单倍型背景，要求支持嵌合变异的读段必须来自同一单倍型。
        *   针对移动元件插入（MEI），整合了目标位点重复（TSD）和 poly(A) 尾部等序列特征过滤。

#### 3. 实验设计
*   **数据集**：
    *   **HG002 标准品**：使用 GIAB T2T Q100 v1.1 真实集作为 Benchmark。
    *   **肿瘤-正常混合样本**：COLO829（1:49 比例）和 H2009（1:10 比例），模拟低频嵌合/体细胞变异。
*   **测序技术**：PacBio HiFi (63x) 和 Oxford Nanopore (ONT) R10.4.1 (50x)。
*   **对比方法**：
    *   **小变异**：Clair3, DeepVariant。
    *   **结构变异**：Sniffles2, cuteSV, pbsv, SVDSS, sawfish 等 8 种工具。
    *   **组装法**：dipcall, PAV（基于 hifiasm 组装结果）。
*   **评估工具**：hap.py（小变异）、Truvari（SV）、aardvark（基于单倍型序列的综合评估）。

#### 4. 资源与算力
*   **计算效率**：在标准服务器上使用 16 个线程处理 40x HiFi 比对文件（BAM），LongcallD 仅需 **19 分钟**，峰值内存小于 **20GB**。
*   **对比**：相比之下，由 DeepVariant + HiPhase + Sniffles2 组成的常规流程需要 218 分钟和 40GB 内存；基于组装的方法（如 hifiasm）则需要数倍的时间和内存资源。

#### 5. 实验数量与充分性
*   **实验规模**：涵盖了生殖系变异（SNP/Indel/SV）、低频嵌合变异、移动元件插入等多个维度。
*   **充分性**：实验设计非常充分。不仅对比了主流的基于比对（Alignment-based）的工具，还挑战了准确度更高的基于组装（Assembly-based）的方法。
*   **客观性**：使用了最新的 T2T-HG002 评估集，该集合包含了大量极具挑战性的重复序列区域，能够客观反映工具在复杂区域的真实性能。

#### 6. 主要结论
*   **SV 检测领先**：在串联重复序列区域，LongcallD 的 SV 检测准确率（F1 score）显著优于所有其他基于比对的工具。
*   **小变异性能稳健**：在保持极高 SV 准确度的同时，其小变异检测性能与 DeepVariant 等深度学习工具相当。
*   **嵌合变异突破**：通过单倍型一致性校验，LongcallD 能够准确识别仅由 1-2 条读段支持的低频变异，显著降低了假阳性。
*   **单倍型重建**：在重复序列区域，LongcallD 生成的单倍型序列与真实序列的一致性极高，接近组装法的水平。

#### 7. 优点与亮点
*   **统一框架**：打破了变异类型之间的壁垒，实现了小变异、大变异与定相的互促。
*   **高效性**：无需进行耗时的全基因组从头组装，直接在比对层面上实现了接近组装法的精度。
*   **重复序列处理**：通过局部 MSA 有效解决了长读段在 VNTR 等区域比对不一致导致的检测难题。
*   **MEI 识别**：专门针对逆转录转座子特征建模，提升了移动元件检测的灵敏度。

#### 8. 不足与局限
*   **同聚物 Indel 限制**：在 ONT 数据上，对于同聚物区域的 Indel 检测准确性仍略逊于经过深度学习专门优化的工具（如 DeepVariant）。
*   **变异类型覆盖**：目前尚未支持倒位（Inversion）和易位（Translocation）等更复杂的结构变异。
*   **嵌合小变异**：由于长读段自身的随机错误模式，目前尚未报告嵌合的小片段 Indel，以避免过高的假阳性。

（完）
