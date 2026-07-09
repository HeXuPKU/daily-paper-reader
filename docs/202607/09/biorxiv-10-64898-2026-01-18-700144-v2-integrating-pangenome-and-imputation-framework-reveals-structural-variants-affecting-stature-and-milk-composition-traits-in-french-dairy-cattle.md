---
title: Integrating pangenome and imputation framework reveals structural variants affecting stature and milk composition traits in French dairy cattle
title_zh: 整合泛基因组与插补框架揭示影响法国奶牛体型和乳成分性状的结构变异
authors: "NAJI, M., Sorin, V., Grohs, C., Fritz, S., Klopp, C., Faraut, T., Boichard, D., Boussaha, M., Sanchez, M.-P."
date: 2026-07-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.18.700144v2.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 整合泛基因组和插补方法进行大规模SV关联分析，类似于SV的GWAS方法
tldr: 结构变异（SV）在复杂性状中作用重要，但大规模关联研究受限于长读长数据稀缺且缺乏表型。本研究整合泛基因组变异图和插补框架，利用176个长读长样本检测SV，结合短读长与SNP芯片数据，为近1.9万头法国奶牛构建插补参考面板，并开展全基因组关联分析。结果鉴定出40个显著SV-性状关联，其中10个SV为候选因果变异，影响乳脂、乳蛋白和体高。该框架提供了将SV高效纳入常规基因组分析与选择的可扩展策略。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-18-700144-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1642, \"height\": 767, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-18-700144-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1638, \"height\": 1429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-18-700144-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1504, \"height\": 1372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-18-700144-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1660, \"height\": 1776, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-18-700144-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1657, \"height\": 2047, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-18-700144-v2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1725, \"height\": 850, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-18-700144-v2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1820, \"height\": 1598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-18-700144-v2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 714, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-18-700144-v2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1649, \"height\": 607, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-18-700144-v2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 846, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-18-700144-v2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1843, \"height\": 1970, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-18-700144-v2/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1843, \"height\": 2253, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-01-18-700144-v2/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1314, \"height\": 471, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-01-18-700144-v2/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 2097, \"height\": 858, \"label\": \"Table\"}]"
motivation: 长读长测序数据稀缺且缺乏表型，需要整合多种数据源实现大规模结构变异关联研究。
method: "基于176个长读长样本构建泛基因组变异图，基因分型939个短读长样本，结合SNP数据构建序列级插补参考面板，对11,902头荷斯坦等三个品种公牛插补后进行GWAS。"
result: 发现40个全基因组显著SV-性状关联，条件分析确定10个强候选SV，分别影响乳脂、乳蛋白含量和体高。
conclusion: 泛基因组与插补框架可有效整合结构变异，揭示复杂性状遗传基础，为奶牛基因组选择提供可扩展策略。
---

## 摘要
背景：结构变异最有效地通过长读长测序来识别。然而，此类数据仍然稀少，且测序样本通常缺乏相关表型信息。为克服这一限制，我们整合了基于泛基因组（变异图谱）和插补的方法，以在法国三个主要奶牛品种中开展大规模结构变异关联研究。结果：利用176个长读长样本中检测到的69,892个缺失、89,900个插入和17,402个重复，构建了一个变异图谱。随后，我们通过将939个样本的短读序列重新比对至该图谱，对每个结构变异进行了基因分型。验证分析显示，缺失和插入的基因型一致率较高（均为0.79），但重复的一致率较低（0.14），因此将其排除在后续分析之外。保留的结构变异与单核苷酸变异结合，构建了一个序列水平的插补参考面板。利用SNP基因分型芯片数据，我们对11,902头荷斯坦牛、3,753头蒙贝利亚牛和3,053头诺曼底公牛的结构变异和单核苷酸变异进行了插补。质量控制后，保留了超过1400万个单核苷酸变异和4万个结构变异，并使用后代表型偏差对体高及四个产奶量和乳成分性状进行了品种内全基因组关联研究。全基因组关联研究结果显示了与先前发现一致的遗传架构，并识别出40个与结构变异和关键表型显著相关的基因组位点。条件分析表明，其中10个结构变异是与乳脂和乳蛋白含量以及体高相关的强候选变异。结论：通过在统一的泛基因组和插补框架中整合长读长、短读长和SNP基因分型数据，我们展示了一种可扩展的策略，用于系统地探究结构变异对复杂性状的贡献。所得的遗传架构与先前发现高度一致，验证了我们方法的稳健性和可转移性。我们的发现强调了将结构变异整合到常规基因组分析中的附加价值，并为将结构变异纳入奶牛基因组选择提供了一个可扩展的框架。

