---
title: Sequence-Based Prioritization of Promoter Regulatory Variants in Colorectal Cancer Using a DNA Foundation Model
title_zh: 基于序列的DNA基础模型优先筛选结直肠癌启动子调控变异
authors: "Shome, S., Vajinepalli, S., Saraf, A."
date: 2026-05-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.25.727528v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 利用DNA基础模型Evo2对启动子调控变异进行优先级排序，辅助非编码GWAS变异功能解读
tldr: "非编码调控变异在结直肠癌易感性中功能解释困难。本研究利用自回归DNA基础模型Evo2，通过计算启动子区域序列变异前后的概率差（delta分数），对约1250个CRC相关基因的启动子变异进行优先级排序。结果显示，启动子变异影响显著高于非启动子，筛选出的287个高影响变异富集于Wnt、p53等通路，36.4%与已知癌症基因重叠，并在CRC GWAS位点和转录因子结合位点得到验证。该框架无需监督训练即可规模化优先排序非编码调控候选，为基础模型在癌症基因组中的应用提供了范例。"
source: biorxiv
selection_source: fresh_fetch
motivation: 非编码调控变异对结直肠癌易感性影响显著，但功能解释困难，现有方法依赖注释且难以规模化。
method: 使用Evo2 DNA基础模型计算启动子区域参考与替代等位基因的序列概率差（delta分数），对变异排序。
result: "启动子变异delta分数显著高于非启动子；筛选287个高影响变异，富集于Wnt和p53通路，36.4%为已知癌症基因。"
conclusion: 基于序列的DNA基础模型可无需监督训练即可偏好非编码调控候选，具有可扩展性和通用性。
---

## 摘要
非编码调控变异与结直肠癌易感性相关，但其功能解读仍困难重重。这主要归因于调控效应具有背景依赖性，且大多数非编码区域缺乏可靠的基因组注释。我们开发了一个计算框架，利用大规模自回归DNA基础模型Evo2辅助优先筛选启动子相关变异。在该框架中，将变异映射到约1,250个结直肠癌相关基因的启动子区域，并使用Evo2衍生的delta分数（参考等位基因与替代等位基因之间序列概率的差异）进行评分。启动子变异比非启动子变异表现出更大的预测调控效应（中位delta = 0.015 vs. 0.002；总体均值 = 0.018，标准差 = 0.011）。应用分布阈值（delta > 0.020；前约25%）在198个结直肠癌相关基因中鉴定出287个高影响变异。这些基因富集于结直肠癌相关通路，如Wnt信号、p53信号和细胞周期调控，其中36.4%（72/198）与已知癌症基因重叠。独立验证表明，高影响变异在结直肠癌GWAS位点富集，并重叠转录因子结合位点（约32%）和基序破坏位置（约21%），支持其功能相关性。综上，这些结果表明基于序列的基础模型可以在无需监督训练或预定义注释的情况下，可扩展地优先筛选结直肠癌中的非编码调控候选变异。

## Abstract
Noncoding regulatory variants contribute to colorectal cancer (CRC) susceptibility, yet their functional interpretation remains difficult.This is mainly attributed to regulatory effects being context-dependent and most noncoding regions lack reliable genomic annotations. We have developed a computational framework that aids in prioritizing promoter-associated variants using Evo2, a large-scale autoregressive DNA foundation model. In the framework, variants were mapped to promoter regions across ~1,250 CRC-associated genes and scored using Evo2-derived delta scores, the difference in sequence probability between reference and alternate alleles. Promoter variants showed greater predicted regulatory impact than non-promoter variants (median delta = 0.015 vs. 0.002; overall mean = 0.018, SD = 0.011). Applying a distributional threshold (delta > 0.020; top ~25%) identified 287 high-impact variants across 198 CRC-associated genes. These genes were enriched in CRC-relevant pathways such as Wnt signaling, p53 signaling, and cell cycle regulation and 36.4% (72/198) overlapped known cancer genes. Independent validation showed high-impact variants were enriched at CRC GWAS loci and overlapped transcription factor binding sites (~32%) and motif-disrupting positions (~21%), supporting their functional relevance. Together, these results show that sequence-based foundation models can scalably prioritize noncoding regulatory candidates in CRC without supervised training or predefined annotations.

---

## 论文详细总结（自动生成）

