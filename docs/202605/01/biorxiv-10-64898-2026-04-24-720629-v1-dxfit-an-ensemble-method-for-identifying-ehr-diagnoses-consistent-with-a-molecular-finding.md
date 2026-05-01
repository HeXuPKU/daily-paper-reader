---
title: "DxFit: An ensemble method for identifying EHR diagnoses consistent with a molecular finding"
title_zh: DxFit：一种用于识别与分子发现一致的 EHR 诊断的集成方法
authors: "Torene, R. I., Meltz Murphy, K., Brandt, T., Retterer, K."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720629v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 挖掘电子健康记录数据以发现罕见遗传病
tldr: DxFit是一个集成工具，旨在从电子健康记录（EHR）中识别与分子发现一致的罕见遗传病诊断。随着基因组测序的普及，准确评估疾病流行率和外显率变得至关重要。DxFit结合了基因名称搜索、本体匹配、词嵌入相似度和Jaccard相似度四种策略，能有效挖掘ICD代码和结构化诊断描述。在350名发育障碍患者的测试中表现出高灵敏度和特异性，为基因组优先研究提供了强有力的支持。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的从EHR中搜索罕见病诊断的方法存在局限性，需要更准确、自动化的工具来验证基因发现。
method: 开发了集成四种策略（基因名搜索、Mondo本体转换、词嵌入和Jaccard相似度）的便携式工具DxFit。
result: "在已知发育障碍队列中，DxFit达到了最高92.7%的灵敏度和84.5%的特异性，且在基因检测后匹配置信度显著提升。"
conclusion: DxFit是一个高效、可定制的开源工具，能够显著提高从EHR中识别罕见遗传病诊断的准确性。
---

## 摘要
随着人群 DNA 测序变得越来越普遍，基因组优先（genomic-first）方法正越来越多地被用于识别可能患有罕见遗传病的个体。为了准确估计患病率和外显率，这些研究通常利用电子健康档案（EHR）来确认疾病的表现。尽管存在多种在 EHR 中搜索罕见病诊断的策略，但每种策略都有其局限性。我们开发了一种便携式集成工具 DxFit，该工具通过挖掘 EHR 数据（来自计费代码和问题列表表的 ICD 代码及结构化诊断描述），来寻找与特定罕见遗传病一致的诊断。DxFit 结合了四种策略的证据：(1) 在诊断描述和注释中进行基因名称搜索；(2) 将 ICD 转换为 Mondo 罕见病本体以寻找精确和相近的匹配；(3) 词嵌入相似度搜索；(4) Jaccard 相似度匹配。DxFit 对匹配类型进行优先级排序，并为每个参与者-疾病对输出置信度最高的匹配结果。在一个由 350 名已知发育障碍诊断性基因检测结果呈阳性的参与者组成的队列中，使用默认参数时，DxFit 的灵敏度为 88.7%，特异性为 86.2%。将语言评分阈值从 0.8 调整为 0.7 并允许同义匹配后，灵敏度达到 92.7%，特异性为 84.5%。将 EHR 证据划分为基因检测前后的时间窗显示，正如预期的那样，检测后的 DxFit 总体匹配率有所提高，且匹配类型的置信度更高。DxFit 已向公众开放，并具有广泛的自定义选项以支持各种用途。

## Abstract
As population DNA sequencing becomes more common, genomic-first approaches are increasingly used to identify individuals with possible rare genetic disorders. To accurately estimate prevalence and penetrance, these studies often confirm manifestation of the disorder using electronic health records (EHRs). Multiple strategies exist to search the EHR for diagnoses of rare disorders, however, each has its limitations. We have developed a portable, ensemble tool, DxFit, that mines EHR data (ICD codes and structured diagnosis descriptions from billing code and problem list tables) for a diagnosis consistent with a given rare genetic disorder. DxFit combines evidence across four strategies: (1) gene name searches in diagnosis descriptions and notes, (2) ICD conversion to Mondo rare disorder ontology to find exact and nearby matches, (3) word embedding similarity searches, and (4) Jaccard similarity matches. DxFit prioritizes the match type and outputs the most confident match for each participant-disorder pair. On a cohort of 350 participants with a known positive result from diagnostic genetic testing for developmental disorders, DxFit had a sensitivity of 88.7% and specificity of 86.2% using default parameters. Adjusting the linguistic scoring thresholds from 0.8 to 0.7 and allowing for synonymous matches yielded a sensitivity of 92.7% and specificity of 84.5%. Partitioning EHR evidence into windows before and after genetic testing demonstrates, as expected, that the overall DxFit rates increase after testing and the match types become more confident. DxFit is available to the public and has extensive customization options to support a wide range of uses.

---

## 论文详细总结（自动生成）

以下是对论文《DxFit: An ensemble method for identifying EHR diagnoses consistent with a molecular finding》的结构化总结：

