---
title: "DxFit: An ensemble method for identifying EHR diagnoses consistent with a molecular finding"
title_zh: DxFit：一种用于识别与分子发现一致的电子健康档案诊断的集成方法
authors: "Torene, R. I., Meltz Murphy, K., Brandt, T., Retterer, K."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720629v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 电子健康记录数据与罕见遗传病分子发现的整合
tldr: DxFit是一个集成工具，旨在从电子健康记录（EHR）中识别与分子发现一致的罕见遗传病诊断。它结合了基因名称搜索、Mondo本体匹配、词嵌入相似度和Jaccard相似度四种策略，解决了传统EHR搜索方法的局限性。在发育障碍队列测试中，该工具表现出高灵敏度和特异性，为基因组优先研究提供了可靠的表型确认手段。
source: biorxiv
selection_source: fresh_fetch
motivation: 随着基因组测序的普及，需要更准确、自动化的方法从复杂的EHR数据中确认罕见遗传病的临床表现，以评估其患病率和外显率。
method: 开发了集成四种策略（基因名搜索、Mondo本体匹配、词嵌入和Jaccard相似度）的DxFit工具，通过挖掘ICD代码和结构化诊断描述来识别匹配项。
result: "在350名发育障碍患者的测试中，DxFit达到了最高92.7%的灵敏度和84.5%的特异性，且在基因检测后的诊断匹配置信度显著提升。"
conclusion: DxFit是一个高效、可定制且开源的工具，能够有效支持大规模基因组研究中的表型验证和临床诊断关联分析。
---

## 摘要
随着人群 DNA 测序的普及，基因组优先（genomic-first）方法正越来越多地被用于识别可能患有罕见遗传病的个体。为了准确估计患病率和外显率，这些研究通常利用电子健康档案（EHR）来确认疾病的表现。虽然目前存在多种在 EHR 中搜索罕见病诊断的策略，但各具局限性。我们开发了一种便携式集成工具 DxFit，该工具通过挖掘 EHR 数据（包括来自计费代码和问题列表表的 ICD 代码及结构化诊断描述），来识别与特定罕见遗传病一致的诊断。DxFit 结合了四种策略的证据：(1) 在诊断描述和笔记中搜索基因名称；(2) 将 ICD 转换为 Mondo 罕见病本体以寻找精确及邻近匹配；(3) 词嵌入相似度搜索；(4) Jaccard 相似度匹配。DxFit 会对匹配类型进行优先级排序，并为每个“参与者-疾病”组合输出置信度最高的匹配结果。在一个包含 350 名发育障碍诊断性基因检测结果呈阳性的参与者队列中，DxFit 在默认参数下的灵敏度为 88.7%，特异性为 86.2%。通过将语言评分阈值从 0.8 调整至 0.7 并允许同义词匹配，其灵敏度提升至 92.7%，特异性为 84.5%。将 EHR 证据划分为基因检测前后的时间窗口分析表明，正如预期，检测后的 DxFit 匹配率有所提高，且匹配类型的置信度更高。DxFit 已向公众开放，并提供丰富的定制选项以支持广泛的应用场景。

图解摘要

O_FIG O_LINKSMALLFIG WIDTH=187 HEIGHT=200 SRC="FIGDIR/small/720629v1_ufig1.gif" ALT="图 1">
查看更大版本 (41K):
org.highwire.dtl.DTLVardef@1a7fae0org.highwire.dtl.DTLVardef@147bd4aorg.highwire.dtl.DTLVardef@dc68ceorg.highwire.dtl.DTLVardef@64e22a_HPS_FORMAT_FIGEXP  M_FIG C_FIG

## Abstract
As population DNA sequencing becomes more common, genomic-first approaches are increasingly used to identify individuals with possible rare genetic disorders. To accurately estimate prevalence and penetrance, these studies often confirm manifestation of the disorder using electronic health records (EHRs). Multiple strategies exist to search the EHR for diagnoses of rare disorders, however, each has its limitations. We have developed a portable, ensemble tool, DxFit, that mines EHR data (ICD codes and structured diagnosis descriptions from billing code and problem list tables) for a diagnosis consistent with a given rare genetic disorder. DxFit combines evidence across four strategies: (1) gene name searches in diagnosis descriptions and notes, (2) ICD conversion to Mondo rare disorder ontology to find exact and nearby matches, (3) word embedding similarity searches, and (4) Jaccard similarity matches. DxFit prioritizes the match type and outputs the most confident match for each participant-disorder pair. On a cohort of 350 participants with a known positive result from diagnostic genetic testing for developmental disorders, DxFit had a sensitivity of 88.7% and specificity of 86.2% using default parameters. Adjusting the linguistic scoring thresholds from 0.8 to 0.7 and allowing for synonymous matches yielded a sensitivity of 92.7% and specificity of 84.5%. Partitioning EHR evidence into windows before and after genetic testing demonstrates, as expected, that the overall DxFit rates increase after testing and the match types become more confident. DxFit is available to the public and has extensive customization options to support a wide range of uses.

Graphical Abstract

