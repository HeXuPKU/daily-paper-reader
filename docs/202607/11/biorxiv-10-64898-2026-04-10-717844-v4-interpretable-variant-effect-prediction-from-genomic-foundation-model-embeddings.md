---
title: Interpretable variant effect prediction from genomic foundation model embeddings
title_zh: 基于基因组基础模型嵌入的可解释变异效应预测
authors: "Pearce, M. T., Dooms, T., Yamamoto, R., Ayanian, S., Ryu, A., Meehl, J., Molnar, C., Kiiskinen, T., Bissell, M., Hazra, D., Fang, C., Nguyen, N., Anderson, M., Osborne, C., Duffy, P., Toomey, B., Klee, E., Myasoedova, E., Korfiatis, P., Redlon, M., Jain, A., Balsam, D., Wang, N. K."
date: 2026-07-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.10.717844v4.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 利用基因组基础模型嵌入进行变异效应预测
tldr: 基因组基础模型Evo 2的嵌入包含丰富信息，但如何提取可解释知识仍是挑战。本文提出协方差探针捕获序列嵌入的二阶结构，预测变体致病性，在多种变体类型中匹配或超越专用预测器。同时训练注释探针检测基因组属性破坏，结合语言模型生成变体特异性机制假设。致病性预测与实验测量、临床外显率和生物库疾病关联相关，机制假设与专家评审一致。开源了ClinVar中420万个变体的评分和解释。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1713, \"height\": 1124, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1713, \"height\": 895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1709, \"height\": 815, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1603, \"height\": 1021, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1708, \"height\": 1348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1619, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1629, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1319, \"height\": 934, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 936, \"height\": 1078, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1810, \"height\": 632, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1817, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1823, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1904, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1575, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1580, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1230, \"height\": 1398, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1614, \"height\": 1184, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1645, \"height\": 2074, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1622, \"height\": 1451, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1663, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1662, \"height\": 832, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1662, \"height\": 899, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1663, \"height\": 900, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-04-10-717844-v4/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1663, \"height\": 937, \"label\": \"Table\"}]"
motivation: 基因组基础模型编码高维表示，但缺乏从嵌入中提取可解释变体效应预测的方法。
method: 利用Evo 2嵌入的协方差探针预测致病性，同时用注释探针检测基因组属性破坏，并通过语言模型整合上下文生成机制假设。
result: 预测在多种变体类型上匹配或超越专用工具，与实验及临床数据一致，机制假设与已知知识吻合。
conclusion: 该结构化探针方法可推广至其他科学基础模型，并发布了大规模开源资源EVEE。
---

## 摘要
科学基础模型从多种数据模态中学习高维表示，然而它们编码了什么以及如何提取这些知识仍是未解之谜。在此，我们展示了探究Evo 2（一个70亿参数的基因组基础模型）内部表示的方法，能够实现准确且可解释的遗传变异效应预测。我们引入了一种基于协方差的探针，从Evo 2序列嵌入中捕获二阶结构，以跨变异类型和功能后果预测变异致病性，在其领域内达到或超越专业预测器的性能。为了将这些预测锚定于已知生物学机制，我们在现有注释上训练了一组互补探针，以检测变异破坏了哪些基因组属性。随后，通过语言模型将这些分类证据与每个变异的基因组背景整合，生成变异特异性机制假说。我们的致病性预测与变异功能的实验测量、临床外显率及生物库疾病关联相关，而机制假说与专家评审、已知机制类别及下游分子读出结果一致。我们通过Evo变异效应浏览器（EVEE）发布了来自ClinVar数据库的420万个变异的致病性评分、破坏图谱及情境化解释，作为开放资源。更广泛地，这种结构化探针方法为跨科学领域探究基础模型并将其输出锚定于现有领域概念提供了一个通用框架。

