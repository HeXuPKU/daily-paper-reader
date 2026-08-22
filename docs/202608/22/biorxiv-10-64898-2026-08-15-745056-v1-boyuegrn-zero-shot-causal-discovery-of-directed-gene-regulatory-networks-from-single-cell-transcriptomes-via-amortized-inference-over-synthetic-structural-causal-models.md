---
title: "BoYueGRN: Zero-shot causal discovery of directed gene regulatory networks from single-cell transcriptomes via amortized inference over synthetic structural causal models"
title_zh: BoYueGRN：通过对合成结构因果模型的摊销推断，从单细胞转录组进行有向基因调控网络的零样本因果发现
authors: "Wu, J., Shen, Y.-Q."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.15.745056v1.full.pdf"
tags: ["query:med-ai"]
score: 6.0
evidence: 通过合成结构因果模型上的摊销推断实现单细胞转录组有向基因调控网络的零样本因果发现，是一种可迁移的大规模基因组模型。
tldr: "单细胞转录组的基因调控网络（GRN）推断通常需针对每个数据集重新优化，且多数方法无法推断因果方向。BoYueGRN通过仅训练于10000个合成结构因果模型，实现零样本推断，对任意新数据集单次前向传播即可输出边概率和调控方向，并利用TF中心滑动窗口与非对称融合覆盖全转录组。在BEELINE基准上表现优异，在两个CRISPRi Perturb-seq筛选中方向准确率达0.86和0.95，成功重建跨5种疾病、超27万细胞的GRN动态。该框架将定向GRN推断转变为\"一次训练、跨数据集复用\"的范式，为图谱级调控解析开辟新路径。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有GRN推断需逐数据集优化，且多数方法无法推断调控方向，缺乏零样本可迁移模型。
method: 使用10000个合成结构因果模型训练BoYueGRN，对新数据集单次前向传播输出边概率与方向，以TF中心滑动窗口和非对称融合覆盖全转录组。
result: 在BEELINE基准上零样本性能优异，两个CRISPRi Perturb-seq筛选中方向准确率达0.86和0.95，重建跨5种疾病、27万细胞GRN动态。
conclusion: "BoYueGRN将定向GRN推断重构为\"一次训练、跨数据集复用\"范式，摆脱逐数据集优化，助力疾病图谱级调控动态系统化映射。"
---

## 摘要
从单细胞RNA-seq推断基因调控网络（GRN）通常依赖于对每个数据集的单独优化。现有工具必须针对每个新数据集重新拟合，而且大多数工具无法推断因果调控方向。在这里，我们提出了BoYueGRN，这是一个专门在10,000个合成结构因果模型上训练的摊销因果发现框架。对于任何未见过的数据集，单次前向传播即可返回边概率和调控方向，同时，基于转录因子（TF）的滑动窗口与非对称融合将这一固定大小的模型扩展到全转录组范围。BoYueGRN在BEELINE基准测试中展示了强大的零样本性能。在两个独立的全基因组CRISPRi Perturb-seq筛选中，保留边上的方向准确性达到0.86和0.95。重建的跨五种疾病、涵盖超过27万个细胞的细胞类型特异性和阶段特异性GRN动态，产生了可经实验验证的生物学假设。BoYueGRN将有向GRN推断重新定义为一种‘一次训练，跨数据集复用’的范式。通过将网络重建与每个数据集的优化解耦，这一范式为跨人类疾病的系统性、图谱规模的调控动态映射打开了大门。

## Abstract
Gene regulatory network (GRN) inference from single-cell RNA-seq conventionally relies on per-dataset optimization. Existing tools must be refit for every new dataset, and the majority fail to infer causal regulatory directions. Here we present BoYueGRN, an amortized causal discovery framework trained exclusively on 10,000 synthetic structural causal models. For any unseen dataset, a single forward pass returns edge probabilities and regulatory directions, while TF-centric sliding windows with asymmetric fusion extend this fixed-size model to full-transcriptome coverage. BoYueGRN demonstrates strong zero-shot performance across BEELINE benchmarks. On two independent genome-wide CRISPRi Perturb-seq screens, directional accuracy on retained edges reaches 0.86 and 0.95. Reconstructed cell-type- and stage-specific GRN dynamics across five diseases spanning more than 270,000 cells yield experimentally testable biological hypotheses. BoYueGRN reframes directed GRN inference as a train-once, reuse-across-datasets paradigm. By decoupling network reconstruction from per-dataset optimization, this paradigm opens the door to systematic, atlas-scale mapping of regulatory dynamics across human diseases.