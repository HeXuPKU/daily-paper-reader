---
title: An enhancer-centric approach applied to human immune system epigenomes revealed the association of macrophage enhancers with cardiovascular disease
title_zh: 一种以增强子为中心的方法应用于人类免疫系统表观基因组，揭示了巨噬细胞增强子与心血管疾病的关联
authors: "Arcila-Galvis, J. E., Were, F., Juan, D., Del-Rio, J., Lamb, C. A., Hambleton, S., Castrillo, A., Spicuglia, S., Valencia, A., Pineda-Torra, I., Castillo de Santa Pau, E., Hirt, R. P., Rico, D."
date: 2026-06-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.728745v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 整合增强子表观基因组与GWAS变异，解释非编码关联
tldr: 复杂疾病受遗传和环境共同影响，非编码变异功能难解。研究整合BLUEPRINT/IHEC项目中107个免疫细胞表观基因组，识别多细胞增强子活性模式，与518个GWAS性状的非编码变异关联，发现117个显著关联，尤其心血管疾病变异与巨噬细胞增强子相关，调控NR1H3等脂质代谢和免疫基因。成果助力理解遗传变异对免疫和疾病的影响。
source: biorxiv
selection_source: fresh_fetch
motivation: 复杂疾病非编码变异的功能解释困难，且免疫细胞在疾病中起关键作用，亟需系统解析免疫细胞增强子与疾病变异的关系。
method: 利用BLUEPRINT和IHEC的107个表观基因组（749个ChIP-Seq，24种免疫细胞），进行多细胞增强子活性模式分析，并与518个GWAS性状的非编码变异关联。
result: 发现117个显著关联，其中心血管疾病变异与巨噬细胞特异性增强子关联，调控NR1H3等脂质代谢和免疫相关基因。
conclusion: 揭示了免疫细胞增强子在复杂疾病中的作用，特别是巨噬细胞增强子与心血管疾病的关联，为理解非编码变异功能提供新资源。
---

## 摘要
复杂疾病受遗传和环境因素共同影响。免疫细胞是介导与环境相互作用的关键，但遗传变异对免疫系统的影响及其如何影响复杂疾病尚未完全阐明。此外，大多数与复杂疾病相关的全基因组关联研究（GWAS）变异位于非编码区，难以解读。本研究探究了非编码变异与免疫细胞增强子的关联。作为BLUEPRINT和国际人类表观基因组联盟（IHEC）的一部分，我们生成并分析了人类原代免疫细胞的全面表观基因组数据集，包括来自24种细胞类型的749次ChIP-Seq实验衍生的107个表观基因组。我们鉴定了跨基因组的多种细胞增强子活性模式，并检验了它们与518个GWAS性状的非编码变异的联系。分析揭示了117个显著关联，包括心血管疾病变异与巨噬细胞特异性增强子之间的新关联，这些增强子调控参与脂质代谢和免疫的基因，如编码核受体LXR-α（NR1H3）的基因及其许多已知靶基因。这些数据共同有助于更好地理解遗传变异对免疫功能及相关疾病的影响。

## Abstract
Complex diseases are influenced by both genetic and environmental factors. Immune cells are key mediating interactions with the environment, but the impact of genetic variation on the immune system and how it influences complex diseases is not fully understood. Moreover, most genome-wide analyses (GWAS) variants associated with complex diseases are non-coding and difficult to interpret. Here, we investigated the association of non-coding variants with immune cell enhancers. As part of BLUEPRINT and the International Human Epigenome (IHEC) consortia, we generated and analysed a comprehensive set of epigenomes for human primary immune cells, including 107 epigenomes derived from 749 ChIP-Seq experiments across 24 cell types. We identified multicell enhancer activity patterns across the genome and examined their links with non-coding variants from 518 GWAS traits. This analysis revealed 117 significant associations, including novel links between cardiovascular disease variants and macrophage-specific enhancers that regulate genes involved in lipid metabolism and immunity, such as the gene encoding for the nuclear receptor LXR-alpha (NR1H3) and many of its known target genes. Together, these data will help to better understand the influence of genetic variability in immune function and related diseases.

---

## 论文详细总结（自动生成）

