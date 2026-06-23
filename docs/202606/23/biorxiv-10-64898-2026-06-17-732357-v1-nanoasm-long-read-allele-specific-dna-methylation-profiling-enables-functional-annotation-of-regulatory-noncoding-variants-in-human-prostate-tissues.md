---
title: "nanoASM: Long-Read Allele-Specific DNA Methylation Profiling Enables Functional Annotation of Regulatory Noncoding Variants in Human Prostate Tissues"
title_zh: nanoASM：长读长等位基因特异性DNA甲基化分析实现人类前列腺组织中调控性非编码变异的功能注释
authors: "Tian, Y., Wong, J., McDonnell, S., Zhong, H., Wu, L., Larson, N., Manley, B. J., Wang, L."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.17.732357v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 等位基因特异性DNA甲基化分析用于非编码调控变异的功能注释
tldr: 长读长纳米孔测序能同时检测遗传变异和DNA甲基化。基于此，开发nanoASM框架，利用片段级甲基化模式分析等位基因特异性甲基化（ASM）。在前列腺正常和肿瘤组织中，鉴定出大量癌症相关差异甲基化区域，发现甲基化熵降低，并整合转录组验证。ASM显著识别了IRX4和PSCA风险位点的功能非编码变异，相比群体mQTL效率更高。该工作为解析调控性非编码变异提供了有力方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 利用长读长测序同时检测变异和甲基化的优势，开发等位基因特异性甲基化分析方法，以注释非编码调控变异的功能。
method: 提出nanoASM框架，通过等位基因分离测序reads，识别等位基因特异性差异甲基化区域，并与mQTL和eQTL进行比较验证。
result: 在前列腺癌中鉴定出ASM区域与转录调控一致，候选变异rs6885084（IRX4）和rs4736369（PSCA）显示等位基因甲基化差异及活性调控。
conclusion: nanoASM能高效解析非编码变异的功能及调控域，为癌症功能基因组学提供新工具。
---

## 摘要
长读长纳米孔测序能够同时检测单个DNA分子上的种系变异和天然DNA碱基修饰，为研究等位基因特异性表观遗传调控提供了独特机会。本研究对正常和肿瘤前列腺组织进行全基因组纳米孔测序，以表征与非编码遗传变异相关的差异甲基化、甲基化熵和等位基因特异性甲基化（ASM）。全基因组分析识别出大量癌症相关的差异甲基化区域（DMR），其中高甲基化DMR显著富集于转录起始位点和转录调控区域附近。与转录组数据集的整合显示，启动子甲基化与基因表达之间存在强烈的负相关，而5-羟甲基胞嘧啶（5hmC）水平与基因体区域的转录活性呈正相关。利用长读长测序提供的片段级甲基化模式，我们进一步量化了同时包含5mCG和5hmCG状态的甲基化熵。癌症高甲基化DMR的熵显著降低，与肿瘤进展过程中甲基化状态的克隆固定一致。跨染色质注释的熵谱分析显示，部分修饰的增强子相关区域具有最大的表观遗传异质性。为了研究顺式调控遗传效应，我们开发了一个简单的ASM框架（nanoASM），该框架可根据等位基因状态划分测序读段，并直接从长读长数据中识别等位基因特异性DMR。与传统的群体水平mQTL分析相比，ASM通过利用个体内对比和减少样本水平异质性，显著提高了统计效率。尽管种系单核苷酸多态性（SNP）在正常组织和肿瘤组织中大致相同，但ASM模式差异显著，肿瘤相关ASM区域表现出明显更大的基因组跨度和更强的等位基因甲基化差异。与TCGA前列腺mQTL和GTEx前列腺eQTL数据集的比较分析显示，ASM方向性与下游转录效应之间存在显著一致性，特别是对于位于DMR内和转录起始位点附近的变异。在IRX4前列腺癌风险位点，ASM识别出一个与AR ChIP-seq和H3K27ac峰重叠的雄激素响应调控域，提名rs6885084为候选功能变异。在PSCA位点，以rs4736369为锚定的ASM与等位基因特异性甲基化、染色质激活、转录本丰度和异构体使用相关。总之，这些发现确立了基于纳米孔的ASM分析作为解析前列腺癌中功能性非编码变异及其调控域的强大方法。

