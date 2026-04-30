---
title: "DxFit: An ensemble method for identifying EHR diagnoses consistent with a molecular finding"
title_zh: DxFit：一种用于识别与分子发现一致的电子健康档案（EHR）诊断的集成方法
authors: "Torene, R. I., Meltz Murphy, K., Brandt, T., Retterer, K."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720629v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 挖掘电子健康档案数据以寻找与罕见遗传病一致的诊断
tldr: DxFit是一个集成工具，旨在从电子健康记录（EHR）中识别与分子发现一致的罕见遗传病诊断。随着基因组测序的普及，准确评估疾病流行率和外显率变得至关重要。DxFit结合了基因名称搜索、本体匹配、词嵌入相似度和Jaccard相似度四种策略，能有效挖掘ICD代码和结构化诊断描述。在350名发育障碍患者的测试中表现出高灵敏度和特异性，为基因组优先研究提供了强有力的支持。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的从EHR中搜索罕见病诊断的方法存在局限性，需要更准确、自动化的工具来验证基因发现。
method: 开发了集成四种策略（基因名搜索、Mondo本体转换、词嵌入和Jaccard相似度）的便携式工具DxFit。
result: "在已知发育障碍队列中，DxFit达到了最高92.7%的灵敏度和84.5%的特异性，且在基因检测后匹配置信度显著提升。"
conclusion: DxFit是一个高效、可定制的开源工具，能够显著提高从EHR中识别罕见遗传病诊断的准确性。
---

## 摘要
随着人群 DNA 测序变得越来越普遍，基因组优先（genomic-first）方法越来越多地被用于识别可能患有罕见遗传病的个体。为了准确估计患病率和外显率，这些研究通常利用电子健康档案（EHR）来确认疾病的表现。目前存在多种在 EHR 中搜索罕见病诊断的策略，但每种策略都有其局限性。我们开发了一种便携式集成工具 DxFit，该工具通过挖掘 EHR 数据（包括来自计费代码和问题列表表的 ICD 代码及结构化诊断描述），来寻找与特定罕见遗传病一致的诊断。DxFit 结合了四种策略的证据：(1) 在诊断描述和注释中进行基因名称搜索；(2) 将 ICD 转换为 Mondo 罕见病本体以寻找精确及相近匹配；(3) 词嵌入相似度搜索；以及 (4) Jaccard 相似度匹配。DxFit 对匹配类型进行优先级排序，并为每个“参与者-疾病”对输出置信度最高的匹配。在一个由 350 名发育障碍诊断性基因检测结果呈阳性的参与者组成的队列中，使用默认参数时，DxFit 的灵敏度为 88.7%，特异性为 86.2%。将语言评分阈值从 0.8 调整至 0.7 并允许同义词匹配后，灵敏度提升至 92.7%，特异性为 84.5%。将 EHR 证据划分为基因检测前后的时间窗显示，正如预期，检测后 DxFit 的整体检出率有所增加，且匹配类型的置信度更高。DxFit 已向公众开放，并提供广泛的定制选项以支持多种用途。

## Abstract
As population DNA sequencing becomes more common, genomic-first approaches are increasingly used to identify individuals with possible rare genetic disorders. To accurately estimate prevalence and penetrance, these studies often confirm manifestation of the disorder using electronic health records (EHRs). Multiple strategies exist to search the EHR for diagnoses of rare disorders, however, each has its limitations. We have developed a portable, ensemble tool, DxFit, that mines EHR data (ICD codes and structured diagnosis descriptions from billing code and problem list tables) for a diagnosis consistent with a given rare genetic disorder. DxFit combines evidence across four strategies: (1) gene name searches in diagnosis descriptions and notes, (2) ICD conversion to Mondo rare disorder ontology to find exact and nearby matches, (3) word embedding similarity searches, and (4) Jaccard similarity matches. DxFit prioritizes the match type and outputs the most confident match for each participant-disorder pair. On a cohort of 350 participants with a known positive result from diagnostic genetic testing for developmental disorders, DxFit had a sensitivity of 88.7% and specificity of 86.2% using default parameters. Adjusting the linguistic scoring thresholds from 0.8 to 0.7 and allowing for synonymous matches yielded a sensitivity of 92.7% and specificity of 84.5%. Partitioning EHR evidence into windows before and after genetic testing demonstrates, as expected, that the overall DxFit rates increase after testing and the match types become more confident. DxFit is available to the public and has extensive customization options to support a wide range of uses.

---

## 论文详细总结（自动生成）

这是一份关于论文《DxFit: An ensemble method for identifying EHR diagnoses consistent with a molecular finding》的结构化总结：

