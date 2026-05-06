---
title: "NERINE reveals rare variant associations in gene networks across phenotypes and implicates an SNCA-PRL-LRRK2 subnetwork in Parkinson's disease"
title_zh: NERINE 揭示了跨表型的基因网络中罕见变异的关联，并提示了帕金森病中 SNCA-PRL-LRRK2 子网络的作用
authors: "Nazeen, S., Wang, X., Morrow, A. R., Strom, R., Ethier, E., Ritter, D., Henderson, A. B. H., Afroz, J., Cassa, C. S., Stitziel, N. O., Gupta, R. M., Luk, K. C., Studer, L., Khurana, V., Sunyaev, S. R."
date: 2026-05-04
pdf: "https://www.biorxiv.org/content/10.1101/2025.01.07.631688v4.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 基于层次模型的罕见变异与基因网络关联测试
tldr: 本研究开发了NERINE，一种将基因网络拓扑结构与稀有变异关联分析相结合的分层模型。它弥补了模型系统实验与统计遗传学之间的鸿沟，能有效测试复杂的网络假设。通过对多种疾病的分析，NERINE发现了单基因测试无法识别的关联，并特别揭示了帕金森病中与SNCA、PRL和LRRK2相关的子网络，为理解复杂疾病的遗传机制提供了新工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的统计遗传学方法缺乏利用基因相互作用拓扑结构来测试特定生物机制模型的工具。
method: 开发了名为NERINE的分层模型，首次将基因网络拓扑纳入稀有变异关联测试，并具备对网络误差的鲁棒性。
result: NERINE在乳腺癌和糖尿病等疾病中发现了新的基因网络关联，并结合CRISPRi筛选识别出帕金森病中关键的SNCA-PRL-LRRK2应激反应子网络。
conclusion: 该方法成功整合了实验筛选与遗传关联分析，为揭示复杂表型背后的基因网络机制提供了强有力的计算框架。
---

## 摘要
研究人类表型遗传基础的方法主要有两种。模型系统实验可产生具有解释性的基因网络，但孤立而言，无法确立其与人类疾病的相关性。统计遗传学能在变异或基因水平识别相关的关联信号，但由于现有方法未纳入基因间相互作用的拓扑结构，缺乏测试特定机制模型的工具。我们通过引入一种利用罕见变异关联来竞争性测试网络假设的方法，桥接了这两种策略。基于分层模型的关联测试 NERINE 首次纳入了基因网络拓扑结构，同时对网络的不准确性保持稳健。我们展示了 NERINE 测试源自经典通路数据库和模型系统筛选的网络假设的能力。利用 NERINE 对通路网络进行全面的全数据库搜索，发现了乳腺癌、心血管疾病和 II 型糖尿病中令人信服的关联，而这些关联是单基因测试无法检测到的。通过测试针对帕金森病（PD）关键病理（多巴胺能神经元存活和 α-突触核蛋白病理学）实验筛选出的定制网络，NERINE 突出了与自噬、囊泡运输和蛋白质稳态相关的基因模块中的罕见变异负荷。人类神经元中 α-突触核蛋白毒性修饰因子的全基因组 CRISPRi 筛选与 NERINE 的结果共同指向了 PRL，揭示了一种可能影响 PD 病理韧性的神经元内 α-突触核蛋白/催乳素应激反应。

## Abstract
There are two primary approaches to study the genetic basis of human phenotypes. Experiments in model systems generate interpretable gene networks but, in isolation, do not establish relevance to the human condition. Statistical genetics identifies relevant association signals at the variant or gene level but lacks tools to test specific mechanistic models, as existing methods do not incorporate the topology of gene-gene interactions. We bridge these two strategies by introducing a method that competitively tests network hypotheses with rare variant associations. A hierarchical model-based association test NERINE for the first time incorporates gene network topology while remaining resilient to network inaccuracies. We demonstrate NERINE's ability to test network hypotheses derived from both canonical pathway databases and model system screens. Comprehensive database-wide search of pathway networks with NERINE uncovers compelling associations for breast cancer, cardiovascular diseases, and type II diabetes, which are undetected by single-gene tests. Testing bespoke networks from experimental screens targeting key PD pathologies: dopaminergic neuron survival and -synuclein pathobiology, NERINE highlights rare variant burden in gene modules related to autophagy, vesicle trafficking, and protein homeostasis. Genome-scale CRISPRi-screening of -synuclein toxicity modifiers in human neurons and NERINE converge on PRL, revealing an intraneuronal -synuclein/prolactin stress response that may impact resilience to PD pathologies.