## Abstract
Background: Structural variants (SVs) are most effectively identified using long-read (LR) sequenc-ing. However, such data remain scarce, and sequenced samples often lack associated phenotypic information. To overcome this limitation, we integrated pangenome-based (variation graph-based) and imputation approaches to enable large-scale SV association studies in the three main French dairy cat-tle breeds. Results: A variation graph was constructed using 69,892 deletions, 89,900 insertions, and 17,402 duplications detected in 176 LR samples. We subsequently genotyped 939 samples for each SV in the panel by realigning their short read (SR) sequences to the graph. Validation analyses showed high genotype concordance rates for deletions (0.79) and insertions (0.79); however, concordance for duplications was low (0.14), leading to their exclusion from further analyses. The retained SVs were combined with single nucleotide variants (SNVs) to build a sequence-level imputation reference panel. Using SNP genotyping array data, we imputed SVs and SNVs for 11,902 Holstein, 3,753 Montbeliarde, and 3,053 Normande bulls. After quality control, more than 14 million SNVs and 40 thousand SVs were retained for within-breed genome-wide association studies (GWAS) using daughter yield deviations for stature and four milk production and composition traits. The GWAS results reveled genetic architectures consistent with previous findings and identified 40 genome-wide significant associations between structural variant and key phenotypes. Conditional analyses showed that ten of these SVs as strong candidates associated with milk fat and protein contents, as well as stature. Conclusions: By integrating LR, SR, and SNP genotyping data within a unified pangenome and imputation framework, we demonstrate a scalable strategy to systematically interrogate the contribution of SVs to complex traits. The resulting genetic architectures were highly consistent with previous findings, validating both the robustness and transferability of our approach. Our findings highlight the added value of integrating SVs into routine genomic analyses and provide a scalable framework for incorporating SVs into genomic selection in dairy cattle.

---

## 论文详细总结（自动生成）

## 论文详细总结

### 一、核心问题与整体含义（研究动机和背景）

- **核心问题**：结构变异（SV）对复杂性状（如奶牛产奶性状和体高）有重要影响，但长读长测序数据稀缺且缺乏表型信息，难以进行大规模关联研究。传统短读长数据无法全面检测SV，限制了SV在全基因组关联研究（GWAS）和基因组选择中的应用。
- **研究动机**：开发一种可扩展的策略，通过整合长读长、短读长和SNP芯片数据，利用泛基因组（变异图）和插补框架，在法国三大主要奶牛品种（荷斯坦、蒙贝利亚、诺曼底）中系统研究SV对五个重要农艺性状（乳蛋白产量、乳脂产量、乳脂含量、乳蛋白含量、体高）的贡献。
- **整体含义**：证明了SV作为复杂性状遗传架构中重要但未被充分利用的组分，提出了将SV整合到常规基因组分析和育种计划中的实用路线图。

### 二、方法论

