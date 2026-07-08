---
title: "Nemo2.4: fast and accurate quantitative genetics forward-time simulations"
title_zh: Nemo2.4：快速准确的定量遗传学前向时间模拟
authors: "Guillaume, F., Cotto, O., Chebib, J., Beeravolu Reddy, C., Schmid, M."
date: 2026-07-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.02.736177v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 定量遗传学的前向时间模拟框架
tldr: 进化数量遗传学面临模拟复杂生态进化动态和遗传基础的挑战。Nemo 2.4采用模块化生命周期事件架构，支持多等位QTL和密集双等位QTN，通过优化位数据结构实现高效计算。它原生集成模块化多效性、显性、上位性及反应规范，模拟多种选择形式。该框架为多基因适应和环境变化下的进化响应提供了高通量模拟平台。
source: biorxiv
selection_source: fresh_fetch
motivation: 解决进化数量遗传学中模拟复杂生态进化动态和遗传基础对灵活高效工具的需求。
method: 模块化生命周期事件框架，结合优化位数据结构和原生集成多效性、显性、上位性及反应规范。
result: 实现快速准确的前向时间模拟，支持基因组尺度分辨率、多样选择形式和种群模型。
conclusion: Nemo 2.4为测试多基因适应和进化响应理论提供了稳健的高通量模拟平台。
---

## 摘要
我们介绍Nemo 2.4，一个先进的前向时间基于个体的模拟框架，旨在模拟复杂的生态进化动态和定量性状的遗传基础。该工具通过提供前所未有的灵活性和计算效率，应对当前进化定量遗传学中的挑战。Nemo 2.4的模块化架构允许研究人员通过组合专门的Life Cycle Event（LCE）模块来设计自定义生命周期，涵盖从繁殖和扩散到选择、杂交和表型表达等过程。该软件支持多种种群模型，包括Wright-Fisher（WF）和非WF动力学、空间显式模型以及变化的种群统计学。Nemo 2.4处理广泛的遗传架构，包括用于一般性状研究的多等位基因数量性状位点（QTL），以及使用高度优化的位运算数据结构实现的密集双等位基因数量性状核苷酸（QTN）。关键的是，它允许在包含其他遗传元件的综合遗传图谱上模拟QTN，提供基因组规模的解析度。关键生物学复杂性被原生集成：模型兼容模块化多效性、显性和跨多个性状的成对上位性，便于研究复杂的基因型-表型映射。此外，Nemo 2.4通过反应规范对表型可塑性进行建模，并整合了潜在阈值，从而能够模拟环境对性状进化的影响，同时支持多种选择形式（例如高斯、线性、截断）。由于其编译设计和对大量位点的内存高效数据表示，Nemo为运行高通量模拟提供了一个稳健的平台，这些模拟对于检验多基因适应中的理论预测以及理解进化对变化环境的响应至关重要。

## Abstract
We present Nemo 2.4, an advanced forward-time individual-based simulation framework designed to model the complex eco-evolutionary dynamics and genetic basis of quantitative traits. This tool addresses current challenges in evolutionary quantitative genetics by providing unprecedented flexibility and computational efficiency. Nemo 2.4's modular architecture allows researchers to design custom life cycles by combining specialized Life Cycle Event (LCE) modules, from reproduction and dispersal to selection, crossing, and phenotype expression. The software supports diverse population models, including both Wright-Fisher (WF) and non-WF dynamics, spatially explicit models, and varying demography. Nemo 2.4 handles a wide range of genetic architectures, including both multi-allelic Quantitative Trait Loci (QTL) for general trait studies, and dense di-allelic Quantitative Trait Nucleotides (QTN) implemented with highly optimized bit-wise data structures. Crucially, it allows the simulation of QTNs on comprehensive genetic maps that incorporate other genetic elements, providing genomic-scale resolution. Key biological complexities are integrated natively: the model accommodates modular pleiotropy, dominance, and pairwise epistasis across multiple traits, facilitating the study of complex genotype-phenotype mappings. Furthermore, Nemo 2.4 models phenotypic plasticity through reaction norms and incorporates underlying liability thresholds, enabling the simulation of environmental influences on trait evolution with various forms of selection (e.g., Gaussian, linear, truncation). Due to its compiled design and memory-efficient data representations for large numbers of loci, Nemo provides a robust platform for running high-throughput simulations critical for testing theoretical predictions in polygenic adaptation and understanding evolutionary responses to changing environments.