---
title: "DPCGS: a computational framework for linking GWAS to single-cell transcriptomics in complex traits and diseases"
title_zh: DPCGS：一个将复杂性状与疾病的GWAS关联到单细胞转录组学的计算框架
authors: "Liu, C., Shen, B., Li, J., Zhu, R., Yang, P., Wu, B., Xuan, Y., Yang, S., Yuan, B., Yang, N., Ma, L., Liu, Q., Dai, S., Zhang, Y."
date: 2026-07-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.14.738331v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 整合GWAS与单细胞转录组的框架
tldr: 复杂性状和疾病由遗传变异与细胞异质性共同作用，但将GWAS关联到特定细胞类型仍有困难。DPCGS框架整合GWAS汇总统计与单细胞RNA测序数据，通过比较基因在相关细胞与对照中的表达来识别关键细胞群和基因。基准测试中DPCGS精度和灵敏度优于现有方法，成功在阿尔茨海默病中锁定少突胶质细胞、星形胶质细胞，在哮喘中锁定巨噬细胞、B细胞。该框架为解析复杂性状的细胞分子机制提供了通用工具，有助于生物标志物发现和治疗开发。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738331-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 925, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738331-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1371, \"height\": 1633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738331-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 901, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738331-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 1747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738331-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1431, \"height\": 1006, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738331-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 952, \"label\": \"Figure\"}]"
motivation: 连接GWAS发现的遗传变异与单细胞转录组中的具体细胞类型，以理解复杂性状和疾病的细胞基础。
method: DPCGS框架基于GWAS优先基因在相关细胞中表达升高的原理，整合GWAS汇总统计与单细胞RNA测序数据，系统性鉴定细胞群、基因和调控程序。
result: 基准测试DPCGS优于现有方法；锁定阿尔茨海默病少突胶质细胞和星形胶质细胞，哮喘巨噬细胞和B细胞，发现CD74、FOS、FLI1、AP-1。
conclusion: DPCGS作为解析复杂性状和疾病细胞分子基础的多功能框架，助力生物标志物发现和治疗开发。
---

## 摘要
复杂性状和疾病源于遗传变异与细胞异质性之间的相互作用，因此理解遗传风险如何在细胞水平上显现至关重要。然而，由于细胞复杂性和非编码变异普遍存在，将全基因组关联研究（GWAS）与特定细胞群体联系起来仍然具有挑战性。在此，我们提出DPCGS，一个系统性地整合GWAS汇总统计数据与单细胞RNA测序（scRNA-seq）数据以识别性状相关细胞群体、基因和调控程序的计算框架。DPCGS基于以下原则：与匹配对照组相比，GWAS优先基因应在相关细胞中表现出更高的表达。使用模拟数据集的基准分析表明，DPCGS持续优于现有方法，在检测性状相关细胞方面具有更高的准确性和敏感性。将其应用于不同的scRNA-seq数据集进一步验证了其稳健性，揭示了少突胶质细胞和星形胶质细胞是阿尔茨海默病的关键亚群，以及巨噬细胞和B细胞是哮喘的关键亚群。这些分析还强调了潜在的分子调控因子，包括CD74、FOS、FLI1和AP-1转录因子。总之，这些发现确立了DPCGS作为一个多功能框架，用于解析复杂性状和疾病的细胞与分子基础，对生物标志物发现和治疗方法开发具有广泛意义。

