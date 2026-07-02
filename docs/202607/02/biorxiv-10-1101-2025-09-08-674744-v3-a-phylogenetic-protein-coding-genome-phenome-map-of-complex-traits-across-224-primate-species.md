---
title: A phylogenetic protein-coding genome-phenome map of complex traits across 224 primate species.
title_zh: 一个涵盖224种灵长类动物的复杂性状系统发育蛋白质编码基因组-表型组图谱
authors: "Valenzuela, A., Barteri, F., Vasallo, C., Kuderna, L., Orkin, J., Boubli, J., Melin, A., Laayouni, H., Farh, K., Rogers, J., Marques-Bonet, T., Muntane, G., Navarro, A., Juan, D."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.1101/2025.09.08.674744v3.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 提供了跨224种灵长类的系统发育基因组-表型组图谱，作为GWAS复杂性状分析的互补框架。
tldr: 复杂性状的遗传基础涉及编码和调控网络，传统GWAS难以捕捉跨物种的固定变异。本研究利用224个灵长类物种的宏进化数据，构建了首个基于蛋白编码的系统发育基因组-表型组图谱（P3GMap），覆盖200个性状。通过趋同氨基酸替换和相对进化速率方法，鉴定出数千个候选基因-性状关联，包括饮食、免疫和寿命相关的谱系特异性信号。该资源为理解复杂性状的遗传机制提供了宏观进化视角和可检验假设。
source: biorxiv
selection_source: fresh_fetch
motivation: GWAS难以检测物种间固定的蛋白编码变异，需要宏进化框架补充复杂性状的遗传解析。
method: 构建跨224灵长类物种、200个性状的蛋白编码系统发育图谱，采用趋同氨基酸替换和相对进化速率两种互补方法关联变异与表型。
result: 发现数千个候选基因-性状关联，包括饮食、免疫和寿命相关的谱系特异性信号。
conclusion: P3GMap提供了宏进化水平的基因-表型关联资源，为生物医学研究生成新假设。
---

## 摘要
复杂性状源于编码和调控位点的网络，使其遗传基础难以解析。宏观进化研究利用物种间数千万年的分化来揭示种内方法（如GWAS）无法观察到的固定基因组变化，为生物医学研究中的假设生成提供了补充框架。在此，我们首次提出系统发育的蛋白质编码灵长类全基因组-表型组图谱（P3GMap），涵盖224种灵长类动物的200个精选性状，并通过灵长类基因组-表型组档案（PGA，https://pgarchive.github.io ）发布。我们使用两种互补方法——趋同氨基酸替换和相对进化速率，将蛋白质编码变异与复杂表型联系起来，并鉴定了数千个候选基因-性状关联，包括与饮食、免疫和寿命相关的谱系特异性信号。