好的，以下是对论文的详细中文总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：非编码调控区域的遗传变异对结直肠癌（CRC）的易感性有重要影响，但其功能解读极其困难。主要障碍在于：
    - **背景依赖性**：调控效应通常依赖于特定的细胞类型、染色质状态和微环境，难以一概而论。
    - **注释不足**：大多数非编码区域缺乏可靠的基因组功能注释或经典的转录因子结合位点（TFBS）信息。
- **研究动机**：鉴于全基因组关联研究（GWAS）发现的大量非编码变异，开发一种能够不依赖现有注释、无需监督训练的规模化优先排序方法，以识别具有潜在功能影响的非编码调控变异。
- **整体含义**：本研究证明，大型自回归DNA基础模型（如Evo2）能够通过纯序列分析，有效、可扩展地优先筛选出与结直肠癌相关的启动子调控变异，为非编码变异的功能解读提供了新范例，有望加速癌症易感位点的发现。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用DNA基础模型对序列的“自然性”或“可能性”的预测能力。假设一个突变（替换等位基因）如果显著改变了局部DNA序列在模型下的概率，那么这个突变就更可能具有调控功能（因为模型已经学习了DNA序列的潜在分布规律）。
- **关键技术细节（Evo2 & Delta分数）**：
    1.  **模型**：使用**Evo2**，一个大规模自回归DNA基础模型，能够直接输入DNA序列并输出序列中每个位置的碱基概率。
    2.  **变异评分（Delta分数）**：对于给定变异（如chr1:12345 A>G），计算以下差值：
        - **Delta = log P(参考等位基因序列) - log P(替代等位基因序列)**
        - 其中 `P(序列)` 是Evo2模型对该特定序列（以该变异位点为中心的一个窗口，如200bp）预测的对数概率（log-likelihood）。
    3.  **变异定位**：首先将全基因组变异映射到约1,250个已知结直肠癌相关基因的启动子区域（定义为转录起始位点TSS上游1kb至下游500bp）。
    4.  **评分与排序**：对每个映射到的启动子变异计算Delta分数。分数越高，表明该替代等位基因导致模型预测的序列概率下降越多，因此可能具有更大的调控效应。
- **算法/流程步骤**：
    1.  **输入**：全基因组变异集 + 1,250个CRC相关基因列表 + GRCh38/hg38参考基因组。
    2.  **定义启动子区域**：为每个基因定义启动子窗口。
    3.  **过滤变异**：提取所有落在启动子窗口内的变异。
    4.  **计算Delta分数**：对每个启动子变异，输入参考序列窗口和替代序列窗口到Evo2，计算Delta分数。
    5.  **设置阈值**：基于Delta分数的分布（如取前25%，Delta > 0.020）确定“高影响”变异。
    6.  **下游分析**：对高影响变异、其所属基因进行功能富集（如通路、已知癌症基因重叠）、GWAS位点富集、TFBS和基序破坏分析。

### 3. 实验设计

- **使用的数据集**：
    - **主要数据集**：约1,250个**结直肠癌（CRC）相关基因**的启动子区域变异。论文未明确指定来源数据（如GnomAD、ClinVar、公开WGS/WES），但使用了大规模变异集合。
    - **验证数据集**：
        - **CRC GWAS位点**：从已发表GWAS研究中获得的结直肠癌风险位点。
        - **转录因子结合位点（TFBS）**：来自ENCODE等公共数据库的人类TFBS数据。
    - **基准（Benchmark）**：论文未使用有明确标签（如实验验证的功能变异）的标准基准数据集，而是采用了**内部对照**和**外部富集验证**：
        - **内部对照**：比较**启动子变异**与**非启动子变异**（随机选择的后台变异）的Delta分数分布。
- **对比方法**：
    - 论文**未**明确与现有的功能预测方法（如CADD、LINSIGHT、PrimateAI、FATHMM-MKL等）进行直接的性能对比（如AUROC/AUPRC）。
    - 对比主要体现在**分析层面**：展示了Evo2的Delta分数与TFBS注释、基序破坏等已知调控特征之间的富集关系，间接证明了方法的有效性。

### 4. 资源与算力