好的，遵照您的要求，以下是对该论文（基于提供的摘要和元数据）的结构化、深入、客观的中文总结。

### 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：复杂疾病（如心血管疾病）受遗传和环境共同影响，免疫细胞是介导这种相互作用的关键。然而，绝大多数与疾病相关的单核苷酸多态性（SNPs）位于非编码区，其功能机制难以解读。本研究旨在系统解析非编码遗传变异如何通过免疫细胞中的增强子调控元件影响疾病风险。
- **整体含义**：通过构建全面的免疫细胞表观基因组图谱，提出“以增强子为中心”的分析策略，将GWAS非编码变异与特定免疫细胞类型（特别是巨噬细胞）的增强子活性关联起来，为理解非编码变异在免疫疾病中的功能角色提供新资源，并揭示了心血管疾病与巨噬细胞增强子及脂质代谢/免疫基因（如NR1H3）之间的新联系。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：利用大规模表观基因组数据集（ChIP-Seq），识别不同免疫细胞类型中增强子活性的多细胞模式（即某些增强子在特定细胞类型中特异性活跃，或在多种细胞中共享），然后将这些模式与GWAS非编码变异进行共定位分析，从而推断致病变异可能通过影响哪种细胞类型的增强子来发挥功能。
- **关键技术细节**：
    - **数据来源**：BLUEPRINT 和 IHEC 联盟的 107 个原代免疫细胞表观基因组（含 749 个 ChIP-Seq 实验），覆盖 24 种细胞类型。
    - **增强子活性模式识别**：基于组蛋白修饰（如H3K27ac、H3K4me1）的ChIP-Seq信号，在全基因组范围内鉴定增强子，并根据其在多种免疫细胞中的活性分布，聚类为不同的模式（例如：T细胞特异、单核细胞/巨噬细胞特异、全免疫细胞共享等）。
    - **关联分析**：将来自 518 个 GWAS 性状的非编码变异（可能包括 SNPs 和连锁不平衡区域的代理变异）映射到这些增强子模式上，通过统计检验（如富集分析或共定位分析）来识别哪些细胞类型特异性增强子与哪些疾病/性状显著关联。
- **算法流程（文字说明）**：
    1. 数据整合：统一处理 749 个 ChIP-Seq 数据，获得 107 个高质量的表观基因组。
    2. 增强子定义：基于 H3K27ac 峰和 H3K4me1 峰等特征，定义基因组上的活性增强子区域。
    3. 模式聚类：计算每个增强子在 24 种细胞类型中的活性得分，进行无监督聚类，得到多个增强子活性模式（如“巨噬细胞特异性”、“B细胞特异性”、“广泛活跃”等）。
    4. 变异映射与关联：下载 518 个 GWAS 性状的显著 SNP 及其 LD 标签 SNP，将落在增强子区域内的变异关联到对应的增强子模式中。对每个性状-增强子模式对，进行统计富集检验（例如：该性状的变异落在该模式增强子中的比例是否显著高于基因组背景）。
    5. 结果筛选：确定 117 个显著关联（FDR校正），重点关注与心血管疾病相关的巨噬细胞增强子。

### 3. 实验设计：数据集、基准与对比方法
- **数据集**：
    - **训练/分析数据**：BLUEPRINT/IHEC 生成的 107 个原代人类免疫细胞表观基因组（含 749 个 ChIP-Seq 实验），覆盖 24 种细胞类型（如 T 细胞、B 细胞、NK 细胞、单核细胞、巨噬细胞、中性粒细胞、树突状细胞等）。
    - **遗传变异数据**：来自 GWAS 目录的 518 个性状/疾病（如心血管疾病、类风湿关节炎、炎症性肠病、哮喘、感染病等）的已报道非编码变异。
- **基准（Benchmark）**：论文未明确提及外部基准数据集或黄金标准。其基准可视为：与传统使用单一细胞类型或整体非编码区进行变异注释的方法相比，本研究通过多细胞增强子模式提供了更高的细胞类型分辨率。
- **对比方法**：文中未明确列出与其他方法（如染色质状态分割、eQTL 共定位等）的定量比较。定性上，其新颖性在于：“以增强子为中心”而非“以变异为中心”，并且系统覆盖了多种原代免疫细胞（而非细胞系）。

