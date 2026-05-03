---
title: "DxFit: An ensemble method for identifying EHR diagnoses consistent with a molecular finding"
title_zh: DxFit：一种用于识别与分子发现一致的 EHR 诊断的集成方法
authors: "Torene, R. I., Meltz Murphy, K., Brandt, T., Retterer, K."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720629v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 挖掘电子健康档案数据，寻找与分子发现和遗传疾病一致的诊断
tldr: DxFit是一个集成工具，旨在从电子健康记录（EHR）中识别与分子发现一致的罕见遗传病诊断。它结合了基因名称搜索、本体映射、词嵌入相似度和Jaccard相似度四种策略，能有效克服传统搜索方法的局限性。在发育障碍队列测试中表现出高灵敏度和特异性，为基因组优先研究中的疾病流行率和外显率评估提供了有力支持。
source: biorxiv
selection_source: fresh_fetch
motivation: 随着基因测序普及，需要更准确的方法从电子健康记录中确认罕见遗传病的临床表现，以克服现有搜索策略的局限性。
method: 开发了集成工具DxFit，通过结合基因名搜索、ICD到Mondo本体转换、词嵌入相似度及Jaccard匹配四种策略来挖掘诊断数据。
result: "在350名发育障碍患者的测试中，DxFit在默认参数下达到了88.7%的灵敏度和86.2%的特异性，调整阈值后灵敏度可提升至92.7%。"
conclusion: DxFit是一个可定制且高效的开源工具，能够显著提高从复杂EHR数据中识别罕见病诊断的准确性。
---

## 摘要
随着人群 DNA 测序变得越来越普遍，基因组优先（genomic-first）的方法正越来越多地被用于识别可能患有罕见遗传病的个体。为了准确评估患病率和外显率，这些研究通常利用电子健康档案（EHR）来确认疾病的表现。目前存在多种在 EHR 中搜索罕见病诊断的策略，但每种策略都有其局限性。我们开发了一种便携式集成工具 DxFit，该工具通过挖掘 EHR 数据（来自计费代码和问题列表表的 ICD 代码及结构化诊断描述），来寻找与特定罕见遗传病一致的诊断。DxFit 结合了四种策略的证据：(1) 在诊断描述和笔记中进行基因名称搜索；(2) 将 ICD 转换为 Mondo 罕见病本体以寻找精确和相近的匹配；(3) 词嵌入相似度搜索；(4) Jaccard 相似度匹配。DxFit 对匹配类型进行优先级排序，并为每个参与者-疾病对输出置信度最高的匹配结果。在一个由 350 名发育障碍诊断性基因检测结果呈阳性的参与者组成的队列中，使用默认参数时，DxFit 的敏感性为 88.7%，特异性为 86.2%。将语言评分阈值从 0.8 调整为 0.7 并允许同义匹配后，敏感性达到 92.7%，特异性为 84.5%。将 EHR 证据划分为基因检测前后的时间窗显示，正如预期的那样，检测后的 DxFit 总体比率有所增加，且匹配类型的置信度更高。DxFit 已向公众开放，并具有广泛的自定义选项以支持各种用途。

## Abstract
As population DNA sequencing becomes more common, genomic-first approaches are increasingly used to identify individuals with possible rare genetic disorders. To accurately estimate prevalence and penetrance, these studies often confirm manifestation of the disorder using electronic health records (EHRs). Multiple strategies exist to search the EHR for diagnoses of rare disorders, however, each has its limitations. We have developed a portable, ensemble tool, DxFit, that mines EHR data (ICD codes and structured diagnosis descriptions from billing code and problem list tables) for a diagnosis consistent with a given rare genetic disorder. DxFit combines evidence across four strategies: (1) gene name searches in diagnosis descriptions and notes, (2) ICD conversion to Mondo rare disorder ontology to find exact and nearby matches, (3) word embedding similarity searches, and (4) Jaccard similarity matches. DxFit prioritizes the match type and outputs the most confident match for each participant-disorder pair. On a cohort of 350 participants with a known positive result from diagnostic genetic testing for developmental disorders, DxFit had a sensitivity of 88.7% and specificity of 86.2% using default parameters. Adjusting the linguistic scoring thresholds from 0.8 to 0.7 and allowing for synonymous matches yielded a sensitivity of 92.7% and specificity of 84.5%. Partitioning EHR evidence into windows before and after genetic testing demonstrates, as expected, that the overall DxFit rates increase after testing and the match types become more confident. DxFit is available to the public and has extensive customization options to support a wide range of uses.

Graphical Abstract

O_FIG O_LINKSMALLFIG WIDTH=187 HEIGHT=200 SRC="FIGDIR/small/720629v1_ufig1.gif" ALT="Figure 1">
View larger version (41K):
org.highwire.dtl.DTLVardef@37a1b1org.highwire.dtl.DTLVardef@58a712org.highwire.dtl.DTLVardef@40c85dorg.highwire.dtl.DTLVardef@12278c7_HPS_FORMAT_FIGEXP  M_FIG C_FIG

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **DxFit** 的集成方法，旨在解决从电子健康档案（EHR）中准确识别与罕见遗传病分子发现相一致的临床诊断这一难题。以下是对该论文的结构化总结：

