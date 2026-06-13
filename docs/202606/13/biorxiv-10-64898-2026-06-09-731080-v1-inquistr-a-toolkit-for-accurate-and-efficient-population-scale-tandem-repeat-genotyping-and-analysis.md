---
title: "inquiSTR: a toolkit for accurate and efficient population-scale tandem repeat genotyping and analysis"
title_zh: "inquiSTR: 用于准确高效的群体规模串联重复基因分型和分析的工具包"
authors: "De Coster, W., Kucukali, F., Sleegers, K., Rademakers, R."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.09.731080v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 全基因组串联重复基因分型并提供关联检验
tldr: 串联重复序列与人类性状和疾病密切相关，但人群规模的长读长测序数据分析需要高效工具。inquiSTR采用并行处理和低内存流式算法，在不到两分钟内完成178万个位点的全基因组重复基因分型。基准测试表明其准确度高且速度显著优于现有工具。该工具还提供群体结构推断、关联检验和异常值检测等下游分析功能。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有工具无法高效处理人群规模长读长测序数据中的大量串联重复序列分析。
method: 采用并行处理和低内存流式算法，实现全基因组重复目录的快速基因分型。
result: 不到两分钟完成178万位点基因分型，准确率高于现有工具和真实集。
conclusion: inquiSTR为大规模串联重复序列基因分型与下游分析提供了高效准确的开源工具包。
---

## 摘要
串联重复是与人类性状和疾病相关的高度可变的基因组元件。从群体规模的长读长测序数据中对大型串联重复目录进行分型需要准确且高效的工具。我们介绍了inquiSTR，一个用于快速全基因组串联重复长度基因分型的命令行工具包。inquiSTR通过高效的并行处理和低内存流式算法，在不到两分钟内对包含178万个位点的全基因组重复目录进行基因分型。基准测试显示，与现有工具和真值集相比，具有高准确性和显著更快的性能。inquiSTR还提供了下游分析方法，如群体结构推断、关联检验和异常值检测。

## Abstract
Tandem repeats are highly mutable genomic elements linked to human traits and diseases. Profiling large catalogs of tandem repeats from population-scale long-read sequencing data requires accurate and efficient tools. We introduce inquiSTR, a command-line toolkit for fast genome-wide tandem repeat length genotyping. inquiSTR, with efficient parallel processing and low-memory streaming algorithms, genotypes a genome-wide repeat catalog of 1.78 million loci in less than two minutes. Benchmarking shows high accuracy and significantly faster performance compared to existing tools and truth sets. inquiSTR also provides methods for downstream analyses such as population structure inference, association testing, and outlier detection.