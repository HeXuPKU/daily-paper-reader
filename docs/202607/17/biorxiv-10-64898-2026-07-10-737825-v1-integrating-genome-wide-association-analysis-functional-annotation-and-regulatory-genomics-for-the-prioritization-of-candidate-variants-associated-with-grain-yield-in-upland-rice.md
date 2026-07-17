---
title: "Integrating Genome-Wide Association Analysis, Functional Annotation and Regulatory Genomics for the Prioritization of Candidate Variants Associated with Grain Yield in Upland Rice"
title_zh: 整合全基因组关联分析、功能注释和调控基因组学用于优先筛选与旱稻籽粒产量相关的候选变异
authors: "da Cruz, A. C., Vianello, R. P., Valdisser, P. A. M. R., Bueno, L. G., Brondani, C."
date: 2026-07-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.10.737825v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 整合GWAS、功能注释和调控基因组学进行候选变异优先排序
tldr: 水稻产量是复杂数量性状，GWAS虽找到关联位点但转化为候选变异困难。本研究整合GWAS、功能注释和调控基因组学，对252份巴西水稻核心种质进行产量关联分析，鉴定29个显著SNP，其中13个基因间区变异富集顺式调控元件。通过优先级策略筛选出7个最有希望的基因间SNP。该框架有效桥接统计关联与生物学功能，为复杂性状分子育种提供策略。
source: biorxiv
selection_source: fresh_fetch
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737825-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1235, \"height\": 693, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737825-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1972, \"height\": 589, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-10-737825-v1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 2258, \"height\": 363, \"label\": \"Table\"}]"
motivation: 翻译GWAS统计关联为有生物学意义的候选变异仍是挑战，尤其调控区变异。
method: 对252份巴西水稻核心种质进行GWAS，结合功能注释和顺式调控元件分析优先候选变异。
result: 鉴定29个显著关联SNP，16个位于基因内，13个在基因间区，其中7个基因间SNP被优先候选。
conclusion: 整合分析框架能有效优先调控变异，为分子育种提供策略。
---

## 摘要
籽粒产量是水稻中一个高度复杂的数量性状，由多种遗传、生理和环境因素的相互作用决定。尽管全基因组关联分析（GWAS）已成功鉴定出与籽粒产量相关的位点，但将统计关联转化为具有生物学意义的候选变异仍然是一个重大挑战，尤其是对于位于调控区域的变异。本研究旨在鉴定与旱稻籽粒产量相关的基因组变异，并通过整合全基因组关联分析、功能注释和调控基因组学，开发一个用于功能优先筛选候选变异的整合框架。利用巴西水稻核心种质资源中的252份材料进行了籽粒产量表型鉴定和35,763个单核苷酸多态性（SNP）标记的基因分型。GWAS鉴定出29个与籽粒产量显著关联的SNP，包括16个位于注释基因内部或附近的变异和13个位于基因间区域的变异。鉴定的候选基因参与信号感知、代谢物转运、氨基酸和能量代谢、激素生物合成、蛋白质周转、RNA加工和抗病性，突显了籽粒产量的多基因架构。对基因间区域的功能特征分析揭示了与激素信号、干旱响应、碳代谢、光合作用和生殖发育相关的转录因子识别的顺式调控元件富集，表明调控变异是籽粒产量决定的重要组成部分。通过整合GWAS信号、候选基因注释、顺式调控元件特征以及SNP与顺式调控元件之间的物理邻近性，一种整合优先筛选策略确定了七个基因间SNP作为最有可能进行功能验证的候选。总之，这些发现建立了一个用于发现、优先筛选和功能验证调控变异的稳健框架，弥合了统计关联与生物学功能之间的差距，同时为将GWAS发现转化为复杂性状的分子育种提供了合理策略。

## Abstract
Grain yield is a highly complex quantitative trait in rice, resulting from the interaction of multiple genetic, physiological and environmental factors. Although genome-wide association studies (GWAS) have successfully identified loci associated with grain yield, translating statistical associations into biologically meaningful candidate variants remains a major challenge, particularly for variants located in regulatory regions. This study aimed to identify genomic variants associated with grain yield in upland rice and to develop an integrative framework for functionally prioritizing candidate variants through the combination of genome-wide association analysis, functional annotation and regulatory genomics. A panel of 252 accessions from the Brazilian Rice Core Collection was phenotyped for grain yield and genotyped with 35,763 single nucleotide polymorphism (SNP) markers. GWAS identified 29 SNPs significantly associated with grain yield, including 16 variants located within or near annotated genes and 13 located in intergenic regions. The identified candidate genes were involved in signal perception, metabolite transport, amino acid and energy metabolism, hormone biosynthesis, protein turnover, RNA processing and disease resistance, highlighting the polygenic architecture of grain yield. Functional characterization of the intergenic regions revealed enrichment of cis-regulatory elements recognized by transcription factors associated with hormonal signaling, drought response, carbon metabolism, photosynthesis and reproductive development, indicating that regulatory variation represents an important component of grain yield determination. By integrating GWAS signals, candidate gene annotation, cis-regulatory element characterization and the physical proximity between SNPs and cis-regulatory elements, an integrative prioritization strategy identified seven intergenic SNPs as the most promising candidates for functional validation. Together, these findings establish a robust framework for discovering, prioritizing and functionally validating regulatory variants, bridging the gap between statistical associations and biological function while providing a rational strategy for translating GWAS discoveries into molecular breeding of complex traits.

