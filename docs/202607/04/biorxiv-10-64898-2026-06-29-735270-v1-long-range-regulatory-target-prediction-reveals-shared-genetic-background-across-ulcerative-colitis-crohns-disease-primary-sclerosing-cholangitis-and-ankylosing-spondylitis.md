---
title: "Long-range regulatory target prediction reveals shared genetic background across ulcerative colitis, Crohn's disease, primary sclerosing cholangitis and ankylosing spondylitis"
title_zh: 长程调控靶点预测揭示溃疡性结肠炎、克罗恩病、原发性硬化性胆管炎和强直性脊柱炎的共享遗传背景
authors: "Dulcic, D., Mandic, K., Hrsak, D., Baresic, A."
date: 2026-07-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735270v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 利用GWAS变异预测长程调控靶点并整合功能基因组，直接与GWAS精细定位和功能整合相关
tldr: 全基因组关联研究发现了大量与疾病相关的非编码变异，但解析其远端调控靶基因及多效性机制面临挑战。本研究运用targPred工具，整合进化保守性及比较基因组数据，系统性预测溃疡性结肠炎、克罗恩病、原发性硬化性胆管炎和强直性脊柱炎四种免疫介导疾病的共享及特有调控靶基因。结果揭示了血小板、血管生物学和固醇代谢等共同通路，以及IBD两种表型间的特定基因簇和IBD与PSC共享的临床相关靶点COG6。该工具能捕获传统SNP-基因关联法遗漏的靶基因，为解析复杂疾病遗传背景及药物靶点发现提供新视角。
source: biorxiv
selection_source: fresh_fetch
motivation: 从非编码GWAS变异推断远端调控靶基因及跨疾病共享机制仍具挑战。
method: 利用targPred工具，结合进化保守性与比较基因组数据，预测四种免疫疾病的调控靶基因。
result: 发现血小板、血管和固醇代谢等共享通路，及IBD与PSC共享的靶基因COG6；揭示传统方法错失的靶点。
conclusion: targPred能有效预测远端调控靶点，揭示跨疾病遗传共性和新药靶点，优于传统方法。
---

## 摘要
全基因组关联研究（GWAS）发现的常见变异为个体性状和疾病的遗传成分提供了丰富的知识。然而，这些变异中绝大多数为非编码变异，阐明其背后的分子机制仍是一项尚未解决的任务，尤其是考虑到这些变异所在的调控元件与基因启动子之间的远端和多效性相互作用。本文聚焦于四种免疫介导的疾病——溃疡性结肠炎、克罗恩病、原发性硬化性胆管炎和强直性脊柱炎，展示了targPred工具的实用性，该工具可预测调控变异靶向的基因。通过考虑进化与比较基因组数据，我们检测到四种疾病共享的调控元件（包含常见变异）靶向基因中涉及的机制趋势（血小板、血管和甾醇簇），以及疾病子集（例如两种IBD表型）的特异性趋势。我们还阐明了IBD与PSC之间共享的临床相关靶点COG6，以及传统SNP-基因分配方法遗漏的一系列其他靶基因。

## Abstract
Common variants detected by the genome-wide association studies (GWAS) create a wealth of knowledge on genetic component of individual traits and diseases. Elucidating the molecular mechanism behind the vast majority of these variants that are found to be non-coding remains a largely unsolved task, especially when distal and pleiotropic interactions between regulatory elements where these variants occur and gene promoters are taken into account. Focusing on four diseases with immune-mediated mechanisms namely ulcerative colitis, Crohn's disease, primary sclerosing cholangitis and ankylosing spondylitis, we demonstrate the utility of the targPred tool, providing prediction of genes targeted by the regulatory variants. We demonstrate that taking into account evolutionary and comparative genomic data, previously unobserved mechanistic trends (the platelet, vascular and sterol clusters) can be detected in terms of implicated genes targeted by the regulatory elements containing common variants, shared between all four diseases, as well as specific trends for subsets of diseases, e.g. two IBD phenotypes. We also elucidate a clinically-relevant target COG6 shared between IBD and PSC, as well as a whole range of other target genes missed by the conventional SNP-to-gene assignments methods.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的详细中文总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：全基因组关联研究（GWAS）发现超过90%的疾病相关变异位于非编码区，这些变异通常位于远端调控元件（如增强子）中。传统的“最近基因”分配策略无法准确识别这些变异的真实调控靶基因，尤其当涉及长程调控（>数百kb）和跨疾病共享的遗传背景时。四种免疫介导疾病——溃疡性结肠炎（UC）、克罗恩病（CD）、原发性硬化性胆管炎（PSC）和强直性脊柱炎（AS）——具有显著的临床共病和遗传重叠，但其非编码变异的远端靶基因及共享机制尚不清楚。
- **研究动机**：验证基于进化的长程调控框架——基因组调控模块（GRB）及其预测工具targPred的有效性，以推断这些疾病非编码变异作用的靶基因，揭示传统方法遗漏的共享生物学通路和潜在药物靶点。

