---
title: The Human Pleiotropic Map of GWAS Associations and Therapeutic Implications
title_zh: GWAS 关联的人类多效性图谱及其治疗启示
authors: "Tsepilov, Y. A., Suveges, D., Considine, D., Szyszkowski, S., Ge, X. J., Lopez Santiago, I., Rusina, P., Alegbe, T., Ho, V. W., Tsukanov, K., Roldan-Romero, J. M., Smit, I. A., Cornu, H., Harris, L., Alasoo, K., Predeus, A., Lessard, S., Chatelain, C., Khader, S., Yang, S., O'Carroll, A., Aulchenko, Y. S., Seaton, D., Buniello, A., Birney, E., Fauman, E. B., McCarthy, M. I., Hulcoop, D. G., Trynka, G., McDonagh, E. M., Ochoa, D."
date: 2026-05-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721048v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 对GWAS关联和可信集的系统分析以进行基因优先级排序
tldr: "该研究通过分析超过10万个GWAS数据集，构建了人类基因多效性图谱，揭示了64%的GWAS相关基因具有多效性。研究发现，高度多效性基因与临床安全风险显著相关，而结合蛋白质改变变异（PAV）支持与中度多效性（2-5个治疗领域）的靶点具有最高的临床成功率（OR=10.3），为开发更安全有效的药物靶点提供了遗传学指导。"
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在通过全基因组关联研究（GWAS）量化基因多效性对药物研发成功率及生物体安全性的影响。
method: "系统分析了100,526个GWAS研究，为15,641个基因生成了789,453个可信集，并评估了基因多效性与临床试验结果的关联。"
result: "发现64%的基因具有多效性，高度多效性基因与临床安全性失败显著相关，而PAV结合中度多效性可将研发成功率提升至10.3倍。"
conclusion: 基因水平的多效性是评估药物安全风险的关键遗传指标，平衡遗传支持与多效性有助于发现更安全有效的治疗靶点。
---

## 摘要
药物靶点的遗传学支持显著提高了临床成功率，确立了全基因组关联研究（GWAS）在治疗假设生成中的核心地位。然而，揭示基因与疾病因果关系的相同遗传证据，同时也暴露了生物体层面的安全性风险——这一维度需要基于原则的全基因组量化。在本研究中，我们系统分析了 100,526 项 GWAS，为 15,641 个基因生成了 789,453 个可信集和基因优先级排序；随着 GWAS 规模的扩大和多样性的增加，发现过程未显示出饱和迹象。我们发现，64% 的 GWAS 相关基因具有多效性（pleiotropic），与跨多种疾病的性状相关，且多效性程度与临床成功率之间呈非线性关系。高度多效性的基因——集中在免疫、炎症和致癌信号程序中——在因安全性问题而终止的临床项目、小鼠致死性敲除实验和癌症驱动基因中富集，从而确立了基因水平的多效性作为一种基于遗传信息的生物体层面安全性风险的潜在衡量指标。蛋白质改变变异（PAV）的支持增强了治疗信号（OR = 6.0），但 PAV 靶点表现出更高的平均多效性，从而引入了竞争性的安全性风险。将 PAV 支持与中等程度的多效性（涉及 2-5 个治疗领域）相结合可以解决这一矛盾，产生 OR = 10.3 和相对成功率 = 4.8 的结果——已有 52 种获批疗法符合这一特征。随着 GWAS 在规模和分辨率上的持续扩展，这些发现为日益复杂的靶点发现策略奠定了基础，从而产生更安全、更有效的治疗假设。

## Abstract
Genetic support for drug targets substantially increases clinical success rates, establishing genomewide association studies (GWAS) as central to therapeutic hypothesis generation. However, the same genetic evidence that reveals causal gene-disease relationships simultaneously exposes organism level safety liabilities - a dimension requiring principled, genome-wide quantification. Here we systematically analyse 100,526 GWAS to yield 789,453 credible sets and gene prioritisations for 15,641 genes, with discovery showing no saturation as GWAS expand and increase diversity. We find that 64% of GWAS-implicated genes are pleiotropic, associated with traits across multiple diseases and showing a non-linear relationship between the degree of pleiotropy and clinical success. Highly pleiotropic genes - concentrated in immune, inflammatory, and oncogenic signalling programmes - are enriched in safety-terminated clinical programmes, mouse lethal knockouts, and cancer driver genes, establishing gene-level pleiotropy as a potential measure of genetically-informed organism-level safety liability. Protein-altering variant (PAV) support amplifies therapeutic signal (OR = 6.0), yet PAV targets show higher average pleiotropy, introducing a competing safety liability. Combining PAV support with intermediate pleiotropy (2-5 therapeutic areas) resolves this tension, yielding OR = 10.3 and relative success = 4.8 - a profile already satisfied by 52 approved therapies. As GWAS continue to expand in scale and resolution, these findings lay the groundwork for increasingly sophisticated target discovery strategies that yield safer and more effective therapeutic hypotheses.

---

