---
title: Evaluating Evo 2 for plant variant effect prediction
title_zh: 评估 Evo 2 在植物变异效应预测中的表现
authors: "Kato, Y., Takayama, S., Fujii, S."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.714098v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 用于GWAS因果变异优先级排序的基因组基础模型
tldr: 本研究评估了基因组基础模型 Evo 2 在植物变异效应预测中的表现。通过对拟南芥生殖隔离基因中已验证的功能获得和缺失变异进行测试，证明了 Evo 2 能够有效识别具有功能影响的变异。研究还提出了一种符号反转幅度指标，成功找回了传统评分漏掉的变异，展示了该模型在植物 GWAS 和 QTL 定位中筛选因果变异的巨大潜力。
source: biorxiv
selection_source: fresh_fetch
motivation: 评估基因组基础模型 Evo 2 在植物领域（特别是拟南芥）进行零样本变异效应预测的有效性。
method: 利用拟南芥中具有实验验证的功能获得和缺失变异数据，结合新提出的符号反转幅度指标对 Evo 2 进行评估。
result: Evo 2 能够准确区分具有功能影响的变异，且新指标能捕捉到标准评分方法遗漏的关键变异。
conclusion: Evo 2 为植物全基因组关联分析（GWAS）和数量性状位点（QTL）定位中的因果变异优先级排序提供了有力工具。
---

## 摘要
基因组基础模型 Evo 2 能够实现零样本变异效应预测。在本研究中，我们利用具有实验证实的“功能获得”和“功能缺失”变异的拟南芥生殖隔离基因评估了其性能，并证明 Evo 2 能够区分具有功能影响的变异。结合一种能够找回被标准评分漏掉的变异的“符号反转幅度”指标，这些结果突显了 Evo 2 在植物 GWAS 和 QTL 定位中进行因果变异优先级排序的潜力。

## Abstract
The genomic foundation model Evo 2 enables zero-shot variant effect prediction. Here, we evaluate its performance using Arabidopsis thaliana reproductive barrier genes with experimentally confirmed gain- and loss-of-function variants, and show that Evo 2 distinguishes functionally impactful variants. Together with a sign-reversal amplitude metric that recovers a variant missed by standard scoring, these results highlight the potential of Evo 2 for causal variant prioritization in plant GWAS and QTL mapping.

---

## 论文详细总结（自动生成）

### 论文结构化总结：评估 Evo 2 在植物变异效应预测中的表现

#### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：验证通用的基因组基础模型 Evo 2 是否能够在无需植物特异性微调的情况下，通过“零样本（zero-shot）”预测，准确识别植物基因组中的功能性变异。
*   **研究背景**：在植物遗传学研究（如 GWAS 和 QTL 定位）中，从大量候选变异中精准锁定导致表型变化的“因果变异”是一个长期挑战。虽然已有针对植物开发的模型（如 PlantCaduceus），但评估像 Evo 2 这样在全生命域数据上训练的通用模型在植物领域的表现具有重要意义。

#### 2. 方法论：核心思想与关键技术
*   **核心思想**：利用 Evo 2 模型对 DNA 序列的似然估计能力，计算变异序列与参考序列之间的似然值差异（$\Delta \text{likelihood}$），以此衡量变异对生物功能的潜在影响。
*   **关键技术细节**：
    *   **零样本评分**：计算 $\Delta \text{likelihood} = \log P(\text{variant}) - \log P(\text{reference})$。负值通常表示功能受损，正值可能表示功能增强。
    *   **双向评分与平均**：由于 DNA 模型存在反向互补不一致性，研究同时计算正向（Forward）和反向互补（Reverse-complement）序列的分数，并取平均值（$\Delta \text{likelihood}_{\text{avg}}$）。
    *   **符号反转幅度（Sign-reversal amplitude）**：针对正反向评分符号相反（一正一负）的变异，提出新指标：$|\Delta \text{likelihood}_{\text{fwd}} - \Delta \text{likelihood}_{\text{rev}}| / 2$。该指标旨在捕捉那些因正负抵消而在平均分中被掩盖的复杂功能变异。
    *   **单倍型评分**：将多个变异组合成完整的单倍型序列进行整体评分，以捕捉变异间的组合效应。

#### 3. 实验设计
*   **研究对象**：拟南芥（*Arabidopsis thaliana*）中控制种间生殖隔离的关键基因 $SPRI1$ 和 $SPRI2$。
*   **数据集**：
    *   变异数据源自“1001 Genomes Project”。
    *   表型数据采用已发表的实验验证数据，包括功能获得（GoF）、功能缺失（LoF）及近中性变异。
*   **Benchmark 与对比**：
    *   以实验确定的功能分类为金标准。
    *   对比了正向评分、反向评分、平均评分以及新提出的符号反转幅度指标。
    *   在单倍型层面，将模型预测分与实际的花粉排斥表型得分进行相关性分析。

#### 4. 资源与算力
*   **模型版本**：使用了拥有 200 亿参数的 **Evo 2 20B** 模型（版本 0.5.0）。
*   **算力细节**：论文**未明确说明**具体的 GPU 型号、数量及推理总时长。由于是零样本推理而非训练，其算力需求主要集中在模型加载和对 8,192 bp 长度序列的似然值计算上。

#### 5. 实验数量与充分性
*   **实验规模**：研究深入分析了两个具有代表性的基因位点（$SPRI1$ 和 $SPRI2$），涵盖了数百个自然变异及数十种自然单倍型。
*   **充分性评价**：实验设计较为精巧，特别选择了具有相反选择压力历史的基因（$SPRI1$ 较不保守，$SPRI2$ 较保守）进行对比。虽然涉及的基因数量较少，但通过对已知实验结果的逐一比对，验证了模型在识别 GoF 和 LoF 变异方面的细粒度能力，逻辑严密且客观。

#### 6. 主要结论与发现
*   **功能区分能力**：Evo 2 能够有效区分功能性变异。强负分变异主要集中在编码区的基因破坏性变异（如移码、终止子提前）。
*   **新指标的必要性**：标准平均分漏掉了 $stop222C$（一种导致蛋白延伸的变异），但“符号反转幅度”指标成功将其识别为高影响变异，说明该指标是标准评分的重要补充。
*   **保守性影响**：模型在保守基因（$SPRI2$）上的表现更稳定，链偏好性较小；而在进化较快的基因（$SPRI1$）上，双向评分的一致性较差。
*   **单倍型效应**：模型预测分与实际表型呈显著负相关，且能捕捉到多个微效变异组合后抵消功能获得变异（G155A）的拮抗效应。

#### 7. 优点（亮点）
*   **零样本优势**：证明了通用大模型无需针对植物进行昂贵的微调即可直接应用。
*   **指标创新**：提出的“符号反转幅度”有效解决了 DNA 语言模型中常见的链不一致性问题，提升了变异检测的灵敏度。
*   **单倍型视角**：不仅关注单个 SNP，还验证了模型处理复杂单倍型组合效应的能力，更贴近实际育种场景。

#### 8. 不足与局限
*   **样本覆盖有限**：仅在拟南芥的两个基因上进行了验证，尚未在大规模作物（如水稻、玉米）或全基因组范围内进行普适性评估。
*   **链不一致性风险**：研究发现模型对非保守序列的预测高度依赖于序列方向，这暗示模型在处理进化快速或分类群特异性基因时可能存在偏差。
*   **应用限制**：对于非编码区变异（如启动子、增强子），模型给出的分数普遍接近于零，这可能限制了其在调控区变异预测中的应用。

（完）