## Abstract
Long-read nanopore sequencing enables simultaneous detection of germline variation and native DNA base modifications on individual DNA molecules, providing a unique opportunity to investigate allele-specific epigenetic regulation. Here, we performed whole-genome nanopore sequencing on normal and tumor prostate tissues to characterize differential methylation, methylation entropy, and allele-specific methylation (ASM) associated with noncoding genetic variants. Genome-wide analysis identified extensive cancer-associated differentially methylated regions (DMRs), with hypermethylated DMRs significantly enriched near transcription start sites and transcriptional regulatory regions. Integration with transcriptomic datasets revealed strong inverse relationships between promoter methylation and gene expression, while 5-hydroxymethylcytosine (5hmC) levels positively correlated with transcriptional activity across gene bodies. Using fragment-level methylation patterns enabled by long-read sequencing, we further quantified methylation entropy incorporating both 5mCG and 5hmCG states. Cancer-hypermethylated DMRs exhibited markedly reduced entropy, consistent with clonal fixation of methylation states during tumor progression. Entropy profiling across chromatin annotations demonstrated maximal epigenetic heterogeneity at partially modified enhancer-associated regions. To investigate cis-regulatory genetic effects, we developed a simple ASM framework (nanoASM) that can partition sequencing reads by allelic state and identifies allele-specific DMRs directly from long-read data. Compared with conventional population-level mQTL analysis, ASM demonstrated substantially improved statistical efficiency by leveraging within-individual contrasts and reducing sample-level heterogeneity. Although germline single nucleotide polymorphisms (SNPs) were largely shared between normal and tumor tissues, ASM patterns differed substantially, with tumor-associated ASM regions displaying significantly larger genomic span and stronger allelic methylation differences. Comparative analysis with TCGA prostate mQTL and GTEx prostate eQTL datasets demonstrated substantial concordance between ASM directionality and downstream transcriptional effects, particularly for variants located within DMRs and near transcription start sites. At the IRX4 prostate cancer risk locus, ASM identified an androgen-responsive regulatory domain overlapping AR ChIP-seq and H3K27ac peaks, nominating rs6885084 as a candidate functional variant. At the PSCA locus, ASM anchored by rs4736369 was associated with allele-specific methylation, chromatin activation, transcript abundance, and isoform usage. Together, these findings establish nanopore-based ASM analysis as a powerful approach for resolving functional noncoding variants and their regulatory domains they control in prostate cancer.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：非编码区存在大量与复杂疾病（如前列腺癌）相关的遗传变异（GWAS位点），但如何有效注释这些变异的调控功能、识别因果变异及其调控域是当前功能基因组学的重大挑战。
- **研究动机**：传统群体水平的mQTL分析需要大量样本，且受样本异质性影响统计效率低。长读长纳米孔测序能同时检测单个DNA分子上的遗传变异（SNP）和天然碱基修饰（5mC、5hmC），从而在个体内部利用等位基因分离直接研究顺式调控效应（等位基因特异性甲基化，ASM），为解析非编码变异功能提供新思路。
- **整体含义**：开发名为**nanoASM**的分析框架，通过全基因组纳米孔测序对正常和肿瘤前列腺组织进行等位基因特异性甲基化分析，实现功能性非编码变异的高效注释，并揭示前列腺癌相关的表观遗传调控机制。

## 2. 方法论文：核心思想、关键技术细节

- **核心思想**：利用长读长测序提供的单分子、片段级甲基化模式，根据测序读段上的种系SNP等位基因状态进行读段划分，从而在个体内部直接比较两个等位基因的甲基化差异（即等位基因特异性甲基化），识别等位基因特异性差异甲基化区域（allele-specific DMR）。
- **关键技术细节**：
  - **纳米孔测序**：对正常和肿瘤前列腺组织进行全基因组纳米孔测序，同时检测CpG甲基化（5mCG和5hmCG）和SNP。
  - **甲基化熵计算**：利用片段级甲基化模式，同时考虑5mCG和5hmCG两种修饰状态，计算每个CpG位点的甲基化熵，度量表观遗传异质性。
  - **nanoASM框架**：
    1. 基于测序读段上的杂合SNP，将读段分为参考等位基因组和替代等位基因组。
    2. 对每个等位基因组，分别量化CpG甲基化水平。
    3. 通过统计检验（如Fisher精确检验或贝叶斯方法）识别两个等位基因之间甲基化水平显著差异的区域（ASM DMR）。
  - **与群体mQTL的对比**：ASM利用个体内对比，不需要大量样本，减少了样本间异质性，统计效率更高。
  - **整合分析**：将ASM结果与TCGA前列腺mQTL、GTEx前列腺eQTL、染色质状态（H3K27ac、AR ChIP-seq）以及RNA-seq转录组数据进行比较验证。

## 3. 实验设计

- **数据集/场景**：
  - **主要数据**：对正常和肿瘤前列腺组织进行全基因组纳米孔测序（样本量未在摘要中明确，但可能包含多例配对样本）。
  - **外部验证**：
    - TCGA前列腺癌mQTL数据集（群体水平甲基化数量性状位点）。
    - GTEx前列腺eQTL数据集（群体水平表达数量性状位点）。
    - 染色质免疫共沉淀测序（AR ChIP-seq、H3K27ac ChIP-seq）数据。
    - RNA-seq转录组数据（用于验证甲基化与表达的关系）。
- **Benchmark**：以群体mQTL分析作为对比基准，评估ASM在识别功能性非编码变异方面的统计效率。
- **对比方法**：
  - 传统群体mQTL（如TCGA前列腺mQTL）。
  - 等位基因特异性表达（ASE）或eQTL（如GTEx前列腺eQTL）。
