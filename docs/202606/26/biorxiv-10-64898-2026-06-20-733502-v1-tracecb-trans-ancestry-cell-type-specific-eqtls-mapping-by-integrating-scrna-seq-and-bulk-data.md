---
title: "traceCB: Trans-ancestry cell-type-specific eQTLs mapping by integrating scRNA-seq and bulk data"
title_zh: "traceCB: 通过整合单细胞RNA测序和批量数据的跨祖先细胞类型特异性eQTL映射"
authors: "JIANG, W., Xiao, J., Cai, M."
date: 2026-06-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.20.733502v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 跨祖源细胞类型特异性eQTL定位方法
tldr: "跨祖先细胞类型特异性eQTL映射因统计功效不足而受限。traceCB通过整合单细胞和批量组织eQTL汇总统计，建模跨祖先遗传架构并处理细胞异质性，实现信息借用。在东亚和非洲免疫细胞中，有效样本量提升2.9倍，eGene发现增加约40%，复制率超90%，并改进GWAS共定位。该框架为利用全球资源揭示细胞层面调控变异提供了可扩展工具。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有跨祖先细胞类型eQTL映射在少数人群中统计功效不足，需要整合多祖先数据提升效能。
method: traceCB通过整合单细胞和批量组织eQTL汇总统计，显式建模跨祖先遗传架构并控制细胞异质性，优化信息借用。
result: "在东亚和非洲队列中，有效样本量提升2.9倍，eGene识别增加约40%，独立数据集复制率超90%。"
conclusion: traceCB是一种可扩展的跨祖先细胞类型eQTL映射工具，能增强调控变异发现并揭示复杂疾病细胞机制。
---

## 摘要
绘制细胞类型特异性表达数量性状位点(ct-eQTL)对于解读疾病相关变异至关重要，然而在代表性不足的人群中的研究因统计效力有限而受阻。本文提出traceCB，一个统计框架，通过整合来自不同人群的单细胞和批量组织eQTL研究的汇总统计量，增强目标祖先群体中的ct-eQTL映射。通过显式建模跨祖先遗传结构并考虑批量组织中的细胞异质性，traceCB优化了从统计效力较高的欧洲队列中借用信息，同时稳健控制第一类错误。模拟研究表明，与原始ct-eQTL相比，traceCB实现了更高的统计效力，尤其是在利用组织水平数据时。在东亚和非洲人群的免疫细胞应用中，traceCB将有效样本量提高了高达2.9倍，并识别出比单祖先分析多约40%的e基因，在独立数据集中的重复率超过90%。此外，traceCB改善了调控变异与血液及免疫相关性状GWAS信号的共定位，揭示了复杂疾病背后的细胞类型特异性机制。这些发现表明traceCB是一个强大且可扩展的工具，可利用全球基因组资源在细胞水平上改善跨人群的调控变异发现。

## Abstract
Mapping cell-type-specific expression quantitative trait loci (ct-eQTLs) is essential for interpreting disease-associated variants, yet studies in underrepresented populations are hindered by limited statistical power. Here, we present traceCB, a statistical framework that enhances ct-eQTL mapping in target ancestries by integrating summary statistics from single-cell and bulk-tissue eQTL studies across diverse populations. By explicitly modeling trans-ancestry genetic architecture and accounting for cellular heterogeneity in bulk tissues, traceCB optimizes information borrowing from well-powered European cohorts while robustly controlling for type I error. Simulation studies demonstrate that traceCB achieves superior statistical power compared to original ct-eQTL, particularly when leveraging tissue-level data. In an application to immune cells in East Asian and African cohorts, traceCB increased the effective sample size by up to 2.9-fold and identified approximately 40% more eGenes than single-ancestry analyses, with a replication rate exceeding 90% in independent datasets. Furthermore, traceCB improved the colocalization of regulatory variants with GWAS signals for blood and immune-related traits, revealing cell-type-specific mechanisms underlying complex diseases. These findings establish traceCB as a powerful and scalable tool for leveraging global genomic resources to improve regulatory variant discovery at the cellular level across diverse populations.

---

## 论文详细总结（自动生成）

# traceCB 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：细胞类型特异性表达数量性状位点（ct-eQTL）的定位对于解析GWAS风险变异的调控机制至关重要，但现有研究严重偏向欧洲血统，非欧洲人群（如东亚、非洲）的ct-eQTL统计效力极低，样本量通常不足百人。
- **背景**：scRNA-seq成本高、测序深度低导致噪声大，限制了ct-eQTL研究规模；同时不同祖先群体间遗传架构（等位基因频率、LD模式、效应大小）高度异质，传统固定效应或随机效应元分析方法无法有效借用跨祖先信息，导致第一类错误膨胀。
- **整体含义**：本文提出**traceCB**框架，通过整合目标人群（低效力）与欧洲人群（高效力）的单细胞和批量组织eQTL汇总统计量，显式建模跨祖先遗传结构，从而自适应地借用信息，提升非欧洲人群ct-eQTL映射效力，并控制假阳性。

