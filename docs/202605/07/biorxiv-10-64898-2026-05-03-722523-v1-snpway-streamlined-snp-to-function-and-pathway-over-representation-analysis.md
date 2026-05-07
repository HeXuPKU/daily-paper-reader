---
title: "SNPWay: streamlined SNP-to-function and pathway over-representation analysis"
title_zh: SNPWay：精简的 SNP 到功能及通路过表达分析
authors: "Queme, B., Kakkar, A., Muruganujan, A., Thomas, P. D., Gauderman, W. J., Mi, H."
date: 2026-05-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.03.722523v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 用于GWAS后解释的SNP到功能及通路分析流程
tldr: SNPWay是一个旨在简化GWAS后分析的Web服务器和R包。针对将SNP列表转化为功能和通路假设时面临的工具集成复杂、可重复性低等挑战，该工具整合了AnnoQ、PEREGRINE和PANTHER等资源。它支持多种输入格式，能自动完成SNP到基因的映射（包括非编码区）及通路富集分析，为研究人员提供了一个标准化、端到端的分析流程，显著降低了生物信息学门槛。
source: biorxiv
selection_source: fresh_fetch
motivation: GWAS后的功能解释通常需要手动整合多种异构工具进行变异注释和通路分析，导致分析流程复杂且难以重复。
method: 开发了集成AnnoQ、PEREGRINE和PANTHER的SNPWay工具，支持从SNP输入到通路富集分析的一站式自动化处理。
result: 该工具实现了SNP到基因的精准映射及功能富集分析，并提供交互式结果展示和模块化扩展能力。
conclusion: SNPWay为研究者提供了高效、标准化的SNP功能解析方案，降低了生物信息学门槛并增强了分析的可重复性。
---

## 摘要
动机：GWAS 后期解释通常需要将变异列表（例如 lead SNPs、聚集位点、置信集或精选面板）转化为通路和功能假设。在实践中，从 SNP 输入获取通路和功能过表达结果通常需要拼接多个工具，用于变异注释、调控注释、基因标识符处理和统计测试。这种集成负担可能会降低研究的可重复性，并将端到端分析限制在拥有专门生物信息学支持的团队中。总结：我们推出了 SNPWay，这是一个 Web 服务器和 R 软件包，可在单个标准化工作流中执行端到端的 SNP 到功能及通路过表达分析。SNPWay 接受 rsID、VCF 文件或 hg19/GRCh37 基因组坐标。它查询 Annotation Query (AnnoQ)，以在 Ensembl 和 RefSeq 基因模型下从 ANNOVAR、SnpEff 和 VEP 获取 SNP 到基因的映射，并通过 PEREGRINE 整合增强子-基因链接，以增强非编码变异的映射。SNPWay 将映射的基因聚合为一个单一、非冗余的组合基因列表，并将其提交给 PANTHER，针对智人（Homo sapiens）参考列表进行过表达测试，返回过表达的通路和功能类别（例如基因本体论 Gene Ontology），并提供在 PANTHER 中进行交互式探索的直接链接。SNPWay 的模块化架构旨在实现可扩展性，以便在未来版本中纳入其他分析方法。补充数据中提供了分步操作指南。

## Abstract
Motivation: Post-GWAS interpretation frequently requires translating variant lists (e.g., lead SNPs, clumped loci, credible sets, or curated panels) into pathway and functional hypotheses. In practice, obtaining pathway and functional over-representation results from SNP inputs often requires stitching together multiple tools for variant annotation, regulatory annotation, gene identifier handling, and statistical testing. This integration burden can reduce reproducibility and restrict end-to-end analysis to groups with dedicated bioinformatics support. Summary: We present SNPWay, a web server and R package that performs end-to-end SNP-to-function and pathway over-representation analysis in a single standardized workflow. SNPWay accepts rsIDs, VCF files, or hg19/GRCh37 genomic coordinates. It queries Annotation Query (AnnoQ) to obtain SNP-to-gene mappings from ANNOVAR, SnpEff, and VEP under both Ensembl and RefSeq gene models, and incorporates enhancer-gene links via PEREGRINE to augment mappings for noncoding variants. SNPWay aggregates mapped genes into a single, non-redundant, combined gene list and submits it to PANTHER for over-representation testing against the Homo sapiens reference list, returning over-represented pathways and functional categories (e.g., Gene Ontology) with direct links for interactive exploration in PANTHER. SNPWay's modular architecture is designed for extensibility, enabling incorporation of additional analysis methods in future releases. A step-by-step walkthrough is provided in Supplementary Data.

---

## 论文详细总结（自动生成）

这篇论文介绍了 **SNPWay**，一个旨在简化全基因组关联研究（GWAS）后分析的端到端工具。以下是对该论文的结构化总结：

