---
title: "DxFit: An ensemble method for identifying EHR diagnoses consistent with a molecular finding"
title_zh: DxFit：一种用于识别与分子发现一致的电子健康档案（EHR）诊断的集成方法
authors: "Torene, R. I., Meltz Murphy, K., Brandt, T., Retterer, K."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720629v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 识别与分子发现一致的EHR诊断的集成方法
tldr: DxFit 是一种集成方法，旨在从电子健康记录（EHR）中识别与分子发现一致的罕见遗传病诊断。随着基因组测序的普及，准确评估疾病流行率和外显率变得至关重要。DxFit 结合了基因名称搜索、本体映射、词嵌入相似度和 Jaccard 相似度四种策略，能有效挖掘 ICD 代码和结构化诊断描述。在发育障碍队列测试中，该工具表现出极高的敏感性和特异性，为基因组优先研究提供了强有力的支持。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的从 EHR 中搜索罕见病诊断的方法存在局限性，需要更准确、便携的工具来验证基因组发现。
method: 开发了集成工具 DxFit，结合基因名称搜索、Mondo 本体映射、词嵌入相似度和 Jaccard 匹配四种策略来挖掘诊断数据。
result: "在 350 名发育障碍患者的测试中，DxFit 达到了最高 92.7% 的敏感性和 84.5% 的特异性。"
conclusion: DxFit 是一个高效、可定制且公开可用的工具，能够显著提升从 EHR 中识别罕见遗传病诊断的准确性。
---

## 摘要
随着人群 DNA 测序的普及，基因组优先（genomic-first）方法越来越多地被用于识别可能患有罕见遗传病的个体。为了准确评估患病率和外显率，这些研究通常利用电子健康档案（EHR）来确认疾病的表现。目前存在多种在 EHR 中搜索罕见病诊断的策略，但每种策略都有其局限性。我们开发了一种便携式集成工具 DxFit，该工具通过挖掘 EHR 数据（来自计费代码和问题列表表的 ICD 代码及结构化诊断描述），来寻找与给定罕见遗传病一致的诊断。DxFit 结合了四种策略的证据：(1) 在诊断描述和注释中搜索基因名称；(2) 将 ICD 转换为 Mondo 罕见病本体以寻找精确和相近的匹配；(3) 词嵌入相似度搜索；(4) Jaccard 相似度匹配。DxFit 对匹配类型进行优先级排序，并为每个参与者-疾病对输出置信度最高的匹配结果。在 350 名已知发育障碍诊断性基因检测结果为阳性的参与者队列中，使用默认参数时，DxFit 的灵敏度为 88.7%，特异性为 86.2%。将语言评分阈值从 0.8 调整为 0.7 并允许同义匹配后，灵敏度达到 92.7%，特异性为 84.5%。将 EHR 证据划分为基因检测前后的时间窗显示，正如预期的那样，DxFit 的整体检出率在检测后有所增加，且匹配类型变得更加可信。DxFit 已向公众开放，并提供广泛的定制选项以支持各种用途。

## Abstract
As population DNA sequencing becomes more common, genomic-first approaches are increasingly used to identify individuals with possible rare genetic disorders. To accurately estimate prevalence and penetrance, these studies often confirm manifestation of the disorder using electronic health records (EHRs). Multiple strategies exist to search the EHR for diagnoses of rare disorders, however, each has its limitations. We have developed a portable, ensemble tool, DxFit, that mines EHR data (ICD codes and structured diagnosis descriptions from billing code and problem list tables) for a diagnosis consistent with a given rare genetic disorder. DxFit combines evidence across four strategies: (1) gene name searches in diagnosis descriptions and notes, (2) ICD conversion to Mondo rare disorder ontology to find exact and nearby matches, (3) word embedding similarity searches, and (4) Jaccard similarity matches. DxFit prioritizes the match type and outputs the most confident match for each participant-disorder pair. On a cohort of 350 participants with a known positive result from diagnostic genetic testing for developmental disorders, DxFit had a sensitivity of 88.7% and specificity of 86.2% using default parameters. Adjusting the linguistic scoring thresholds from 0.8 to 0.7 and allowing for synonymous matches yielded a sensitivity of 92.7% and specificity of 84.5%. Partitioning EHR evidence into windows before and after genetic testing demonstrates, as expected, that the overall DxFit rates increase after testing and the match types become more confident. DxFit is available to the public and has extensive customization options to support a wide range of uses.

Graphical Abstract

O_FIG O_LINKSMALLFIG WIDTH=187 HEIGHT=200 SRC="FIGDIR/small/720629v1_ufig1.gif" ALT="Figure 1">
View larger version (41K):
org.highwire.dtl.DTLVardef@aa1be0org.highwire.dtl.DTLVardef@c2b29org.highwire.dtl.DTLVardef@e5beeeorg.highwire.dtl.DTLVardef@15a26cd_HPS_FORMAT_FIGEXP  M_FIG C_FIG

---

## 论文详细总结（自动生成）

