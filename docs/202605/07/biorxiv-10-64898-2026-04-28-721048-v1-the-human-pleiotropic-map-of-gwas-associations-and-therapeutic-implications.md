---
title: The Human Pleiotropic Map of GWAS Associations and Therapeutic Implications
title_zh: GWAS 关联的人类多效性图谱及其治疗意义
authors: "Tsepilov, Y. A., Suveges, D., Considine, D., Szyszkowski, S., Ge, X. J., Lopez Santiago, I., Rusina, P., Alegbe, T., Ho, V. W., Tsukanov, K., Roldan-Romero, J. M., Smit, I. A., Cornu, H., Harris, L., Alasoo, K., Predeus, A., Lessard, S., Chatelain, C., Khader, S., Yang, S., O'Carroll, A., Aulchenko, Y. S., Seaton, D., Buniello, A., Birney, E., Fauman, E. B., McCarthy, M. I., Hulcoop, D. G., Trynka, G., McDonagh, E. M., Ochoa, D."
date: 2026-05-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.28.721048v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: GWAS可信集和基因优先级的系统分析
tldr: "本研究通过系统分析10万余项GWAS研究，构建了涵盖1.5万个基因的人类多效性图谱。研究发现64%的GWAS相关基因具有多效性，且高多效性与临床安全性风险（如临床试验终止、小鼠致死性）密切相关。研究提出，将蛋白质改变变异（PAV）支持与中等程度的多效性（涉及2-5个治疗领域）相结合，可将药物研发成功率提高至10.3倍，为开发更安全有效的治疗方案提供了遗传学指导。"
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在系统性量化GWAS揭示的基因多效性对药物靶点发现及其临床安全性和成功率的影响。
method: "对100,526个GWAS进行系统分析，生成了针对15,641个基因的信度集和优先级排序，并绘制了全基因组多效性图谱。"
result: "发现64%的基因具有多效性，且高多效性基因富集于安全性失败的临床项目，而PAV支持结合中等水平多效性能显著提升临床成功率。"
conclusion: 基因水平的多效性是评估药物安全性的重要遗传指标，优化多效性与变异支持的组合可显著提高治疗假设的可靠性。
---

## 摘要
药物靶点的遗传学支持显著提高了临床成功率，使全基因组关联研究 (GWAS) 成为治疗假设生成的中心。然而，揭示因果基因-疾病关系的相同遗传证据，同时也暴露了生物体层面的安全性风险——这是一个需要原则性、全基因组量化的维度。在此，我们系统地分析了 100,526 项 GWAS，为 15,641 个基因生成了 789,453 个可信集和基因优先级排序；随着 GWAS 规模的扩大和多样性的增加，相关发现并未显示出饱和。我们发现 64% 的 GWAS 相关基因具有多效性，与跨多种疾病的性状相关，且多效性程度与临床成功率之间呈现非线性关系。高度多效性的基因集中在免疫、炎症和致癌信号程序中，并在因安全性而终止的临床项目、小鼠致死性敲除和癌症驱动基因中富集，从而确立了基因水平的多效性作为遗传学告知的生物体层面安全性风险的潜在衡量标准。蛋白质改变变异 (PAV) 的支持放大了治疗信号 (OR = 6.0)，但 PAV 靶点显示出更高的平均多效性，引入了竞争性的安全性风险。将 PAV 支持与中等程度的多效性（2-5 个治疗领域）相结合可以解决这种矛盾，产生 OR = 10.3 和相对成功率 = 4.8——这一特征已被 52 种已批准的疗法所满足。随着 GWAS 在规模和分辨率上的持续扩展，这些发现为日益复杂的靶点发现策略奠定了基础，从而产生更安全、更有效的治疗假设。

## Abstract
Genetic support for drug targets substantially increases clinical success rates, establishing genome-wide association studies (GWAS) as central to therapeutic hypothesis generation. However, the same genetic evidence that reveals causal gene-disease relationships simultaneously exposes organism-level safety liabilities--a dimension requiring principled, genome-wide quantification. Here we systematically analyse 100,526 GWAS to yield 789,453 credible sets and gene prioritisations for 15,641 genes, with discovery showing no saturation as GWAS expand and increase diversity. We find that 64% of GWAS-implicated genes are pleiotropic, associated with traits across multiple diseases and showing a non-linear relationship between the degree of pleiotropy and clinical success. Highly pleiotropic genes--concentrated in immune, inflammatory, and oncogenic signalling programmes--are enriched in safety-terminated clinical programmes, mouse lethal knockouts, and cancer driver genes, establishing gene-level pleiotropy as a potential measure of genetically-informed organism-level safety liability. Protein-altering variant (PAV) support amplifies therapeutic signal (OR = 6.0), yet PAV targets show higher average pleiotropy, introducing a competing safety liability. Combining PAV support with intermediate pleiotropy (2-5 therapeutic areas) resolves this tension, yielding OR = 10.3 and relative success = 4.8--a profile already satisfied by 52 approved therapies. As GWAS continue to expand in scale and resolution, these findings lay the groundwork for increasingly sophisticated target discovery strategies that yield safer and more effective therapeutic hypotheses.

---

