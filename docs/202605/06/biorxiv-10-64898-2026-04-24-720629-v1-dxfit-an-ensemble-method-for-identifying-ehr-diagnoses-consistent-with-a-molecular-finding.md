---
title: "DxFit: An ensemble method for identifying EHR diagnoses consistent with a molecular finding"
title_zh: DxFit：一种用于识别与分子发现一致的电子健康档案（EHR）诊断的集成方法
authors: "Torene, R. I., Meltz Murphy, K., Brandt, T., Retterer, K."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720629v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 挖掘电子健康记录（EHR）数据以识别与分子发现一致的诊断
tldr: DxFit是一个集成工具，旨在从电子健康记录（EHR）中识别与分子发现一致的罕见遗传病诊断。它结合了基因名称搜索、ICD到Mondo本体匹配、词嵌入相似度和Jaccard相似度四种策略。在发育障碍队列测试中，DxFit表现出极高的灵敏度和特异性，能有效支持基因组优先研究中的疾病流行率和外显率评估，且该工具已向公众开放并支持高度定制。
source: biorxiv
selection_source: fresh_fetch
motivation: 随着人群DNA测序的普及，需要更准确的方法从复杂的电子健康记录中确认罕见遗传病的临床表现，以克服现有搜索策略的局限性。
method: 开发了集成工具DxFit，通过结合基因名搜索、ICD到Mondo本体转换、词嵌入相似度及Jaccard匹配四种策略，从计费代码和问题列表中挖掘诊断信息。
result: "在350名发育障碍患者的测试中，DxFit达到了最高92.7%的灵敏度和84.5%的特异性，并证明了基因检测后的诊断匹配置信度显著提升。"
conclusion: DxFit是一个高效、可移植且可定制的工具，能够显著提升从EHR中识别罕见病诊断的准确性，为基因组医学研究提供有力支持。
---

## 摘要
随着人群 DNA 测序变得越来越普遍，基因组优先（genomic-first）的方法正越来越多地被用于识别可能患有罕见遗传病的个体。为了准确评估患病率和外显率，这些研究通常利用电子健康档案（EHR）来确认疾病的表现。目前存在多种在 EHR 中搜索罕见病诊断的策略，但每种策略都有其局限性。我们开发了一种便携式集成工具 DxFit，该工具通过挖掘 EHR 数据（包括来自计费代码和问题列表表的 ICD 代码及结构化诊断描述），来寻找与特定罕见遗传病一致的诊断。DxFit 结合了四种策略的证据：(1) 在诊断描述和笔记中进行基因名称搜索；(2) 将 ICD 转换为 Mondo 罕见病本体以寻找精确和相近的匹配；(3) 词嵌入相似度搜索；以及 (4) Jaccard 相似度匹配。DxFit 对匹配类型进行优先级排序，并为每个受试者-疾病对输出置信度最高的匹配结果。在一个由 350 名发育障碍诊断性基因检测结果呈阳性的受试者组成的队列中，使用默认参数时，DxFit 的敏感性为 88.7%，特异性为 86.2%。将语言评分阈值从 0.8 调整为 0.7 并允许同义词匹配后，敏感性达到 92.7%，特异性为 84.5%。将 EHR 证据划分为基因检测前后的时间窗显示，正如预期的那样，检测后的 DxFit 总体匹配率有所提高，且匹配类型的置信度更高。DxFit 已向公众开放，并提供广泛的自定义选项以支持各种用途。

## Abstract
As population DNA sequencing becomes more common, genomic-first approaches are increasingly used to identify individuals with possible rare genetic disorders. To accurately estimate prevalence and penetrance, these studies often confirm manifestation of the disorder using electronic health records (EHRs). Multiple strategies exist to search the EHR for diagnoses of rare disorders, however, each has its limitations. We have developed a portable, ensemble tool, DxFit, that mines EHR data (ICD codes and structured diagnosis descriptions from billing code and problem list tables) for a diagnosis consistent with a given rare genetic disorder. DxFit combines evidence across four strategies: (1) gene name searches in diagnosis descriptions and notes, (2) ICD conversion to Mondo rare disorder ontology to find exact and nearby matches, (3) word embedding similarity searches, and (4) Jaccard similarity matches. DxFit prioritizes the match type and outputs the most confident match for each participant-disorder pair. On a cohort of 350 participants with a known positive result from diagnostic genetic testing for developmental disorders, DxFit had a sensitivity of 88.7% and specificity of 86.2% using default parameters. Adjusting the linguistic scoring thresholds from 0.8 to 0.7 and allowing for synonymous matches yielded a sensitivity of 92.7% and specificity of 84.5%. Partitioning EHR evidence into windows before and after genetic testing demonstrates, as expected, that the overall DxFit rates increase after testing and the match types become more confident. DxFit is available to the public and has extensive customization options to support a wide range of uses.

Graphical Abstract

O_FIG O_LINKSMALLFIG WIDTH=187 HEIGHT=200 SRC="FIGDIR/small/720629v1_ufig1.gif" ALT="Figure 1">
View larger version (41K):
org.highwire.dtl.DTLVardef@2fd828org.highwire.dtl.DTLVardef@1183579org.highwire.dtl.DTLVardef@5eaae1org.highwire.dtl.DTLVardef@124d263_HPS_FORMAT_FIGEXP  M_FIG C_FIG

---

## 论文详细总结（自动生成）