## Abstract
Scientific foundation models learn high-dimensional representations from diverse data modalities, yet what they encode and how to extract that knowledge remain open questions. Here we show that probing the internal representations of Evo 2, a 7-billion-parameter genomic foundation model, enables accurate and interpretable genetic variant effect prediction. We introduce a covariance-based probe that captures second-order structure from Evo 2 sequence embeddings to predict variant pathogenicity across variant types and functional consequences, matching or exceeding specialized predictors within their domains. To ground these predictions in known biological mechanisms, we train a complementary panel of probes on existing annotations to detect which genomic properties are disrupted by a variant. This categorized evidence is then integrated with each variant's genomic context through a language model to generate variant-specific mechanistic hypotheses. Our pathogenicity predictions correlate with experimental measures of variant function, clinical penetrance, and biobank disease associations while the mechanistic hypotheses are consistent with expert reviews, known mechanism classes, and downstream molecular readouts. We release pathogenicity scores, disruption profiles, and contextualized interpretations for 4.2 million variants from the ClinVar database as an open resource through the Evo Variant Effect Explorer (EVEE). More broadly, this structured probing approach offers a general framework for interrogating foundation models across scientific disciplines and grounding their outputs in existing domain concepts.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

基因组基础模型（如Evo 2）从大量DNA序列中学习到高维嵌入表示，但这些表示的具体内容以及如何从中提取可解释、可预测的知识仍是开放问题。**核心瓶颈**：现有变异效应预测方法（如AlphaMissense、CADD、EVE等）存在两大局限：

- **碎片化**：蛋白类方法只适用于错义替换，序列-功能模型侧重调控效应，基因组级元预测器则压缩证据为单一分数，无法统一覆盖所有变异类型（编码、非编码、插入缺失等）。
- **缺少机制**：大多数方法只输出一个致病性评分，不提供“为什么”的机制性解释。临床变异分类（如ACMG/AMP指南）依赖于分类证据，而非单一分数。

本文探索**能否从同一个基因组基础模型的内部表示中同时获得高精度的致病性预测和生物学机制解释**，从而将准确性与可解释性统一起来。

## 2. 方法论：核心思想、关键技术细节

### 2.1 整体框架
基于**Evo 2（7B参数）**模型，对每个变异提取参考序列和变异序列的**每位置嵌入差异**（embedding difference），然后训练两类探针：

- **协方差探针（Covariance Probe）**：用于致病性预测。
- **注释探针（Annotation Probes）**：用于检测变异破坏的已知基因组/蛋白特征，生成“破坏图谱”（disruption profile），再通过LLM合成自然语言解释。

### 2.2 协方差探针详细设计
- **输入**：Evo 2第27层嵌入（经层扫描选择最优），对每条序列保留与变异位点最不同的256个位置（两个方向：正/反义）。参考和变异嵌入逐位置相减得到 \( X_s \in \mathbb{R}^{K \times d} \)（\(K=256, d=4096\)）。
- **二阶结构捕获**：不采用简单的均值池化（丢弃特征间协方差），而是计算**非对称投影后的协方差**：
  - 对每个方向 \(s\)，学习两个投影 \(P_s, Q_s \in \mathbb{R}^{d \times h}\)（\(h=64\)），计算 \( C = \frac{1}{K} \sum_s (X_s P_s)^\top (X_s Q_s) + \epsilon I \)。
  - 得到的 \(64 \times 64\) 矩阵捕获了投影维度间最显著的成对交互，避免了满 \(4096 \times 4096\) Gram矩阵。
- **谱正则化**：对原始协方差矩阵应用矩阵平方根变换（三次Newton-Schulz迭代），抑制大奇异值对训练的干扰。
- **读出**：正则化后的协方差展平后通过线性层映射到良性和致病性logits，softmax输出致病性概率。
- **训练**：Muon优化器（常数lr 0.005, batch 512×8, weight decay 0.1），单epoch，标签为ClinVar P/LP vs B/LB，80/20基因级划分（无超参选择）。参数约105万。

### 2.3 注释探针与破坏图谱
- 对236个二进制/连续基因组注释（蛋白结构域、剪切模块、二级结构、PTM、进化保守性等），每个注释训练一个协方差探针，在Evo 2第27层参考嵌入上预测注释值（\( \sim 100M \)个位置，18k基因，80/20基因级划分）。
- 对每个变异，计算注释预测值的变化：\( \Delta_a = f_a(E_{\text{alt}}) - f_a(E_{\text{ref}}) \)，得到破坏图谱。

