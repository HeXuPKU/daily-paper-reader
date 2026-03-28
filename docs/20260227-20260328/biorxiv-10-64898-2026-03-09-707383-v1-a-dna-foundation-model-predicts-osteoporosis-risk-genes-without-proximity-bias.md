---
title: A DNA foundation model predicts osteoporosis risk genes without proximity bias
title_zh: 一种预测骨质疏松症风险基因且无邻近偏差的 DNA 基础模型
authors: "Regep, C., Kapourani, C.-A., Sofyali, E., Dobrowolska, A., Loukas, G., Anighoro, A., Canale, E., Gross, T., Licciardello, M., Gupta, R., Maciuca, S., Desai, T., Del Vecchio, A., Field, C., Gemayel, K., Javer, A., Zhang, Z., Tsujikawa, R., Inoue, F., Hessel, E., Taylor-King, J., Whittaker, J., Roblin, D., McIntyre, R., Edwards, L."
date: 2026-03-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.09.707383v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于从 GWAS 变异预测疾病风险基因的 DNA 基础模型
tldr: 本研究开发了名为Rosalind的DNA基础模型，旨在解决全基因组关联分析（GWAS）中非编码变异与效应基因关联时的“邻近偏差”问题。该模型基于GTEx人类遗传变异数据进行微调，能直接从序列预测变异-基因的调控关系。通过在骨质疏松症等多种复杂性状中的验证，证明了其在识别远端致病基因方面的优越性，为药物研发提供了更精准的遗传学证据。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-09-707383-v1/fig-001.webp\", \"caption\": \"Fig. 1 Rosalind architecture\", \"page\": 8, \"index\": 1, \"width\": 937, \"height\": 549}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-09-707383-v1/fig-002.webp\", \"caption\": \"Fig. 2 Benchmarking Rosalind on GWAS loci and clinically validated drug targets from OpenTargets+\", \"page\": 10, \"index\": 2, \"width\": 979, \"height\": 566}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-09-707383-v1/fig-003.webp\", \"caption\": \"Fig. 3 Using Rosalind for target discovery in Osteoporosis a. All variant–gene pairs within a receptive field of 256kbp are scored by Rosalind. Genes above the elbow threshold are kept as candidate causal genes. b. The distribution of protein-coding genes around the 1103 lead variants from the eBMD\", \"page\": 13, \"index\": 3, \"width\": 931, \"height\": 497}]"
motivation: 现有的基因映射方法过度依赖邻近基因启发式算法，导致难以准确识别非编码变异对应的远端效应基因。
method: 开发了基于DNA基础模型的Rosalind，利用GTEx遗传变异数据进行微调，直接从序列预测变异与基因间的调控关系。
result: 实验证明，在骨质疏松症风险变异中，远端基因比最近邻基因更有可能显著改变骨形成表型。
conclusion: 基于深度学习的调控模型为将遗传学发现转化为药物研发靶点提供了一个通用且可扩展的框架。
---

## 摘要
受人类遗传关联支持的靶点从临床开发到获批的可能性是其他靶点的两倍以上。全基因组关联研究是疾病风险遗传证据的最大来源，但将非编码变异与效应基因联系起来仍然是识别因果靶点的主要障碍。目前的基因映射方法存在邻近偏差，在很大程度上忽略了远端基因。在此，我们介绍了 Rosalind，这是一个基于 GTEx 人类遗传变异进行微调的 DNA 基础模型，它直接从序列预测变异-基因调控关系，而不依赖于最近基因启发式方法。我们通过广泛的基准测试证明了 Rosalind 的准确性，将其应用于多种复杂性状以确立其广泛的实用性，并利用转化成骨细胞实验在骨质疏松症中提供了实验验证。我们证明，与最近基因相比，远离骨质疏松症风险变异的基因显著更有可能改变骨形成表型。总之，这些结果强调了基于深度学习的调控模型是将新的遗传见解转化为药物发现的通用且可扩展的框架。

## Abstract
Targets supported by human genetic associations are more than twice as likely to progress from clinical development to approval. Genome-wide association studies are the largest source of genetic evidence for disease risk but linking non-coding variants to effector genes remains a significant barrier to identifying causal targets. Current gene-mapping approaches suffer from proximity bias, largely ignoring distal genes. Here we introduce Rosalind, a DNA foundation model fine-tuned on human genetic variation from GTEx, that directly predicts variant-gene regulatory relationships from sequence without relying on nearest-gene heuristics. We demonstrate Rosalinds accuracy through extensive benchmarking, apply it to multiple complex traits to establish broad utility, and provide experimental validation in osteoporosis using a translational osteoblast assay. We demonstrate that genes distal to osteoporosis risk variants were significantly more likely to alter a bone formation phenotype than nearest genes. Together, these results highlight deep learning-based regulatory models as a general and scalable framework for translating novel genetic insights to drug discovery.