这篇论文介绍了一种名为 **DxFit** 的集成工具，旨在解决从电子健康档案（EHR）中准确识别与分子遗传学发现相一致的罕见病诊断这一挑战。

以下是对该论文的结构化总结：

### 1. 核心问题与背景
*   **研究动机**：随着大规模人群基因组测序（Genomic-first）的普及，研究人员需要验证携带致病变异的个体是否在临床上表现出相应症状。
*   **核心挑战**：现有的 EHR 检索方法存在局限性。例如，ICD 代码（计费代码）与 Mondo（罕见病本体）之间的映射非常稀疏（约 75% 的 Mondo 术语没有直接对应的 ICD）；而简单的语义相似度匹配容易产生误报（如将“遗传性肥胖”误匹配为普通“肥胖”）。
*   **整体含义**：DxFit 旨在通过集成多种搜索策略，提供一种高灵敏度、高特异性且可移植的工具，帮助研究者在海量 EHR 数据中自动确认罕见遗传病的临床诊断。

### 2. 方法论
DxFit 核心思想是**集成（Ensemble）**四种互补的证据搜索策略，并根据置信度进行优先级排序：
*   **策略 1：基因符号搜索 (Gene Dx Match)**：在诊断描述或临床笔记中直接搜索致病基因符号（如 *SCN1A*）。
*   **策略 2：ICD 到 Mondo 映射 (ICD-to-Mondo)**：利用 Monarch Initiative 的映射表。除了精确匹配，还允许在 Mondo 本体结构中进行 1 度或 2 度的“近邻匹配”。为了防止过度匹配，研究者对 Mondo 本体进行了修剪（剔除了“遗传性疾病”等过于宽泛的术语）。
*   **策略 3：词嵌入相似度 (Word Embedding)**：使用 NLP 模型（`en_core_sci_md`）计算诊断描述与疾病名称之间的语义向量相似度。
*   **策略 4：Jaccard 相似度**：通过 n-gram 重叠度进行匹配，主要用于捕捉 NLP 模型可能遗漏的专有名词（人名病名）或缩写。
*   **数据清洗与优化**：引入了自定义停用词列表、排除词（如“筛查”、“家族史”）以及针对常见病的后处理过滤，以提升特异性。

### 3. 实验设计
*   **数据集**：
    *   **病例组**：350 名经临床基因检测确认患有发育障碍（Developmental Disorders）的患者（共 355 个受试者-疾病对）。
    *   **对照组**：按 1:10 比例匹配的年龄、性别对照者（3,500 人），每人被随机分配一个病例组的疾病标签以测试误报率。
*   **Benchmark**：以已知的分子诊断结果为金标准。
*   **对比维度**：
    *   不同参数配置（默认阈值 0.8 vs. 调整阈值 0.7 + 同义词匹配）。
    *   时间维度分析：对比基因检测日期前后的诊断匹配率变化。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号或训练时长。
*   **技术栈**：该工具基于 Python 开发，使用了 `scispaCy` 库进行 NLP 处理。由于其主要涉及向量相似度计算和本体查询，而非大规模深度学习模型训练，预计对算力的需求较低，普通工作站即可运行。

### 5. 实验数量与充分性
*   **实验规模**：使用了 350 个真实病例和 3,500 个对照，样本量对于罕见病研究而言较为充分。
*   **实验类型**：包括了灵敏度/特异性分析、参数消融实验（阈值调整）、专家人工复核（针对非精确匹配的病例）以及时间序列分析。
*   **公平性**：通过 1:10 的对照组设计和时间窗划分，较好地证明了工具的区分能力和在临床诊断演变过程中的有效性。

### 6. 主要结论与发现
*   **高性能**：默认参数下灵敏度为 88.7%，特异性为 86.2%；优化参数后灵敏度可提升至 **92.7%**。
*   **集成优势**：基因名称搜索虽然最准确，但会漏掉约 40% 的病例，这些病例需要靠 ICD 映射和语义相似度来补全。
*   **诊断演变**：基因检测后，DxFit 的匹配率从 56.8% 显著上升至 80.4%，且匹配类型的置信度（如从“近邻匹配”变为“基因名匹配”）明显增强，反映了临床诊断随基因检测结果而确化的过程。
*   **误报来源**：对照组中的误报主要集中在置信度最低的“2 度近邻匹配”类别。

### 7. 优点
*   **多模态集成**：结合了结构化代码（ICD）、本体知识（Mondo）和非结构化文本（NLP），覆盖面广。
*   **本体修剪技术**：通过修剪 Mondo 本体中的模糊节点，有效解决了本体匹配中常见的“过度匹配”问题。
*   **高度可定制**：支持用户更换 NLP 模型、调整相似度阈值、自定义停用词，具有很强的灵活性。
*   **开源便携**：工具已在 GitHub 公开，方便其他研究机构使用。

### 8. 不足与局限
*   **依赖描述质量**：虽然支持临床笔记，但实验评估主要基于 ICD 描述和问题列表，如果 EHR 记录过于简略，工具性能会受限。
*   **本体局限性**：如果用户使用的疾病词汇不在 Mondo 或其支持的本体中，ICD 映射功能将失效。
*   **近邻匹配的噪声**：2 度近邻匹配虽然增加了召回率，但也引入了较多模糊匹配（如将特定遗传病匹配到宽泛的“智力障碍”），需要人工二次确认。
*   **特定领域偏向**：实验主要在发育障碍队列中完成，在其他复杂多系统疾病中的表现尚需进一步验证。

（完）
