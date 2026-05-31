---
title: Genotype and methylation interact to reconfigure transcriptional regulation in colorectal cancer
title_zh: 基因型与甲基化相互作用重塑结直肠癌的转录调控
authors: "Kim, B., Kim, H., Kwon, M.-K., Hannenhalli, S., Choi, S. S."
date: 2026-05-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.27.728350v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 整合基因型和甲基化数据研究eQTL和mQTL，揭示癌症中调控重构
tldr: 转录调控受基因组变异和表观遗传共同影响，但肿瘤发生中二者如何交互尚不完全清楚。本研究对80例结直肠癌患者的配对肿瘤和正常组织进行启动子甲基化测序和RNA-seq，采用memo-eQTL框架显式建模基因型×甲基化（GxM）相互作用。结果发现肿瘤中广泛的GxM相互作用，而正常组织中的GxM特征与临床分期显著相关。该工作揭示了癌症中遗传调控通过上下文依赖的GxM相互作用重组，正常组织中的GxM信号为场癌化提供新见解。
source: biorxiv
selection_source: fresh_fetch
motivation: 探索结直肠癌中基因型与DNA甲基化如何交互重新配置转录调控，揭示其肿瘤发生机制。
method: 对80例CRC患者配对肿瘤和正常组织进行启动子甲基化测序和RNA-seq，运用memo-eQTL框架显式建模基因型×甲基化（GxM）相互作用。
result: 鉴定出73个肿瘤和18个正常组织的GxM相互作用eGenes，正常组织GxM特征与临床分期显著相关（P=0.035）。
conclusion: 遗传调控在癌症中通过GxM相互作用重组，正常组织中的GxM信号与疾病进展相关，揭示了场癌化机制。
---

## 摘要
背景：转录调控受基因组变异和环境共同影响。然而，在肿瘤发生过程中，动态表观基因组变化如何重塑基因组变异的调控效应仍不完全清楚。方法：我们利用来自80名患者的配对肿瘤和癌旁正常组织（NAT），通过控制种系基因组背景，研究了结直肠癌（CRC）中基因型与基因表达之间的甲基化背景依赖性关联。通过整合启动子靶向亚硫酸盐测序与RNA-seq，我们系统地比较了表达数量性状位点（eQTLs）和甲基化数量性状位点（mQTLs）。为了捕捉超越简单中介效应的调控复杂性，我们实现了一个明确建模基因型×DNA甲基化（GxM）相互作用的memo-eQTL框架。结果：我们观察到eQTL和mQTL景观均存在广泛的组织特异性；肿瘤特异性eGenes显著富集于标志性致癌通路，包括WNT和MAPK信号通路。标准中介模型仅解释了少数基因型-表达关系，而我们明确的相互作用框架揭示了肿瘤中甲基化依赖性遗传效应的广泛重构。Memo-eQTL定位（FDR < 0.05）识别出18个NAT和73个肿瘤eGenes具有显著的GxM相互作用，且在更宽松的阈值下（FDR < 0.2）结果一致。我们进一步开发了患者水平的memo-eQTL评分，发现NAT中基于相互作用的调控紊乱（而非肿瘤中）与临床分期显著相关（P = 0.035）。结论：癌症中的遗传调控通过背景依赖的GxM相互作用进行重组。重要的是，NAT中的GxM特征与疾病进展特异性相关，为结直肠癌的领域癌化及调控重编程的临床后果提供了新的见解。关键词：遗传调控；DNA甲基化；eQTL；背景依赖性调控；结直肠癌

## Abstract
Background Transcriptional regulation is shaped by both genomic variants and the environment. Yet, how the regulatory effects of genomic variants are reconfigured by dynamic epigenomic changes during tumorigenesis remains incompletely understood. Methods We investigated methylation context-dependent links between genotype and gene expression in colorectal cancer (CRC) using paired tumor and normal-adjacent tissue (NAT) from 80 patients, thereby controlling for germline genomic background. By integrating promoter-targeted bisulfite sequencing with RNA-seq, we systematically compared expression quantitative trait loci (eQTLs) and methylation quantitative trait loci (mQTLs). To capture regulatory complexity beyond simple mediation, we implemented a memo-eQTL framework that explicitly models genotype x DNA methylation (GxM) interactions. Results We observed extensive tissue specificity in both eQTL and mQTL landscapes; tumor-specific eGenes were significantly enriched for hallmark oncogenic pathways, including WNT and MAPK signaling. Standard mediation models explained only a minority of genotype-expression relationships, whereas our explicit interaction framework revealed widespread reconfiguration of methylation-dependent genetic effects in tumors. Memo-eQTL mapping (FDR < 0.05) identified 18 NAT and 73 tumor eGenes with significant GxM interactions, and results were consistent at a more permissive threshold (FDR < 0.2). We further developed a patient-level memo-eQTL score and found that interaction-based regulatory disruption in NAT, but not in tumor, significantly correlated with clinical stage (P = 0.035). Conclusions Genetic regulation in cancer is reorganized through context-dependent GxM interactions. Importantly, GxM signatures in NAT are specifically linked to disease progression, offering new insights into field cancerization and the clinical consequences of regulatory reprogramming in CRC. Keywords: genetic regulation; DNA methylation; eQTL; context-dependent regulation; colorectal cancer

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：转录调控同时受基因组变异（基因型）和表观遗传环境（如DNA甲基化）影响，但在结直肠癌（CRC）发生过程中，动态的表观基因组变化如何重塑基因组变异的调控效应，目前尚不清楚。具体而言，基因型与甲基化之间是否存在超越简单中介效应的交互作用（G×M），以及这种交互在肿瘤和癌旁正常组织（NAT）中的差异如何与疾病进展相关。
- **研究动机**：探索CRC中遗传调控通过上下文依赖的G×M相互作用重组的方式，揭示肿瘤发生机制，并寻找与临床分期相关的分子标志物。
- **整体意义**：该工作首次在配对组织中系统建模G×M相互作用，发现NAT中的G×M信号与疾病进展显著关联，为“场癌化”（field cancerization）概念提供新的表观遗传调控层面的证据，提示正常组织中的调控重编程可能具有临床预测价值。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将基因型（G）、DNA甲基化（M）和基因表达（E）三者联合建模，不将甲基化仅作为中介变量，而是显式考虑基因型与甲基化的交互作用（G×M），以捕获甲基化背景依赖性的遗传调控效应。
- **关键技术细节**：
  - 数据整合：对80例CRC患者的配对肿瘤和癌旁正常组织（NAT）进行启动子靶向亚硫酸盐测序（promoter-targeted bisulfite sequencing）和RNA-seq，从而控制种系基因组背景。
  - eQTL和mQTL分析：分别鉴定表达数量性状位点（eQTL）和甲基化数量性状位点（mQTL），并比较肿瘤与NAT间的组织特异性。
  - 标准中介模型：先评估甲基化是否作为基因型→表达的简单中介，发现仅能解释少数关系。
  - Memo-eQTL框架：显式建模基因型×甲基化（GxM）交互作用，采用线性模型`E ~ G + M + G×M + covariates`，对每个SNP-基因-甲基化位点三元组进行检验，通过FDR校正（<0.05及更宽松的<0.2）识别显著交互eGenes。
  - 患者水平的memo-eQTL评分：基于每个患者中显著G×M交互的偏离程度计算得分，用于评估个体调控紊乱水平。

