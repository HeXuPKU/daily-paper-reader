---
title: SELECT-seq allows Pre-Sequencing Enrichment of SNP Edits in One-Pot Single-Cell Whole-Transcriptome Sequencing
title_zh: SELECT-seq 实现在一锅法单细胞全转录组测序中对 SNP 编辑进行测序前富集
authors: "Iwama, S., Gitterman, D., Brendler-Spaeth, T., Waters, A. J., Robertson, H., Strauss, M., Adams, D., Cooper, S. E., Wu, Q., Bassett, A. R."
date: 2026-07-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.07.736965v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 测序前富集SNP编辑以识别因果变异
tldr: "现有单细胞方法无法在测序前富集正确编辑的细胞，限制了规模。SELECT-seq通过Cas12a靶向实现SNP特异性PCR扩增和荧光检测，与全转录组扩增同步进行，一步法富集含SNP的单细胞。在PIK3CA突变细胞系和NRF2 T80K突变池中分别达到86%和87.5%的基因型准确性及转录组效应一致性。该方法为单细胞分辨率下的基因型-表型关联提供了快速可扩展的途径。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-736965-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1560, \"height\": 1969, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-736965-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1551, \"height\": 1564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-736965-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1523, \"height\": 1667, \"label\": \"Figure\"}]"
motivation: 现有单细胞方法无法在测序前富集正确编辑的细胞，缺乏可扩展的因果验证手段。
method: SELECT-seq利用Cas12a靶向同时进行SNP特异性PCR和荧光检测，与全转录组扩增在单管中完成。
result: "在PIK3CA突变细胞系中准确区分基因型，NRF2突变池富集后准确率86%，转录组效应一致性87.5%。"
conclusion: SELECT-seq提供快速、可扩展的单细胞基因型-表型关联方法，避免克隆步骤。
---

## 摘要
高通量测序的进步已将数百万个假定的遗传变异与疾病关联起来。然而，建立遗传变异与下游转录结果之间因果关系的可扩展实验方法仍然是一个重大挑战。将基因分型与转录组分析相结合的单细胞方法提供了一种解决途径，但无法在测序前富集正确编辑的细胞，限制了规模。我们提出了 SELECT-seq（SNP Enrichment Leveraging Cas12a Targeting），这是一种快速方法，可在全转录组扩增的同时实现 SNP 特异性 PCR 扩增和 Cas12a 介导的荧光检测。这种一锅法工作流程能够识别和富集携带 SNP 的单细胞，从而为分析基因型-表型关联提供一种快速且可扩展的方法，避免了繁琐的单细胞克隆步骤。作为原理验证，我们展示了 SELECT-seq 能够基于 PIK3CA (NM_006218.4:c.3463A>G) 突变区分 U-2 OS 和 T-47D 细胞系，同时保持转录组完整性。它从初编辑池中物理富集了罕见的 NRF2 T80K (NM_006164.5:c.390C>A) 突变细胞（6.7%），实现了 86% 的基因型准确性，并且与克隆的 NRF2 T80K 细胞系相比，在转录组效应上显示出 87.5% 的方向一致性。因此，SELECT-seq 提供了一种快速、可扩展且广泛可用的方法，用于以单细胞分辨率绘制基因型-表型关系。

## Abstract
Advances in high-throughput sequencing have associated millions of putative genetic variants with disease. However, scalable experimental methods to establish causal relationships between genetic variants and downstream transcriptional outcomes remain a major challenge. Single-cell methods that integrate genotyping with transcriptomic profiling provide a way to address this, but do not enable pre-sequencing enrichment of correctly edited cells, limiting scale. We present SELECT-seq (SNP Enrichment Leveraging Cas12a Targeting), a rapid method that allows SNP-specific PCR amplification and Cas12a-mediated fluorescence detection simultaneously with whole-transcriptome amplification. This one-pot workflow enables identification and enrichment of SNP-bearing single cells, making a rapid and scalable methodology for analysis of genotype-phenotype linkage avoiding laborious single cell cloning steps. As a proof of principle we show that SELECT-seq distinguishes U-2 OS and T-47D cell lines based on a PIK3CA (NM_006218.4:c.3463A>G) mutation while preserving transcriptome integrity. It physically enriches a rare NRF2 T80K (NM_006164.5:c.390C>A) mutant cells (6.7%) from a prime-edited pool, achieving 86% genotype accuracy, and shows 87.5% directional concordance in the transcriptomic effects compared with a clonal NRF2 T80K cell line. SELECT-seq thus provides a rapid, scalable and widely accessible approach for mapping genotype-phenotype relationships at single-cell resolution.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：高通量测序发现了数百万遗传变异与疾病关联，但缺乏可扩展的实验方法建立变异与下游转录结果之间的因果关系。现有单细胞方法（如Target-seq、CRAFT-seq、scSNV-seq）虽能结合基因分型与转录组分析，但均无法在测序前富集正确编辑的细胞，导致当编辑效率低或异质性高时，测序数据被未编辑或错误编辑的细胞主导，限制了实验规模和成本效率。
- **整体含义**：本文提出的SELECT-seq（SNP Enrichment Leveraging Cas12a Targeting）旨在通过一锅法（one-pot）工作流程，在单细胞全转录组扩增的同时，实现SNP特异性PCR和Cas12a介导的荧光检测，从而在测序前直接识别和富集携带SNP的单细胞，避免繁琐的单细胞克隆步骤，加速基因型-表型关联研究。