### 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：利用基因组调控模块（GRB）——即进化极端保守、涵盖远端调控元件及其靶基因的基因组区域——作为长程调控的骨架。GRB中的增强子通常通过染色质环作用到距离很远的靶基因启动子上，而旁路基因则不受影响。基于此，targPred通过量化增强子活性与目标基因表达的关联来预测靶基因，而非基于基因组距离。
- **关键技术细节**：
  - **GRB注释**：基于人×狗非编码保守性定义GRB区间。
  - **增强子-启动子关联量化**：利用FANTOM5的CAGE数据，跨309个人类生物样本（细胞、组织、发育阶段），统计每个增强子-启动子对内增强子转录活性与基因表达之间的关联（以经验p值表示，empP），捕捉激活与抑制方向。
  - **靶基因预测**：使用随机森林模型，以增强子-启动子关联强度、保守性等特征区分真正的靶基因与旁路基因。
- **算法流程**：
  1. 从GWAS Catalog获取四个疾病的显著关联位点（P<5×10⁻⁸），计算基于1000 Genomes Phase3欧洲人群的LD块。
  2. 将LD块与GRB区间重叠，筛选落入GRB内的位点。
  3. 对每个GRB，targPred输出预测的远端靶基因（长程调控靶点），并与GWAS Catalog中该位点报告的基因（通常基于最近基因或其他方法）进行比较。
  4. 根据一致/不一致将靶基因分为三类：GRB=GWAS（一致）、GRB≠GWAS（不一致）以及跨疾病重复出现的次级基因。

### 3. 实验设计：数据集、基准测试（benchmark）及对比方法

- **使用数据集**：
  - **GWAS Catalog**：提取四种疾病（UC、CD、PSC、AS）的显著关联位点（P<5×10⁻⁸），基于已处理的LD块和基因注释。
  - **1000 Genomes Phase3（GRCh37，欧洲超种群）**：用于计算LD块。
  - **FANTOM5 CAGE数据**：跨309个人类生物样本，用于增强子-启动子关联定量。
  - **GRB注释**：基于人×狗非编码保守性，来自targPred资源。
- **基准测试（benchmarking）**：论文未在本工作中重做基准测试，但引用了targPred原始论文[11]中对targPred预测与实验验证的SNP-基因关联及其他增强子-基因预测器（如GeneHancer、ABC模型等）的广泛比较，表明其预测可信。本工作直接应用该工具。
- **对比方法**：传统GWAS Catalog中报告/映射的基因（通常为最近基因或局部优先方法）。论文通过对比targPred预测与GWAS Catalog基因来量化长程调控的差异。

### 4. 资源与算力

- 文中**未提供任何关于计算资源（GPU型号、数量、训练时长等）的信息**。仅提到代码和数据集在GitHub仓库（https://github.com/mlkr-rbi/UC-CD-PSC-AS_targPred）上可用。推测主要依赖标准CPU计算（因为不涉及深度学习大规模训练），但未明确说明。在总结中需指出这一点。

### 5. 实验数量与充分性

