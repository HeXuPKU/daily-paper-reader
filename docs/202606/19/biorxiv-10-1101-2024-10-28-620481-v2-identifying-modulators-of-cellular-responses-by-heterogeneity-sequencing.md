---
title: Identifying Modulators of Cellular Responses by Heterogeneity-sequencing
title_zh: 通过异质性测序鉴定细胞反应的调节因子
authors: "Berg, K., Sakellaridi, L., Rummel, T., Hennig, T., Whisnant, A., Lodha, M., Krammer, T., Toussaint, C., Szymanska-De Wijs, K., Zheng, Y., Prusty, B. K., Doelken, L., Saliba, A.-E., Erhard, F."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.1101/2024.10.28.620481v2.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 单细胞RNA-seq结合双机器学习识别细胞反应因果调节因子
tldr: 单细胞转录组学因破坏性采样无法直接比较细胞初始状态与刺激结果，只能做关联分析。为此，我们开发了Heterogeneity-seq，整合单细胞RNA-seq、代谢RNA标记(scSLAM-seq)与双重机器学习，同时测量未标记和标记RNA，追踪数千个细胞从刺激前状态到不同反应结果的转变。该方法成功鉴定了药物反应及巨细胞病毒感染中已知和新型的因果调节因子，为解析异质性细胞反应的驱动机制提供了有力工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法无法直接测量细胞初始状态与刺激结果，只能获得相关性，缺乏因果推断能力。
method: 结合scSLAM-seq与双重机器学习，同时测量细胞中未标记和标记RNA，追踪状态转变。
result: 鉴定出驱动药物反应和巨细胞病毒感染过程的多重已知与新型因果调节因子。
conclusion: Heterogeneity-seq能够从单细胞分辨率下解析异质性反应的因果驱动因子。
---

## 摘要
单个细胞对药物治疗、病毒感染或其他分子刺激的反应具有高度异质性，且取决于细胞的初始状态。单细胞转录组学的文库制备具有破坏性，阻碍了初始状态与刺激结果之间的直接比较。因此，当前方法局限于识别相关关联，而非解析异质性结果的因果驱动因素。我们开发了Heterogeneity-seq，该方法结合了单细胞RNA测序与代谢RNA标记（scSLAM-seq）以及双重机器学习，以克服这一限制。通过利用单个细胞中未标记和标记RNA的同时测量，Heterogeneity-seq揭示了数千个细胞从刺激前状态到不同刺激结果的转变。这些联系使得能够识别因果调控异质性细胞反应的因子。我们使用Heterogeneity-seq鉴定了已知和新颖的驱动药物反应的基因，以及调控巨细胞病毒感染的促病毒和抗病毒宿主因子。

## Abstract
The response of individual cells to drug treatment, virus infections or other molecular stimuli is highly heterogeneous and depends on the cells initial state. Library preparation for single-cell transcriptomics is destructive, precluding a direct comparison between the initial state and the stimulus outcome. Consequently, current methods are restricted to identifying correlative associations rather than resolving causal drivers of heterogeneous outcomes. We developed Heterogeneity-seq, which combines single-cell RNA-seq with metabolic RNA labeling (scSLAM-seq) and double machine learning to overcome this limitation. By leveraging simultaneous measurements of unlabeled and labeled RNA in individual cells, Heterogeneity-seq uncovers the transition from pre-stimulated cell states to distinct stimulation outcomes across thousands of cells. These links enable the identification of factors that causally govern heterogeneous cellular responses. We used Heterogeneity-seq to identify both known and novel genes that drive responses to drug treatment, as well as pro- and antiviral host factors governing cytomegalovirus infection.