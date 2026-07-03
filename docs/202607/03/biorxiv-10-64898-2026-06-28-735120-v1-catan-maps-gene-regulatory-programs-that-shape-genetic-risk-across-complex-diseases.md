---
title: CATaN maps gene regulatory programs that shape genetic risk across complex diseases
title_zh: CATaN映射塑造复杂疾病遗传风险的基因调控程序
authors: "Takahashi, H., Hatano, H., Kono, M., Haruta, K., Nakano, M., Bagherzadeh, R., Drees, M. M., Oguma, Y., Harita, D., Kawashima, T., Arakawa, T., Inokuchi, H., Nishino, T., Asahara, K., Itamiya, T., Inamo, J., Natsumoto, B., Tsuchida, Y., Sumitomo, S., Suzuki, A., Kochi, Y., Fujio, K., Yamamoto, K., Ohta, T., Kawakami, E., Ishigaki, K."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.28.735120v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 开发CATaN框架整合转录因子调控网络与转录组评估遗传力，直接支持功能基因组学与GWAS整合
tldr: 复杂疾病因果变异富集于转录因子结合位点，通过干扰转录因子活性导致转录组失调。现有方法通常分别处理转录因子介导的基因调控网络与转录组，缺乏联合分析框架。CATaN通过典型相关分析提取两者共享变异成分，转化为全基因组功能注释分数，结合分层LD回归进行遗传力分析。在69种复杂性状中识别出588个显著富集SNP遗传力的典型相关成分，且其功能注释轨迹不同于传统转录组分析，揭示了未被捕获的疾病调控程序。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有研究将转录因子调控网络和转录组分开分析，缺乏联合利用两者系统评估疾病遗传力的方法。
method: 构建TF-GRN矩阵，开发CATaN流程，用CCA提取共享变异成分，转化为功能注释分数并结合S-LDSC进行遗传力分析。
result: "在8个数据集（19,198个体样本和611,772单细胞）中，识别出588个CC成分在69个复杂性状中显著富集遗传力，且优于传统转录组分析。"
conclusion: 整合TF-GRN与转录组可揭示疾病相关调控程序，为因果变异精细定位提供新工具。
---

## 摘要
复杂性状的因果变异富集在转录因子（TF）结合位点，并被认为通过破坏TF活性而导致转录组失调，从而促进病理发生。然而，现有方法通常分别处理TF介导的基因调控网络（TF-GRNs）和转录组，能够同时利用两者系统评估疾病遗传力的方法仍然有限。我们旨在开发一个联合利用TF-GRNs和转录组评估疾病遗传力的框架。在此，我们构建了编码TF-GRNs的矩阵，并开发了一种无监督分析流程——转录组与TF基因调控网络的典型相关分析（CATaN）。CATaN应用典型相关分析（CCA）提取典型相关（CC）成分，即转录组与TF-GRNs之间的共享变异成分，并将其转化为全基因组功能注释得分，与分层LD得分回归（S-LDSC）关联用于遗传力分析。我们将CATaN应用于八个数据集，包括来自人类和小鼠的19,198个批量样本和611,772个单细胞，识别出588个CC成分，这些成分在69个复杂性状中对SNP遗传力显著富集。值得注意的是，基于这些TF-GRNs的功能注释轨迹与LDSC-SEG优先考虑的转录组特征不同，对部分性状的遗传力富集更大。最后，我们建议CATaN可能有助于通过基因组编辑优先选择候选因果变异进行实验性精细定位。总之，将TF-GRNs与转录组整合揭示了与疾病相关的调控程序，这些程序仅基于转录组的分析无法完全捕捉。