- **实验数量**：主要包含一项应用分析——对四个疾病的所有GWAS位点进行targPred预测和分类，获得145个重叠位点、86个候选靶基因（其中18个与GWAS一致，68个不一致，12个为次级/跨疾病基因）。未进行传统的消融实验或不同参数下的敏感性测试。
- **手工解析**：对部分自动输出缺失的位点进行了手工查找和补充，但这并非完全自动化的大规模检验。
- **充分性与客观性**：分析是描述性和生成假设性的，缺乏独立的实验验证。基准测试引用自另一篇论文，本工作并未重新评估targPred在免疫疾病上的特异预测性能。仅使用了欧洲人群LD参考，可能降低对其他人群的普遍性。实验覆盖了四个疾病的主要GWAS信号，但未包括更全面的跨疾病或人群多样性分析。总体而言，该方法提供了新的生物学见解，但在因果验证和模型鲁棒性方面不充分。

### 6. 论文的主要结论与发现

- **多数长程调控靶点不同于传统分配**：71%的targPred预测靶基因与GWAS Catalog报告的基因不同（GRB≠GWAS），说明传统最近基因策略大量遗漏远端调控关系。
- **共享的生物学通路**：
  - **网络1：淋巴细胞主转录因子程序**（RUNX3、PRDM1、SATB1、IKZF1、ETS1、FLI1、HHEX、EGR2）——四种疾病共有，其中部分基因（如SATB1、IKZF1、HHEX）仅在不一致组中出现，补充了传统信号。
  - **网络2：NR5A2核受体肠-肝-胰轴**（NR5A2、ABCG5、ABCG8、TRIB1、JAZF1、HHEX）——与胆汁酸代谢、脂质代谢相关，尤其可能解释PSC的遗传组分。
  - **血小板/血管/甾醇簇**：FLI1（巨核细胞增殖）、TUBB1（血小板微管）、ABCG5/ABCG8（甾醇转运）等，提示与IBD和PSC中血小板功能障碍的临床联系。
- **IBD与PSC共享的临床相关靶点**：**COG6**（高尔基体保守寡聚体亚基6）——其缺陷导致先天性糖基化障碍（CDG-IIL），表型同时影响肠道黏液分泌（UC/CD）和胆管上皮稳态（PSC），完美匹配IBD-PSC共病。
- **次级模块**：TGF-β/SMAD7+ FYN（UC/CD）、NOTCH/Wnt/NR4A2 Treg分化（UC/CD）、LPHN2-TENM3-FLRT粘附三联体（UC/CD/AS）等，提供了机制性可测试假设。
- **总体结论**：targPred能有效扩展GWAS结果的解读，从离散位点列表转化为整合的调控模块和生物学通路，并提出特定药物靶点（如COG6、NR5A2轴）用于后续功能验证。

### 7. 优点

- **理论优势**：基于进化保守性（GRB）而非特定组织或疾病，规避了组织偏倚和训练数据大小限制，对长程调控具有天然敏感性。
- **实用性**：可直接应用于现有GWAS Catalog数据，快速产生可测试假设；预测结果与传统GWAS基因互补而非矛盾，完成生物学模块。
- **发现能力**：识别出传统最近基因方法明显遗漏的靶点（如血小板/甾醇模块、COG6），且这些靶点具有临床和机制相关性。
- **透明性**：代码和数据公开，方法描述清晰，便于复现。

### 8. 不足与局限

- **缺乏直接实验验证**：所有预测均基于统计关联和保守性，需要CRISPR扰动、eQTL、Hi-C等实验确认真正的因果靶向关系。
- **群体偏差**：仅使用欧洲人群LD参考和GWAS研究，对非欧洲人群的适用性未知；GRB注释基于人-狗保守性，可能遗漏哺乳动物特有的调控结构。
- **方法内部局限性**：
  - GRB定义依赖于缺失、有限物种的比较（人·狗），可能无法覆盖所有长程调控，尤其是组织特异或谱系特异的增强子。
  - targPred的随机森林模型可能受训练数据中阳性样本（已验证的SNP-基因对）大小和偏差影响。
  - FANTOM5数据覆盖了多种样本但仍可能缺少某些疾病相关细胞类型（如肠道上皮、胆管细胞、滑膜细胞）。
- **分析规模不足**：仅分析了四种疾病，未进行系统性的全表型组扫描；手工解析部分缺失值增加了主观性。
- **因果推断强度有限**：所描述的调控网络基于文献支持，属于假设生成性质，并非由数据直接推出的因果关系。

（完）