### 2. 论文提出的方法论
- **核心思想**：整合等位基因特异性PCR（使用3'端硫代磷酸酯修饰的引物）与CRISPR-Cas12a的附带切割活性。在单细胞裂解、逆转录后，进行多重PCR：同时扩增全长cDNA和SNP目标位点（引物3'末端匹配SNP，并带有3个硫代磷酸酯键以增强特异性）。PCR产物直接加入Cas12a反应混合物（含crRNA和荧光-淬灭ssDNA报告探针），Cas12a识别目标扩增子后激活附带切割，释放荧光信号，从而在测序前判断该孔是否含有SNP编辑的细胞。
- **关键技术细节**：
  - **引物设计**：基于Primer-BLAST设计，引物3'末端与SNP完全匹配，最后3个核苷酸为硫代磷酸酯修饰。通过测试不同碱基配对情况（19个额外SNP位点，76对引物）验证特异性达98.7%。
  - **Cas12a检测优化**：使用DeepCpf1预测crRNA活性，筛选最优crRNA；优化缓冲液、酶浓度、crRNA浓度和报告探针设计。
  - **一锅法工作流**：逆转录后，在同一管中进行全程扩增（增加PCR循环至35轮），然后直接添加Cas12a反应液（5 μL至10 μL PCR产物），无需纯化。荧光监测30分钟，根据阈值判断SNP阳性/阴性。
  - **下游处理**：纯化全转录组文库（AMPure XP磁珠），进行标签化和索引PCR，用于测序。
- **公式/算法流程**：无明确公式，但包含阈值判断：以ΔF（t时刻荧光减去初始荧光）作为分类依据，根据阴性对照和阳性群体分离程度设定阈值（如NRF2实验中以100,000为界）。

### 3. 实验设计
- **数据集与场景**：
  - **场景1（区分细胞系）**：U-2 OS（PIK3CA野生型，T/T纯合）和T-47D（PIK3CA c.3463A>G杂合突变，T/C）。单细胞分选到96孔板，SELECT-seq检测PIK3CA突变。
  - **场景2（稀有编辑富集）**：使用初编辑（prime editing）技术对HAP1细胞引入NRF2 T80K突变（c.390C>A），池中突变比例约6.7%。分别使用T80K特异性引物和WT特异性引物，通过Cas12a荧光筛选阳性孔。
- **基准方法（benchmark）**：
  - 与Smart-seq3（金标准scRNA-seq方法）比较转录组质量：检测基因数、伪批量表达相关性、差异表达一致性、标记基因重叠。
  - 与独立克隆的NRF2 T80K细胞系比较转录组效应方向一致性。
- **对比方法**：在引言中提及Target-seq、CRAFT-seq、scSNV-seq等，但未直接进行实验对比。主要对比自身条件的差异（有/无crRNA、不同crRNA、不同测序深度）。

### 4. 资源与算力
- **未明确说明**：文中未提及使用的GPU型号、数量、训练时长。仅说明使用Element Aviti平台进行测序，数据分析使用zUMIs v2.9.7、STAR v2.7.11b等软件。无深度学习模型训练，因此无相关算力需求。