## Abstract
Causal variants of complex traits are enriched at transcription factor (TF) binding sites and are thought to contribute to pathology by disrupting TF activity and thereby causing transcriptome dysregulation. However, existing approaches typically address TF-mediated gene regulatory networks (TF-GRNs) and transcriptomes separately, and methods that jointly leverage both to systematically assess disease heritability remain limited. We aimed to develop a framework that jointly leverages TF-GRNs and transcriptomes to assess disease heritability. Here, we constructed a matrix encoding TF-GRNs and developed an unsupervised analytical pipeline, Canonical correlation Analysis of Transcriptome and TF-gene regulatory Networks (CATaN). CATaN applies canonical correlation analysis (CCA) to extract canonical correlation (CC) components, i.e., shared variation components between transcriptomes and TF-GRNs, and converts them into genome-wide functional annotation scores connected to stratified LD score regression (S-LDSC) for heritability analysis. We applied CATaN to eight datasets, including 19,198 bulk samples and 611,772 single cells from human and mouse sources, identifying 588 CC components that are significantly enriched for SNP heritability across 69 complex traits. Notably, functional annotation tracks based on these TF-GRNs are distinct from transcriptome signatures prioritized by LDSC-SEG, with greater heritability enrichment for a subset of traits. Finally, we suggest that CATaN may help prioritize candidate causal variants for experimental fine-mapping using genome editing. Together, integrating TF-GRNs with transcriptomes reveals disease-relevant regulatory programs that are not fully captured by transcriptome-based analyses alone.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：复杂疾病的因果变异主要富集于转录因子（TF）结合位点，并通过干扰TF活性导致转录组失调。然而，现有方法通常将TF介导的基因调控网络（TF-GRN）与转录组分析分开处理，缺乏联合利用两者系统评估疾病遗传力的框架。
- **研究动机**：虽然已有方法（如LDSC-SEG）利用转录组特异性表达基因进行遗传力富集，或（如IMPACT）基于TF染色质免疫沉淀测序（ChIP-seq）数据定义调控元件，但它们均未在SNP层面联合建模TF-GRN与转录组变异，且大多依赖预定义的细胞类型或比较组标签。
- **整体含义**：开发一种无监督的分析框架，整合TF-GRN与转录组数据，以揭示疾病相关调控程序，提供更精确的遗传力富集分析并辅助因果变异优先化。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：利用典型相关分析（CCA）提取转录组矩阵与TF-GRN矩阵之间的共享变异成分，并将其转化为全基因组、单碱基对分辨率的功能注释分数，再结合分层LD得分回归（S-LDSC）进行遗传力富集分析。
- **关键技术细节**：
  - **构建TF-GRN矩阵**：收集2,868个人类TF ChIP-seq谱（覆盖410个TF、24个组织、287个细胞类型）。采用指数距离加权方案（半衰距离10 kb）计算每个基因与邻近TF结合位点的连接得分，形成基因×TF样本矩阵。
  - **构建转录组矩阵**：对RNA测序（RNA-seq）或微阵列数据进行标准化处理，保留与TF-GRN矩阵基因交集，采用TMM归一化及log2(CPM+1)转换（或单细胞数据的LogNormalize）。
  - **CCA分析**：使用对角化CCA（源自Seurat），对两个矩阵分别进行基因维度缩放和样本维度缩放，选取前10,000个最可变基因的并集，通过奇异值分解（SVD）得到：
    - TF样本加载（TF sample loadings）
    - 转录组样本加载（transcriptome sample loadings）
    - 转录组基因投影（transcriptome gene projections）
  - **生成CC注释轨迹**：将TF样本加载值赋给其对应的ChIP-seq峰区域；对每个SNP，累加所有与之重叠的峰的TF加载值，得到SNP的CC分数。取分数最高/最低的10%的SNP分别构建二元注释（top 10%和bottom 10%）。
  - **S-LDSC分析**：将CC二元注释与基线LD模型（v1.2）共同输入S-LDSC，计算遗传力富集统计量（调整后的τ及其p值）。
- **算法流程**（文字说明）：
  1. 输入：转录组矩阵（基因×样本）和TF-GRN矩阵（基因×TF-Chip-seq样本）
  2. 预处理：对两个矩阵分别进行基因-wise和样本-wise缩放，选择前10,000高变基因的交集。
  3. 计算协方差矩阵 K = X'Y，对K进行SVD：K = UΔV^T，得到TF样本加载U、转录组样本加载V和奇异值Δ。
  4. 计算基因投影：将原始矩阵与对应样本加载相乘。
  5. 生成CC注释：将TF加载映射到TF峰上，累加形成SNP级别的CC分数。
  6. 定义二元注释（top/bottom 10%），运行S-LDSC。

## 3. 实验设计：数据集、场景、基准对比
- **数据集与场景**（8个数据集，共19,198个批量样本和611,772个单细胞）：
  - **GTEx**：53种人类尸检组织，8,555个批量转录组样本。
  - **人类免疫细胞数据集**：28种免疫细胞类型，来自健康供体。
  - **ImmGen**：30种小鼠免疫细胞类型，653个微阵列样本。
  - **单细胞神经类器官**：8,295个细胞。
  - **单细胞RA滑膜数据集**：T细胞子集94,046个细胞、B细胞子集30,691个细胞。
  - **单细胞ILC（先天淋巴样细胞）数据集**。
  - **细胞因子CD4 T细胞刺激数据集**：5种极化条件（Th0/1/2/17/iTreg），138个样本。
  - **多自身免疫疾病临床数据集**（ImmuNexUT）：10种自身免疫疾病，包括系统性红斑狼疮（SLE）、类风湿关节炎（RA）等。
- **基准对比方法**：
  - 主要与 **LDSC-SEG**（基于转录组特异性表达基因的遗传力富集）进行比较。
  - 额外与fine-mapped eQTL（GTEx v10）、RA GWAS精细定位变异、以及相关的染色质状态注释（Roadmap ChromHMM）进行比较。