### 2.4 LLM机制解释
- 将top-10破坏特征（按\(|\Delta|\)排序）与变异元数据（基因、后果类型、HGVS命名等）组装成结构化提示，输入Claude Sonnet 4.6，生成自然语言解释。
- 提示设计包含：基因功能背景、破坏表格（区域和位点）、校准的致病性百分比等。目标：使LLM以破坏故事为主导，不使用外部临床工具。

## 3. 实验设计：数据集、基准场景、对比方法

### 3.1 实验数据集
| 数据集 | 用途 | 规模/说明 |
|--------|------|----------|
| **ClinVar (2026-03-21)** | 主训练和评估 | 833,970个SNV（≥1星）；73,961个indel；4.2M全部变异（含VUS、未分类） |
| **Deconfounded benchmark** | 控制后果类型混淆 | 158,616个变异，每个后果类型内平衡致病/良性 |
| **Deep Mutational Scans (DMS)** | 跨基因泛化验证 | BRCA1 (2,803), BRCA2 (6,270), TP53 (1,920), LDLR (24,999) – 四种基因完全基因级留出 |
| **Mayo Clinic Tapestry cohort** | 临床外显率验证 | 147个LDLR变异载体，专家标注FH严重度三级（临床FH、疑似FH、症状前） |
| **FinnGen R12** | 人群规模疾病关联 | ~500k参与者，2,489疾病终点；EVEE评分分组分析λGC |
| **CCLE RNA-seq** | RNA-seq机制验证 | 82个变异-载体对（卵巢癌细胞系） |
| **Mayo Clinic RA cohort** | 早期部署展示 | 588名类风湿关节炎患者外显子组，225个罕见VUS |

### 3.2 对比方法
AlphaMissense、CADD v1.7、GPN-MSA、NTv3（650M）、AlphaGenome、Evo 2基于似然的评分、均值池化探针（自己训练的Evo 2基线）。

### 3.3 评价指标
- 主指标：AUROC（按后果类型分层，基因级留出交叉验证）
- DMS：Spearman |ρ|
- 机制分类：平衡准确度（5折交叉验证）
- 解释质量：LLM-judge打分（1-5，三轴：机制覆盖度、生物学准确性、特异性）
- 外显率：AUC区分有症状 vs 无症状载体
- 人群：λGC（基因组膨胀因子，匹配等位基因频率）

## 4. 资源与算力
文中明确提到：
- 嵌入提取使用了 **~20,000 H100-hours**（约20000小时H100 GPU计算）。
- 训练协方差探针：单epoch，Muon优化器，batch 512×8，未明确训练时间（但推测可快速收敛）。
- 注释探针训练：~100M位置，约18k基因，80/20划分。
- 最终数据集：34 TB（bf16），约4.25M变异 × 2方向 × 512位置 × 4096维度。

**注意**：未给出各对比方法的训练/推理成本，尤其AlphaMissense等可能消耗更大。试验以推理为主，算力需求适中。

## 5. 实验数量与充分性

### 5.1 实验组数
- **主基准**：ClinVar SNV按7种后果类型分层+indel按多种分层（5种后果×2方向/大小）。
- **去混淆基准**：1组（控制后果类型先验）。
- **DMS泛化**：4个基因各1组。
- **保守性分层**：1组（phyloP分层）。
- **机制分类恢复**：4个基因，每基因5折CV。
- **LLM解释质量**：147个专家审核变异×5种上下文配置×3个Claude型号 = 约2205个解释，每个由2个独立法官评分。
- **RNA-seq验证**：82个变异-载体对，3个机制层级。
- **临床外显率**：1组（LDLR Tapestry）。
- **人群关联**：1组（FinnGen，多种EVEE阈值分组）。
- **ACMG/AMP提名**：21个候选经筛选后6个达到阈值。

### 5.2 充分性评价
- **充分**：覆盖了从临床标签到实验测量再到人群队列的多层次验证。
- **公平**：
  - 使用基因级留出（避免基因泄露）。
  - 对后果类型混淆进行了专门去混淆基准和分层评估。
  - 等位基因频率匹配用于FinnGen人群分析，避免分层偏差。
- **可能不足之处**：
  - ClinVar标签本身有噪声且存在报告偏倚（致病性更容易被报告）。
  - DMS仅四个基因，且均为单基因疾病相关。
  - LLM解释评估存在记忆化风险和主观性（虽然使用了双法官独立评分和多级别配置）。
  - Tapestry症状前组样本小（n=16）。

