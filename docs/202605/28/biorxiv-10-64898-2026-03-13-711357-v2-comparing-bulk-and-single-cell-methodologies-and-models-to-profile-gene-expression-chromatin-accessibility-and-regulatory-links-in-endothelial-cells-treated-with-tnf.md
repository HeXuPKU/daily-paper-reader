---
title: "Comparing bulk and single-cell methodologies and models to profile gene expression, chromatin accessibility and regulatory links in endothelial cells treated with TNFα"
title_zh: 比较批量与单细胞方法学及模型用于分析TNFα处理的内皮细胞中的基因表达、染色质可及性和调控连接
authors: "Zevounou, J., Lo, K. S., McGinnis, C. S., Satpathy, A. T., Lettre, G."
date: 2026-05-27
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.13.711357v2.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 比较bulk与单细胞方法连接非编码GWAS变异与基因
tldr: GWAS发现的非编码变异难以定位因果基因，通常依赖物理相互作用或统计模型。本文以TNFα处理的人内皮细胞为模型，对比bulk和单细胞RNAseq/ATACseq谱图及增强子-基因预测模型（ABC、scE2G）的效果。尽管bulk和单细胞谱图相似，但在冠心病和舒张压GWAS分析中，两种模型在遗传力捕获、精细定位变异和基因优先排序上存在差异，例如一个CAD位点ABC预测BCAR1而scE2G优先选择CFDP1。结果表明，选择bulk或单细胞方法会影响调控链接预测，设计实验验证GWAS发现时需考虑此因素。
source: biorxiv
selection_source: fresh_fetch
motivation: 对比bulk和单细胞方法及模型在基因表达、染色质可及性和调控链接分析中的差异，以指导GWAS因果基因优先排序。
method: 使用TNFα处理的人内皮细胞，生成bulk和scRNAseq/ATACseq数据，并应用ABC、scE2G等增强子-基因预测模型。
result: bulk与sc谱图相似，但基于不同模型的GWAS分析在遗传力捕获、精细定位和基因优先排序上存在差异，如CAD位点BCAR1与CFDP1的不同预测。
conclusion: 选择bulk或单细胞方法会显著影响调控链接预测结果，开展功能性实验解读GWAS发现时应慎重考虑。
---

## 摘要
全基因组关联研究已经鉴定出成千上万与复杂性状和疾病相关的非编码变异。然而，确定相关遗传变异调控的因果基因仍然具有挑战性。将因果非编码变异与基因联系起来，可以依赖于识别直接物理相互作用的方法（如染色体构象捕获）或预测调控连接的概率模型。这些统计模型利用通过批量或单细胞方法学在细胞和组织中产生的基因表达和染色质可及性图谱。在这里，我们测试了使用批量或单细胞RNA测序/ATAC测序数据以及相应的预测增强子-基因模型是否会影响因果GWAS基因的优先级排序。以未处理和TNF处理的人内皮细胞体外实验作为良好控制的实验系统，我们表明批量与单细胞RNA测序/ATAC测序图谱相似，并突出相同的生物学（例如生物通路）。尽管存在这些相似性，但我们使用冠状动脉疾病和舒张压的GWAS结果展示，应用为批量或单细胞方法学设计的增强子-基因模型在捕获的遗传力、精细定位的变异和连接的基因方面可能会产生差异。例如，在一个CAD位点，基于批量的ABC模型预测与BCAR1的调控连接，而基于单细胞的模型scE2G则优先考虑另一个基因（CFDP1）。在相同的实验模型上，我们的结果表明，在批量或单细胞方法之间进行选择将影响调控连接模型的预测；在规划功能性实验以表征GWAS发现时应考虑这一点。