## 论文详细总结（自动生成）

这篇论文由 Open Targets 团队发表，系统性地构建了人类全基因组关联研究（GWAS）的多效性图谱，并探讨了其对药物研发成功率及安全性的深远影响。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：虽然 GWAS 证据能显著提高药物研发的成功率（约 2.6 倍），但同一遗传证据往往也预示着潜在的安全性风险（副作用）。
*   **研究动机**：基因多效性（Pleiotropy，即一个基因影响多个性状）是人类基因组的普遍特征。研究旨在通过大规模量化基因水平的多效性，构建一个能够平衡“治疗有效性”与“生物体安全性”的靶点优先级排序框架，解决药物研发中因安全性导致的临床失败问题。

### 2. 方法论：核心思想与关键技术
*   **Gentropy 框架**：开发了 Open Targets Gentropy 分析流程，处理了超过 10 万项 GWAS 研究，涉及逾一万亿个统计数据点。
*   **关键技术细节**：
    *   **精细映射（Fine-mapping）**：采用 SuSiE-inf 和 PICS 等算法，结合特定祖先群体的连锁不平衡（LD）参考面板，生成了约 79 万个可信集（Credible Sets）。
    *   **Locus-to-Gene (L2G) 模型**：利用梯度提升决策树（XGBoost）训练机器学习模型，整合距离、分子 QTL 共定位（eQTL/pQTL）和变异致病性特征，将 GWAS 信号精准关联至候选效应基因。
    *   **多效性评分（gPS）**：定义了基因多效性评分（gPS），即与某一基因关联的独特疾病数量，并将其作为衡量生物体层面安全风险的指标。
*   **公式/逻辑**：通过负二项回归模型分析 gPS 与基因特征（如保守性、表达特异性）的关系；利用逻辑回归模型评估遗传支持与临床试验成功（Phase I 到批准）的关联。

### 3. 实验设计
*   **数据集**：整合了来自 UK Biobank、FinnGen、美国百万退伍军人项目（MVP）、日本生物库等大型队列的 100,526 项 GWAS 研究。
*   **Benchmark（基准）**：使用 ChEMBL 数据库中的临床试验数据（37,377 个靶点-适应症对）作为金标准，评估不同遗传证据下的临床成功率。
*   **对比方法**：对比了蛋白质改变变异（PAV）支持、罕见变异支持、单基因疾病资源（OMIM/Orphanet）以及传统的“最近基因”分配法。

### 4. 资源与算力
*   **算力说明**：论文提到使用了 Google Airflow 进行流程编排，并利用 PySpark、Dataproc 和 Google Batch 在云端进行大规模并行计算。
*   **具体细节**：文中未明确给出具体的 GPU/CPU 核心数量或具体的训练时长，但强调了处理“一万亿个统计数据”的计算规模，显示出极高的算力需求。

### 5. 实验数量与充分性
*   **实验规模**：分析了 15,641 个蛋白质编码基因（占总数的 77.9%），涵盖 1,394 种疾病和 3,412 种测量性状。
*   **充分性**：实验设计非常充分。作者不仅进行了横向的跨性状分析，还进行了纵向的时间趋势分析（2006-2024 年），并开展了大量的消融实验和敏感性分析（如排除肿瘤靶点、考虑祖先多样性等），确保了结论的客观性和稳健性。

### 6. 主要结论与发现
*   **多效性普遍性**：64% 的 GWAS 相关基因具有多效性。
*   **安全性预警**：高度多效性的基因（gPS 高）在安全性终止的临床项目、小鼠致死基因和癌症驱动基因中显著富集。
*   **非线性成功率**：多效性与临床成功率呈非线性关系。中度多效性（涉及 2-5 个治疗领域）的靶点成功率最高。
*   **最优策略**：结合 **PAV（蛋白质改变变异）支持** 与 **中度多效性** 的靶点，其临床成功概率（OR）高达 **10.3**，相对成功率提升 4.8 倍。

### 7. 优点
*   **规模宏大**：是目前已知最全面的 GWAS 多效性图谱，整合了极具多样性的全球生物库数据。
*   **维度创新**：首次系统性地将“多效性”从一种遗传现象转化为可量化的“药物安全风险指标”。
*   **实用性强**：直接为药物研发提供了可操作的筛选标准（PAV + 中度多效性），并已集成至 Open Targets 开源平台。

### 8. 不足与局限
*   **祖先偏差**：尽管非欧洲裔数据在增加，但欧洲裔样本仍占主导（65%），可能限制了某些结论在特定人群中的适用性。
*   **模型偏好**：L2G 模型在基因分配上仍表现出一定的“距离偏好”（81.2% 预测为最近基因），可能存在对远端调控元件识别不足的风险。
*   **表型映射**：将异质性的临床表型映射到统一的本体（EFO）过程中可能存在信息损失或分类误差。
*   **功能证据不全**：仍有 46.1% 的优先排序基因缺乏直接的分子 QTL 或 PAV 支持，依赖于预测模型。

（完）
