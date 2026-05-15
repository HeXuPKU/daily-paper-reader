---
title: A ML-framework for the discovery of next-generation IBD targets using a harmonized single-cell atlas of patient tissue
title_zh: 一种利用患者组织统一单细胞图谱发现下一代 IBD 靶点的机器学习框架
authors: "Joglekar, A., Joseph, A., Honsa, P., Ruppova, K., Pizzarella, V., Honan, A., Mediratta, D., Vollmer, E., Geller, E., Valny, M., Macuchova, E., Zheng, S., Greenberg, A., Taus, P., Kline-Schoder, A., Konickova, R., Cerna, L., Sharim, H., Ness, L., Camilli, G., Chouri, E., Kaymak, I., D'Rozario, J., Castiblanco, D., Oliveira, J., Prandi, F., Popov, N., Moldoveanu, A. L., Oliphant, C., Escudero-Ibarz, L., Uhlitz, F., Freinkman, E., Sponarova, J., Vijay, P., Joyce, C., Leonardi, I., Nayar, S., Raveh-Sadka, T., Solomon, N., Platt, A., Ort, T., De Baets, G., Corridoni, D., Wroblewska, A., Rahman, A."
date: 2026-05-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.06.699999v3.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 利用单细胞图谱发现基因靶点的机器学习框架
tldr: 该研究针对炎症性肠病（IBD）靶点发现缺乏细胞分辨率的问题，构建了包含100万个细胞的人类肠道单细胞图谱。通过机器学习框架（IPR）识别出85个疾病相关转录程序和400个细胞类型特异性靶点。通过实验验证了PTGIR和IL6ST等候选靶点在缓解炎症和纤维化方面的潜力，为IBD及其他免疫疾病提供了可扩展的精准治疗发现新范式。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统的IBD靶点发现主要依赖遗传关联，难以识别具有细胞类型特异性的新型可操作疾病通路。
method: 构建了百万级肠道单细胞图谱，并利用机器学习框架IPR与AI辅助推理系统，系统性地识别和筛选疾病相关的细胞特异性基因靶点。
result: 成功识别出85个疾病相关转录程序和400个候选靶点，并验证了PTGIR和IL6ST在调节炎症和纤维化中具有不同于现有生物制剂的机制。
conclusion: 该框架通过整合计算发现与实验验证，为IBD及其他免疫介导疾病提供了高效、精准且可扩展的药物靶点发现新途径。
---

## 摘要
炎症性肠病（IBD）的靶点发现传统上依赖于遗传关联，这缺乏识别新型、可成药、细胞类型特异性疾病通路所需的细胞分辨率。在此，我们描述了一个整合的分析与实验框架，该框架利用统一的单细胞数据系统地发现 IBD 的新型治疗策略。我们利用 Immunai 的单细胞 RNA 数据集统一数据库 AMICA DB™，构建了一个包含 100 万个细胞的人类肠道统一单细胞图谱。我们应用了一种机器学习框架（免疫患者表征，IPR）来识别疾病相关的转录程序和细胞类型特异性的基因靶点。候选靶点根据图谱衍生的指标进行优先级排序，并使用强调转化可操作性的自定义标准进行精炼，随后在独立临床队列中进行了验证。选定的候选靶点在反映靶点细胞类型背景的人类原代细胞模型中进行了评估。IPR 框架识别了 85 个疾病相关的转录程序，并对免疫和基质谱系中的 400 个细胞类型特异性靶基因进行了排序。利用结构化的 AI 辅助推理框架对疾病相关程序进行了解释，以进行结构化生物学推理，将其与 IBD 相关通路联系起来，并指导新型、有前景的基因靶点的识别。对两个细胞类型特异性候选靶点（髓系细胞中的 PTGIR 和成纤维细胞中的 IL6ST）的功能验证证实，它们能够减少与 IBD 病理相关的炎症和纤维化通路。多组学分析以及体外表型向患者数据集的投影表明，通过不同于现有生物制剂的机制，可以逆转疾病相关程序。我们的以单细胞为核心的机器学习框架将计算机模拟发现与实验验证相结合，揭示了新的细胞类型特异性治疗机会，并为 IBD 和其他免疫介导疾病的精准靶点发现提供了一种可扩展的方法。

## Abstract
Target discovery for IBD has traditionally relied on genetic associations, which lack the cellular resolution needed to identify novel, actionable, cell type-specific disease pathways. Here, we describe an integrated analytical and experimental framework that leverages harmonized single-cell data to systematically discover novel therapeutic strategies for IBD.

We used AMICA DBTM, Immunais harmonized database of single-cell RNA datasets to construct a harmonized 1 million single-cell atlas of the human intestine. We applied a machine learning framework (Immune Patient Representation, IPR) to identify disease-associated transcriptional programs and cell type-specific gene targets. Candidate targets were prioritized using atlas-derived metrics, refined using custom criteria emphasizing translational actionability, and validated across independent clinical cohorts. Select candidates were evaluated in human primary-cell models reflecting the targets cell-type context.

The IPR framework identified 85 disease-associated transcriptional programs and ranked 400 cell type-specific target genes across immune and stromal lineages. Disease-associated programs were interpreted using a structured AI-assisted reasoning framework for structured biological reasoning, linking them to IBD-relevant pathways and guiding the identification of novel, promising gene targets. Functional validation of two cell-type-specific candidates, PTGIR in myeloid cells and IL6ST in fibroblasts, confirmed the reduction of inflammatory and fibrotic pathways linked to IBD pathology. Multi-omic profiling and projection of in vitro phenotypes to patient datasets demonstrated the reversal of disease-associated programs via mechanisms distinct from those of existing biologics.

Our single-cell anchored, machine-learning framework integrates in silico discovery with experimental validation, revealing new cell type-specific therapeutic opportunities and supporting a scalable approach for precision target discovery in IBD and other immune-mediated diseases.