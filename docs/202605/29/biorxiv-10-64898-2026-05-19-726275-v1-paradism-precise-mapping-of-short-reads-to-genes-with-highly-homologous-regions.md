---
title: "ParaDISM: Precise mapping of short reads to genes with highly homologous regions"
title_zh: ParaDISM：短读序列到具有高同源区域基因的精确比对
authors: "Tzimotoudis, D., Farrugia, R., Zammit, J., Masini, M. C., Balestrucci, A., Carbott, F. B., Wettinger, S. B., Alexiou, P., Ciach, M. A."
date: 2026-05-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.19.726275v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 短读映射算法减少同源区域假变异，提升GWAS数据质量
tldr: 基因高度同源区域（旁系同源、串联重复、假基因）导致短读段比对困难，容易产生错误变异调用。ParaDISM通过多重序列比对识别歧义位点，仅将读段分配给有明确特异性证据的序列，并可选迭代精炼调用变异。在模拟和真实数据上，它显著降低了比对错误和假阳性变异，提高了特异性和精确性。该工具开源，增强了同源区域变异调用的可靠性。
source: biorxiv
selection_source: fresh_fetch
motivation: 高度同源区域短读段比对困难导致大量假阳性变异调用，影响下游分析准确性。
method: 基于多重序列比对识别歧义位点，仅在有明确序列特异性证据时分配读段，并可选迭代精炼更新参考序列。
result: 相比bowtie2、bwa-mem等，ParaDISM在模拟和真实数据上减少了错误比对和假阳性变异，提高了特异性和精确性。
conclusion: ParaDISM提高了同源序列中读段放置和SNP调用精度，减少假阳性，提供更强证据。
---

## 摘要
背景
具有高度相似基因组拷贝（旁系同源、串联重复和假基因）的基因对短读高通量测序（srHTS）构成了重大挑战。高序列相似性使得难以明确识别短读序列的来源，导致比对伪影，这些伪影可能在生物信息学流程中传播，并增加变异检测的错误率。

结果
我们提出了ParaDISM，一个优化标准比对以改善读段放置并减少高同源序列中由比对错误驱动的假变异调用的流程。ParaDISM仅在无歧义的序列特异性证据支持时，通过使用参考序列的多序列比对来识别消歧位置，从而将读段/读段对分配到一个序列。一个可选的迭代优化过程从可信分配的读段中调用变异，更新参考序列，并处理剩余未分配的读段。

我们通过广泛的计算模拟实验和Genome in a Bottle HG002基准评估了ParaDISM在读段比对和产生的短变异调用方面的性能。我们将ParaDISM应用于重新分析两个案例研究：GNAQ/GNAQP1基因座的五个公共肿瘤外显子组，以及18个被诊断为常染色体显性多囊肾病患者的短读测序数据集（16个外显子组和2个面板测序数据集）。与标准比对器（bowtie2、bwa-mem和minimap2）相比，ParaDISM减少了比对伪影和假变异调用的数量，从而提高了结果的特异性和精确性。

结论
ParaDISM提高了高同源参考序列中读段放置和单核苷酸变异调用的精确性。通过减少由比对伪影引起的假变异调用数量，与现有方法相比，ParaDISM为调用的变异提供了更强的证据水平。该流程是开源的，并在MIT许可下于github.com/BioGeMT/ParaDISM提供。

## Abstract
BackgroundGenes with highly similar genomic copies (paralogs, tandem duplications and pseudogenes) pose a major challenge for Short-Read High Throughput Sequencing (srHTS). High sequence similarity makes it difficult to unambiguously identify the sequences of origin of short reads. This results in misalignment artifacts which can propagate through bioinformatic pipelines and increase error rates in variant calling.

ResultsWe present ParaDISM, a pipeline that refines standard alignments to improve read placement and reduce misalignment-driven false variant calls in highly homologous sequences. ParaDISM assigns a read/read pair to a sequence only when supported by unambiguous sequence-specific evidence by using a multiple sequence alignment of reference sequences to identify disambiguating positions. An optional iterative refinement procedure calls variants from confidently assigned reads, updates the reference sequences, and processes remaining non-assigned reads.

We evaluated the performance of ParaDISM both in terms of read alignment and the resulting short variant calls using extensive computational simulation experiments and the Genome in a Bottle HG002 benchmark. We applied ParaDISM to reanalyze two case studies: five public tumour exomes at the GNAQ/GNAQP1 locus, and 18 short-read sequencing datasets of patients diagnosed with Autosomal Dominant Polycystic Kidney Disease (16 exomes and 2 panel sequencing datasets). Compared to the standard aligners (bowtie2, bwa-mem and minimap2), ParaDISM reduced the number of misalignment artifacts and false variant calls, resulting in an increased specificity and precision of the results.

ConclusionsParaDISM improves the precision of read placement and single-nucleotide variant calling in highly homologous reference sequences. By reducing the number of false variant calls caused by misalignment artifacts, ParaDISM provides a stronger level of evidence for the called variants compared to currently available approaches. The pipeline is open source and available under the MIT license at github.com/BioGeMT/ParaDISM.