---

## 论文详细总结（自动生成）

# 论文中文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：籽粒产量是水稻中高度复杂的数量性状，受多基因和环境交互影响。GWAS虽能识别与产量相关的遗传位点，但将统计关联转化为具有生物学意义的候选变异（尤其位于非编码调控区域的变异）仍是重大挑战。
- **研究背景**：大量证据表明，表型变异很大程度上源于顺式调控元件的改变，其影响基因表达的强度、时间和空间特异性，而不直接改变蛋白质编码序列。然而，在热带旱稻种质中，调控区域SNP的贡献尚未被充分探索。
- **整体含义**：本研究通过整合GWAS、功能注释和调控基因组学，建立了一个从统计关联到功能候选变异优先筛选的整合框架，旨在为复杂性状的分子育种提供可操作的工具，缩小关联基因组学与功能基因组学之间的差距。

## 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

### 核心思想
将GWAS输出的统计显著性信号与功能注释（编码区基因功能）和调控基因组学（基因间区域的顺式调控元件分析）相结合，通过多层证据（统计显著性、基因功能、调控元件富集、物理邻近性）对候选变异进行优先级排序。

### 关键技术细节与流程
1. **基因分型**：使用基因分型测序（GBS）技术对252份巴西水稻核心种质进行测序，比对到参考基因组Os-Nipponbare-Reference-IRGSP-1.0/MSU7，鉴定得到35,763个SNP（最小等位基因频率0.01，近交系数0.9，位点覆盖率≥0.1）。
2. **群体结构分析**：使用Structure软件估计亚群，Evanno方法确定最佳K=2，分为改良品种/品系和传统地方品种两个遗传群。
3. **GWAS分析**：使用Tassel v5.2.44软件中的混合线性模型（MLM），以群体结构矩阵（Q）为固定效应，亲缘关系矩阵（K）为随机效应。显著关联阈值采用FDR ≤ 0.05。
4. **候选变异功能注释**：
   - 对基因内/附近SNP：使用RiceVarMap和RGAP平台进行基因功能注释。
   - 对基因间SNP：提取相邻基因间序列，使用PlantCARE平台表征顺式调控元件（优先关注与激素响应、水分胁迫、碳代谢、生殖发育和产量调控相关的元件类型：ABRE, MBS, MYC, DRE, W-box, G-box, GARE/P-box, ERE等）。
5. **优先级排序整合策略**：结合统计关联显著性、候选基因功能、基因间区顺式元件富集程度，以及SNP与最邻近调控元件之间的物理距离（以“相邻”或数碱基内为高优先级）确定7个最有希望的基因间SNP。

### 未提供数学公式或伪代码，但流程是清晰的。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：来自巴西水稻核心种质（Embrapa Rice Core Collection）的252份材料，包括栽培品种、优良品系和传统地方品种。表型数据为籽粒产量（rainfed旱稻条件下）。基因型数据为35,763个GBS衍生SNP。
- **基准（Benchmark）**：该研究未与其他已发表的方法进行直接对比，而是提出了自己的整合框架。本质上，其“基准”是传统仅使用GWAS统计显著性进行候选变异筛选的方法。本研究通过增加功能注释和调控元件分析来改进。
- **对比方法**：没有与其他计算工具或模型（如Fine-mapping、eQTL分析等）进行定量比较。研究重点在于提出一个概念性整合框架，而非算法竞赛。
- **实验验证**：未进行功能验证实验（如基因编辑、表达量分析等），仅通过生物信息学分析进行“优先排序”，提出候选变异供后续验证。

## 4. 资源与算力

**论文中未明确提及使用的计算资源**（如GPU型号、数量、训练时长）。但从方法描述可知：
- 使用了常见生物信息学软件（Structure, Tassel, PlantCARE, RiceVarMap等），这些通常在CPU上进行。
- 未涉及深度学习模型训练，因此算力需求不高，属于常规统计分析。