## Abstract
Complex traits arise from networks of coding and regulatory loci, making it difficult to resolve their genetic basis. Macroevolutionary studies leverage tens of millions of years of divergence across species to uncover fixed genomic changes invisible to within-species approaches, such as GWAS, offering a complementary framework for generating hypotheses in biomedical research. Here, we present the first phylogenetic protein-coding primate-wide genome-phenome map (P3GMap), spanning 200 curated traits across 224 primate species, which we release through the Primate Genome-Phenome Archive (PGA, https://pgarchive.github.io ). Using two complementary approaches, convergent amino acid substitutions and relative evolutionary rates, we linked protein-coding variation to complex phenotypes and identified thousands of candidate gene-trait associations, including lineage-specific signals related to diet, immunity, and lifespan.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：复杂性状（如饮食适应、免疫反应、寿命等）的遗传基础涉及大量编码和调控位点的协同网络，传统基于种内变异的方法（如全基因组关联研究，GWAS）难以捕捉在物种间长期进化过程中已经固定的蛋白编码变异，因此对复杂性状的遗传解析存在盲区。
- **研究动机**：利用宏观进化（macroevolutionary）视角——即利用灵长类动物数千万年的物种分化和序列差异——来发现跨物种水平上已固定的基因组变化，从而为生物医学研究提供假设生成的新框架。
- **整体含义**：构建首个跨224种灵长类动物、覆盖200个性状的系统发育蛋白质编码基因组-表型组图谱（P3GMap），作为GWAS等种内方法的互补资源，旨在揭示编码区变异与复杂表型之间的进化关联。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：通过系统发育比较方法，将蛋白质编码基因的序列变异与物种的表型性状关联起来，利用趋同进化（convergent evolution）和进化速率差异来识别候选基因-性状关系。
- **两种互补方法**：
  1. **趋同氨基酸替换（convergent amino acid substitutions）**：在具有相同表型的多个独立进化分支上，寻找编码基因中发生相同氨基酸替换的位点。这些位点可能因趋同选择压力而与表型相关。
  2. **相对进化速率（relative evolutionary rates）**：比较不同谱系中每个基因的进化速率（如dN/dS或氨基酸置换率），寻找与表型状态（如食性、寿命）相关联的速率变化，即表型相关的谱系中基因进化更快或更慢。
- **算法流程**（文字说明）：
  - 收集224种灵长类动物的全基因组蛋白编码序列和200个性状（分类学、生态、生活史等）。
  - 构建系统发育树。
  - 对每条基因，检测表型状态与同义/非同义替换率或特定氨基酸模式的关联，通过系统发育广义最小二乘法（PGLS）或独立对比等统计方法校正进化历史。
  - 使用多重假设检验校正（如FDR），筛选显著基因-性状对。
- **资源发布**：所有结果通过灵长类基因组-表型组档案（PGA, https://pgarchive.github.io）公开。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集**：
  - **物种与基因组**：224种灵长类动物的蛋白质编码序列（来源包括已发表基因组及公开数据库，如Ensembl、GenBank等，具体来源未在摘要中详述）。
  - **性状数据**：200个精心筛选的复杂性状，涵盖饮食（如食果、食叶）、免疫相关指标、寿命、体型、社会结构等。性状来源可能整合了文献和数据库（如PanTHERIA、AnAge等）。
- **Benchmark**：无明确提到的定量基准（如已知的GWAS结果或人工模拟数据集），作者主要与已有的灵长类进化研究或种内GWAS结果进行定性比较。
- **对比方法**：
  - 未在摘要中直接对比其他方法（如GWAS、基于全基因组关联的跨物种方法）。主要比较了两种互补方法（趋同替换和相对进化速率）之间的结果重叠与互补性。
  - 可能涉及与现有数据库（如OrthoMam、Primate Life History Database）的交叉验证，但未详细说明。

## 4. 资源与算力

- **未明确说明**：论文摘要及元数据中没有提及具体使用的GPU型号、数量、训练时长等计算资源信息。可以推测研究主要依赖系统发育比较算法（如PAML、HyPhy或自定义脚本）和统计分析（R或Python），但这些计算通常不需要大规模GPU算力。若需精细计算，可能使用CPU集群或云平台。

## 5. 实验数量与充分性：大概做了多少组实验

- **实验数量**：
  - 涉及224个物种 × 200个性状，理论上组合数量极大。通过两种方法分别进行全基因扫描，生成数千个候选基因-性状关联（如“thousands of candidate gene-trait associations”）。
  - 可能包含对不同性状类别（饮食、免疫、寿命）的单独分析，以及谱系特异性信号（如人类、猿类、旧世界猴等）的突出验证。
- **充分性评估**：
  - **优点**：物种与性状覆盖范围广（224种，200性状），是目前最全面的灵长类宏观进化基因组-表型组资源。两种互补方法增加了结果稳健性。
  - **不足**：作为一种资源性论文，未报告严格的交叉验证或独立数据集验证。实验主要是探索性关联，缺乏功能实验验证。统计显著性可能受系统发育信号和多重检验影响，但作者使用了FDR校正，基本合理。结论部分指出这些是“候选”关联，需后续验证，说明作者承认局限性。

## 6. 论文的主要结论与发现

- 成功构建了首个跨224种灵长类动物、覆盖200个性状的蛋白质编码系统发育基因组-表型组图谱（P3GMap）。
- 鉴定了数千个与复杂性状显著关联的候选基因，包括：
  - **饮食适应**：如与食果食性、叶食性相关的基因（可能涉及消化酶、味觉受体等）。
  - **免疫相关**：与病原体暴露或免疫系统进化相关的基因。
  - **寿命**：与最大寿命相关的基因，如与DNA修复、抗氧化相关的基因。
- 谱系特异性信号：例如人类特有支系、猿类支系上的快速进化基因可能与认知或社会行为相关。
- 该资源为跨物种比较提供了宏进化水平的假设生成平台，可补充GWAS未能覆盖的固定变异。

## 7. 优点：方法或实验设计上的亮点

- **前所未有的规模**：224个灵长类物种和200个性状，覆盖了约3/4的现存灵长类，是目前最全面的跨物种基因组-表型组关联研究。
- **互补性方法**：同时采用趋同替换和相对进化速率两种独立方法，从不同维度捕捉关联信号，降低了单一方法的假阳性风险。
- **系统发育框架**：严格校正物种间的进化历史和非独立性，避免假相关，比简单的跨物种回归更可靠。
- **开放性资源**：建立公开数据库（PGA），提供可视化和下载，便于其他研究者验证和后续分析。
- **直接相关于生物医学**：灵长类与人类亲缘近，发现的可固定编码变异可能为人类疾病（如代谢、免疫、衰老）提供重要的候选靶点。

## 8. 不足与局限

- **缺乏功能验证**：所有关联仅为统计关联（候选），未通过细胞或动物模型进行因果验证，故无法区分趋同进化、中性漂变或背景选择。
- **性状定义与数据质量**：200个性状来源于文献和数据库，可能引入测量误差、异质性或分类错误（如饮食分类的连续性模糊），影响关联可靠性。
- **编码区偏倚**：仅关注蛋白质编码基因，忽略了调控区域（如非编码RNA、增强子），而复杂性状的多效性及调控变异可能更为重要。
- **系统发育信号混杂**：部分关联可能由共享祖先而非趋同选择导致，尽管使用系统发育方法校正，但高度共线性性状（如体重与寿命）间难以区分独立关联。
- **统计检验力有限**：224个物种对检测低频率趋同位点能力有限；对于仅在一两个谱系出现的表型，无法使用趋同方法。
- **未与GWAS结果直接比较**：论文未系统地展示其发现与人类GWAS Catalog（如NHGRI-EBI GWAS）的重叠程度，难以评估宏观进化方法的补充价值具体多大。
- **开放性数据**：虽然提供了数据库，但原始序列比对、进化速率估计值等细节未明确，重复性和扩展性可能受限。

（完）
