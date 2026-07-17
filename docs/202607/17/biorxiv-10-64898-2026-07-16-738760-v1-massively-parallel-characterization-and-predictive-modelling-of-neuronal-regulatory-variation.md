---
title: Massively parallel characterization and predictive modelling of neuronal regulatory variation
title_zh: 神经元调控变异的大规模平行表征与预测建模
authors: "Salomon, K., Deng, C., Dash, P. M., Chalkiadakis, T., Li, Q., Chen, Z., Page, N. F., Helal, M., Roener, S., Kundaje, A., Langenberg, C., Pietzner, M., Shendure, J., Schubach, M., Ahituv, N., Kircher, M."
date: 2026-07-17
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.16.738760v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 将大规模MPRA功能基因组学数据与GWAS变异效应预测相结合
tldr: "非编码调控变异是疾病风险的主要来源但功能难以解析。本研究对524个疾病相关基因附近>2.7万个候选CREs中的>4.6万个自然变异进行大规模lentiMPRA测定，系统量化其调控效应。结果显示等位基因效应在不同频率变异中发生率相似，效应强度主要由元件活性和序列上下文决定，且调控效果分散于多种转录因子而非单一主调控因子。该资源改善了调控变异效应预测并为模型开发提供基准。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738760-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1696, \"height\": 881, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738760-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1701, \"height\": 1233, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738760-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1333, \"height\": 2235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738760-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1564, \"height\": 2085, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738760-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1683, \"height\": 1377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738760-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1764, \"height\": 1154, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738760-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1039, \"height\": 1037, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738760-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1686, \"height\": 1296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738760-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1711, \"height\": 663, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738760-v1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1686, \"height\": 1246, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738760-v1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1690, \"height\": 643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738760-v1/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1527, \"height\": 1018, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738760-v1/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1642, \"height\": 1642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-16-738760-v1/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1168, \"height\": 2063, \"label\": \"Figure\"}]"
motivation: 非编码调控变异功能未知，亟需大规模实验量化其调控效应以理解疾病机制。
method: "利用大规模lentiMPRA在人类兴奋性神经元中测定>4.6万变异对>2.7万CREs的等位基因效应。"
result: 变异效应率在常见、罕见和单例中相当，效应大小由元件活性和序列上下文主导。
conclusion: 建立功能变异目录，改进调控变异预测模型，揭示调控效应分散于多种转录因子。
---

## 摘要
疾病相关变异常位于非编码顺式调控元件（CREs）中，但其功能后果仍知之甚少。我们在人类兴奋性神经元中进行了大规模lentiMPRA实验，量化了超过46,000个自然发生的变异对524个疾病相关基因附近超过27,000个候选CREs的影响。这些数据比当前最先进的模型更有效地改善了调控变异效应的预测。常见、罕见和单例变异的显著等位基因效应发生率相当，表明在MPRA可测量的效应范围内，群体频率携带的关于每个变异调控影响的信息有限。变异效应的可检测性和幅度主要由其所在调控元件的基线活性和局部序列背景决定。调控效应分布在众多转录因子上，而非集中于主调控因子，这与组合增强子架构一致。我们建立了一个大规模功能变异目录，并为开发和评估非编码调控变异模型提供了互补的基准和资源。

## Abstract
Disease-associated variants reside frequently in noncoding cis-regulatory elements (CREs), yet their functional consequences remain poorly understood. We performed a large-scale lentiMPRA in human excitatory neurons, quantifying the impact of >46,000 naturally occurring variants across >27,000 candidate CREs near 524 disease-associated genes. These data improved regulatory variant effect predictions beyond state-of-the-art models. Significant allelic effects occurred at comparable rates across common, rare, and singleton variants, demonstrating that, within MPRA-measurable effects, population frequency carries limited information about per-variant regulatory impact. Variant effect detectability and magnitude were governed primarily by baseline activity of the enclosing regulatory element and local sequence context. Regulatory effects were distributed across numerous transcription factors rather than concentrated in master regulators, consistent with a combinatorial enhancer architecture. We establish a large-scale functional variant catalog and provide a complementary benchmark and resource for developing and evaluating models of noncoding regulatory variation.

---

## 论文详细总结（自动生成）

