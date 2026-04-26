---
title: Sex stratified analyses enable new genetic insights into brain imaging phenotypes
title_zh: 性别分层分析为脑成像表型提供了新的遗传学见解
authors: "Zhang, N., Wang, S., Fu, J., Ji, Y., Liu, N., Qian, Q., Xue, H., Ding, H., Liang, M., Qin, W., Xu, J., Yu, C."
date: 2026-04-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.21.719541v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 脑影像表型的性别分层遗传分析和精细定位
tldr: "本研究通过对22,950名男性和22,950名女性的805种神经影像表型进行系统分析，对比了性别分层与性别合并的遗传研究方法。研究发现性别分层分析不仅识别出大量新的遗传关联、因果关联以及与性激素和精神分裂症的共定位信号，还显著提升了遗传力估计和多基因风险预测的准确性。该工作强调了在神经影像遗传学研究中常规开展性别分层分析的重要性，为理解大脑表型及相关疾病的性别差异提供了新见解。"
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在探究大脑影像表型及相关疾病风险中普遍存在的性别差异及其背后的遗传机制。
method: "对样本量和协变量匹配的男女各22,950人的805种神经影像表型，系统对比性别分层与性别合并的遗传关联分析。"
result: 性别分层分析发现了47个新遗传关联、170个新因果关联，以及大量与性激素和精神分裂症的新共定位信号，并优化了遗传力估计。
conclusion: 常规进行性别分层遗传分析对于阐明大脑影像表型及相关疾病的性别特异性与共有遗传控制具有重要意义。
---

## 摘要
神经影像表型和脑疾病风险中普遍存在性别差异，但其潜在的遗传机制仍不清楚。我们研究了 22,950 名男性和 22,950 名女性（样本量和协变量均匹配）中 805 种神经影像表型遗传结构的性别差异，并系统地比较了性别分层与性别合并的遗传分析。我们发现了 8 个具有显著性别差异的变异-性状关联、235 个精细定位的性别主导因果关联、457 个与性激素的性别主导共定位，以及 96 个与精神分裂症的性别主导共定位。与性别合并分析相比，性别分层分析识别出 47 个新的遗传关联、170 个新的精细定位因果关联、1,019 个与性激素的新共定位，以及 191 个与精神分裂症的新共定位。此外，性别分层分析改进了全局遗传率和遗传相关性的估计，并增强了某些表型的多基因预测。这项工作强调了常规进行性别分层遗传关联分析的必要性，以阐明神经影像表型及相关疾病中性别特异性和性别共享的遗传控制。

## Abstract
Sex differences are commonly observed in neuroimaging phenotypes and in the risk of brain diseases, yet the underlying genetic mechanisms remain poorly understood. We investigated sex differences in the genetic architecture of 805 neuroimaging phenotypes in 22,950 males and 22,950 females matched for sample size and covariates, and systematically compared sex-stratified with sex-combined genetic analyses. We found eight variant-trait associations with significant sex differences, 235 fine-mapped sex-dominant causal associations, 457 sex-dominant colocalizations with sex hormones, and 96 sex-dominant colocalizations with schizophrenia. Compared with sex-combined analysis, sex-stratified analysis identified 47 new genetic associations, 170 new fine-mapped causal associations, 1,019 new colocalizations with sex hormones, and 191 new colocalizations with schizophrenia. Additionally, sex-stratified analysis improved global heritability and genetic-correlation estimates and enhanced polygenic prediction for certain phenotypes. This work highlights the need to routinely perform sex-stratified genetic association analyses to elucidate sex-specific and sex-shared genetic control of neuroimaging phenotypes and related disorders.

---

## 论文详细总结（自动生成）

这篇论文对脑成像表型的性别差异遗传结构进行了系统且深入的研究。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：人类大脑结构（如灰度体积、白质微结构等）及相关脑疾病风险存在显著的性别差异，但由于以往的大规模全基因组关联研究（GWAS）多采用“性别合并”（Sex-combined）样本，掩盖了性别特异性的遗传机制。
*   **研究动机**：旨在通过严格的样本匹配和性别分层分析，揭示大脑成像衍生表型（IDPs）背后的性别特异性遗传控制，并评估性别分层分析相较于传统合并分析在发现新遗传信号、提高预测精度等方面的优势。