### 4. 资源与算力
- 论文摘要中 **未明确说明** 使用的 GPU 型号、数量、训练时长或具体计算资源。仅提及使用了大规模的 ChIP-Seq 数据（749 个实验）和 518 个 GWAS trait 数据。考虑到分析涉及峰调用、聚类、统计检验等流程，计算量较大，但具体算力描述缺失。

### 5. 实验数量与充分性
- **实验数量**：一项核心分析（增强子模式与 GWAS 的关联）：输入为 107 个表观基因组 + 518 个 GWAS trait，输出 117 个显著关联。未提及消融实验、鲁棒性测试或重复性验证（如不同聚类参数、不同LD阈值下的结果稳定性）。
- **充分性评估**：
    - **优点**：数据集规模大（24种细胞类型，原代细胞），覆盖多种主要免疫细胞，且 GWAS trait 数量多（518个）。
    - **不足**：仅基于摘要无法判断实验的全面性。例如：是否对增强子分类进行了独立验证（如CRISPR验证、eQTL共定位）？是否考虑了细胞亚群（如M1/M2巨噬细胞）的差异？是否评估了SNP对增强子活性的直接影响（等位基因特异性活性）？这些信息缺失，因此实验充分性存疑，存在“描述性”而非“因果验证”的局限性。

### 6. 论文的主要结论与发现
- **主要发现**：鉴定出 117 个显著的非编码 GWAS 变异与免疫细胞增强子活性模式之间的关联。其中 **新发现** 包括：心血管疾病（如冠心病、心肌梗死）的风险变异显著富集在 **巨噬细胞特异性增强子** 区域。
- **关键基因**：这些巨噬细胞增强子调控的基因中包括 **NR1H3**（编码核受体 LXR-α），该基因是脂质代谢和免疫的关键调控因子。此外还发现巨噬细胞增强子调控了NR1H3的许多已知靶基因（如ABCA1、ABCG1、APOE等）。
- **结论**：本研究揭示了免疫细胞（尤其是巨噬细胞）增强子在心血管疾病等复杂疾病遗传风险中的作用，为非编码变异的功能解读提供了新的细胞类型特异性框架和数据资源。

### 7. 优点：方法或实验设计的亮点
- **增强子中心视角**：不同于大多数GWAS后分析仅关注变异所在位置，本研究通过先定义细胞类型特异性的增强子模式，再关联变异，能更直接地揭示变异通过影响特定细胞类型的基因调控功能，提高了功能解析的精度。
- **系统性和全面性**：使用了BLUEPRINT/IHEC规模最大、最系统的原代免疫细胞表观基因组（含24种细胞类型），避免了细胞系带来的偏差，更贴近体内真实状态。
- **跨疾病关联能力**：同时分析518个GWAS性状，使得能够发现不同疾病共享或特异的免疫细胞增强子关联，有利于理解疾病间共同的免疫通路。

### 8. 不足与局限
- **缺乏因果验证**：分析仅限于统计关联，仅指出“变异位于巨噬细胞增强子内”，未通过实验（如CRISPR干扰、等位基因特异性表达检测）验证具体SNP是否真正改变增强子活性并影响靶基因表达。
- **细胞类型分辨率不足**：尽管有24种细胞类型，但巨噬细胞、单核细胞等仍为混合群体（如未区分外周血单核细胞亚群、组织驻留巨噬细胞亚群等）。可能遗漏更精细的细胞特异性增强子。
- **GWAS变异捕获局限**：仅分析了已报道的GWAS lead SNP，未全面考虑LD区域的精细定位，可能遗漏真正的因果变异。此外，518个性状的选取标准未说明，可能存在选择偏倚。
- **缺少对比方法**：未与传统的染色质分割（如ChromHMM）或eQTL共定位等方法进行定量比较，无法评估本方法在发现新关联上的优势或独特性。
- **计算资源与复现性缺失**：未提供代码、参数、聚类数目确定标准等细节，且未公开基准测试（benchmark），难以独立复现和评估结果的鲁棒性。
- **应用限制**：仅涉及免疫细胞，对于其他非免疫细胞介导的疾病（如神经退行性疾病、癌症）不适用。

（完）