### 1. 论文的核心问题与整体含义（研究动机和背景）
随着大规模人群基因组测序的普及，“基因组优先”（Genomic-first）的研究模式日益增多。这种模式要求研究者在发现致病变异后，回溯电子健康记录（EHR）以验证个体的临床表现。然而，从 EHR 中识别罕见遗传病诊断面临巨大挑战：
*   **映射稀疏性**：常用的计费代码（如 ICD）与罕见病本体（如 Mondo）之间缺乏直接对应关系，超过 75% 的 Mondo 术语没有直接对应的 ICD 代码。
*   **映射贪婪性**：一个通用的 ICD 代码可能对应数十个具体的遗传病，导致过度匹配。
*   **语义模糊性**：传统的自然语言处理（NLP）在处理罕见病专有名词、缩写或同义词时表现不佳。
**DxFit** 的开发动机正是为了提供一种自动化、高灵敏度且可定制的集成工具，将 EHR 中的结构化诊断数据与分子发现进行精准匹配。

### 2. 论文提出的方法论
DxFit 采用了一种**集成学习（Ensemble）**的思想，结合了四种互补的匹配策略，并根据置信度进行优先级排序：
*   **核心思想**：通过多维度证据（基因名、本体结构、语义向量、字符重叠）综合判定 EHR 诊断是否与特定遗传病一致。
*   **关键技术细节**：
    1.  **基因符号搜索**：在诊断描述中直接检索致病基因符号（如 *SCN1A*）。
    2.  **ICD-to-Mondo 映射**：利用 Monarch Initiative 的映射表，支持精确匹配及 Mondo 本体中 1-2 级的邻近匹配。为防止过度匹配，对 Mondo 本体进行了**自定义剪枝**（移除“遗传病”等过于宽泛的节点）。
    3.  **词嵌入相似度（Word Embedding）**：使用 `en_core_sci_md` 预训练模型计算诊断描述与疾病名称的语义向量余弦相似度。
    4.  **Jaccard 相似度**：基于字符 n-grams 的重叠度计算，有效捕捉缩写和人名首字母缩写类疾病。
*   **优先级排序**：输出结果按置信度排序：基因名匹配 > 精确 ICD 匹配 > Jaccard 相似度 > 词嵌入相似度 > 1级邻近匹配 > 2级邻近匹配。

### 3. 实验设计
*   **数据集**：
    *   **病例组**：350 名经临床基因检测确诊为发育障碍的患者（共 355 个“个体-疾病”对）。
    *   **对照组**：按 1:10 比例匹配的年龄、性别对照组，共 3500 人，每人被随机分配一个病例组的疾病标签以测试误报率。
*   **Benchmark（基准）**：主要对比了 DxFit 在不同参数配置下的表现，包括默认参数、调整语言阈值（0.8 vs 0.7）以及是否启用同义词匹配。
*   **对比维度**：评估了灵敏度（Sensitivity）、特异性（Specificity），并对比了“仅使用基因名搜索”与“DxFit 集成方法”的效果差异。

### 4. 资源与算力
论文**未明确说明**具体的硬件算力（如 GPU 型号或数量）。由于该工具主要基于预训练的 NLP 模型（ScispaCy）和本体映射表，其运行开销相对较小，重点在于算法逻辑的集成而非大规模深度学习模型的从头训练。

### 5. 实验数量与充分性
实验设计较为充分且具有针对性：
*   **消融与参数实验**：测试了不同相似度阈值对结果的影响。
*   **时间窗分析**：对比了基因检测前、检测中、检测后三个阶段的匹配率，验证了临床诊断随时间演进的规律。
*   **人工审核**：由两名专家对非精确匹配的结果进行了独立的人工复核，以验证 DxFit 判定的“模糊匹配”是否具有临床合理性。
*   **客观性**：通过 1:10 的大规模对照组设计，较好地评估了工具在真实世界数据中的特异性。

### 6. 论文的主要结论与发现
*   **高性能**：在默认参数下，DxFit 的灵敏度为 88.7%，特异性为 86.2%。通过优化参数（阈值降至 0.7 并开启同义词），灵敏度可提升至 **92.7%**。
*   **超越单一方法**：约 40.8% 的病例匹配是通过非基因名搜索的方法（如语义相似度或本体映射）实现的，证明了集成方法的必要性。
*   **诊断演进**：基因检测后，EHR 中的诊断记录变得更加具体，DxFit 的匹配置信度显著提升（54.5% 的病例在检测后匹配等级上升）。
*   **本体剪枝的重要性**：通过剪枝 Mondo 本体中的宽泛节点，有效降低了 2 级邻近匹配带来的噪声。

### 7. 优点
*   **便携性与通用性**：工具不依赖于特定的医疗专科，可广泛应用于各类罕见病研究。
*   **高度可定制**：用户可以自定义停用词列表、调整相似度阈值、更换 NLP 模型或使用不同的疾病词汇表（如 OMIM, Orphanet）。
*   **解决冷启动问题**：通过 Jaccard 相似度解决了 NLP 模型中缺失罕见病专有名词向量的问题。
*   **开源共享**：代码已在 GitHub 公开，便于社区使用。

### 8. 不足与局限
*   **依赖 EHR 记录质量**：如果临床医生未在 ICD 描述或问题列表中记录相关信息（仅记录在非结构化文本中且未提供给工具），DxFit 将无法识别。
*   **2级邻近匹配的噪声**：尽管进行了剪枝，2 级邻近匹配仍是误报的主要来源（占对照组误报的绝大部分）。
*   **语言限制**：目前主要针对英文 EHR 环境开发，迁移至其他语言需重新配置 NLP 模型和本体映射。
*   **偏差风险**：实验队列集中在发育障碍领域，在其他疾病领域（如代谢病或自身免疫病）的表现尚需进一步验证。

（完）
