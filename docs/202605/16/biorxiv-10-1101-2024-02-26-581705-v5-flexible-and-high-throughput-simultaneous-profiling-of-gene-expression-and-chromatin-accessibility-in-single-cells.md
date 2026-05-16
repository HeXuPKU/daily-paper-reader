---
title: Flexible and high-throughput simultaneous profiling of gene expression and chromatin accessibility in single cells
title_zh: 灵活且高通量的单细胞基因表达与染色质可及性同时分析
authors: "Soltys, V., Peters, M., Su, D., Kucka, M., Chan, Y. F."
date: 2026-05-08
pdf: "https://www.biorxiv.org/content/10.1101/2024.02.26.581705v5.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 同时分析基因表达和染色质可及性的方法支持功能基因组学集成
tldr: 本研究开发了easySHARE-seq，这是一种改进的单细胞多组学技术，旨在同时测量染色质可及性（ATAC-seq）和基因表达（RNA-seq）。该方法通过优化条形码和实验流程，显著增加了可用序列长度并降低了测序成本。在小鼠肝脏样本的应用中，它展现了比同类技术更高的转录本回收率，能有效揭示细胞类型特异性的顺式调节元件与靶基因之间的联系，为研究复杂的基因调控网络提供了高通量且灵活的解决方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在解决现有单细胞多组学技术在测序长度限制、操作复杂性和高昂成本方面的挑战。
method: 通过改进SHARE-seq的条形码设计和简化实验流程，开发出支持长片段测序且无需专用运行的easySHARE-seq。
result: 在小鼠肝脏实验中回收了近两万个细胞，转录本回收率提升1.5倍以上，并成功建立了顺式调节元件与靶基因的关联。
conclusion: easySHARE-seq是一种高质量、低成本且具有高扩展性的多组学工具，适用于广泛的生物学研究设计。
---

## 摘要
基因调节是发育的基础，是一个涉及转录的复杂生物过程，通常发生在开放染色质内的启动子处。为了理解细胞类型特异性的调节网络，同时捕获转录和染色质可及性的能力至关重要。然而，联合测量在技术上具有挑战性，且当前的方法仍面临应用普及方面的挑战。在这里，我们提出了 easySHARE-seq，这是对 SHARE-seq 的改进，用于单细胞中 ATAC-seq 和 RNA-seq 的同时测量。我们通过改进条形码和简化实验流程，解决了先前方法的若干局限性。结果显示，easySHARE-seq 文库的可用序列长度可达 300bp（增加了 200bp），使其适用于等位基因特异性信号调查或变异发现等研究。此外，easySHARE-seq 文库不需要专门的测序运行，从而节省了成本。我们将 easySHARE-seq 应用于小鼠肝脏细胞核，并获得了 19,664 个具有染色质和表达联合图谱的细胞核。通过与其他基于组合索引的技术进行基准测试，我们证明了在保持高扩展性和低成本的同时，每个细胞可以多回收 1.5 倍以上的转录本。为了展示我们的方法，我们识别了细胞类型，利用多组学测量将顺式调节元件与其靶基因联系起来，并研究了肝脏特异性的微观尺度变化。我们得出结论，easySHARE-seq 改进了先前的方法，并能产生高质量的多组学数据集。我们期望它能适用于广泛的研究设计。

## Abstract
Gene regulation underpins development and is an intricate biological process involving transcription, typically at promoters within accessible chromatin. To understand cell-type specific regulatory networks, the ability to capture both transcription and chromatin accessibility simultaneously is crucial. However, joint measurements are technically challenging and current methodologies still face adoption challenges. Here, we present easySHARE-seq, an improvement on SHARE-seq, for the simultaneous measurement of ATAC- and RNA-seq in single cells. We address several limitations of the previous method by improving the barcode and streamlining the protocol. As a result, easySHARE-seq libraries have a usable sequence of up to 300bp (+200bp increase), making it suitable for e.g. investigation of allele-specific signals or variant discovery. Furthermore, easySHARE-seq libraries do not require a dedicated sequencing run thus saving costs. We applied easySHARE-seq to murine liver nuclei and recovered 19,664 nuclei with joint chromatin and expression profiles. By benchmarking against other combinatorial indexing-based techniques, we showed we can recover over 1.5 fold more transcripts per cell while retaining high scalability and low cost. To showcase our method, we identified cell types, exploited the multiomic measurements to link cis-regulatory elements to their target genes and investigated liver-specific micro-scale changes. We conclude that easySHARE-seq improves upon previous methods and can produce high-quality multiomic datasets. We expect it to be applicable to a wide range of study designs.