## Abstract
Complex traits and diseases arise from the interplay between genetic variation and cellular heterogeneity, making it essential to understand how genetic risk manifests at the cellular level. However, connecting genome-wide association studies (GWAS) to specific cell populations remains challenging due to cellular complexity and the prevalence of noncoding variants. Here, we present DPCGS, a computational framework that systematically integrates GWAS summary statistics with single-cell RNA-sequencing (scRNA-seq) data to identify trait-associated cell populations, genes, and regulatory programs. DPCGS is based on the principle that GWAS-prioritized genes should exhibit elevated expression in relevant cells compared with matched controls. Benchmark analyses with simulated datasets showed that DPCGS consistently outperforms existing methods, achieving higher accuracy and sensitivity in detecting trait-relevant cells. Applications to diverse scRNA-seq datasets further validated its robustness, revealing oligodendrocytes and astrocytes as key subpopulations in Alzheimer's disease and macrophages and B cells in asthma. These analyses also highlighted potential molecular regulators, including CD74, FOS, FLI1, and AP-1 transcription factors. Together, these findings establish DPCGS as a versatile framework for dissecting the cellular and molecular basis of complex traits and diseases, with broad implications for biomarker discovery and therapeutic development.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：复杂性状和疾病（如阿尔茨海默病、哮喘）由遗传变异与细胞异质性共同驱动，但GWAS发现的大多数变异位于非编码区，难以直接解释其功能角色。如何将GWAS遗传信号与单细胞分辨率下的特定细胞类型/亚群精确关联，是当前计算生物学的重要挑战。
- **研究动机**：现有方法（如scDRS、scPagwas）在灵敏度、特异性和可扩展性方面存在局限，无法系统识别疾病相关细胞亚群及其分子调控因子。
- **整体含义**：建立一种稳健、准确、可扩展的框架，将遗传关联与单细胞表达谱整合，揭示疾病在细胞层面的因果机制，为生物标志物发现和治疗靶点开发提供新途径。

## 2. 方法论：核心思想、关键技术细节与算法流程

- **核心思想**：基于“GWAS优先基因在相关细胞中应比随机基因集有更高表达”的原理，将GWAS汇总统计与scRNA-seq数据整合，量化每个细胞的性状关联性。
- **关键步骤（算法流程）**：
    1. **构建疾病相关基因集**：使用MAGMA框架对GWAS汇总统计进行基因水平关联分析。将SNP映射到基因（默认±20 kb窗口），基于LD矩阵计算基因检验统计量，取排名前1000的基因作为候选基因集。
    2. **计算疾病评分与控制评分**：
        - 对每个细胞，计算候选基因集的平均表达作为**原始疾病评分**。
        - 随机抽取1000个相同大小的背景基因集，计算每个细胞的**背景控制评分**。
        - 对原始评分减去背景平均分，然后进行z-score标准化，最后通过sigmoid函数映射到(0,1)区间，得到**最终疾病模块评分（TRS）**。
    3. **统计显著性评估**：对每个细胞，将其TRS与1000个背景控制得分的经验分布比较，计算经验p值，并使用Benjamini-Hochberg方法进行多重假设检验校正（FDR控制）。
- **下游分析**：基于TRS进行细胞类型水平、基因水平和调控因子水平的分析，包括差异表达分析、通路富集分析（Reactome）和基因调控网络分析（SCENIC）。

## 3. 实验设计：数据集、基准测试与对比方法

- **模拟数据集**：
    - 基于scDesign2生成，参考FACS分选的血细胞数据（GSE107011）。
    - **单核细胞计数性状**：1000个单核细胞（正例）+ 1000个其他细胞（T、B、NK、DC），各125个。
    - **NK细胞比例性状**：NK细胞为正例，其余为负例（比例类似）。
- **真实scRNA-seq数据集**：
    - **BMMC数据集**（n=35,582）：用于单核细胞计数性状验证。
    - **PBMC数据集**（n=97,039）：用于NK细胞比例性状验证。
    - **外周血免疫细胞数据集**（n=32,738）：用于NK细胞比例性状验证。
    - **人脑snRNA-seq数据集**（内嗅皮层，n=13,214）：用于阿尔茨海默病分析（GWAS: 21,982病例+41,944对照）。
    - **人肺scRNA-seq数据集**（n=10,360）：用于哮喘分析（GWAS: UK Biobank哮喘数据）。
- **GWAS数据来源**：IEU OpenGWAS数据库，包括单核细胞计数（ukb-d-30130_irnt）、NK细胞百分比（ebi-a-GCST90001647）、阿尔茨海默病（ieu-b-2）、哮喘（ukb-d-J10_ASTHMA）。
- **对比方法**：scDRS、scPagwas。
- **评估指标**：AUROC（ROC曲线下面积）和AUPR（精确率-召回率曲线下面积）。

## 4. 资源与算力

- **文中未明确说明**：论文未提及使用的GPU型号、数量、训练时长等算力信息。仅提到“计算资源由昆明理工大学提供”，但无具体规格。
- **备注**：由于DPCGS方法主要依赖MAGMA（CPU）和单细胞表达矩阵的运算，整体计算负担应属于中等水平，但大规模数据集（如97,039细胞）也需要一定内存和计算时间。