- **未明确说明**：论文正文及元数据中**没有提供**关于GPU型号（如A100、H100）、数量、训练总时长（小时/天）、内存消耗等具体算力信息。Evo2本身是一个非常大和昂贵的模型，但该研究主要进行的是**模型推理（Inference）**而非从头训练，因此对算力的需求相对较低，可能可在单个高端GPU上完成。

### 5. 实验数量与充分性

- **实验数量**：
    - **主要分析**：1组（启动子 vs. 非启动子变异的整体Delta分数比较）。
    - **阈值筛选**：1组（基于单一阈值筛选高影响变异）。
    - **下游验证**：3组（GWAS位点富集、TFBS重叠、基序破坏位置重叠）。
- **充分性评估**：
    - **优点**：验证策略合理，使用了多个独立的生物学证据（GWAS、TFBS、通路）来支持筛选出的变异，增强了结论的可信度。
    - **不足与风险**：
        - **缺乏消融实验**：没有探索不同窗口大小、不同阈值、或是否考虑单碱基上下文等因素对结果的影响。
        - **缺乏对比实验**：没有与现有最先进的方法（如CADD、LINSIGHT）进行系统比较，无法直接证明Evo2在该任务上比这些方法更优或更高效。
        - **验证方式**：富集分析是相关性而非因果关系。高Delta分数变异与TFBS重叠，不等于该变异具有真正的调控功能。最终的功能验证需要实验。

### 6. 论文的主要结论与发现

1.  **有效性**：Evo2的Delta分数能够有效区分启动子变异与非启动子变异。启动子区域的变异在序列概率上具有显著更大的变化（中位delta=0.015 vs. 0.002），表明模型对启动子区域的序列扰动更敏感。
2.  **筛选结果**：通过设定阈值（delta>0.020），共识别出287个高影响变异，这些变异位于198个CRC相关基因中。
3.  **功能相关性**：
    - 这些高影响基因富集在**Wnt信号、p53信号、细胞周期调控**等经典CRC通路中。
    - **36.4%**（72/198）的基因与已知癌症基因重叠。
    - 高影响变异在**CRC GWAS位点**中显著富集（非随机）。
    - 高影响变异与**转录因子结合位点（~32%）**和**基序破坏位置（~21%）**具有显著重叠。
4.  **方法学意义**：证明了基于序列的DNA基础模型可以在**无需监督训练**（即不需要有标记的功能变异数据）、也**不需要预定义基因组注释**的情况下，对非编码调控候选变异进行规模化优先排序。

### 7. 优点

1.  **突破依赖**：摆脱了对传统基因组注释（如TFBS、DNase-seq等）的依赖，只使用原始DNA序列，具有很好的通用性和可扩展性。
2.  **零样本能力**：不需要任何结直肠癌特异性或人类特异性标记的功能变异数据进行微调，即可进行有效的优先排序，降低了数据获取和模型训练的壁垒。
3.  **多证据验证**：使用了GWAS、TFBS、基序破坏等多种独立的生物学证据进行验证，使结论更扎实。
4.  **清晰的分析框架**：从定位、评分到筛选、验证的流程清晰，易于复现和理解。

### 8. 不足与局限

1.  **验证局限性**：
    - **缺乏对比方法**：未与现有主流工具（如CADD、Eigen、LINSIGHT）进行定量比较，说服力不足。
    - **缺乏金标准验证**：筛选出的“高影响”变异**未进行任何实验验证**（如CRISPRi/a、双荧光素酶报告基因等），结论停留在预测层面。
    - **因果关系未定**：富集分析表明的是相关性，无法证明这些变异直接介导了致病性。
2.  **模型与方法的局限**：
    - **Evo2本身**：虽然强大，但它的训练数据、架构、偏差可能会影响对特定变异（如罕见杂合变异、非编码重复区域）的预测效果。
    - **窗口效应**：模型对序列概率的计算依赖于固定的窗口大小（200bp），无法捕捉远端增强子或更广泛的染色质构象变化。
    - **阈值选择**：基于数据分布的简单阈值（前25%）可能过于粗糙，容易包含假阳性或错过一些效应值适中但真正重要的变异。
3.  **分析范围有限**：仅关注了启动子区域，忽略了远端增强子、绝缘子、内含子等同样重要的非编码调控区域。
4.  **因果推断不清**：只分析了一个变异位点，无法区分“因果变异”和“标签变异”（LD），也无法解释多位点联合效应（平顺效应）。

（完）
