---
title: "DxFit: An ensemble method for identifying EHR diagnoses consistent with a molecular finding"
title_zh: DxFit：一种用于识别与分子发现一致的 EHR 诊断的集成方法
authors: "Torene, R. I., Meltz Murphy, K., Brandt, T., Retterer, K."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720629v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 挖掘电子健康记录以匹配分子发现的集成方法
tldr: DxFit是一个集成工具，旨在从电子健康记录（EHR）中识别与分子发现一致的罕见遗传病诊断。它结合了基因名称搜索、本体匹配、词嵌入相似度和Jaccard相似度四种策略。在发育障碍队列测试中表现出高灵敏度和特异性，为基因组优先研究提供了有效的表型确认手段。
source: biorxiv
selection_source: fresh_fetch
motivation: 随着人群DNA测序的普及，需要更准确的方法从复杂的EHR数据中确认罕见遗传病的临床表现。
method: 开发了集成四种策略（基因搜索、本体转换、词嵌入和Jaccard相似度）的DxFit工具，用于挖掘ICD代码和诊断描述。
result: "在350名发育障碍患者的测试中，DxFit达到了最高92.7%的灵敏度和84.5%的特异性。"
conclusion: DxFit是一个可移植且高度可定制的工具，能有效支持基因组优先研究中的表型验证和患病率估算。
---

## 摘要
随着人群 DNA 测序变得越来越普遍，基因组优先（genomic-first）的方法正越来越多地被用于识别可能患有罕见遗传病的个体。为了准确估计患病率和外显率，这些研究通常利用电子健康档案（EHR）来确认疾病的表现。尽管存在多种在 EHR 中搜索罕见病诊断的策略，但每种策略都有其局限性。我们开发了一种便携式集成工具 DxFit，该工具通过挖掘 EHR 数据（来自计费代码和问题列表表的 ICD 代码及结构化诊断描述），来寻找与特定罕见遗传病一致的诊断。DxFit 结合了四种策略的证据：(1) 在诊断描述和注释中进行基因名称搜索；(2) 将 ICD 转换为 Mondo 罕见病本体以寻找精确和相近的匹配；(3) 词嵌入相似度搜索；以及 (4) Jaccard 相似度匹配。DxFit 对匹配类型进行优先级排序，并为每个受试者-疾病对输出置信度最高的匹配结果。在一个由 350 名已知发育障碍诊断性基因检测结果呈阳性的受试者组成的队列中，使用默认参数时，DxFit 的敏感性为 88.7%，特异性为 86.2%。将语言评分阈值从 0.8 调整为 0.7 并允许同义词匹配后，敏感性达到 92.7%，特异性为 84.5%。将 EHR 证据划分为基因检测前后的时间窗显示，正如预期的那样，检测后的 DxFit 总体检出率有所提高，且匹配类型的置信度更高。DxFit 已向公众开放，并提供广泛的自定义选项以支持各种用途。

## Abstract
As population DNA sequencing becomes more common, genomic-first approaches are increasingly used to identify individuals with possible rare genetic disorders. To accurately estimate prevalence and penetrance, these studies often confirm manifestation of the disorder using electronic health records (EHRs). Multiple strategies exist to search the EHR for diagnoses of rare disorders, however, each has its limitations. We have developed a portable, ensemble tool, DxFit, that mines EHR data (ICD codes and structured diagnosis descriptions from billing code and problem list tables) for a diagnosis consistent with a given rare genetic disorder. DxFit combines evidence across four strategies: (1) gene name searches in diagnosis descriptions and notes, (2) ICD conversion to Mondo rare disorder ontology to find exact and nearby matches, (3) word embedding similarity searches, and (4) Jaccard similarity matches. DxFit prioritizes the match type and outputs the most confident match for each participant-disorder pair. On a cohort of 350 participants with a known positive result from diagnostic genetic testing for developmental disorders, DxFit had a sensitivity of 88.7% and specificity of 86.2% using default parameters. Adjusting the linguistic scoring thresholds from 0.8 to 0.7 and allowing for synonymous matches yielded a sensitivity of 92.7% and specificity of 84.5%. Partitioning EHR evidence into windows before and after genetic testing demonstrates, as expected, that the overall DxFit rates increase after testing and the match types become more confident. DxFit is available to the public and has extensive customization options to support a wide range of uses.

Graphical Abstract

O_FIG O_LINKSMALLFIG WIDTH=187 HEIGHT=200 SRC="FIGDIR/small/720629v1_ufig1.gif" ALT="Figure 1">
View larger version (41K):
org.highwire.dtl.DTLVardef@1191031org.highwire.dtl.DTLVardef@76028dorg.highwire.dtl.DTLVardef@1a1a97borg.highwire.dtl.DTLVardef@7de3b1_HPS_FORMAT_FIGEXP  M_FIG C_FIG

---

## 论文详细总结（自动生成）