## 2. 论文提出的方法论
### 核心思想
- 基于**广义矩估计（GMM）**框架，利用细胞类型特异性遗传力（heritability）和跨祖先共遗传力（co-heritability）实现信息跨群体转移。
- 对于批量组织数据，引入细胞类型去卷积模型，将批量eQTL效应分解为目标细胞类型贡献与非目标细胞类型贡献，并通过平均细胞类型比例将批量效应与单细胞效应关联。

### 关键技术细节
1. **模型构建**：
   - 目标人群单细胞：\( y_1 = X_1\beta_{c1} + \epsilon_1 \)
   - 辅助人群单细胞：\( y_2 = X_2\beta_{c2} + \epsilon_2 \)
   - 辅助人群批量组织：\( y_t = \pi_c \odot X_t\beta_{c2} + \pi_o \odot X_t\beta_{o2} + \epsilon_t \)，其中 \(\pi_c\) 为目标细胞类型比例（用均值\(\bar\pi_c\)近似）。
2. **效应模型**：假设 \(\beta_{c1}, \beta_{c2}\) 服从均值为0、协方差矩阵 \(\Omega\) 的分布，\(\Omega\) 包含SNP水平遗传力 \(\omega_1, \omega_2\) 和共遗传力 \(\omega_x\)。
3. **汇总统计量整合**：通过LD分数（ancestry-specific LD和trans-ancestry LD）将边际效应与 \(\Omega\) 连接，推导出条件均值和方差。
4. **traceCB估计量**：闭式解，\(\hat{b}_{1j}^{traceCB} = w_{1j}^\top (\hat{b}_{1j}, \hat{b}_{2j}, \hat{b}_{tj})^\top\)，权重 \(w_{1j}\) 由 \(\Omega\)、LD分数、细胞比例和估计误差方差决定。
5. **参数估计**：使用跨祖先LD分数回归（trans-ancestry LDSC）估计 \(\Omega\) 和膨胀常数；细胞比例通过CIBERSORTx去卷积获得。
6. **稳健策略**：仅当估计的共遗传力显著（p<0.10）时才借用信息，否则退化为原始目标人群统计量。若GMM方差非正，则回退至简化版本traceC（仅用单细胞数据）。

### 算法流程（文字说明）
1. 输入：目标祖先sc-eQTL汇总统计量、辅助祖先sc-eQTL汇总统计量、辅助祖先批量组织eQTL汇总统计量；参考面板（1000 Genomes）的LD分数；平均细胞类型比例。
2. 利用LDSC回归估计遗传力 \(\hat\omega_1, \hat\omega_2\)、共遗传力 \(\hat\omega_x\) 及膨胀常数。
3. 对每个基因的每个cis-SNP，根据公式（13）计算加权组合估计量 \(\hat{b}_{1j}^{traceCB}\) 及其方差（14）。
4. 若共遗传性不显著，设 \(\omega_x=0\)，仅利用目标人群信息。
5. 若批量数据不可用，采用traceC（仅使用 \(\hat{b}_{1}, \hat{b}_{2}\)）。
6. 输出：增强后的ct-eQTL效应大小、标准误、p值。

## 3. 实验设计
### 数据集
- **目标人群**：
  - **东亚（EAS）**：Biobank Japan (BBJ) ct-eQTL（样本量103，5个免疫细胞类型：单核细胞、CD4+ T、CD8+ T、NK、B细胞）。
  - **非洲（AFR）**：POPCELL项目（样本量80）。
- **辅助人群（欧洲）**：
  - 10个sc-eQTL研究（来自eQTL Catalogue，样本量167–420，匹配细胞类型）。
  - 批量组织eQTL：eQTLGen（全血，n=31,684）和GTEx v8（全血，n=670）作为辅助批量数据。
- **验证数据集**：独立东亚批量eQTL（Wang et al.，n=1,019）、OASIS单细胞eQTL（n=235）、CIMA（中国免疫多组学）。
- **GWAS数据**：Blood Cell Consortium (BCX) 14种血细胞性状（EAS）、BBJ三种免疫相关疾病（哮喘、类风湿关节炎、特应性皮炎）。

### Benchmark与对比方法
- **原始目标人群统计量**（仅使用BBJ或POPCELL单细胞eQTL）。
- **RE2(sc)**：随机效应元分析（仅整合sc-eQTL）。
- **RE2(sc+tissue)**：随机效应元分析（整合sc-eQTL+批量eQTL）。
- **traceC**：本文简化版（仅跨祖先sc整合）。
- **traceCB**：本文完整版。

### 模拟设计
- 基于UKBB和Chinese cohort的真实基因型，选择Chr22区域2,000个SNP作为cis-SNP。
- 模拟不同遗传架构：因果SNP比例（0.005–0.02）、遗传力（0.1–0.2）、跨祖先遗传相关性（0–0.9）、目标细胞比例（0.01–0.8）、样本大小（N1=50/100, N2=400, Nt=1000/5000）。
- 空假设设置：EAS遗传力=0，跨祖先遗传相关=0，评估第一类错误。
- 每个参数设定100次重复。