## 5. 实验数量与充分性

- **实验组数量**：
    - 模拟数据实验：2个性状（单核细胞计数、NK细胞比例） × 2指标（AUROC、AUPR） = 主要对比实验4组。
    - 真实数据实验：4个数据集 × 3种方法对比 = 12组主要实验，加上后续AD和哮喘的细胞亚群识别、差异表达、通路富集、调控因子分析等约6组（含图5、图6各子图）。
    - 总计约20余组定量或定性实验。
- **充分性评价**：
    - **充分**：模拟+真实数据覆盖了不同大小、不同组织来源、不同性状类型（免疫数量性状、复杂疾病）的数据，对比方法均为当前主流方法，评估指标客观。
    - **公平性**：所有对比方法均使用相同输入数据（GWAS汇总统计+单细胞表达矩阵），且参数设置遵循各自默认或推荐配置，较为公平。
    - **局限性**：未进行消融实验（如不同基因集大小、不同控制基因集数量对性能的影响），也未在更多疾病上验证（仅AD和哮喘两个疾病）。

## 6. 主要结论与发现

- **性能优势**：在模拟和真实数据上，DPCGS在AUROC和AUPR上均显著优于scDRS和scPagwas，尤其在模拟数据中AUROC>0.99、AUPR>0.98。真实数据上，AUC差距在0.03~0.28之间，AUPR差距更大（如在单核细胞计数BMMC数据上AUPR: 0.825 vs scDRS 0.685, scPagwas 0.237）。
- **疾病特异性发现**：
    - **阿尔茨海默病**：鉴定出少突胶质细胞和星形胶质细胞为主要关联细胞群；高表达基因CD74、FOS、FLI1；富集于免疫相关通路（T细胞活化、信号转导、细胞因子释放）。
    - **哮喘**：巨噬细胞和B细胞为关键免疫亚群；FOS显著上调；富集于中性粒细胞脱颗粒通路；AP-1家族转录因子（JUNB、FOS、FOSB）为关键调控因子。
- **整体意义**：DPCGS是一个通用框架，可解析复杂性状的细胞和分子基础，具有广泛的 biomarker 和治疗开发应用潜力。

## 7. 优点

- **方法创新性**：将GWAS基因优先化（MAGMA）与单细胞表达评分相结合，并通过匹配随机基因集构建经验分布，减少技术噪声和批次效应。
- **鲁棒性**：在模拟和多个真实数据集（大小从1万到10万细胞）上一致表现优异，且对性状类型不敏感。
- **可解释性**：输出细胞级TRS和p值，支持多层级下游分析（细胞类型、基因、调控因子），提供机制见解。
- **与现有方法对比的优势**：在准确率、敏感性和可扩展性上均优于scDRS和scPagwas，尤其是在scPagwas表现极差的情况下（模拟AUC约0.1~0.3），DPCGS仍保持高精度。
- **代码和数据公开**：代码开源（GitHub），GWAS和scRNA-seq数据均来自公共数据库，可复现。

## 8. 不足与局限

- **对GWAS质量依赖**：DPCGS的准确性强烈依赖于GWAS汇总统计的质量以及MAGMA基因映射的准确性（±20kb窗口可能遗漏长距离调控或远端增强子效应）。
- **scRNA-seq技术噪声**：数据仍受稀疏性、dropout和批次效应影响，虽用标准化和控制基因集部分缓解，但可能仍有偏差。作者提到可进一步整合scATAC-seq或空间转录组学来提升。
- **缺乏因果验证**：本工作为关联分析，未结合CRISPR等扰动实验或孟德尔随机化进行因果推断，发现的细胞亚群和基因仅为潜在关联而非因果关系。
- **实验覆盖不足**：仅测试了两个疾病（AD和哮喘），未在其他类型复杂疾病（如糖尿病、自身免疫病）或组织类型上验证。未做消融实验分析参数敏感性。
- **计算资源未汇报**：缺乏运行时间和硬件需求的量化评估，不利于其他研究者的复现和资源规划。
- **方法局限性**：依赖于先验的细胞类型注释（来自聚类），若注释不准可能影响下游分析；控制基因集的随机抽样可能引入偏差（未采用严格匹配表达分布的策略）。

（完）