### 1. 论文的核心问题与整体含义
随着“基因组优先”（Genomic-first）研究的兴起，研究人员需要在大规模人群中验证基因变异是否导致了临床表型。然而，从电子健康档案（EHR）中准确识别罕见遗传病诊断存在挑战：
*   **映射稀疏性**：ICD代码（用于计费）与Mondo本体（用于罕见病描述）之间缺乏一一对应关系。
*   **匹配过度**：简单的语义搜索可能将普通疾病（如普通肥胖）误匹配为罕见遗传病（如遗传性肥胖）。
*   **术语不规范**：罕见病常使用人名（Eponyms）或缩写，标准NLP模型难以识别。
**DxFit** 的提出旨在通过一种集成的自动化方法，准确地将患者的EHR记录与疑似的分子诊断结果进行匹配。

### 2. 论文提出的方法论
DxFit 采用集成学习的思想，结合了四种互补的搜索策略，并根据特异性对结果进行优先级排序：
*   **核心策略**：
    1.  **基因符号搜索**：在诊断描述或临床文本中直接搜索基因名（如 *SCN1A*）。
    2.  **ICD-to-Mondo 映射**：利用 Monarch Initiative 的映射表，允许在 Mondo 本体中进行 1-2 度的邻近匹配，并对本体树进行了剪枝（移除“遗传病”等过于宽泛的节点）以防止过度匹配。
    3.  **词嵌入相似度（Word Embedding）**：使用 `scispaCy` 模型（`en_core_sci_md`）计算诊断描述与疾病名称之间的语义向量相似度。
    4.  **Jaccard 相似度**：通过 n-gram 重叠度评估文本相似性，专门用于捕捉 NLP 模型可能遗漏的人名病名或缩写。
*   **优先级排序**：匹配结果按置信度从高到低排列（基因匹配 > 精确匹配 > Jaccard > 语义相似度 > 1度邻近 > 2度邻近）。

### 3. 实验设计
*   **数据集**：
    *   **病例组**：350 名经临床基因检测确认患有单基因发育障碍的患者（共 355 个“个体-疾病对”）。
    *   **对照组**：按 1:10 比例匹配的年龄、性别对照组（共 3500 人），用于评估误报率。
*   **Benchmark**：以临床已知的分子诊断结果为金标准，对比 DxFit 在不同参数下的表现。
*   **对比维度**：评估了默认参数（阈值 0.8）与宽松参数（阈值 0.7 + 同义词匹配）的效果，并分析了基因检测前后的诊断检出率变化。

### 4. 资源与算力
*   论文**未明确说明**具体的硬件配置（如 GPU 型号或数量）。
*   由于该工具主要基于预训练的 NLP 模型（`scispaCy`）进行推理，且涉及的是本体映射和字符串匹配，其计算开销相对较小，重点在于算法逻辑而非大规模模型训练。

### 5. 实验数量与充分性
*   **实验规模**：针对 350 多个真实病例和 3500 个对照进行了验证，样本量对于罕见病研究而言较为充分。
*   **消融与分析**：
    *   进行了参数敏感性分析（0.8 vs 0.7 阈值）。
    *   进行了时间窗口分析（检测前 vs 检测后），证明了工具能捕捉到临床诊断随时间演进的过程。
    *   进行了人工复核，对 DxFit 漏掉的病例和误报的病例进行了深入的定性分析。
*   **评价**：实验设计客观、公平，通过对照组设置有效地评估了特异性。

### 6. 论文的主要结论与发现
*   **高性能**：在默认参数下，DxFit 的灵敏度为 **88.7%**，特异性为 **86.2%**。
*   **参数影响**：通过降低语言匹配阈值并引入同义词，灵敏度可提升至 **92.7%**，但特异性会略微下降至 84.5%。
*   **时间趋势**：基因检测后，EHR 中的诊断记录变得更加明确（如加入基因名），DxFit 的匹配置信度显著提升。
*   **集成优势**：约 40.8% 的病例无法仅通过基因名搜索找到，证明了多策略集成的必要性。

### 7. 优点
*   **便携性与开源**：工具已在 GitHub 开源，且不依赖特定的医疗系统架构。
*   **本体优化**：对 Mondo 本体进行了定制化剪枝，有效解决了本体匹配中的“过度贪婪”问题。
*   **高度可定制**：允许用户更换 NLP 模型、调整阈值、自定义停用词表，适应不同疾病领域。

### 8. 不足与局限
*   **术语差异限制**：如果 EHR 中的描述与 Mondo 本体定义的术语完全不同（且未提及基因名），DxFit 仍会漏诊。
*   **依赖结构化数据**：虽然支持临床注释，但主要评估仍基于 ICD 描述，对于非结构化文本挖掘的深度可能有限。
*   **假阳性风险**：在对照组中仍有约 15% 的假阳性率，主要集中在“2度邻近匹配”类别，对于需要极高精确度的场景需谨慎使用。

（完）
