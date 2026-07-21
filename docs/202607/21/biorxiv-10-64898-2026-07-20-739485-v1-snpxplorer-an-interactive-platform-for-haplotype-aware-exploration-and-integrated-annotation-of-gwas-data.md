---
title: "snpXplorer: an interactive platform for haplotype-aware exploration and integrated annotation of GWAS data"
title_zh: "snpXplorer: 一个用于GWAS数据单倍型感知探索与整合注释的交互式平台"
authors: "Tesi, N., Green, G. S., Salazar, A., van der Lee, S. J., Hulsman, M., Holstege, H., Reinders, M."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.20.739485v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 单倍型感知的GWAS数据探索与功能注释
tldr: GWAS数据解析面临非编码变异和LD区块挑战，单倍型分析至关重要。snpXplorer平台整合超万个数据集，提供基于LD结构的单倍型表示和统一注释框架，支持跨性状语义相似性探索。以阿尔茨海默症TMEM106B位点为例，揭示单倍型与11种性状的关联，展示协同和拮抗多效性。该平台降低GWAS生物学解读门槛，克服多数据库碎片化查询问题。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739485-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1764, \"height\": 1100, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739485-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1720, \"height\": 617, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739485-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1723, \"height\": 825, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739485-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1723, \"height\": 1141, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739485-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1745, \"height\": 926, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739485-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1736, \"height\": 892, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739485-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1691, \"height\": 943, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739485-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1743, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-20-739485-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1423, \"height\": 1127, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-20-739485-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 711, \"height\": 396, \"label\": \"Table\"}]"
motivation: 现有GWAS解读工具数据集分散，缺乏单倍型感知的集成分析，难以揭示多位点联合效应。
method: 构建交互式平台，集成OpenGWAS超万个数据集，实现基于LD的单倍型聚类、多源注释整合和跨性状语义聚类。
result: 在阿尔茨海默症相关位点识别出与11种性状关联的单倍型，揭示神经和行为表型间的协同多效性。
conclusion: snpXplorer通过单倍型感知和集成注释，简化了GWAS数据的生物学解释，减少了跨数据库查询的碎片化。
---

## 摘要
全基因组关联研究（GWAS）已识别出数千个与复杂性状和疾病相关的位点，但将这些信号转化为生物学洞见仍具挑战性。大多数关联变异是非编码的，且位于连锁不平衡（LD）区块中，其中多个相关变异共同贡献于关联信号。这些簇（即单倍型）可能捕获共享的调控和功能背景。因此，解读GWAS信号需要整合调控、功能和跨性状证据的方法，同时保留疾病相关位点的更广泛的单倍型背景。与此同时，公开可用的GWAS汇总统计数据的快速增长使得大规模跨性状分析成为可能，但也引入了密切相关的表型之间的冗余。因此，对GWAS数据的有效解释需要整合异构数据源的工具，同时保留基因组和生物学背景。我们提出snpXplorer，一个用于GWAS数据单倍型感知探索和注释的交互式网页平台。该平台整合了来自OpenGWAS的超过10,000个GWAS数据集，并支持跨变异、单倍型、基因和性状的多尺度分析。主要功能包括：(i) 基于LD结构的关联信号单倍型表示，(ii) 统一变异注释框架，整合临床注释（ClinVar）、等位基因频率（gnomAD）、功能预测（CADD, AlphaGenome）、数量性状位点（GTEx）、结构变异和GWAS关联，以及(iii) 基于语义相似性的表型聚类实现跨性状探索。以阿尔茨海默病为中心的使用案例展示了其实用性：例如，在TMEM106B位点，snpXplorer识别出一个与十一种不同性状相关的单倍型，揭示了神经和行为表型的协同多效性以及与身高的拮抗多效性。snpXplorer允许用户浏览、筛选和检查变异、单倍型、基因和性状层面的证据，降低了GWAS结果生物学解读的门槛。与专注于GWAS解读特定方面的现有工具相比，snpXplorer的优势在于它减少了跨数据库的碎片化查询需求。

## Abstract
Genome-wide association studies (GWAS) have identified thousands of loci associated with complex traits and diseases, yet translating these signals into biological insight remains challenging. Most associated variants are non-coding and reside in linkage disequilibrium (LD) blocks, where multiple correlated variants jointly contribute to association signals. These clusters, or haplotypes, may capture shared regulatory and functional contexts. Interpreting GWAS signals thus requires approaches that integrate regulatory, functional, and cross-trait evidence, while preserving the broader haplotypic context of disease-associated loci. At the same time, the rapid growth of publicly available GWAS summary statistics has enabled large-scale cross-trait analyses, but also introduced redundancy across closely related phenotypes. Efficient interpretation of GWAS data therefore requires tools that integrate heterogeneous data sources while preserving genomic and biological contexts. We present snpXplorer, an interactive web platform for haplotype-aware exploration and annotation of GWAS data. The platform incorporates >10,000 GWAS datasets from OpenGWAS and enables multi-scale analysis across variants, haplotypes, genes, and traits. Key features include (i) a haplotype-based representation of association signals derived from LD structure, (ii) a unified variant annotation framework integrating clinical annotations (ClinVar), allele frequencies (gnomAD), functional predictions (CADD, AlphaGenome), quantitative trait loci (GTEx), structural variation, and GWAS associations, and (iii) cross-trait exploration using semantic similarity-based clustering of phenotypes. Use cases centered on Alzheimer's disease illustrate this utility: for example, at the TMEM106B locus, snpXplorer identified a haplotype linked to eleven distinct traits, revealing synergistic pleiotropy across neurological and behavioral phenotypes alongside antagonistic pleiotropy with height. snpXplorer allows users to browse, filter, and inspect variant-, haplotype-, gene- and trait-level evidence, lowering the barrier to biological interpretation of GWAS results. Compared with existing tools that focus on specific aspects of GWAS interpretation, the strength of snpXplorer is that it reduces the need for fragmented queries across databases.