这是一份关于论文《DxFit: An ensemble method for identifying EHR diagnoses consistent with a molecular finding》的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
随着大规模人群基因组测序（Genomic-first）研究的兴起，研究人员需要从电子健康记录（EHR）中确认受试者是否表现出与特定遗传变异相关的临床表型，以准确评估变异的外显率和疾病流行率。
然而，现有的 EHR 匹配方法存在显著局限：
*   **映射稀疏与过度匹配：** 计费用的 ICD 代码与罕见病本体（如 Mondo）之间缺乏一一对应关系。
*   **语义搜索缺陷：** 标准 NLP 模型往往难以识别罕见病的特定缩写或人名命名（Eponymous）的疾病。
*   **缺乏通用性：** 现有工具往往针对特定疾病类别（如代谢病），缺乏跨学科的通用性。

### 2. 论文提出的方法论：DxFit 集成工具
DxFit 是一种便携式集成工具，通过四种互补策略在 EHR 数据（ICD 代码、诊断描述、临床注释）中搜索证据：
1.  **基因符号搜索（Gene symbol search）：** 在诊断描述或注释中直接检索变异基因的官方符号（如 *SCN1A*）。
2.  **ICD-to-Mondo 映射：** 利用 Monarch Initiative 的映射表，在 Mondo 本体中寻找精确匹配或 1-2 级以内的近邻匹配。为了防止过度匹配，DxFit 对 Mondo 树进行了**自定义剪枝**（移除“遗传性疾病”等过于宽泛的节点）。
3.  **词嵌入相似度（Word embedding similarity）：** 使用 `en_core_sci_md` 医疗 NLP 模型计算诊断描述与疾病名称之间的语义向量相似度。
4.  **Jaccard 相似度：** 通过 n-gram 重叠评估文本相似性，专门用于捕捉 NLP 模型可能遗漏的缩写或人名病名。

**优先级排序：** DxFit 根据匹配类型的特异性（基于优势比 Odds Ratio）对结果进行排序，输出置信度最高的匹配。

### 3. 实验设计
*   **数据集：** 包含 350 名（355 个受试者-疾病对）经临床基因检测确诊为发育障碍的患者队列。
*   **对照组：** 按 1:10 的比例匹配了年龄、性别相同的对照个体，并为其分配相同的目标疾病以测试误报率。
*   **Benchmark（基准）：**
    *   对比了默认参数（阈值 0.8）与调整参数（阈值 0.7 + 同义词匹配）的表现。
    *   对比了仅使用基因名称搜索与 DxFit 集成方法的差异。
    *   进行了**时间窗分析**，对比基因检测前、检测中、检测后的诊断检出率。

### 4. 资源与算力
*   论文中**未明确说明**具体的硬件算力（如 GPU 型号或数量）。
*   技术栈方面，提到了使用 `scispaCy` 的 `en_core_sci_md` 模型进行词嵌入计算。由于该工具主要用于推理和匹配而非大规模模型训练，其对算力的需求预计在常规服务器或高性能工作站范围内。

### 5. 实验数量与充分性
*   **实验规模：** 针对 350 名阳性病例和 3500 名对照进行了测试，涵盖了多种发育障碍相关基因。
*   **消融与参数分析：** 评估了不同相似度阈值（0.7 vs 0.8）对敏感性和特异性的影响。
*   **客观性：** 引入了独立评审员对非精确匹配结果进行人工复核，并分析了“模糊匹配”在临床上的合理性。
*   **充分性：** 实验设计较为充分，特别是通过时间轴分析证明了 DxFit 能够捕捉到确诊前后的诊断演变，增强了结果的说服力。

### 6. 主要结论与发现
*   **高性能：** 默认参数下敏感性为 88.7%，特异性为 86.2%；优化参数后敏感性提升至 **92.7%**。
*   **集成优势：** 约 40.8% 的病例匹配是通过基因名称搜索以外的策略（如语义相似度或本体映射）发现的，证明了集成方法的必要性。
*   **时间相关性：** 基因检测后，DxFit 的检出率显著提高（从 56.8% 升至 80.4%），且匹配类型的置信度（如出现基因名）随之增加。
*   **误报分析：** 对照组中的误报大多属于置信度最低的“2 级以内近邻匹配”，用户可以通过过滤该类别来提高特异性。

### 7. 优点
*   **高度可定制：** 支持用户更换 NLP 模型、调整阈值、自定义停用词列表和本体映射。
*   **解决本体痛点：** 通过对 Mondo 本体的剪枝处理，有效解决了医学本体中常见的“过度匹配”问题。
*   **便携性：** 工具已开源，且不依赖于特定的医疗系统架构，易于在不同研究中心推广。

### 8. 不足与局限
*   **依赖结构化数据：** 虽然支持临床注释，但核心评估仍高度依赖 ICD 代码和简短的诊断描述。
*   **本体局限性：** 尽管进行了剪枝，但 Mondo 等本体在不同分支的深度和特异性不一，可能导致某些疾病类别的匹配效果优于其他类别。
*   **假阴性风险：** 人工复核显示，部分未检出病例是因为 EHR 中的描述与 Mondo 标准术语差异过大（如“学习障碍” vs “智力低下”），这反映了医疗记录非规范化的固有挑战。

（完）