### 1. 论文的核心问题与整体含义
*   **研究动机**：在 GWAS 研究后，将识别出的单核苷酸多态性（SNP）转化为生物学功能和通路假设是一个复杂的过程。研究人员通常需要手动拼接多个工具（如变异注释、调控元件映射、基因富集分析等），这不仅增加了生物信息学门槛，还导致分析流程难以标准化和重复。
*   **核心问题**：现有的工具往往只涵盖流程的一部分，或者依赖单一的注释策略，容易忽略由于不同注释算法和基因模型差异带来的生物学信号。
*   **整体含义**：SNPWay 提供了一个集成的 Web 服务器和 R 包，通过标准化工作流，实现了从 SNP 列表到功能通路过表达分析的一站式处理。

### 2. 论文提出的方法论
*   **核心思想**：整合多源注释数据，通过“取并集”策略最大化基因映射的覆盖面，并结合非编码区的调控信息。
*   **关键技术流程**：
    1.  **数据输入**：支持 rsID、VCF 文件或 hg19/GRCh37 基因组坐标。
    2.  **多源映射（AnnoQ）**：通过 AnnoQ API 同时调用 ANNOVAR、SnpEff 和 VEP 三种工具，并在 Ensembl 和 RefSeq 两种基因模型下进行映射。
    3.  **增强子关联（PEREGRINE）**：利用 PEREGRINE 数据库将非编码区的变异链接到潜在的靶基因，增强对非编码 SNP 的解释力。
    4.  **基因聚合**：将所有映射到的基因去重并聚合成一个非冗余列表。
    5.  **富集分析（PANTHER）**：将基因列表提交至 PANTHER API，针对智人参考列表进行 Fisher 精确检验（默认 FDR 校正），识别显著富集的通路和 GO 类别。

### 3. 实验设计
*   **应用场景**：论文通过一个结直肠癌（CRC）的实际案例来演示 SNPWay 的功能。
*   **数据集**：使用了 204 个与结直肠癌相关的 GWAS 显著 SNP。
*   **对比与验证**：
    *   **功能对比**：在引言部分对比了 FUMA、snpXplorer、GSA-SNP2、XGR 等现有工具，强调了 SNPWay 在“多注释器聚合”和“免登录端到端流程”上的优势。
    *   **案例验证**：复现了已发表的通路多基因风险评分（pPRS）工作流，验证其是否能识别出如 TGF-β 等关键信号通路。

### 4. 资源与算力
*   **算力说明**：论文中**未明确提及**具体的硬件算力（如 GPU 型号或训练时长）。
*   **性质分析**：由于 SNPWay 主要是基于 API 调用（AnnoQ 和 PANTHER）的 Web 工具和 R 软件包，其核心计算压力在于服务器端，用户端的计算需求极低，不涉及深度学习模型的训练。

### 5. 实验数量与充分性
*   **实验规模**：主要展示了一个深入的结直肠癌用例，涉及 78,253 名受试者的研究背景数据。
*   **充分性评价**：作为一篇“应用工具类”论文，其实验重点在于展示工具的可用性和结果的生物学一致性。论文引用了作者之前的基准测试研究（Queme et al., 2026），证明了“多注释器并集策略”在不增加假阳性的前提下，能比单一工具找回更多生物学相关的基因。实验设计对于展示工具功能是充分的，但缺乏大规模跨物种或跨疾病的广泛横向对比。

### 6. 论文的主要结论与发现
*   **流程简化**：SNPWay 成功将复杂的 SNP-to-Gene-to-Pathway 流程整合进单一工作流。
*   **生物学发现**：在 CRC 案例中，SNPWay 识别出了 TGF-β 信号通路、早老素（Presenilin）通路等显著富集的类别。基于这些通路构建的 pPRS 能显著捕捉到药物（如 NSAIDs）与基因的交互作用，而传统的全基因组 PRS 则无法做到。
*   **策略优势**：整合多种注释工具和增强子信息能显著提升从 GWAS 变异中提取生物学意义的能力。

### 7. 优点
*   **易用性高**：提供 Web 界面和 R 包，无需登录，降低了非生物信息学专业人员的使用难度。
*   **注释全面**：克服了单一注释工具的局限性，通过聚合策略提高了基因映射的敏感性。
*   **调控关注**：整合了 PEREGRINE 增强子数据，解决了 GWAS 中大量非编码 SNP 难以映射到靶基因的痛点。
*   **模块化设计**：架构灵活，易于未来扩展其他分析方法（如 pPRS 计算）。

### 8. 不足与局限
*   **基因组版本限制**：目前仅支持 hg19/GRCh37 坐标，虽然计划支持 hg38，但当前用户可能需要手动进行坐标转换（LiftOver）。
*   **物种限制**：目前仅支持人类（Homo sapiens）数据。
*   **LD 处理**：该工具不直接进行连锁不平衡（LD）建模，用户需要预先提供处理好的变异列表（如 lead SNPs 或精选面板）。
*   **依赖性**：高度依赖 AnnoQ 和 PANTHER 的 API 稳定性，如果外部服务宕机，工具功能将受限。

（完）