### 5. 实验数量与充分性
- **实验数量**：
  - 引物特异性验证：19个额外SNP位点×4种碱基引物=76对引物，在U-2 OS（纯合）和T-47D（杂合）中测试。
  - PIK3CA细胞系实验：U-2 OS和T-47D各约40-42个单细胞（crRNA-和crRNA+条件），加上Smart-seq3对照。
  - NRF2 T80K稀有富集实验：960孔板（约960个单细胞），筛选出46个T80K阳性孔（4.8%），随后对36个阳性细胞和34个阴性细胞进行基因型验证。
  - 转录组分析：比较不同测序深度（50k~400k reads/cell）、不同crRNA、有无Cas12a反应等。
- **充分性评价**：
  - **优点**：实验设计覆盖了原理验证（区分已知基因型）、实际应用（富集稀有编辑）、基准比较（与Smart-seq3和克隆参考）。消融实验（crRNA- vs crRNA+、不同crRNA、测序深度）较全面。
  - **不足**：
    - 样本量偏小：每个条件仅几十个单细胞，统计效力有限。
    - 未与现有同类方法（如CRAFT-seq、scSNV-seq）进行直接实验对比，缺乏公平的性能比较（如富集效率、转录组质量、通量等）。
    - 只测试了两种变异类型（点突变PIK3CA和NRF2 T80K），未涉及缺失、插入、剪接变异等。
    - 验证仅基于一个细胞系（HAP1）和一个编辑系统（prime editing），推广性需更多验证。

### 6. 论文的主要结论与发现
- SELECT-seq可在8小时内完成单细胞SNP检测和全转录组扩增，而传统克隆扩增需2-3周。
- 在PIK3CA突变细胞系中：SELECT-seq准确区分U-2 OS（WT）和T-47D（突变），Cas12a荧光信号与转录组UMAP身份一致。虽然基因检测数略有降低，但伪批量表达相关性高（Pearson r≈0.95），差异表达方向与Smart-seq3一致。
- 在NRF2 T80K稀有突变池（6.7%）中：SELECT-seq成功富集（4.8%阳性孔），基因型验证准确率86%（31/36），WT阴性准确率94%。富集后转录组分析显示NRF2靶基因上调，与独立克隆系方向一致性达87.5%（14/16核心基因，二项检验P=0.004），表明可捕捉生物学相关的基因型-表型关系。
- 增加测序深度（如200,000 reads/cell）可补偿SELECT-seq的敏感性损失，保持生物学对比度。

### 7. 优点（方法或实验设计亮点）
- **一锅法工作流**：避免样本转移和纯化步骤，减少丢失和操作时间，适合低起始量单细胞。
- **测序前富集**：直接通过荧光筛选阳性孔，避免对大量未编辑细胞测序，节省成本。
- **无需专用仪器**：仅需qPCR仪（用于荧光监测）和常规PCR仪，广泛可及。
- **快速且可扩展**：从分选到文库制备仅需8小时，比克隆扩增快数十倍；通过编程微流控或水凝胶胶囊有望进一步提高通量。
- **灵活性**：Cas12a通过重新设计crRNA即可检测不同SNP，无需设计TaqMan探针等复杂优化。
- **适用于不可克隆细胞**：如原代T细胞、造血干细胞等，无需长期培养。

### 8. 不足与局限
- **荧光读数为二值**：只能判断是否存在编辑，无法区分杂合/纯合，需后续测序验证。
- **转录组质量略有下降**：与Smart-seq3相比，同样的测序深度下检测基因数减少，需要更高测序深度补偿（约200k reads/cell以上）。
- **通量限制**：当前为96/384孔板格式，低于液滴微流控方法（如scSNV-seq）。作者提及未来可通过可编程微流控或半透性水凝胶提高通量，但未实现。
- **样本量较小**：验证细胞数较少（每个条件几十个），统计稳定性不足。
- **未直接对比同类方法**：缺乏与CRAFT-seq、Target-seq等在相同条件下的性能比较（富集效率、准确性、转录组完整性）。
- **可能引入Cas12a干扰**：Cas12a反应可能轻微降低基因检测数（特别是在有靶标扩增时），虽然差别不大，但需谨慎处理。
- **仅测试点突变**：未验证对插入、缺失、剪接位点等复杂变异的适用性。引物设计对某些序列上下文可能不理想（如GC含量低或重复区域）。
- **应用限制**：需要已知SNP序列和单细胞分选设备（如FACS），且对转录组完整性要求高的场景可能需优化。

（完）