## 5. 实验数量与充分性

- **实验组数量**：仅一套数据集（252份种质，35,763 SNP），进行了一次GWAS分析。
- **消融实验**：无。未比较“仅用GWAS”与“整合方法”在候选变异优先排序上的差异（例如，随机置换、交叉验证等）。
- **充分性分析**：
  - **优点**：对29个显著SNP进行了详细的功能归类，对13个基因间SNP逐一进行了顺式元件表征，并展示了物理距离；提供了7个高优先级候选的详细表格。
  - **不足**：
    1. 样本量相对较小（252份），统计功效有限，可能遗漏许多微效基因。
    2. 未进行任何独立验证（如另一群体或环境下的重复实验）。
    3. 未使用eQTL数据或染色质状态数据（如ATAC-seq、DNase-seq）来直接支持调控功能，仅依赖PlantCARE数据库预测的顺式元件，精度有限。
    4. 未进行模拟实验或与其他优先排序方法（如SIFT, PolyPhen, CADD等）比较。
  - **总体评价**：作为概念验证研究，实验设计是合理的，但充分性不高；结果属于假设生成阶段，亟需功能验证。

## 6. 论文的主要结论与发现

1. **鉴定到29个与旱稻籽粒产量显著关联的SNP**，其中16个位于基因内/附近，13个位于基因间区，揭示了产量的高度多基因性。
2. **候选基因功能广泛**：涉及信号感知（RLK）、代谢物转运（OsALMT7）、氨基酸代谢（苏氨酸合酶）、能量代谢（G6PDH）、激素合成（细胞色素P450）、蛋白质周转（F-box, RING锌指）、RNA加工（PPR, PHF5）和抗病性等，与已报道的经典产量基因（如Gn1a, DEP1等）不同，构成了新的候选。
3. **基因间区SNP富集顺式调控元件**：如ABRE（ABA响应）、MBS（MYB结合）、DRE（脱水响应）、W-box（WRKY结合）、G-box（光响应）、GARE/P-box（赤霉素响应）、ERE（乙烯响应），表明调控变异是产量决定的重要成分。
4. **整合优先级策略产生7个高可能性候选**：基于SNP与顺式元件的物理邻近性（如S3_4047832紧邻STRE元件，S8_5699891紧邻TGA元件等），这7个SNP最值得进行功能验证（基因表达分析、eQTL、启动子活性、基因编辑）。

## 7. 优点：方法或实验设计上的亮点

1. **跨层次的整合思路创新**：将传统的GWAS下游分析从功能注释扩展到调控基因组学，提出了一种“统计关联→功能基因→调控元件→物理邻近性”的多层证据链，具有较强的逻辑说服力。
2. **关注非编码变异**：特别针对大多数GWAS研究忽视的基因间区域，从顺式调控元件角度挖掘调控变异，符合当前数量遗传学前沿。
3. **清晰的优先级排序标准**：不仅定性描述富集，还定量给出了SNP与元件间的核苷酸距离（相邻、1-6核苷酸），增强了可操作性。
4. **候选基因的功能多样性**：发现了多个与已知经典产量基因不同但生理功能收敛的新基因，为分子育种提供了新靶点。
5. **旱稻针对性**：旱稻面临水分胁迫等特殊环境，研究中强调的ABA、干旱响应元件具有生态相关性。

## 8. 不足与局限

1. **缺乏功能验证**：所有结论基于生物信息学预测，未进行任何实验验证（如CRISPR编辑、过表达/敲除、表达量检测），候选变异的因果作用仍为假设。
2. **样本量和统计功效有限**：仅252份材料、35,763个SNP，在旱稻产量这种高度多基因、低遗传力的性状中，检测能力不足，可能遗漏大量重要位点。
3. **调控元件预测依赖数据库**：PlantCARE数据库可能不完整，且未考虑顺式元件的染色质可及性、三维基因组背景，假阳性率可能较高。
4. **未与其他优先排序方法比较**：如Fine-mapping、Bayesian模型、集成优先级算法（例如CADD、GWAS-PW等），无法证明本方法相比已有方法的优势。
5. **未区分因果与连锁**：SNP与调控元件的物理邻近性并不代表因果关系，未考虑LD结构。
6. **未考虑表型和环境互作**：产量表型仅在一个环境（旱稻条件）下评估？论文未明确重复地点或年份，缺乏跨环境的验证。
7. **缺少消融实验**：没有证明整合框架相比仅使用GWAS+基因注释能够有效降低假阳性或提高召回率。

（完）