### 2. 方法论：核心思想与关键技术
*   **核心思想**：利用英国生物样本库（UK Biobank）数据，通过倾向评分匹配（PSM）构建样本量和协变量完全平衡的男女亚组，进行性别分层 GWAS，并与合并分析结果进行多维度对比。
*   **关键技术细节**：
    *   **样本匹配**：使用 PSM 算法（1:1 匹配，卡钳值 0.2），确保男女组在年龄、扫描地点、前 40 个遗传主成分等 45 个协变量上达到平衡（ASMD < 0.1）。
    *   **遗传关联分析**：使用 BGENIE 软件对 16,013,685 个常染色体变异进行分析。
    *   **遗传力与相关性**：利用 LDSC 估计 SNP 遗传力（$h^2$）和遗传相关性（$r_g$）。
    *   **精细定位（Fine-mapping）**：使用 FINEMAP 识别因果变异（PIP > 0.8）。
    *   **共定位分析（Colocalization）**：使用 Coloc 评估 IDPs 与性激素（TT, BT, SHBG）及精神分裂症（SCZ）的共享遗传机制。
    *   **基因优先化**：采用 FLAMES 框架整合多组学证据识别效应基因。

### 3. 实验设计
*   **数据集**：UK Biobank（UKB）。
*   **样本规模**：最终纳入 45,900 名参与者（22,950 名男性和 22,950 名女性）。
*   **表型对象**：805 种脑成像衍生表型（IDPs），包括 373 种结构 MRI（sMRI）指标（体积、厚度、面积）和 432 种弥散 MRI（dMRI）指标（白质完整性）。
*   **对比基准（Benchmark）**：
    *   **性别差异对比**：男性组 vs. 女性组。
    *   **策略对比**：性别分层分析（Sex-stratified）vs. 性别合并分析（Sex-combined）。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的硬件配置（如 GPU/CPU 型号、数量）或具体的训练/计算时长。但考虑到其处理的是 4.5 万人规模的 16M 变异和 805 个表型，通常需要高性能计算集群（HPC）支持。

### 5. 实验数量与充分性
*   **实验规模**：研究涵盖了 805 种表型，每种表型均在三个样本（男、女、合并）中进行了 GWAS，并进行了后续的遗传力估计、遗传相关性计算、多基因风险评分（PGS）预测、精细定位和共定位分析。
*   **充分性与客观性**：实验设计非常充分。通过 PSM 匹配消除了样本量和协变量不平衡带来的偏倚；引入了性激素和精神分裂症的外部 GWAS 数据进行共定位验证；进行了敏感性分析以排除样本重叠的影响。整体方法论严谨，实验结果具有高度的客观性。

### 6. 主要结论与发现
*   **性别差异显著**：发现了 8 个具有显著性别差异的变异-性状关联，以及数百个性别主导的因果关联和共定位信号。
*   **遗传力偏倚**：发现性别合并分析会高估男性的遗传力，低估女性的遗传力。
*   **新信号发现**：性别分层分析虽然样本量减半，但识别出了 47 个合并分析未能发现的新遗传关联和 170 个新因果关联。
*   **疾病关联**：识别出 82 个男性主导的 IDPs 与精神分裂症共定位信号，这与精神分裂症在男性中发病率更高的流行病学事实相符。
*   **预测提升**：在特定表型上，性别特异性的 PGS 模型预测准确度显著优于合并模型。

### 7. 优点（亮点）
*   **严谨的样本匹配**：通过 PSM 解决了以往研究中男女样本量不均和协变量干扰的问题。
*   **全方位对比**：不仅关注关联分析，还从遗传力、精细定位、共定位等多个遗传学维度系统对比了分层与合并策略。
*   **白质研究的补充**：填补了以往研究多关注灰质而忽视白质遗传性别差异的空白。
*   **生物学解释力强**：通过通路富集和基因优先化，将统计信号转化为具体的生物学发现（如 *SH3PXD2A* 基因与白质微结构的关联）。

### 8. 不足与局限
*   **族裔局限性**：研究对象仅限于 UKB 中的高加索人群，结果在其他族裔中的普适性有待验证。
*   **外部数据限制**：由于缺乏其他精神疾病的性别分层 GWAS 汇总统计数据，目前仅对精神分裂症进行了深入分析。
*   **样本量挑战**：尽管分层分析发现了新信号，但分层本身会导致单组样本量减小，可能降低对某些微效变异的检测效力。
*   **性染色体缺失**：研究主要集中在常染色体变异，未包含性染色体（X/Y）的分析，这可能遗漏了部分性别差异的源头。

（完）
