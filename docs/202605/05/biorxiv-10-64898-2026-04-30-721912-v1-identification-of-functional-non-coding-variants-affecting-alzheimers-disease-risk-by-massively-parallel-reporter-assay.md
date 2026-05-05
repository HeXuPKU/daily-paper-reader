---
title: "Identification of functional non-coding variants affecting Alzheimer's disease risk by Massively Parallel Reporter Assay"
title_zh: 通过大规模并行报告基因检测鉴定影响阿尔茨海默病风险的功能性非编码变异
authors: "Hudgins, A. D., Chang, H.-K., Kim, S., Yang, J., Guan, D., Wang, X., Zhu, Y., Suh, Y."
date: 2026-05-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721912v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 鉴定GWAS位点中的功能性变异
tldr: 本研究针对晚发型阿尔茨海默病（LOAD）中大多数风险变异位于非编码区这一现状，利用高通量MPRA技术在单核细胞中筛选了2231个SNP，成功鉴定出62个功能性变异。重点研究发现rs636317变异通过干扰CTCF结合和染色质构象，调控MS4A基因家族及TREM2的表达，为理解非编码变异如何通过免疫途径影响AD发病提供了重要的机械论依据。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在系统性地鉴定位于非编码区且影响晚发型阿尔茨海默病风险的功能性遗传变异及其致病机制。
method: 在THP-1单核细胞系中应用大规模并行报告基因检测（MPRA）筛选2231个SNP，并利用CRISPR/Cas9技术在人胚胎干细胞衍生的单核细胞中进行验证。
result: 鉴定出62个具有等位基因特异性调节作用的变异，并证实rs636317通过破坏CTCF结合位点来改变染色质环化，进而上调MS4A家族基因和TREM2的表达。
conclusion: 研究建立了非编码遗传变异、MS4A家族转录调控与TREM2介导的免疫反应之间的机械联系，揭示了其在阿尔茨海默病发病中的作用。
---

## 摘要
迟发性阿尔茨海默病（LOAD）的大多数遗传风险变异位于非编码基因组区域，这表明它们通过破坏转录调控程序发挥致病作用。为了系统地鉴定功能性变异，我们在 THP-1 人单核细胞系中进行了无偏倚、高通量的大规模并行报告基因检测（MPRA），筛选了 24 个 LOAD GWAS 位点中的 2,231 个 SNP。我们鉴定了 62 个表现出显著等位基因特异性转录调控输出的变异，其中包括 MS4A 位点中的 rs636317。rs636317 的风险等位基因破坏了 CTCF 结合基序，从而改变了精细尺度的染色质环化。为了验证这些发现，我们利用 CRISPR/Cas9 在 H9 人胚胎干细胞中实现了 rs636317 T 等位基因的等位基因特异性缺失。由这些编辑后的细胞分化而来的单核细胞表现出 MS4A4E、MS4A6A 和 TREM2 的表达增加，以及可溶性 TREM2（sTREM2）水平的显著升高。这些结果在非编码遗传变异、MS4A 家族的转录调控以及阿尔茨海默病发病机制中 TREM2 介导的免疫反应之间建立了机制联系。

## Abstract
The majority of genetic risk variants for late-onset Alzheimer's disease (LOAD) reside within non-coding genomic regions, suggesting they exert pathogenic effects by disrupting transcriptional regulatory programs. To systematically identify functional variants, we performed an unbiased, high-throughput Massively Parallel Reporter Assay (MPRA) in the THP-1 human monocytic cell line, screening 2,231 SNPs across 24 LOAD GWAS loci. We identified 62 variants exhibiting significant allele-specific transcriptional regulatory output, including rs636317 in the MS4A locus. The risk allele of rs636317 disrupts a CTCF binding motif, altering fine-scale chromatin looping. To validate these findings, we employed CRISPR/Cas9 to generate an allele-specific deletion of the rs636317 T allele in H9 human embryonic stem cells. Monocytes differentiated from these edited cells displayed increased expression of MS4A4E, MS4A6A, and TREM2, along with highly elevated levels of soluble TREM2 (sTREM2). These results provide a mechanistic link between a non-coding genetic variant, transcriptional regulation of the MS4A family, and TREM2-mediated immune responses in Alzheimer's disease pathogenesis.

---

## 论文详细总结（自动生成）

这是一份关于论文《通过大规模并行报告基因检测鉴定影响阿尔茨海默病风险的功能性非编码变异》的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：全基因组关联研究（GWAS）已鉴定出许多与晚发型阿尔茨海默病（LOAD）相关的遗传位点，但绝大多数变异位于**非编码区**。如何从成千上万个连锁的单核苷酸多态性（SNP）中精准识别出具有生物学功能的致病变异，并阐明其调控靶基因的机制，是当前神经退行性疾病研究的重大挑战。
*   **研究背景**：非编码变异通常通过干扰增强子或启动子等调控元件来影响基因表达。由于免疫系统（特别是小胶质细胞和单核细胞）在AD发病中起关键作用，研究者聚焦于髓系细胞背景下的调控逻辑。