以下是对论文《DxFit: An ensemble method for identifying EHR diagnoses consistent with a molecular finding》的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
随着大规模人群基因组测序的普及，“基因组优先”（Genomic-first）研究成为主流，即先发现致病变异，再回溯临床表现。然而，**如何准确、自动地在电子健康档案（EHR）中识别出与特定罕见遗传病一致的临床诊断**是一个重大挑战。
*   **现有局限：** 临床常用的 ICD 代码（计费用途）与遗传学常用的 Mondo 本体（疾病定义）之间存在映射稀疏（匹配不到）或过于贪婪（一个 ICD 对应太多疾病）的问题。
*   **研究目标：** 开发一种集成工具 DxFit，能够跨越不同的命名规范和编码体系，高效识别 EHR 中支持罕见病诊断的证据。

### 2. 论文提出的方法论
DxFit 是一种集成（Ensemble）方法，核心思想是结合四种互补的搜索策略，并根据置信度对结果进行优先级排序：
1.  **基因符号搜索（Gene Symbol Search）：** 在诊断描述或临床文本中直接搜索致病基因符号（如 *SCN1A*）。
2.  **ICD 到 Mondo 映射：** 利用 Monarch Initiative 的映射表，允许在 Mondo 本体中进行 0 到 2 度的近邻搜索。为了防止匹配到过于宽泛的术语（如“遗传性疾病”），研究者对 Mondo 树进行了**自定义剪枝**。
3.  **词嵌入相似度（Word Embedding Similarity）：** 使用 NLP 模型（`en_core_sci_md`）将疾病名称和 EHR 诊断描述转化为向量，计算余弦相似度。
4.  **Jaccard 相似度：** 基于 n-gram 的字符重叠度匹配，专门用于捕捉 NLP 模型可能遗漏的**人名首字母缩写（Eponyms）或缩写词**。
*   **优先级排序：** 匹配结果按置信度排序：基因匹配 > 精确匹配 > Jaccard 匹配 > 语义相似度 > 1度近邻 > 2度近邻。

### 3. 实验设计
*   **数据集：** 
    *   **病例组：** 350 名经临床基因检测确认患有发育障碍（Developmental Disorders）的患者（共 355 个个体-疾病对）。
    *   **对照组：** 按 1:10 比例匹配的年龄、性别对照者（约 3500 人），用于评估误报率。
*   **Benchmark：** 以临床确诊结果为金标准。
*   **对比场景：** 
    *   默认参数（阈值 0.8）vs. 宽松参数（阈值 0.7 + 启用同义词）。
    *   基因检测前 vs. 基因检测后的诊断检出率对比。
    *   消融分析：评估移除“基因名称搜索”后，其他集成策略的召回能力。

### 4. 资源与算力
*   **算力说明：** 文中**未明确提及**具体的 GPU 型号、数量或训练时长。
*   **技术栈：** 提到了使用 Python 开发，NLP 部分使用了 `scispaCy` 的 `en_core_sci_md` 模型。由于该工具主要用于推理和匹配而非大规模模型训练，预计对算力需求较低，普通工作站即可运行。

### 5. 实验数量与充分性
*   **实验规模：** 涵盖了 350 多个真实病例和 3500 多个对照，样本量对于罕见病研究而言较为充分。
*   **充分性评价：** 实验设计较为全面，不仅评估了整体性能，还进行了**参数敏感性分析**（0.8 vs 0.7 阈值）和**时间维度分析**（检测前后）。此外，研究者还进行了**人工复核**，对 315 个匹配结果进行了专家评审，以区分“错误匹配”和“模糊匹配”，体现了研究的客观性和严谨性。

### 6. 论文的主要结论与发现
*   **高性能：** 在默认参数下，DxFit 的敏感性为 88.7%，特异性为 86.2%；调整参数后，**敏感性可提升至 92.7%**（特异性降至 84.5%）。
*   **集成优势：** 约 40.8% 的病例匹配是通过非基因名称搜索（如语义相似度或本体映射）实现的，证明了集成方法的必要性。
*   **时间趋势：** 基因检测后，DxFit 的检出率显著提高（从 56.8% 升至 80.4%），且匹配的置信度等级明显提升，反映了临床诊断随检测结果而变得精确的过程。
*   **误报来源：** 对照组中的误报大多属于低置信度的“2度近邻匹配”。

### 7. 优点
*   **多模态匹配：** 结合了本体论、语言学（NLP）和字符串重叠，解决了罕见病命名不规范的问题。
*   **高度可定制：** 用户可以自定义 NLP 模型、调整相似度阈值、修改停用词列表或更新 ICD-Mondo 映射表。
*   **实用性强：** 工具已开源，且对“基因组优先”研究中的外显率评估具有直接的应用价值。
*   **本体剪枝：** 巧妙地通过剪枝解决了本体映射中常见的“术语漂移”和过度匹配问题。

### 8. 不足与局限
*   **依赖结构化数据：** 虽然支持临床注释，但主要评估仍基于 ICD 描述。如果 EHR 中完全缺失相关记录，工具无法凭空发现。
*   **本体局限性：** Mondo 本体的深度和特异性在不同疾病分支间不统一，导致“2度近邻”在某些领域可能过于宽泛。
*   **特定领域偏差：** 实验主要集中在发育障碍领域，在其他医学专业（如代谢病或自身免疫病）的泛化能力尚需更多验证。
*   **模糊匹配风险：** 约 13.3% 的匹配属于“模糊匹配”（如将特定遗传病匹配到“智力障碍”），虽然临床相关，但不够精确。

（完）
