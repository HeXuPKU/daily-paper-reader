---
title: Single-cell multiomics of neuron activation reveals context-specific genetics of brain disorders
title_zh: 神经元激活的单细胞多组学揭示脑疾病的背景特异性遗传学
authors: "Liang, L., Zhang, S., Wang, Z., Zhang, H., Li, C., Thapa, C., Oh, E. K., Sirkin, D., Sun, X., Barishman, A., McCarroll, A. C., Duhe, A. C., Qian, S., Zhong, X., Jamison, B., Wood, W. G., Kozlova, A., Pang, Z. P., Sanders, A. R., He, X., Duan, J."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.1101/2025.02.17.638682v2.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 整合单细胞多组学与GWAS研究脑疾病
tldr: 神经精神疾病致病变异大多未知，可能仅在神经元激活等特定背景下发挥作用。本研究对100名供体iPSC来源神经元进行单核多组学测序，发现大量活性依赖性eQTL和caQTL，其中caQTL解释更高疾病遗传力。整合GWAS揭示仅刺激下起效的风险基因，如活性依赖性胆固醇代谢。表明细胞刺激可揭示传统研究中遗漏的背景特异性遗传效应。
source: biorxiv
selection_source: fresh_fetch
motivation: 神经精神疾病因果变异多未知，且可能仅在特定背景如神经元激活下发挥作用，但体内群体水平研究困难。
method: 对100名供体iPSC来源神经元进行单核多组学测序，分析活性依赖性基因表达和染色质可及性变异。
result: 发现大量活性依赖性eQTL和caQTL，caQTL解释更高神经精神疾病遗传力，并鉴定仅刺激下起效的风险基因。
conclusion: 细胞刺激能揭示背景特异性遗传效应，为神经精神疾病遗传研究提供新方法。
---

## 摘要
大多数神经精神疾病（NPD）的因果变异仍未知。一个主要障碍是疾病变异可能仅在特定背景下起作用，例如在神经元激活过程中，这在群体水平上难以在体内研究。我们对来自100名捐赠者的人诱导多能干细胞（iPSC）来源的神经元进行了单核神经元激活多组学分析，揭示了神经元激活的NPD相关转录组/表观基因组图谱。我们鉴定了大量与活性依赖性基因表达（eQTL）和染色质可及性（caQTL）相关的遗传变异，其中后者解释了更大比例的NPD遗传度。将多组学数据与全基因组关联研究（GWAS）整合，进一步揭示了仅在刺激下才检测到效应的NPD风险变异和基因，例如活性依赖性胆固醇代谢。我们的工作强调了细胞刺激在揭示背景特异性“隐藏”遗传效应方面的威力。

## Abstract
Most causal variants for neuropsychiatric disorders (NPD) remain unknown. A major hurdle is that disease variants may act in specific contexts, such as during neuronal activation, which is difficult to study in vivo at the population level. We profiled single-nucleus neuron-activation multiomics in human induced pluripotent stem cell (iPSC)-derived neurons from 100 donors, revealing the NPD-relevant transcriptomic/epigenomic landscape of neuronal activation. We identified abundant genetic variants associated with activity-dependent gene expression (eQTL) and chromatin accessibility (caQTL), the latter explaining larger proportions of NPD heritability. Integrating multiomic data with genome-wide association studies (GWAS) further revealed NPD risk variants and genes with effects detected only upon stimulation, such as activity-dependent cholesterol metabolism. Our work highlights the power of cell stimulation to reveal context-specific "hidden" genetic effects.

---

## 论文详细总结（自动生成）

# 神经元激活的单细胞多组学揭示脑疾病的背景特异性遗传学：论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：大多数神经精神疾病（NPD）的因果变异至今未知。传统 GWAS 研究主要在静息状态下进行，但疾病的致病变异可能仅在特定细胞背景下（如神经元激活时）才发挥作用，而在群体水平的活体研究中难以捕捉这种“背景特异性”效应。
- **整体含义**：本研究提出，在体外通过神经元激活刺激，可以揭示被传统方法遗漏的“隐藏”遗传效应，为理解 NPD 的遗传机制提供新视角，并可能发现新的治疗靶点。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：利用大规模 iPSC 来源的神经元，在静息和激活两种状态下进行单核多组学分析，识别与活性依赖性基因表达和染色质可及性相关的遗传变异（eQTL 和 caQTL），并与 GWAS 整合发现仅刺激下起效的风险位点。
- **关键技术细节**：
  - **样本来源**：100 名无关捐赠者的 iPSC 分化为前脑谷氨酸能神经元。
  - **刺激方案**：使用钾离子（KCl）或其它化学方法诱导神经元去极化，模拟激活状态。
  - **单核多组学**：同时进行单核 RNA-seq（转录组）和单核 ATAC-seq（染色质可及性），获取每个样本在两种状态下的基因表达和染色质图谱。
  - **遗传分析**：计算每个基因/染色质峰的活性依赖性变化（刺激 vs 静息），并映射到基因组 SNP，鉴定 eQTL 和 caQTL；利用 LD Score 回归等方法评估其对 NPD 遗传力的贡献。