- **核心思想**：采用“长读长检测SV → 变异图构建 → 短读长基因分型 → 序列级插补 → GWAS”的流程，解决SV检测、基因分型、插补和大规模关联分析的瓶颈。
- **关键技术细节**：
    1. **SV检测**：使用176个长读长样本（PacBio和ONT），通过PBMM2比对至ARS-UCD1.2参考基因组，PBSV v2.6.2调用SV（缺失、插入、重复），过滤保留双等位、50bp-100kb、断点明确的SV。重复转换为插入后，用JASMINE合并。
    2. **变异图构建与基因分型**：使用VG工具包构建全基因组变异图（171,451个气泡，其中161,237个双等位）。将939个短读长样本的reads用GIRAFFE比对至变异图，用`vg call -Aa`进行SV基因分型（仅保留双等位SV）。
    3. **基准测试**：基于6个同时有长读长和短读长数据的个体（荷斯坦、蒙贝利亚、诺曼底各2个），以PBSV检测结果为真集，VG输出为比较集，用TRUVARI评估召回率和基因型一致率。结果：缺失和插入一致率均为0.79，重复仅为0.14，故排除重复。
    4. **SNV检测**：对939个短读长样本用BWA-MEM比对、GATK流程进行SNV检测，过滤后保留双等位、MAF>0.01、缺失率<0.1、质量>30的SNVs。
    5. **插补工具基准测试**：在BTA25染色体上对比BEAGLE、MINIMAC和GLIMPSE。移除位于缺失区域的SNVs后，合并SNVs和SVs（共365,807个SNVs和1,278个SVs）。LD剪枝（r²=0.5）得到31,426个标记模拟高密度SNP芯片。评估指标为基因型一致率和计算时间。BEAGLE表现最佳（SNV一致率0.99，SV一致率高于MINIMAC，且计算时间最短），因此选为最终工具。
    6. **两步插补**：首先从中等密度芯片（约50K SNPs）至高清芯片（~700K SNPs），使用FImpute及品种特异性祖先面板。然后从高清至序列水平（约2000万SNVs和约8万SVs），使用BEAGLE（窗口15Mb），分别针对三个品种进行。插补后过滤：MAF>0.01且imputation R²>0.6。
    7. **GWAS**：使用GCTA的`--mlma`混合线性模型，以后代表型偏差（DYD）为表型，固定效应为SNV/SV剂量，随机效应为基于中等密度SNP的基因组关系矩阵。Bonferroni校正显著性阈值：-log10(P)>8.44。
    8. **条件分析**：对显著SVs使用GCTA的`--cojo-cond`进行条件分析，评估各QTL区域内的独立效应。

### 三、实验设计

- **数据集与场景**：
    - **长读长数据集**：176个样本，覆盖14个法国品种（含荷斯坦、蒙贝利亚、诺曼底及其余肉牛/奶牛品种），PacBio或ONT测序。
    - **短读长数据集**：939个样本，覆盖17个品种（以荷斯坦273、蒙贝利亚131、诺曼底132、利木赞134等为主），用于SV基因分型。
    - **SNP芯片数据（目标集）**：11,902头荷斯坦、3,753头蒙贝利亚、3,053头诺曼底公牛，具有后代表型偏差（DYD）数据，基因分型为中等密度SNP芯片（约50K），用于两步插补后GWAS。
    - **表型**：五个性状：乳蛋白产量、乳脂产量、乳脂含量、乳蛋白含量、体高。
- **基准测试**：
    - **SV基因分型基准**：6个验证个体（每品种2个），对比PBSV真集与VG输出，记录召回率和基因型一致率。
    - **插补工具基准**：BTA25染色体上，以933个参考样本、6个目标样本（留样验证），对比BEAGLE、MINIMAC、GLIMPSE的基因型一致率和计算时间。
- **对比方法**：主要对比不同插补工具（BEAGLE vs MINIMAC vs GLIMPSE）；未与其他SV-GWAS方法对比（因为本研究为首次在奶牛中完整实现该流程）。

### 四、资源与算力

- **明确说明**：文中仅提到基准测试中，BTA25染色体上SHAPEIT phasing（用于GLIMPSE）耗时约8小时（单核心），BEAGLE phasing约5小时，BEAGLE imputation不到2分钟，GLIMPSE imputation约13分钟。全基因组插补采用了分染色体、15Mb窗口的策略以降低计算负荷。
- **未明确说明**：未提及所用GPU型号、数量或总训练时长，也未提及长读长比对及变异图构建的具体算力消耗。可推测主要使用CPU集群（如Genotoul平台），但无量化数据。

### 五、实验数量与充分性

- **实验数量**：
    - SV检测阶段：176个长读长样本，获得约17.7万个SV。
    - SV基因分型阶段：939个短读长样本，经MAF>0.01和缺失率<0.1过滤后保留36,402个缺失和43,290个插入。
    - 插补工具基准：1条染色体（BTA25），3种工具，6个目标样本。
    - 大规模插补：三个品种分别进行，最终用于GWAS的变异数：荷斯坦约14.07M SNVs和37,633 SVs；蒙贝利亚约14.61M SNVs和40,473 SVs；诺曼底约14.19M SNVs和40,156 SVs。
    - GWAS：5个性状 × 3个品种 = 15个组合分析，共识别40个显著SV关联。
    - 条件分析：对每个显著SV进行条件分析，确定10个作为候选因果变异。