O_FIG O_LINKSMALLFIG WIDTH=187 HEIGHT=200 SRC="FIGDIR/small/720629v1_ufig1.gif" ALT="Figure 1">
View larger version (41K):
org.highwire.dtl.DTLVardef@1a7fae0org.highwire.dtl.DTLVardef@147bd4aorg.highwire.dtl.DTLVardef@dc68ceorg.highwire.dtl.DTLVardef@64e22a_HPS_FORMAT_FIGEXP  M_FIG C_FIG

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **DxFit** 的集成工具，旨在解决如何从复杂的电子健康档案（EHR）中准确识别与分子遗传学发现相一致的临床诊断。以下是对该论文的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **研究动机**：随着大规模人群基因组测序的普及，“基因组优先”（genomic-first）的研究方法日益增多。研究者需要确认携带特定致病变异的个体是否在临床上表现出相应的疾病，以准确评估疾病的患病率和外显率。
*   **核心问题**：传统的 EHR 搜索方法存在局限性。例如，ICD 代码（国际疾病分类）通常过于宽泛，无法区分具体的罕见遗传病；而简单的关键词搜索又容易因同义词、拼写差异或描述不规范而漏诊。
*   **整体含义**：DxFit 提供了一种自动化的集成方案，能够跨越结构化代码和非结构化描述，提高从 EHR 中提取罕见病表型的准确性和效率。

### 2. 论文提出的方法论
DxFit 的核心思想是**集成四种互补的搜索策略**，并根据匹配的置信度进行优先级排序：
1.  **基因名称搜索（Gene Name Search）**：在诊断描述或临床笔记中直接搜索相关的基因符号（如 *SCN1A*）。
2.  **Mondo 本体匹配（Mondo Ontology Matching）**：利用 Mondo 罕见病本体，将 EHR 中的 ICD 代码映射到具体的罕见病术语，支持精确匹配以及父节点/子节点的层级匹配。
3.  **词嵌入相似度（Word Embedding Similarity）**：使用预训练的生物医学语言模型（如 BioSentVec）计算 EHR 诊断文本与目标疾病名称之间的语义向量相似度。
4.  **Jaccard 相似度（Jaccard Similarity）**：基于字符重叠度进行模糊匹配，以捕获拼写变体或部分匹配的术语。

**工作流程**：工具接收参与者的 EHR 数据（ICD 代码和诊断描述）及分子发现（基因或疾病名），运行上述四种策略，最后输出置信度最高的匹配结果及其来源。

### 3. 实验设计
*   **数据集**：使用了 350 名已通过临床诊断性基因检测确认患有发育障碍（Developmental Disorders, DD）的患者数据。
*   **基准测试（Benchmark）**：以人工临床专家审查的结果作为“金标准”。
*   **对比场景**：
    *   **默认参数 vs. 优化参数**：调整语言评分阈值（从 0.8 降至 0.7）并允许同义词匹配。
    *   **时间窗口分析**：对比基因检测前（Pre-test）和检测后（Post-test）的 EHR 记录，观察诊断记录的演变。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号、数量或训练时长。
*   **技术栈**：提到使用了 Python 开发，并集成了 BioSentVec 模型。由于该工具主要侧重于推理和相似度计算，而非从头训练大型语言模型，因此对算力的需求预计在常规服务器或高性能工作站的可控范围内。

### 5. 实验数量与充分性
*   **实验规模**：针对 350 名患者的真实临床数据进行了验证，涵盖了多种不同的发育障碍基因。
*   **充分性评价**：
    *   **灵敏度与特异性分析**：通过调整阈值展示了工具在不同应用场景下的性能权衡。
    *   **消融/对比分析**：通过时间窗口分析证明了工具在捕获“确诊后诊断更新”方面的敏感性。
    *   **客观性**：使用了独立的临床金标准进行验证，实验设计较为客观。

### 6. 主要结论与发现
*   **高性能**：在默认参数下，DxFit 的灵敏度为 88.7%，特异性为 86.2%。通过优化参数，灵敏度可提升至 **92.7%**。
*   **超越 ICD 代码**：实验证明，仅靠 ICD 代码映射会漏掉大量病例，而结合基因名称和语义相似度能显著提高检出率。
*   **诊断演变**：基因检测后的 EHR 记录中，匹配类型的置信度显著更高（更多直接提及基因或具体疾病名），这反映了分子诊断对临床记录的反馈作用。

### 7. 优点
*   **集成化思维**：结合了本体论、语言模型和传统字符串匹配，弥补了单一方法的短板。
*   **便携性与通用性**：设计为可移植工具，能够处理标准化的 EHR 数据表，易于在不同医疗机构间部署。
*   **高度可定制**：允许用户根据研究需求（如追求高灵敏度或高特异性）调整匹配阈值。
*   **开源贡献**：工具向公众开放，促进了罕见病研究社区的协作。

### 8. 不足与局限
*   **数据源限制**：目前主要依赖结构化的诊断描述和 ICD 代码，尚未充分挖掘非结构化的长篇临床病程记录（Clinical Notes）。
*   **本体依赖**：Mondo 匹配的效果受限于 ICD 到 Mondo 映射表的完整性。
*   **罕见病偏向**：该工具专门为罕见遗传病设计，对于表型复杂、非单基因驱动的常见病可能适用性有限。
*   **假阳性风险**：在允许同义词或降低相似度阈值时，可能会引入与目标疾病症状相似但本质不同的误报。

（完）