### 2. 论文提出的方法论
*   **核心思想**：采用“高通量筛选 + 针对性功能验证”的策略。
*   **关键技术细节**：
    *   **大规模并行报告基因检测（MPRA）**：在 THP-1 人单核细胞系中，对 24 个 LOAD GWAS 位点内的 2,231 个 SNP 进行了无偏倚筛选。通过合成包含不同等位基因的 DNA 片段并连接报告基因，测量其转录活性差异。
    *   **生物信息学预测**：利用转录因子结合基序分析（如 CTCF 结合位点预测）来解释 MPRA 观察到的等位基因特异性差异。
    *   **CRISPR/Cas9 基因编辑**：在 H9 人胚胎干细胞（hESCs）中对候选 SNP（rs636317）进行等位基因特异性缺失，随后将其分化为单核细胞进行功能验证。
    *   **多组学分析**：结合 RNA-seq（转录组）、ChIP-seq（染色质免疫共沉淀）和染色质构象捕获技术（Hi-C/精细尺度环化分析），研究变异对染色质三维结构和靶基因表达的影响。

### 3. 实验设计
*   **数据集/场景**：
    *   **筛选阶段**：针对 24 个已知的 LOAD GWAS 风险位点。
    *   **细胞模型**：THP-1（人单核细胞系）用于高通量筛选；H9 hESC 衍生的单核细胞用于内源性功能验证。
*   **对比方法**：
    *   对比了风险等位基因与保护等位基因在转录活性上的差异（Allele-specific activity）。
    *   对比了野生型细胞与 CRISPR 编辑后的等位基因缺失细胞的基因表达谱。
    *   **Benchmark**：以已知的 GWAS 风险信号为基准，验证 MPRA 鉴定出的功能性 SNP 是否与遗传关联信号一致。

### 4. 资源与算力
*   **算力说明**：论文中未明确提及具体的 GPU 型号、数量或训练时长。
*   **资源消耗**：研究的主要资源消耗在于**大规模 DNA 库的合成**、**高通量测序（NGS）**以及**干细胞分化培养**。数据处理涉及标准的生物信息学流程（如序列比对、差异表达分析、Hi-C 数据处理），通常在高性能计算集群（HPC）上完成。

### 5. 实验数量与充分性
*   **实验规模**：
    *   初步筛选了 **2,231 个 SNP**，覆盖 24 个位点。
    *   鉴定出 **62 个** 具有显著等位基因特异性输出的功能变异。
    *   对 **rs636317** 进行了深入的单克隆编辑和分化实验。
*   **充分性评价**：实验设计非常充分。研究不仅停留在相关性层面（MPRA），还通过 CRISPR 编辑在内源性基因组水平上验证了因果性，并从染色质构象（3D 基因组）的角度提供了机械论解释。

### 6. 主要结论与发现
*   **鉴定出 62 个功能性 SNP**：这些变异在单核细胞中表现出显著的等位基因特异性调控活性。
*   **rs636317 的关键作用**：位于 *MS4A* 基因簇的 rs636317 风险等位基因会破坏 **CTCF 结合基序**。
*   **机制链条**：rs636317 变异 -> 破坏 CTCF 结合 -> 改变染色质环化（Looping） -> 导致 *MS4A4E*、*MS4A6A* 表达上调 -> 进而导致 **TREM2 表达增加及可溶性 TREM2（sTREM2）水平升高**。
*   **免疫联系**：建立了非编码遗传变异与 TREM2 介导的免疫反应之间的直接机械联系，TREM2 是 AD 风险的关键调节因子。

### 7. 优点
*   **系统性强**：从大规模筛选到单个变异的深度机制解析，逻辑链条完整。
*   **细胞模型相关性高**：选择了与 AD 神经炎症密切相关的单核/小胶质细胞谱系，而非通用的 HEK293 细胞。
*   **技术先进**：结合了 MPRA 和 CRISPR 辅助的等位基因特异性分析，克服了传统 GWAS 仅能提供相关性的局限。

### 8. 不足与局限
*   **细胞系局限**：THP-1 是白血病来源的细胞系，虽然具有单核细胞特征，但与原代小胶质细胞或单核细胞仍有差异。
*   **覆盖范围**：虽然筛选了 24 个位点，但仍有许多 AD 相关位点未被纳入研究。
*   **环境因素缺失**：实验主要在基础培养条件下进行，未模拟 AD 大脑中的炎症或淀粉样蛋白沉积环境，可能遗漏某些应激依赖性的调控变异。
*   **单点深入**：虽然鉴定出 62 个变异，但论文仅对 rs636317 进行了详尽的机制验证，其余 61 个变异的功能仍待进一步研究。

（完）