## 6. 主要结论与发现

1. **单一协方差探针在SNV上匹配或超越所有现有方法**（按后果类型AUROC：同义0.984，错义0.970，无义0.900，内含子0.984等），并且零样本泛化到indel（整体AUROC 0.991 vs CADD 0.980）。
2. **Evo 2嵌入编码的信息超越进化保守性**：在快进化和高保守区域均保持高AUROC，而CADD和GPN-MSA在极端端性能下降。
3. **预测与实验测量一致**：四个DMS基因上协方差探针与AlphaMissense和CADD竞争或领先，始终优于均值池化和似然评分。
4. **破坏图谱可区分同一基因内不同疾病机制类别**（LDLR 5类，LMNA 3类等），平衡准确度0.74（位置基线0.51，致病性评分基线仅0.26-0.33）。
5. **LLM解释质量随上下文增加而提升**，加入Evo 2破坏信息后提升最显著（+1.03分），最终复合得分3.80/5（Claude Sonnet 4.6）。
6. **BRCA1 c.5278-1G>A机制预测被RNA-seq精确验证**：预测的隐蔽剪接受体位点（+8 bp）在JHOS-4细胞系中得到证实（reads精确落在预测位置）。
7. **致病性评分跟踪临床外显率**：Tapestry LDLR载体中，临床FH组中位EVEE分0.76，疑似FH组0.10，症状前组0.01，AUROC=0.91区分有症状vs无症状。
8. **人群规模疾病关联富集**：FinnGen R12中EVEE≥0.95的变异λGC=1.33，而等位频率匹配的低分对照λGC=1.00；即使在无ClinVar标记的变异中也保持富集（λGC=1.17）。
9. **六名FinnGen候选变异达到ACMG/AMP证据阈值**，证明EVEE能贡献结构化证据支持临床提交。

## 7. 优点

- **统一性**：一个模型（Evo 2嵌入）同时适用于SNV、indel、编码、非编码、剪切等多种变异类型，无需专门化工具。
- **二阶特征捕获**：协方差池化相比均值池化显著提升性能，且理论上有明确意义（捕获特征间共变）。
- **可解释性创新**：将基础模型嵌入通过探针转化为领域内的命名特征（蛋白结构域、剪切信号等），再通过LLM合成机制解释，形成从原始表示到临床推理的完整链路。
- **严格去混淆**：明确量化后果类型混淆的影响，并设计了去混淆基准评估模型是否仅靠后果类型先验得分。
- **多维度验证**：从标签（ClinVar）到实验（DMS）到临床队列（Tapestry）到人群（FinnGen）到分子实验（RNA-seq），证据链完整。
- **开放资源**：发布4.2M变体的致病性评分、破坏图谱和解释（EVEE web+API+Zenodo），促进社区使用。
- **通用框架**：方法论不限于基因组，可推广到其他科学基础模型。

## 8. 不足与局限

- **进化先验局限**：Evo 2基于广泛进化训练，对调控、上位效应或多基因效应可能不完整。
- **ClinVar监督偏差**：致病性探针在ClinVar上训练，导致ClinVar内评估存在“主场优势”；DMS、RNA-seq和人群分析是更强的泛化证据，但ClinVar标签质量参差不齐。
- **LLM解释的质量依赖LLM能力**：生成和评估均使用同一模型族（Claude），可能存在循环依赖；且LLM可能记忆已知变异（如CFTR F508del），削弱测试公平性。
- **临床验证的样本量限制**：Tapestry症状前组仅16人，可能影响统计力；RA队列为单中心、小规模演示。
- **人群验证仅一个生物库（FinnGen）**，且芬兰人群独特，泛化到其他人群需谨慎。
- **注释探针局限于已知标签**：未探索无监督特征（如稀疏自编码器可发现的隐式特征），可能遗漏未知生物学。
- **ACMG/AMP证据强度未正式校准**：PP3仅作为支持性启发式使用，未遵循ClinGen SVI的OddsPath正式校准。
- **LLM生成解释应视为假设**，不能替代专家评审或进一步实验验证。
- **资源消耗大**：嵌入提取约20k H100小时，数据集34 TB，对普通研究组可及性有限。

（完）