## Abstract
Genome-wide association studies (GWAS) have identified thousands of non-coding variants associated with complex traits and diseases. However, it remains challenging to pinpoint the causal genes that are regulated by associated genetic variants. Connecting causal non-coding variants with genes can rely on methods that identify direct physical interactions (e.g. chromosome conformation capture) or on probabilistic models that predict regulatory links. These statistical models take advantage of gene expression and chromatin accessibility profiles generated in cells and tissues by bulk or single-cell (sc) methodologies. Here, we tested whether using bulk or sc RNAseq/ATACseq data and corresponding predictive enhancer-to-gene models impact the prioritization of causal GWAS genes. Using non-treated and TNF-treated human endothelial cells in vitro as a well-controlled experimental system, we show that bulk and sc RNAseq/ATACseq profiles are similar and highlight the same biology (e.g. biological pathways). Despite these similarities, we show using GWAS results for coronary artery disease (CAD) and diastolic blood pressure that applying enhancer-to-gene models designed for bulk or sc methodologies can yield differences in terms of captured heritability, fine-mapped variants and linked genes. For instance, at one CAD locus, the bulk-based ABC model predicts a regulatory link with BCAR1, whereas the sc-based model scE2G prioritizes a different gene (CFDP1). On the same experimental model, our results indicate that choosing between a bulk or sc approach will influence regulatory link model predictions; this should be considered when planning functional experiments to characterize GWAS discoveries.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **背景**：全基因组关联研究（GWAS）已发现大量与复杂性状/疾病相关的非编码变异，但确定这些变异调控的因果基因仍是重大挑战。
- **问题**：连接非编码变异与基因的常用方法包括物理相互作用（如染色体构象捕获）或概率模型（如增强子-基因预测）。这些模型依赖批量（bulk）或单细胞（single-cell, sc）方法生成的基因表达和染色质可及性图谱，但两种方法是否影响因果基因的优先级排序尚不清楚。
- **整体含义**：本文以TNFα处理的人内皮细胞为实验系统，系统比较bulk与sc RNAseq/ATACseq图谱及其对应的增强子-基因预测模型（ABC和scE2G），揭示方法选择可能显著改变调控连接预测和GWAS因果基因优先排序，对设计功能实验解读GWAS发现具有重要指导意义。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程
- **核心思想**：在同一实验系统下，同时生成bulk和sc多组学数据（RNAseq和ATACseq），然后分别应用针对bulk或sc设计的增强子-基因预测模型，比较它们在捕获遗传力、精细定位变异以及连接基因上的差异。
- **关键技术细节**：
  - **数据产生**：使用体外培养的人内皮细胞，分为未处理组和TNFα处理组，分别进行bulk RNAseq/ATACseq和scRNAseq/scATACseq测序。
  - **模型选择**：
    - **ABC模型（Activity-by-Contact）**：基于bulk数据的增强子-基因连接预测模型，利用染色质可及性、Hi-C接触频率和基因表达等特征。
    - **scE2G（single-cell Enhancer-to-Gene）模型**：专为单细胞数据设计的增强子-基因连接预测模型，可能利用单细胞水平的共可变性等信息。
- **算法流程（文字描述）**：
  1. 对bulk和sc数据分别进行标准化和差异分析，构建表达和可及性图谱。
  2. 应用ABC和scE2G模型，基于各自的输入特征（bulk或sc的染色质可及性、基因表达等）预测增强子-基因调控连接。
  3. 使用冠心病（CAD）和舒张压（DBP）的GWAS汇总统计，对每个模型预测的调控连接进行遗传力富集分析、精细定位变异映射和因果基因优先排序。
  4. 比较两种模型在关键位点（如一个CAD位点）上的基因连接差异。

### 3. 实验设计：数据集、基准测试、对比方法
- **数据集与场景**：
  - **细胞模型**：人内皮细胞（体外培养），两种条件：未处理（baseline）和TNFα处理（炎症模型）。
  - **多组学数据**：bulk RNAseq、bulk ATACseq、scRNAseq、scATACseq。
  - **GWAS数据**：冠心病（CAD）和舒张压（DBP）的公开GWAS汇总统计。