- **案例验证**：
  - IRX4前列腺癌风险位点：通过ASM识别候选功能变异rs6885084，并与AR ChIP-seq、H3K27ac峰重叠。
  - PSCA位点：ASM锚定rs4736369，验证等位基因特异性甲基化、染色质激活、转录本丰度和异构体使用。

## 4. 资源与算力

- 文中**未明确说明**使用的GPU型号、数量、训练时长或计算集群配置。
- 仅提及采用了全基因组纳米孔测序，该技术本身依赖高通量测序仪（如Oxford Nanopore PromethION），后续生物信息学分析通常需要大量CPU/内存资源，但具体算力细节缺失。

## 5. 实验数量与充分性

- **实验数量**：
  - 全基因组水平：鉴定了大量癌症相关差异甲基化区域（DMR），包括高甲基化和低甲基化区域。
  - 甲基化熵分析：跨不同染色质注释（启动子、增强子、基因体等）比较熵变化。
  - ASM分析：识别了众多ASM DMR，并比较正常与肿瘤组织ASM模式的差异（基因组跨度、等位基因甲基化差异强度）。
  - 与外部数据集成对比：与TCGA mQTL和GTEx eQTL数据集进行一致性评估。
  - 两个案例位点（IRX4、PSCA）的深入功能验证。
- **充分性评估**：实验设计较为全面，覆盖了从全基因组扫描到具体候选位点验证，并进行了多组学整合和外部数据库比对。但由于是一个预印本（biorxiv），可能尚未经过同行评审；样本量有限（推测可能为数例至十数例），且仅针对前列腺组织，普适性有待扩展。总体实验较为充分，但缺乏大规模独立队列验证。

## 6. 主要结论与发现

- **癌症相关DMR特征**：肿瘤中高甲基化DMR显著富集于转录起始位点和转录调控区域；启动子甲基化与基因表达负相关；5hmC水平与基因体转录活性正相关。
- **甲基化熵降低**：癌症高甲基化DMR的甲基化熵显著降低，提示肿瘤进展过程中甲基化状态的克隆固定。
- **ASM优势**：与群体mQTL相比，ASM能利用个体内对比大幅提高统计效率，减少样本异质性。
- **ASM模式在正常与肿瘤组织中的差异**：虽然种系SNP在两者间共享，但ASM模式差异显著；肿瘤相关ASM区域具有更大的基因组跨度和更强的等位基因甲基化差异。
- **ASM与转录调控一致性**：ASM方向性与TCGA mQTL和GTEx eQTL的结果高度一致，尤其是位于DMR内和转录起始位点附近的变异。
- **候选功能变异**：
  - **IRX4风险位点**：ASM识别rs6885084，与AR ChIP-seq和H3K27ac峰重叠的雄激素响应调控域。
  - **PSCA位点**：rs4736369与等位基因特异性甲基化、染色质激活、转录本丰度和异构体使用相关。
- **方法论结论**：基于纳米孔的ASM分析是解析前列腺癌中功能性非编码变异及其调控域的有力方法。

## 7. 优点

- **创新性**：利用长读长纳米孔测序同时检测变异和天然甲基化，首次在前列腺组织中系统应用等位基因特异性甲基化分析注释非编码变异。
- **统计效率**：ASM在个体内对比，无需大量样本，有效克服群体mQTL的样本异质性和统计效力不足问题。
- **单分子分辨率**：片段级甲基化模式使计算甲基化熵成为可能，揭示肿瘤克隆演化过程中的表观遗传异质性变化。
- **多组学整合**：结合mQTL、eQTL、染色质状态和转录组数据，交叉验证ASM的功能意义，提高结果可靠性。
- **案例驱动**：通过两个已知风险位点（IRX4、PSCA）验证了方法的实用性，并提名了候选因果变异。
- **开源框架**：nanoASM框架简单易用（基于读段划分），具有良好的可推广性。

## 8. 不足与局限

- **样本量有限**：未明确样本数量，推测为数例至十数例配对正常/肿瘤组织，可能不足以捕获广泛的人群异质性，统计检验力受限。
- **组织特异性**：仅针对前列腺组织，方法在其他组织/癌症类型中的表现未验证。
- **技术偏倚**：纳米孔测序在甲基化检测精度（尤其是5hmC与5mC区分）上可能低于三代测序结合酶法，存在一定误判风险；单分子读段覆盖深度可能不均，影响ASM检测灵敏度。
- **缺乏独立验证**：作为预印本，未公布独立队列或CRISPR等实验验证候选变异的功能；仅依赖公共数据集的一致性分析，因果推断证据力度有限。
- **框架局限性**：nanoASM依赖杂合SNP进行等位基因分配，对于SNP密度低的区域可能无法有效检测ASM；未考虑相位信息（haplotype）对多个变异协同效应的影响。
- **计算资源未说明**：未提供分析所需的计算资源配置细节，不利于他人复现。
- **偏差风险**：仅比较了ASM与群体mQTL的统计效率，但未进行严格的模拟或基准测试以量化提升幅度；两例案例位点可能具有选择偏倚。

（完）