- **验证实验**：
  - CRISPRa介导的RELA过表达RNA-seq数据（评估NF-κB相关基因表达方向一致性）。
  - 使用GTEx半数据集进行hold-out验证（检验模型稳健性）。
  - 通过CRISPR prime editing和UNIChro-seq进行单基因座caQTL验证（T1D相关位点）。

## 4. 资源与算力
- **论文中未明确说明**：未提及GPU型号、数量、训练时长等计算资源信息。方法部分仅描述了计算步骤（如Bowtie2比对、MACS峰调用、CCA分析、S-LDSC等），均可在标准CPU环境下完成，但大规模置换检验（如1,000次）可能需要一定并行计算能力。具体算力需求未报告。

## 5. 实验数量与充分性
- **实验数量**：
  - 8个转录组数据集，总共构建了740个CC注释轨迹（top/bottom × 10 CCs × 37个数据集）。
  - 对90个性状/疾病进行S-LDSC，共检测到588个显著遗传力富集（涉及69个性状）。
  - 额外的验证实验：CRISPRa RELA实验、GTEx半数据集验证、与eQTL相关性检验（3,646个基因）、RA fine-mapping变异富集检验（20个注释）、一个位点的caQTL实验。
  - 消融分析：基因标签置换检验（评估CCA鲁棒性）、不同加权距离比较、TF加载方差分解等。
- **充分性与客观性**：
  - 实验设计较为全面：覆盖多种数据模态（bulk、单细胞、跨物种、临床样本）和多个维度（组织、细胞类型、刺激、疾病）。
  - 设置了阴性对照（置换检验）和独立验证（hold-out、eQTL），表明方法具有可泛化性且非过拟合。
  - 与LDSC-SEG的比较客观，展示了在某些性状（如风湿病）上CATaN更优，但也承认在精神分裂症上LDSC-SEG更优，体现了公平对比。
  - 实验验证（caQTL）仅有1个成功案例，规模较小，但作者已将其列为局限性。

## 6. 论文的主要结论与发现
- CATaN能够无监督地识别转录组与TF-GRN之间的共享变异，并产生与疾病遗传力显著相关的注释轨迹，在69个性状上获得588个显著富集的CC成分。
- TF-GRN来源的CC注释与LDSC-SEG的转录组注释在功能上互补：CC注释更集中于增强子和活跃TSS等调控区域，而SEG注释偏向转录相关区域；在风湿病等免疫相关性状上，CC注释的遗传力富集更显著。
- CATaN可在单细胞数据中定位疾病遗传力富集的特定细胞类型，例如在RA滑膜中识别出Tph细胞、GZMK/B+记忆CD8+ T细胞、GC样B细胞和ABCs；在神经类器官中，揭示了MDD遗传力富集于放射状胶质细胞和成熟神经元。
- 通过一个实例（T1D位点）展示了CATaN有助于优先化功能性因果变异：CC SNP的caQTL效应大于原GWAS lead SNP。

## 7. 优点
- **完全无监督**：不依赖预定义的细胞类型或比较标签，能发现超越传统分类的调控程序。
- **全基因组单碱基分辨率**：CC注释轨迹提供精细的SNP级功能性评分，可直接用于S-LDSC和变异优先化。
- **多输出维度解释性强**：同时提供TF样本加载、转录组样本加载和基因投影，可同时解析调控因子、细胞状态和通路。
- **广泛适用性**：支持批量RNA-seq、单细胞RNA-seq、微阵列数据，兼容人类和小鼠。
- **有效整合TF-GRN**：通过结合ChIP-seq数据，捕捉到了仅凭转录组分析无法获得的调控信号。

## 8. 不足与局限
- **TF ChIP-seq资源偏差**：当前数据集偏向常见TF（如CTCF占10%）和免疫相关TF（RELA、STAT等），且约三分之一的样本来自免疫细胞，导致神经系统等领域的TF覆盖不足，限制了在某些性状（如精神分裂症）上的表现。
- **TF-GRN模型精度有限**：采用距离指数加权链接TF位点到基因，缺乏实验验证的金标准，可能存在错误连接。
- **实验验证规模小**：caQTL比较仅在一个位点成功（编辑效率是主要瓶颈），缺乏多基因座大规模验证，削弱了对变异优先化效用的说服力。
- **单细胞遗传力分析的统计独立性**：单细胞数据中来自同一供体的细胞不满足独立假设，虽然进行的是细胞级别分析，但结果需在供体感知方法中验证。
- **缺少与更多最新方法的直接比较**：未与sc-linker、scDRS、Perturb-multiome等其他方法在相同任务上进行定量对比，仅与LDSC-SEG比较，基准有限。

（完）