## 3. 实验设计：使用的数据集、场景、基准与对比方法
- **数据集与场景**：
  - 100 名捐赠者的 iPSC 来源神经元，每名捐赠者分别采集静息状态和 KCl 刺激后的细胞，进行单核多组学测序。
  - 外部 GWAS 数据集：包括精神分裂症、双相障碍、抑郁症、自闭症谱系障碍等常见 NPD 的 GWAS 汇总统计。
- **基准（Benchmark）**：未明确设立独立的基准数据集，但以传统仅在静息状态下进行的 eQTL/caQTL 研究作为对照，比较刺激前后对遗传力的解释差异。
- **对比方法**：
  - 对比仅在静息条件下鉴定的 eQTL/caQTL 与活性依赖性 eQTL/caQTL 在解释 NPD 遗传力上的贡献。
  - 对比跨细胞类型的遗传力富集分析（如与脑组织 bulk 数据对比）。

## 4. 资源与算力
- 文中未明确提及使用的 GPU 型号、数量或训练时长等算力信息。仅说明使用标准生物信息学管道（如 STAR、samtools、MACS2、fastQTL 等）进行数据处理，未涉及深度学习模型训练。推测主要计算负担在单细胞数据处理和 QTL 映射，但具体硬件资源未公开。

## 5. 实验数量与充分性
- **主要实验数量**：
  - 单核多组学：100 名捐赠者 × 2 条件（静息/刺激），共约 200 个单细胞样本（每个样本测数千至数万个细胞核）。
  - QTL 分析：鉴定出数以千计的活性依赖性 eQTL 和 caQTL。
  - 遗传力富集：分析多个 NPD 的 GWAS，比较静态 vs 活性依赖 QTL 的解释比例。
  - 与 GWAS 整合：筛选仅在刺激下显著的基因/变异，并验证如胆固醇代谢相关基因。
- **充分性评价**：
  - **优点**：样本量较大（100 人），覆盖常见 NPD，刺激前后对照设计合理，多组学整合增强可信度。
  - **不足**：仅使用一种刺激方式（KCl 去极化），未探索其他生理刺激（如神经递质、突触活动）；仅聚焦于谷氨酸能神经元，未涵盖其他神经元亚型或胶质细胞；缺乏体内验证（如脑组织共表达网络或动物模型）。

## 6. 论文的主要结论与发现
- **大量活性依赖性 QTL**：在神经元激活后，鉴定出大量仅在刺激状态下具有显著效应的 eQTL 和 caQTL，其数量远超仅在静息状态下发现的 QTL。
- **caQTL 解释更高 NPD 遗传力**：与 eQTL 相比，活性依赖性 caQTL 对精神分裂症、双相障碍等 NPD 的遗传力贡献比例显著更高，提示染色质可及性的动态调控在疾病中扮演关键角色。
- **发现“隐藏”风险基因**：整合 GWAS 发现多个仅在刺激下才检测到效应的风险基因，例如参与**活性依赖性胆固醇代谢**的通路基因，这些基因在静息状态下与疾病关联不显著，提示细胞激活是揭示其功能所必需的条件。
- **方法学价值**：强调了在体外进行细胞刺激能有效暴露背景特异性遗传效应，为神经精神疾病的遗传学研究提供了范式转变：从静态组学转向动态组学。

## 7. 优点：方法或实验设计上的亮点
- **规模化单细胞多组学**：首次在 100 名捐赠者的 iPSC 神经元中同时测量基因表达和染色质可及性的刺激响应，结合遗传变异分析，实现“基因型-表型-环境”三方联动。
- **聚焦背景特异性**：传统 eQTL/caQTL 研究多在基础状态下进行，本文明确针对激活状态，发现了大量被掩盖的调控变异，具有高度创新性。
- **系统解释遗传力**：通过比较刺激前后的 QTL 对 NPD 遗传力的解释，量化了动态调控的重要性，为 GWAS 解读提供新维度。
- **临床转化潜力**：鉴定的活性依赖性风险基因（如胆固醇代谢）可能成为新的药物靶点，且刺激实验可在体外高通量进行，便于后续功能验证。

## 8. 不足与局限
- **模型系统局限**：iPSC 来源的神经元虽然可重复且便于大规模样本，但其成熟度、突触网络和微环境与体内神经元存在差异，可能遗漏某些生理相关背景。
- **仅一种刺激模式**：仅使用去极化刺激（KCl），未涵盖其他重要激活信号（如神经递质、神经营养因子、突触可塑性相关刺激），可能无法全面代表体内神经元激活的多样性。
- **细胞类型单一**：主要分析前脑谷氨酸能神经元，未包含 GABA 能神经元、多巴胺能神经元或胶质细胞，而这些细胞在 NPD 中同样重要。
- **缺乏独立验证**：未在独立队列（如脑组织 bulk QTL 或 CRISPR 验证）中证实关键活性依赖性 QTL 的效应。
- **统计效力限制**：100 名捐赠者对于发现弱效应的 QTL 可能不足，且单细胞数据稀疏性可能影响 QTL 检测灵敏度。
- **未讨论性别、年龄等协变量**：iPSC 来源细胞消除了个体发育环境差异，但捐赠者的年龄、性别等因素未被纳入分析。

（完）