---

## 论文详细总结（自动生成）

# snpXplorer: 一个用于 GWAS 数据单倍型感知探索与整合注释的交互式平台

## 1. 论文的核心问题与整体含义

- **研究动机**：GWAS 已发现数千个与复杂性状/疾病相关的位点，但大部分关联变异位于非编码区且处于连锁不平衡（LD）区块中，多个相关变异共同贡献于关联信号。这些 LD 簇（单倍型）可能比单个 SNP 更具生物学意义，能捕获共享的调控和功能背景。同时，公开 GWAS 汇总统计数量激增（>10,000 个），但带来表型冗余，跨性状分析需要集成多种数据源的工具。
- **整体含义**：现有工具通常仅聚焦于 GWAS 解读的某一方面（如 LocusZoom 的区域可视化、ClinVar 的临床变异、PheWAS 的关联查询等），导致用户需在多个数据库间碎片化查询。snpXplorer 旨在提供一个**单倍型感知**的一体化交互平台，整合变异注释、LD 结构、跨性状关联，降低 GWAS 生物学解读的门槛。

## 2. 论文提出的方法论：核心思想与关键技术

- **核心思想**：以单倍型作为关联信号的基本单元，集成多源注释（临床、人群频率、功能预测、QTL、结构变异、GWAS 关联），并通过语义相似性聚类减少表型冗余，支持从变异到单倍型到基因到表型的多尺度导航。
- **关键技术细节**：
  - **单倍型定义**：
    1. 根据 UCSC 基因组浏览器的重组率（阈值=25 cM/Mb）将基因组分割为子区域；
    2. 使用来自 4,777 名欧洲无关个体的基因型数据，在每个子区域内计算所有变异对的 LD（R²）；
    3. 采用**完全连锁层次聚类**，以 LD 为距离度量，确保簇内所有成对 LD > 0.1，从而形成单倍型。
  - **变异注释框架**：
    - 集成来源：ClinVar（临床注释）、gnomAD（跨祖先等位基因频率）、CADD & AlphaGenome（功能预测）、GTEx（eQTL/sQTL）、结构变异（SINE、LINE、串联重复）、OpenGWAS 表型关联。
    - 对于查询变异，自动扩展至 LD R²>0.6 的伙伴变异，以提升因果基因识别。
  - **跨性状探索**：
    - 使用预训练的生物医学语言模型**BioLORD-2023**（权重 0.70）和**SapBERT**（权重 0.30）对 GWAS 表型描述生成嵌入向量，经 L2 归一化后加权拼接。
    - 计算余弦距离，用**层次聚类（平均链接）** 分组，阈值 0.5；孤立性状重新分配给余弦相似度≥0.4 的最近非孤立簇。
    - 可视化：UMAP 降维 + 簇间热图。
  - **PRS 模块**：对于 OpenGWAS 中任何性状，预计算基于 clumping-and-thresholding（LD R²=0.05，窗口=500 kbp）的变异集，供用户下载用于外部 PRS 工具。
- **算法流程**（文字描述）：
  1. 用户输入一个性状/基因/变异；
  2. 平台从 OpenGWAS 提取该性状的 GWAS 汇总统计；
  3. 根据预先计算的 LD 结构将显著变异（p<5×10⁻⁸）聚类为单倍型；
  4. 输出单倍型组成、关联表型列表、效应方向热图；
  5. 用户可点击进入变异注释模块，查看多源注释及 LD 伙伴信息；
  6. 可选则进行基因集富集分析（gProfiler）并基于语义相似性聚类通路。

## 3. 实验设计

- **使用数据集**：
  - GWAS 数据：>10,000 个研究来自 **OpenGWAS** 数据库（IEU 平台）。
  - 参考基因型：4,777 名欧洲无关个体的基因分型数据（用于 LD 计算，来源见作者之前的研究[16]）。
  - 注释数据库：ClinVar、gnomAD v3/4、CADD、AlphaGenome、GTEx v8、RefSeq、结构变异数据库。