## 论文详细总结（自动生成）

这是一份关于论文《The Human Pleiotropic Map of GWAS Associations and Therapeutic Implications》（GWAS 关联的人类多效性图谱及其治疗意义）的结构化总结：

### 1. 核心问题与整体含义
该研究的核心动机在于解决药物研发中“有效性”与“安全性”的平衡问题。虽然遗传学证据（如 GWAS）能显著提高药物靶点发现的成功率，但同一个基因往往影响多个性状（即**多效性，Pleiotropy**），这可能预示着潜在的副作用。论文旨在通过系统性量化全基因组范围内的多效性，构建一个人类多效性图谱，从而为筛选更安全、更有效的药物靶点提供原则性的指导框架。

### 2. 方法论
研究团队开发了 **Open Targets Gentropy** 框架，其核心流程包括：
*   **数据集成与标准化**：整合了超过 10 万项 GWAS 研究，涉及 1 万亿个统计数据点，并将其映射到统一的疾病本体（EFO）。
*   **精细映射（Fine-mapping）**：应用 SuSiE-inf 和 PICS 等算法，在考虑祖先多样性的基础上生成“可信集”（Credible Sets, CS）。
*   **因果基因预测（L2G 模型）**：改进了 Locus-to-Gene (L2G) 机器学习模型（基于 XGBoost），整合距离、分子 QTL 共定位和变异致病性特征，预测最可能的效应基因。
*   **多效性量化**：定义了变异水平（vPS）和基因水平（gPS）的多效性评分，即一个变异或基因关联的独立疾病数量或治疗领域（TA）数量。

### 3. 实验设计
*   **数据集**：涵盖了英国生物样本库（UK Biobank）、芬兰基因组项目（FinnGen）、美国百万退伍军人项目（MVP）等大型生物库，以及 GWAS Catalog 中的公开研究。
*   **Benchmark（基准）**：
    *   使用 **ChEMBL** 数据库中的临床试验数据（Phase I 到已批准）作为验证药物成功率的标准。
    *   对比了 **Minikel et al. (2024)** 的研究方法，验证遗传证据对临床成功率的预测能力。
    *   引入了小鼠致死敲除数据、癌症驱动基因（COSMIC）、孟德尔疾病基因（OMIM）等作为生物学功能和安全性的参考。
*   **对比方法**：将 L2G 模型与传统的“最近基因”分配法、单纯的 eQTL 共定位法进行了性能对比。

### 4. 资源与算力
论文提到该框架基于 **Google Airflow** 进行编排，利用 **PySpark、Dataproc 和 Google Batch** 在云端处理海量数据。虽然未明确给出具体的 GPU 型号和训练总时长，但考虑到处理的是“万亿级”统计数据，其计算规模属于超大规模生物信息学处理范畴。

### 5. 实验数量与充分性
*   **规模**：分析了 100,526 项 GWAS，识别了 789,453 个可信集，涉及 15,641 个基因。
*   **维度**：进行了时间趋势分析（2006-2024 年）、祖先多样性分析、非线性回归建模以及通路富集分析（GSEA）。
*   **充分性**：实验设计非常充分，不仅涵盖了全基因组范围，还通过临床试验结果进行了回顾性验证。通过消融实验和不同子集的对比（如 PAV vs. 非 PAV），确保了结论的客观性和公平性。

### 6. 主要结论与发现
*   **多效性普遍存在**：64% 的 GWAS 相关基因具有多效性。
*   **安全性预警**：高度多效性的基因（gPS 高）显著富集在因安全性问题而终止的临床试验、小鼠致死基因和癌症驱动基因中。
*   **临床成功率的“甜点区”**：
    *   具有**蛋白质改变变异（PAV）**支持的靶点成功率更高（OR=6.0）。
    *   **最佳组合**：PAV 支持 + 中等程度多效性（涉及 2-5 个治疗领域）的靶点，其临床成功率是无遗传支持靶点的 **10.3 倍**，相对成功率提升 4.8 倍。
*   **非线性关系**：多效性与成功率之间并非简单的线性关系，极高多效性会因安全性风险抵消其有效性优势。

### 7. 优点
*   **规模空前**：是目前最全面的 GWAS 关联与多效性系统分析。
*   **转化价值高**：直接为药企提供了可操作的靶点筛选标准（PAV + 中等多效性）。
*   **动态更新**：Gentropy 框架支持随新研究发布而持续更新，具有长期的生命力。
*   **多维度整合**：成功将群体遗传学、分子生物学与临床药理学数据无缝衔接。

### 8. 不足与局限
*   **祖先偏差**：尽管努力增加多样性，但欧洲裔数据仍占主导，可能影响非欧洲人群的精细映射准确性。
*   **基因分配偏见**：L2G 模型仍存在一定的“距离偏见”（81.2% 的预测指向最近基因），非编码变异的效应基因分配仍具挑战性。
*   **本体映射噪声**：将异质性的表型映射到统一疾病本体时可能存在精度损失。
*   **细胞模型局限**：研究发现 GWAS 揭示的生物体水平安全性信号在细胞实验中无法完全模拟，这限制了早期体外筛选的预测力。

（完）