## 论文总结：神经元调控变异的大规模平行表征与预测建模

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：非编码区的顺式调控元件（CREs）携带大量疾病相关变异，但其功能影响仍难以解析。现有注释资源（如ENCODE SCREEN）虽能标注候选CREs，但细胞类型特异性强，且大部分自然变异的功能后果未知。需要大规模功能实验来量化变异对调控活性的影响，并评估当前计算模型的预测能力。
- **整体含义**：该研究通过大规模lentiMPRA在人类兴奋性神经元中直接测量>4.6万个自然变异（覆盖常见、罕见和单例变异）对>2.7万个CREs的等位基因调控效应，旨在解答：调控活性与等位基因频率的关系如何？当前计算模型（如Enformer、AlphaGenome）能否准确预测这些效应？调控变异的机制是否依赖于单一主转录因子还是组合性架构？研究建立了一个大规模功能变异目录，为理解非编码变异的功能约束、改进预测模型提供了重要资源。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：采用**慢病毒载体介导的大规模平行报告分析（lentiMPRA）**，将待测的270 bp序列（包含候选CRE及其内部的变异）克隆到含随机条形码的报道基因载体中，在NGN2诱导的人类兴奋性神经元（iPSC来源）中检测转录活性。通过比较RNA与DNA的条形码比率（即RNA/DNA比值）量化调控活性；通过比较参考等位基因和替代等位基因的活性差异（log2FC）估计变异的等位基因效应。
- **关键技术细节**：
  - **CRE选择**：选取ENCODE SCREEN v3中位于524个疾病相关基因（神经、心脏、临床可干预基因及随机基因）TSS ± 50 kb范围内的cCREs，去除CTCF-only及不良序列。
  - **变异选择**：从gnomAD v3.1.2中提取所有常见变异（AF >1%）以及通过**Enformer**预测（基于ΔDNase信号）优先选择的罕见/单例变异（优先选择预测效应最强的激活型和抑制型，各约70%和15%，另15%随机）。
  - **实验流程**：合成270 bp寡核苷酸池，连接随机条形码，克隆至lentiMPRA载体，包装慢病毒，以MOI=100转导NGN2诱导神经元（第7天感染，培养至第14天），分别提取DNA和RNA，通过靶向测序获得条形码计数。
  - **定量分析**：使用**BCalm**软件（基于limma框架）进行统计学检验：CRE活性相对于scramble对照的差异（FDR <0.05），变异等位基因效应的显著性（FDR <0.1）。效应大小定义为log2(ALT/REF)比值。
  - **计算模型评估**：将AlphaGenome编码器在MPRA数据上进行**微调**，采用3折交叉验证，序列输入包括两侧15 bp接头序列和32 bp启动子，通过MLP头预测活性值，损失函数为MSE。数据增强包括随机反向互补和循环移位。
  - **TF结合分析**：利用**ReMap2022 ChIP-seq峰**（实验支持）和**FIMO + HOCOMOCO v13 PWM**（预测）注释TF结合位点，检验与显著变异的富集性，并采用弹性网络回归和ridge逻辑回归分析TF与元件活性的关联。

### 3. 实验设计：数据集、场景、基准和对比方法

- **数据集**：
  - 实验数据：68,904个通过质控的寡核苷酸，对应24,358个独特CREs（24,510个包括双链方向）和38,684个自然变异（38,968个包括双链测试）。其中包含10,309个单例、10,251个罕见、8,077个常见和10,047个极常见变异。
  - 对照集：阳性对照（166个已知活性增强子）、阴性对照（500个scramble序列、451个低活性元件）。
  - 外部注释：ENCODE SCREEN v4、ReMap2022、FIMO/HOCOMOCO、E2G连接、精细定位eQTL、GWAS目录、phyloP保守性等。
- **基准场景**：在三个变异集上评估模型性能：
  1. 所有测试变异（n=38,968，阳性=1,018）；
  2. 位于显著活性CRE（dCRE）内的变异（n=2,711，阳性=195）；
  3. NGN2开放染色质区域的变异（n=453，阳性=38）。
  进一步按等位基因频率层级（极常见、常见、罕见、单例）和元件活性四分位数分层。
- **对比方法**：
  - **预训练模型**：Enformer（200 kb上下文）、AlphaGenome（1 Mb上下文）、CADD v1.7、NGN2 chromBPNet（仅在NGN2 ATAC-seq上训练）。
  - **微调模型**：基于AlphaGenome编码器的MPRA微调模型。
- **评估指标**：ROC-AUC和PR-AUC，95%置信区间通过分层bootstrap（2000次）估计。

### 4. 资源与算力

论文**未明确说明**训练模型所使用的GPU型号、数量或训练时长。仅提及计算在柏林健康研究所（BIH）的HPC集群上完成，并使用HPC@Charité和吕贝克大学OMICS HPC集群。AlphaGenome微调模型的训练细节包含batch size=128、Adam优化器、早停等，但未提及硬件规格。

### 5. 实验数量与充分性