## 4. 资源与算力
- **未明确使用GPU**；算法基于CPU实现。
- **运行时分析**：处理22条常染色体加1个辅助研究，聚合CPU时间约3,201.7秒（平均约0.3秒/基因）；通过染色体级并行，最长单染色体处理时间432秒（约7.2分钟/研究）。论文未说明具体CPU型号或GPU型号。

## 5. 实验数量与充分性
- **模拟实验**：3大类（空假设、功率扫描、染色体级混合架构），每类包含多个参数组合（6–10种），每种100次重复。覆盖了不同因果SNP比例、遗传力、遗传相关、细胞比例、样本量。实验设计系统，但未对所有参数组合进行全交叉（部分默认固定）。
- **真实数据实验**：
  - 东亚：10个辅助研究 × 5种细胞类型（共50次分析），每个分析包含约2千–4千个基因。
  - 非洲：10个辅助研究（但大部分基因通过共遗传性过滤后数量较少，平均277个基因）。
  - 验证：内部（Wang et al.独立批量eQTL、OASIS、CIMA）和外部（GTEx替代批量组织实验）。
  - 共定位分析：14个BCX性状 + 3个BBJ疾病，跨多个辅助研究。
  - 敏感性分析：模拟去卷积误差、不同批量样本量、不同祖先（非洲）。
- **充分性与公平性**：
  - 与RE2比较时，明确指出RE2第一类错误膨胀，因此功率比较时未在主图中展示（补充图中有完整比较）。
  - 模拟中区分了来源特异性效应和共享效应，考虑了不同遗传架构。
  - 真实数据中使用了多个独立验证集，复制率高（>90%）。
  - 但主要局限性：仅验证血液免疫细胞类型；参数估计依赖LDSC，在小基因集中可能不准确。

## 6. 论文的主要结论与发现
1. **统计效力提升**：在东亚BBJ中，traceC平均有效样本量从103提升至188（1.82倍），traceCB提升至239（2.32倍）。在非洲队列（n=80）中，traceC提升至120（1.50倍），traceCB提升至136（1.70倍）。
2. **eGene发现增加**：东亚平均traceC识别28%更多eGenes（1929→2463），traceCB识别38%更多（1929→2669）。非洲traceC发现57个新eGenes，traceCB发现67个。
3. **复制率高**：东亚traceC/traceCB发现的eGenes在独立批量eQTL中复制率>90%（分别为93%和92%），与原始BBJ相当。
4. **共定位改善**：traceC和traceCB减少了共定位分析中的未决状态，使更多位点得以归类为共享因果变异或独立信号。例如在单核细胞计数GWAS中，traceC识别36个新共定位事件，traceCB识别41个。
5. **细胞类型特异性机制**：成功发现被原始BBJ遗漏但在H3K27ac ChIP-seq中具有调控活性的位点（如CTSW、KCNN4、MDFIC），揭示了单核细胞特异性调控。
6. **稳健性**：在非洲人群中也获得一致增益，验证了方法的跨祖先鲁棒性。

## 7. 优点
- **显式建模跨祖先遗传异质性**：通过估计遗传力、共遗传力和LD差异，自适应借用信息，而非简单元分析，严格控制第一类错误。
- **利用批量组织提升功率**：通过细胞去卷积模型，有效整合大规模批量eQTL数据（如eQTLGen n=31,684），显著提升低频细胞类型的检测效力。
- **汇总统计量驱动**：无需个体水平数据，仅需汇总统计和LD参考面板，便于共享和应用。
- **计算高效**：GMM闭式解，基因组规模分析仅需数分钟（并行后）。
- **完全开源**：提供Python包和详细文档，代码可重复。
- **多级验证**：内部重复（同一队列的不同细胞类型）、外部独立数据集（不同人群、不同技术平台）均验证高复制率。

## 8. 不足与局限
- **适用组织有限**：仅验证了血液免疫细胞类型；其他组织（如脑、肝）的单细胞eQTL数据在非欧洲人群中尚缺乏，限制了更广泛的应用。
- **参数估计敏感**：依赖于基因水平遗传力和共遗传力的估计，在小样本或SNP数少的基因中估计可能不稳定，导致信息借用不足或方差非正定。
- **去卷积不确定性被忽略**：细胞类型比例作为固定输入，未传递其估计不确定度；当前敏感性分析显示第一类错误控制良好，但可能降低功率或引入偏差（特别是稀有细胞类型）。
- **仅针对两个人群**：当前实现仅整合两个祖先群体（目标+欧洲），未扩展到多人群或混合祖先。
- **依赖辅助数据质量**：辅助人群sc-eQTL和批量eQTL的样本量、技术异质性（如BLUEPRINT测序方法不同）影响增益大小；eQTLGen中包含部分非欧洲样本，但论文声称鲁棒。
- **非目标细胞类型的处理简化**：bulk模型中用一个聚合效应代表所有非目标细胞，未能解析多种非目标细胞类型的独立贡献，可能丢失部分信号。
- **未扩展到其他分子层级**：当前仅限于eQTL，未整合splicing QTL、protein QTL、methylation QTL等。

（完）