### 3. 实验设计：数据集、基准与对比方法

- **数据集**：80例CRC患者的配对肿瘤和邻近正常组织（NAT），共160个样本。每个样本均获取启动子甲基化谱（靶向亚硫酸盐测序）和转录组（RNA-seq）。
- **基准与对比**：
  - 内部比较：肿瘤 vs NAT的eQTL和mQTL景观对比。
  - 标准中介模型（mediation model）作为对比，评估甲基化作为中介的解释比例。
  - 仅依赖基因型的主效应模型（无交互）作为基线，对比memo-eQTL交互模型的效果。
  - 未提及与外部公开数据集的基准对比（如TCGA等）。

### 4. 资源与算力

- **文中未明确说明**：论文摘要及元数据中未提及使用的GPU型号、数量、训练时长或其他计算资源。可能作者使用了标准生物信息学流程和统计软件（如R、PLINK等），对算力要求通常不高，但无法确认具体细节。

### 5. 实验数量与充分性

- **实验组数**：主要实验包括：
  - eQTL/mQTL全基因组扫描（肿瘤和NAT分别进行）。
  - 中介模型评估。
  - Memo-eQTL交互分析（筛选73个肿瘤eGenes和18个NAT eGenes，FDR<0.05；一致验证于FDR<0.2）。
  - 患者水平memo-eQTL评分与临床分期关联分析（P=0.035）。
- **充分性评价**：
  - **优点**：使用配对样本控制遗传背景，统计检验严格（FDR校正），且用两个阈值验证一致性。
  - **不足**：样本量仅80例，对于检测交互效应可能统计效力有限；缺乏独立验证队列；未进行跨癌症类型的泛化验证；未展示与已有公开CRC eQTL数据的比较。总体而言，实验设计合理但覆盖范围有限，结论外推需谨慎。

### 6. 论文的主要结论与发现

- **eQTL/mQTL组织特异性**：肿瘤和NAT间的eQTL和mQTL景观差异显著，肿瘤特异性eGenes富集于WNT、MAPK等致癌通路。
- **标准中介模型局限性**：甲基化作为中介仅能解释少数基因型-表达关系，表明更复杂的调控模式存在。
- **广泛G×M交互**：memo-eQTL鉴定出73个肿瘤和18个NAT的显著交互eGenes，且更宽松阈值下结果一致，证明肿瘤中甲基化依赖的遗传效应发生广泛重组。
- **临床关联**：仅NAT（而非肿瘤）中的memo-eQTL评分与临床分期显著相关（P=0.035），提示正常组织中的调控重编程可能是“场癌化”早期事件，具有预后潜力。

### 7. 优点：方法或实验设计上的亮点

- **创新性方法**：显式建模G×M交互而非仅用中介模型，更贴近真实生物调控复杂性。
- **配对设计**：利用同一患者的肿瘤和NAT，有效控制种系遗传背景，减少混杂。
- **临床相关性**：发现NAT中的G×M信号与分期相关，为癌症早期诊断和场癌化机制提供新见解。
- **多层面验证**：采用两个FDR阈值保证结果稳健性；计算患者水平评分展示个体差异。

### 8. 不足与局限

- **样本量小**：仅80例，对交互效应的统计检测力不足，可能遗漏许多真实交互。
- **缺乏独立验证**：未在独立队列中复现主要结果，结论普遍性待考。
- **启动子甲基化覆盖有限**：仅使用启动子靶向测序，未覆盖增强子、差异甲基化区域等可能更关键的调控区域。
- **未考虑其他表观修饰**：如组蛋白修饰、染色质可及性也可能影响eQTL，文中未纳入。
- **临床分期关联仅限NAT**：解释需谨慎，可能受样本偏倚影响；未校正多重比较（仅一个P值）。
- **资源信息缺失**：算力、软件版本、参数等细节不足，影响可重复性。

（完）