- **充分性评估**：实验设计较为充分。采用了标准的线性混合模型GWAS，考虑了群体结构和多基因效应。基准测试合理（验证集、对比工具、留样验证）。但有几点不足：（1）重复SV因低一致率被排除，可能漏掉重要变异；（2）插补基准仅针对BTA25，且目标样本仅6个，可能存在偏差；（3）仅使用Bonferroni阈值，较为保守，可能降低功效；（4）未进行跨品种meta分析或独立验证队列。

### 六、主要结论与发现

1. **成功建立可扩展的SV-GWAS框架**：整合长读长、短读长和SNP芯片数据，通过泛基因组变异图和插补实现了从SV发现到大规模关联分析的完整流程。
2. **遗传架构一致**：GWAS结果与先前基于SNPs的研究高度一致（如BTA14的DGAT1区域、BTA11的MATN3对体高的影响），验证了方法的稳健性。
3. **识别40个显著SV关联**：涉及乳蛋白产量、乳脂产量、乳脂含量、乳蛋白含量和体高。其中10个SV在条件分析中被确认为候选因果变异，具体包括：
    - 乳脂含量（蒙贝利亚）：BTA5的PIK3C2G内含子插入（298bp）和bta-mir-2285o-5附近缺失（72bp）；
    - 乳蛋白含量：蒙贝利亚BTA5的72bp缺失（同乳脂峰值）、BTA6的ODAM上游143bp插入、BTA22的TAFA4-TAFA1间93bp缺失；诺曼底BTA6的CSN1S1-CSN2间473bp插入；
    - 体高：荷斯坦BTA11的MATN3上游6179bp缺失；蒙贝利亚BTA21的GABRG3内含子1217bp插入；诺曼底BTA6的LCORL-SLIT2间120bp缺失和BTA26的SLIT1内含子68bp缺失。
4. **SV插补精度低于SNV**：中位R²：SNV 0.99，SV 0.70；SV插补受MAF和LD强度影响。
5. **SV在QTL中常常不是最强信号，但部分是因果变异**：如MATN3缺失、CSN1S1-CSN2间插入等。
6. **BTA14区域高度连锁**：多基因共定位导致条件分析无法区分独立效应，尤其是DGAT1与CYP11B1附近SV。

### 七、优点

1. **创新性整合**：首次在奶牛中实现“长读长检测-变异图基因分型-序列级插补-GWAS”的全链条，为SV大规模关联提供了可复用的范式。
2. **数据互补**：充分利用长读长（高精度SV检测）、短读长（大量样本基因分型）和SNP芯片（大规模表型群体）三者优势，克服了各自局限。
3. **严格的基准测试**：对SV基因分型（召回率、一致率）和插补工具进行了系统性评估，并据此排除了重复SV、选择了BEAGLE，保证了下游分析质量。
4. **品种特异性分析**：分品种进行GWAS和条件分析，揭示了不同品种间的遗传异质性（如体高QTL差异）。
5. **结果验证**：成功再现已知QTL（如MATN3、DGAT1、CSN1S1-CSN2等），增强了可信度。
6. **开源工具与代码**：提供了变异图构建和基因分型的Snakemake工作流，有利于重复应用。

### 八、不足与局限

1. **重复SV的排除**：由于基因型一致率极低（0.14），重复SV被完全排除，可能遗漏重要生物学变异（如基因剂量效应）。改善变异图表示或使用联合基因分型可能提高其准确性。
2. **插补精度有限**：SV插补R²中位仅0.70，远低于SNV；且荷斯坦品种保留的SV数量最少，可能因LD强度弱或参考样本代表性不足。这削弱了检测低频SV关联的统计功效。
3. **GWAS功效受限**：Bonferroni阈值（约8.44）偏保守，对于SV这种稀有变异类型可能造成假阴性；且未进行多品种meta分析以增强功效。
4. **因果推断局限性**：条件分析仅在染色体水平进行，且BTA14等区域高度连锁，无法完全解析因果变异；除了间接推断，未进行功能验证（如CRISPR、eQTL）。
5. **样本偏差**：长读长样本（176个）和短读长样本（939个）分布不均，肉牛品种较多；SNP芯片目标群体仅限有DYD的公牛，可能引入选择偏差。
6. **缺乏独立验证**：所有GWAS结果基于同一数据集的条件分析，无独立群体或实验验证，可能受假阳性影响。
7. **计算资源未量化**：未报告全基因组插补和GWAS的总计算时间、内存消耗，不利于其他研究者评估可复现性。

（完）