- **实验场景（三个典型案例）**：
  1. **性状中心的单倍型发现**：以阿尔茨海默病（AD）为例，从 OpenGWAS 检索 18 个相关 GWAS（含 AD 及密切表型，如父母 AD 史），识别出 5,505 个显著 SNP，映射到 227 个单倍型。
  2. **基因中心的跨性状单倍型探索**：以 **TMEM106B** 基因为查询对象，识别出 22 个常见单倍型，其中单倍型 B（52 kb，24 个 SNP）与 11 种神经/行为性状（神经质、抑郁、睡眠时长）相关，且与身高呈拮抗多效性；单倍型 A（38 kb，120 个 SNP）与 28 种性状相关。
  3. **单变异注释**：以 rs7908662（PLEKHA1 附近）为例，展示等位基因频率、QTL、AlphaGenome 预测（影响 PLEKHA1 和 MIR3941 在脑细胞中的表达）、GWAS 关联（与 23 个性状显著相关，包括 AD 保护效应及与身高的拮抗效应）。
- **Benchmark 对比**：论文提供了与主流工具的对比表（Table S10），提及 LocusZoom、FUMA、Open Target Genetics、PheWeb、PhenoScanner、GWAS Atlas、SNiPA 等。但**未进行定量实验对比**，仅定性说明 snpXplorer 在单倍型感知和集成度上的优势。

## 4. 资源与算力

- 论文未明确提及实验所使用的 GPU 型号、数量或训练时长。仅提到部分计算在 **Spider 超算**上完成，由 SURF Cooperative 支持，计算时长由荷兰科研委员会（NWO）项目拨款（如 100plus、Role of VNTRs in AD 等），但未给出具体小时数。
- 注释模块（如 AlphaGenome）的预测结果来自外部数据库，不涉及本地模型训练。
- **不足之处**：缺乏具体的计算资源描述，不利于可重复性评估。

## 5. 实验数量与充分性

- **实验数量**：论文主要展示 3 个使用案例（AD 全基因组单倍型、TMEM106B 基因位点、rs7908662 变异），每个案例都配有交互式可视化截图和表格（共 9 个主图/表）。
- **充分性评价**：
  - **优点**：案例覆盖了平台的主要模块（单倍型、注释、跨性状），且涉及不同尺度（全基因组、基因位点、单变异）。
  - **不足**：
    - 缺乏**消融实验**（如比较有无单倍型聚合对因果基因识别的影响）；
    - 缺乏**正式的性能对比**（如与 FUMA 或 Open Targets 在相同数据集上的运行时间、注释覆盖率等）；
    - 仅以欧洲人群为例，未验证跨种族表现；
    - 未进行大规模用户测试或稳定性评估。
  - 总体而言，实验设计偏向功能演示而非严格的统计验证，充分性属于中等偏低。

## 6. 论文的主要结论与发现

1. **单倍型层面更能揭示多效性**：在 TMEM106B 位点，单倍型 B 同时与 11 种神经/行为性状关联，揭示了协同多效性；而单个 SNP 可能无法体现这种联合效应。
2. **集成注释减少碎片化**：通过统一界面整合 ClinVar、gnomAD、CADD、GTEx 等，用户无需在多个数据库间切换。
3. **语义相似性聚类有效降低冗余**：如 AD 相关表型（包括父母 AD 史）被聚类在同一组，邻近簇为帕金森病、神经质等，有助于跨疾病比较。
4. **实用性**：支持 PRS 变异集下载，方便下游多基因风险评分计算。

## 7. 优点

- **单倍型感知**：是少数将单倍型作为分析单元的 GWAS 解读工具，比单 SNP 视角更贴近生物学现实（如多个 LD 变异共同影响调控元件）。
- **数据库集成度极高**：同时整合临床、人群频率、功能预测、QTL、结构变异和 GWAS 关联，且支持 LD 扩展注释。
- **交互性与实时性**：基于 Web 的点击式界面，无需安装，支持实时过滤和下载。
- **跨性状探索创新**：使用大语言模型嵌入进行语义聚类，而非简单关键字匹配，能捕捉表型间的概念相似性。
- **开源与免费**：代码（MIT 许可证）和网站完全公开，无注册限制，支持批量作业。

## 8. 不足与局限

- **人群偏差**：单倍型定义目前仅基于欧洲个体基因型数据，无法直接推广到其他祖先群体，可能会遗漏或错误表征跨种族特异性单倍型。
- **语义聚类非遗传相关**：跨性状分组基于表型描述的语义相似性，而非 LD 评分或遗传相关性。这意味着语义上相似的性状不一定具有共享的遗传结构，可能引入误导。
- **缺乏严格基准测试**：未与现有工具在同一数据集上进行定量比较（如运行时间、注释召回率、因果基因排名），说服力有限。
- **依赖外部数据库**：功能预测（AlphaGenome）和 GWAS 数据（OpenGWAS）均为第三方来源，其更新和质控可能影响结果可靠性；如某些数据库更新滞后或停止维护，平台需适配。
- **PRS 模块局限性**：仅提供预先计算好的变异集，不支持用户自定义 clumping 参数（如 R² 阈值、窗口大小），且必须搭配外部工具使用。
- **计算资源描述不完整**：未说明服务器配置或响应速度，用户在大并发场景下的体验未知。
- **单倍型定义阈值主观**：LD>0.1 作为簇内联结阈值，可能过松导致包含弱相关变异；不同 LD 阈值对结果的影响未被探讨。

（完）