- **基准测试（Benchmark）**：首先比较bulk与sc图谱在基因表达、染色质可及性、生物通路富集等方面的相似性，确认两者在生物学上具有可比性。
- **对比方法**：
  - **bulk-based增强子-基因模型**：ABC模型（使用bulk数据）。
  - **sc-based增强子-基因模型**：scE2G模型（使用sc数据）。
  - 同时比较两种模型在相同位点上的基因优先级排序结果。

### 4. 资源与算力
- **未明确说明**：文中未提及使用的GPU型号、数量、训练时长等计算资源信息。仅提及了数据生成（测序）和分析流程，未涉及具体硬件或计算开销。

### 5. 实验数量与充分性
- **实验数量**：
  - 一个细胞类型（内皮细胞），两种条件（未处理+TNFα）。
  - 两组多组学数据（bulk与sc）。
  - 两种增强子-基因模型（ABC vs scE2G）。
  - 两个GWAS性状（CAD和DBP），重点分析了一个CAD位点的具体差异。
  - 未进行额外的消融实验或跨细胞类型验证。
- **充分性评价**：
  - **正面**：实验控制严格（同一个细胞系统、同一处理条件），直接比较bulk与sc对模型输出的影响，内部效度较高。
  - **不足**：仅涉及一种细胞类型（内皮细胞），一种刺激（TNFα），两种模型，两个GWAS性状。未测试其他细胞类型、其他模型（如基于Hi-C的模型）、其他GWAS性状，也未进行功能实验验证预测连接。因此结论的泛化能力有限，属于概念验证性质。

### 6. 论文的主要结论与发现
1. **图谱相似性**：bulk和sc RNAseq/ATACseq图谱在整体上高度相似，突出相同的生物学通路（如炎症相关通路）。
2. **模型预测差异**：尽管图谱相似，但针对bulk设计的ABC模型和针对sc设计的scE2G模型在GWAS应用中产生差异：
   - **遗传力捕获**：两者在CAD和DBP的遗传力富集分析中表现不同。
   - **精细定位变异**：连接的具体精细定位位点存在差异。
   - **基因优先排序**：在同一个CAD位点，ABC模型预测BCAR1为靶基因，而scE2G模型优先选择CFDP1。
3. **方法选择影响**：选择bulk或sc方法学将直接影响调控连接模型的预测结果，因此在设计功能实验验证GWAS发现时需慎重考虑这一点。

### 7. 优点
- **控制良好的对比系统**：使用相同的细胞类型、处理条件和多组学技术，最大限度地减少了混淆因素，使比较更公平。
- **结合真实GWAS应用**：不仅比较了图谱，还直接使用了两个主要疾病的GWAS数据，展示了实际影响。
- **揭示潜在偏差**：明确指出了方法学选择可能导致的基因优先级偏差，对于GWAS后功能研究的设计具有实际指导意义。
- **同时覆盖表达和可及性**：全面考虑了基因表达和染色质可及性两个层面。

### 8. 不足与局限
- **细胞类型单一**：仅使用了一种细胞类型（内皮细胞），难以推广至其他细胞或组织背景。
- **刺激条件有限**：仅使用了TNFα处理，未涉及其他刺激或疾病相关环境。
- **模型覆盖不全**：仅对比了ABC和scE2G两种模型，其他流行的增强子-基因预测模型（如EpiMap、FOCS、基于深度学习的模型）未被纳入比较。
- **缺乏功能验证**：预测的基因连接（如BCAR1 vs CFDP1）未通过CRISPR敲除或eQTL等实验进行验证，无法判断哪种模型更准确。
- **未讨论计算资源**：未提及bulk与sc方法在计算成本、数据量需求上的差异，实际应用中可能需要考虑资源投入。
- **统计力度有限**：仅详细展示了一个CAD位点的例子，可能是个案而非普遍规律。

（完）