### 1. 核心问题与研究动机
*   **研究背景**：随着“基因组优先”（Genomic-first）研究的兴起，研究人员经常在人群测序中发现致病变异。为了评估这些变异的外显率和临床意义，必须在 EHR 中确认患者是否具有相应的临床表现。
*   **核心问题**：现有的 EHR 匹配方法存在局限性。直接将 ICD 代码映射到 Mondo（罕见病本体）会导致**匹配稀疏**（ICD 粒度不够）或**过度匹配**（一个 ICD 对应多个遗传病）；而单纯的语义相似度搜索容易受到非特异性词汇（如“家族性”、“异常”）的干扰，且难以识别以人名命名（Eponymous）或缩写形式存在的疾病。

### 2. 方法论：DxFit 核心思想与技术细节
DxFit 是一个集成工具，通过结合四种互补策略来挖掘诊断证据：
*   **基因符号搜索（Gene Symbol Search）**：在诊断描述或临床笔记中直接搜索致病基因符号（如 *SCN1A*）。
*   **ICD 到 Mondo 映射**：利用 Monarch Initiative 提供的映射表。除了精确匹配外，还允许在 Mondo 本体结构中进行 1 度或 2 度的“近邻匹配”。为了防止过度匹配，研究者对 Mondo 树进行了**剪枝处理**（移除过于宽泛的术语，如“遗传性疾病”）。
*   **词嵌入相似度（Word Embedding Similarity）**：使用 NLP 模型（如 `en_core_sci_md`）计算遗传病名称与 EHR 诊断描述之间的语义向量相似度。
*   **Jaccard 相似度**：通过 n-gram 重叠度评估文本相似性，专门用于捕捉 NLP 模型可能遗漏的缩写或人名病名。
*   **优先级排序**：DxFit 根据不同匹配类型的优势比（Odds Ratio）进行排序，输出置信度最高的匹配结果（排序：基因匹配 > 精确匹配 > Jaccard 匹配 > 词嵌入匹配 > 1度近邻 > 2度近邻）。

### 3. 实验设计
*   **数据集**：
    *   **病例组**：350 名经临床基因检测确诊为发育障碍的患者（共 355 个个体-疾病对）。
    *   **对照组**：按年龄和性别匹配的 10 倍对照（3500 人），每人被随机分配一个病例组的遗传病标签以测试误报率。
*   **Benchmark（基准）**：以已知的分子诊断结果为金标准，评估 DxFit 的敏感性（Sensitivity）和特异性（Specificity）。
*   **对比与变量**：对比了默认参数（阈值 0.8）与宽松参数（阈值 0.7 + 同义词匹配）的表现，并分析了基因检测前后的诊断检出率变化。

### 4. 资源与算力
*   论文**未明确说明**具体的硬件算力（如 GPU 型号或数量）。
*   由于该工具基于 Python 开发，使用了 `scispaCy` 等 NLP 库，且处理的是结构化诊断数据和文本描述，预计其对算力的需求处于常规工作站可处理的范围内，具有较好的便携性。

### 5. 实验数量与充分性
*   **实验规模**：使用了 350 名真实患者的临床数据，并构建了大规模对照组，实验设计较为严谨。
*   **消融与分析**：
    *   进行了参数敏感性分析（调整相似度阈值）。
    *   进行了**时间窗分析**，对比了基因检测前、检测中、检测后的匹配率，证明了临床诊断随时间演进的规律。
    *   进行了**专家人工复核**，对 DxFit 未能匹配的病例以及匹配质量较差的病例进行了手动 EHR 审查，确保了结果的客观性。

### 6. 主要结论与发现
*   **高性能**：在默认参数下，DxFit 的敏感性为 **88.7%**，特异性为 **86.2%**。通过调整阈值至 0.7 并加入同义词，敏感性可提升至 **92.7%**。
*   **基因名称的重要性**：约 47.9% 的病例通过基因名称直接匹配成功，但 DxFit 的集成方法额外找回了 40.8% 仅靠基因名无法识别的病例。
*   **诊断演进**：基因检测后，EHR 中的诊断记录变得更加具体和准确，DxFit 的高置信度匹配率显著上升（从检测前的 56.8% 升至检测后的 80.4%）。

### 7. 优点
*   **集成化**：结合了本体论、语言学和直接搜索，克服了单一方法的局限。
*   **可定制性强**：用户可以自定义 NLP 模型、相似度阈值、停用词列表以及本体映射表。
*   **解决冷门病名**：通过 Jaccard 相似度有效解决了 NLP 模型对罕见人名病名识别不足的问题。
*   **开源便携**：工具已在 GitHub 开源，易于集成到现有的基因组研究流程中。

### 8. 不足与局限
*   **依赖描述质量**：如果 EHR 中仅记录了 ICD 代码而没有详细的文本描述，或者描述过于笼统（如仅写“发育迟缓”），DxFit 的表现会受限。
*   **本体深度差异**：Mondo 本体在不同分支的深度不一，导致“2度近邻匹配”在某些分支下可能引入噪声（尽管已进行剪枝）。
*   **笔记挖掘限制**：虽然支持临床笔记，但由于隐私和非结构化数据的复杂性，大规模应用笔记挖掘仍具挑战。

（完）