- **实验组数**：
  - 3个生物重复的lentiMPRA实验。
  - 变异效应显著性检验覆盖38,968个变异。
  - 模型评估**3折交叉验证**（按染色体分组），并针对不同分层（频率、活性、开放染色质）进行多组分析。
  - TF富集分析采用Fisher精确检验（多组比较，BH校正）和ridge逻辑回归（bootstrap 1000次）。
  - 消融分析：比较Enformer优先选择vs随机选择对罕见/单例变异显著率的影响。
- **充分性评估**：
  - 实验规模巨大（>4.6万变异，>2.7万CREs），具有统计效力。
  - 针对变异频率和元件活性的分层分析较全面，且讨论了优先选择偏好导致的偏差，并通过随机子集验证结论稳健性。
  - 仍存在局限：罕见/单例变异中仅1.7%被测试（受限于合成容量），且Enformer优先策略引入偏向，可能影响频率-效应关系推断的普遍性。
  - 模型评估仅在MPRA数据集上，未在不同检测方法（如CRISPR扰动、eQTL）上验证泛化性。

### 6. 论文的主要结论与发现

1. **调控活性稀疏且具有细胞类型特异性**：仅约2.1%的CRE显示显著激活活性，4.8%显示显著抑制活性；脑注释的CREs在活跃元件中比例略高（OR=1.18），但大部分活跃元件缺乏脑注释，说明当前表观基因组图谱尚不完整。
2. **等位基因效应频率依赖性弱**：显著效应在常见、罕见和单例变异中的发生率相近（2.1%–3.0%）。去除Enformer偏好后，罕见/单例比率略降（1.9%/2.3%），但群体频率对效应大小和方向无显著解释力；效应可检测性主要由元件基线活性和序列环境决定。
3. **调控效果分散于众多转录因子**：未发现单一主调控因子主导变异效应；PWM预测和ReMap实验数据均显示效应分布在多个TF上，支持组合型增强子架构。
4. **序列预测模型性能有限但可提升**：Enformer和AlphaGenome在区分显著变异时ROC-AUC约0.57–0.58，PR-AUC约0.034；在活性元件内提升至0.61–0.62。NGN2 chromatin模型（chromBPNet）表现出更高PR-AUC（0.064–0.22）。通过在MPRA数据上微调AlphaGenome编码器，性能显著提升（全集ROC-AUC 0.78，PR-AUC 0.27；活性元件内0.81/0.43）。
5. **表型关联案例**：鉴定出多个与已知疾病（如帕金森病、杜普伊特伦病、ASD相关基因）重叠的变异，提供机制假设。

### 7. 优点：方法或实验设计上的亮点

- **系统化设计**：从疾病相关基因出发而非GWAS lead变异，避免了LD不确定性问题，覆盖了更完整的顺式调控空间。
- **大样本覆盖**：同时检测>4.6万变异，包括几乎所有常见变异和优先选择的罕见/单例变异，提供了大规模功能效应数据集。
- **多种方法的框架**：同时比较了多种序列模型（Enformer、AlphaGenome、CADD、chromBPNet）及通过微调适应MPRA的方法，为评估计算模型提供了统一基准。
- **TF机制分析**：结合实验（ReMap）和预测（PWM）两种方式注释TF结合，通过弹性网络和ridge逻辑回归识别与活性相关的TF，揭示了组合型调控机制。
- **偏差讨论与稳健性验证**：明确分析了Enformer优先选择对罕见/单例变异显著率的影响，并通过随机子集验证主要结论不受偏向驱动。

### 8. 不足与局限

- **实验覆盖局限性**：
  - 仅测试了270 bp片段，无法捕获长程染色质环化和全基因组染色质环境。
  - 仅测试了TSS ± 50 kb内的CREs，可能遗漏远距离增强子（如>1 Mb的作用）。
  - 罕见/单例变异覆盖率极低（1.7%），且优先选择主要基于单一模型（Enformer），可能引入系统性偏向。
- **细胞类型特异性**：仅在NGN2诱导的兴奋性神经元中测试，无法直接扩展到其他神经元亚型或神经胶质细胞。
- **模型评估的公平性**：微调模型在相同实验条件下训练和测试，而其他模型是预训练的，不具备MPRA特异性，因此性能比较存在训练目标不匹配的问题，不能简单判定优劣。
- **缺乏正交验证**：变异效应的统计显著性基于MPRA内部统计，未在独立实验（如CRISPR敲除、胶质细胞MPRA）中验证。
- **统计效力限制**：在频率分层和活性分层中，阳性变异数量较少（尤其单例、罕见组），导致置信区间宽，部分差异无统计学意义。
- **TF富集分析的不确定性**：PWM扫描导致的假阳性率高，ReMap数据有限，且未直接证明TF结合的改变导致效应。

（完）
