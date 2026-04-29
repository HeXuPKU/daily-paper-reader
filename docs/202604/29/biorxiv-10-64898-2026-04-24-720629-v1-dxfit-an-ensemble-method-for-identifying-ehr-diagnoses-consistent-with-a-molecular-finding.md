---
title: "DxFit: An ensemble method for identifying EHR diagnoses consistent with a molecular finding"
title_zh: DxFit：一种用于识别与分子检测结果一致的电子健康档案诊断的集成方法
authors: "Torene, R. I., Meltz Murphy, K., Brandt, T., Retterer, K."
date: 2026-04-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.24.720629v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 电子健康档案数据与罕见病分子发现的整合
tldr: DxFit是一个集成工具，旨在从电子健康记录（EHR）中识别与分子发现一致的罕见遗传病诊断。随着基因组测序的普及，准确评估疾病流行率和外显率变得至关重要。DxFit结合了基因名称搜索、本体匹配、词嵌入相似度和Jaccard相似度四种策略，能有效挖掘ICD代码和结构化诊断描述。在350名发育障碍患者的测试中表现出高灵敏度和特异性，为基因组优先研究提供了强有力的支持。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的从EHR中搜索罕见病诊断的方法存在局限性，需要更准确、自动化的工具来验证基因发现。
method: 开发了集成四种策略（基因名搜索、Mondo本体转换、词嵌入和Jaccard相似度）的便携式工具DxFit。
result: "在已知发育障碍队列中，DxFit达到了最高92.7%的灵敏度和84.5%的特异性，且在基因检测后匹配置信度显著提升。"
conclusion: DxFit是一个高效、可定制的开源工具，能够显著提高从EHR中识别罕见遗传病诊断的准确性。
---

## 摘要
随着人群 DNA 测序变得越来越普遍，基因组优先的方法正越来越多地被用于识别可能患有罕见遗传病的个体。为了准确评估患病率和外显率，这些研究通常利用电子健康档案（EHR）来确认疾病的表现。目前存在多种在 EHR 中搜索罕见病诊断的策略，但每种策略都有其局限性。我们开发了一种便携式集成工具 DxFit，该工具通过挖掘 EHR 数据（来自计费代码和问题列表表的 ICD 代码及结构化诊断描述），来寻找与特定罕见遗传病一致的诊断。DxFit 结合了四种策略的证据：(1) 在诊断描述和注释中进行基因名称搜索；(2) 将 ICD 转换为 Mondo 罕见病本体，以寻找精确和相近的匹配；(3) 词嵌入相似度搜索；以及 (4) Jaccard 相似度匹配。DxFit 对匹配类型进行优先级排序，并为每个参与者-疾病对输出置信度最高的匹配结果。在一个由 350 名已知发育障碍诊断性基因检测结果呈阳性的参与者组成的队列中，使用默认参数时，DxFit 的灵敏度为 88.7%，特异性为 86.2%。将语言评分阈值从 0.8 调整为 0.7 并允许同义匹配后，灵敏度达到 92.7%，特异性为 84.5%。将 EHR 证据划分为基因检测前后的时间窗显示，正如预期的那样，检测后的 DxFit 总体检出率有所提高，且匹配类型的置信度更高。DxFit 已向公众开放，并具有广泛的自定义选项以支持各种用途。

## Abstract
As population DNA sequencing becomes more common, genomic-first approaches are increasingly used to identify individuals with possible rare genetic disorders. To accurately estimate prevalence and penetrance, these studies often confirm manifestation of the disorder using electronic health records (EHRs). Multiple strategies exist to search the EHR for diagnoses of rare disorders, however, each has its limitations. We have developed a portable, ensemble tool, DxFit, that mines EHR data (ICD codes and structured diagnosis descriptions from billing code and problem list tables) for a diagnosis consistent with a given rare genetic disorder. DxFit combines evidence across four strategies: (1) gene name searches in diagnosis descriptions and notes, (2) ICD conversion to Mondo rare disorder ontology to find exact and nearby matches, (3) word embedding similarity searches, and (4) Jaccard similarity matches. DxFit prioritizes the match type and outputs the most confident match for each participant-disorder pair. On a cohort of 350 participants with a known positive result from diagnostic genetic testing for developmental disorders, DxFit had a sensitivity of 88.7% and specificity of 86.2% using default parameters. Adjusting the linguistic scoring thresholds from 0.8 to 0.7 and allowing for synonymous matches yielded a sensitivity of 92.7% and specificity of 84.5%. Partitioning EHR evidence into windows before and after genetic testing demonstrates, as expected, that the overall DxFit rates increase after testing and the match types become more confident. DxFit is available to the public and has extensive customization options to support a wide range of uses.

---

## 论文详细总结（自动生成）

这是一份关于论文《DxFit: An ensemble method for identifying EHR diagnoses consistent with a molecular finding》的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
随着大规模人群 DNA 测序（基因组优先研究）的普及，研究人员面临一个核心挑战：如何验证基因变异是否在临床上表现为相应的罕见遗传病。电子健康档案（EHR）是验证这些表现的主要来源，但由于罕见病诊断在 EHR 中往往以非结构化文本、不精确的 ICD 计费代码或滞后的记录形式存在，传统的单一搜索策略（如仅搜索 ICD 代码）往往漏诊率高或准确性不足。
**DxFit 的核心目标**是开发一种自动化的集成工具，能够从 EHR 的计费代码和问题列表中，高效、准确地识别出与特定分子发现（基因变异）一致的临床诊断。

### 2. 论文提出的方法论
DxFit 采用了一种**集成学习（Ensemble）**的思想，结合了四种互补的搜索策略来挖掘 EHR 数据：
*   **基因名称搜索（Gene Name Search）：** 在诊断描述和注释中直接检索相关的基因符号或名称。
*   **Mondo 本体匹配（Mondo Ontology Matching）：** 利用 Mondo 罕见病本体，将参与者的 ICD-9/10 代码转换为标准化的罕见病术语，寻找精确匹配或语义相近的诊断。
*   **词嵌入相似度（Word Embedding Similarity）：** 使用预训练的生物医学词向量（如 BioWordVec），计算 EHR 诊断描述与目标疾病术语之间的余弦相似度，捕捉语义相关但措辞不同的记录。
*   **Jaccard 相似度匹配：** 基于字符/单词重叠度进行文本匹配，作为词嵌入的补充。

**算法流程：** DxFit 会对上述四种策略的结果进行优先级排序，并为每个“参与者-疾病”对输出置信度最高的匹配类型和评分。它允许用户自定义阈值，以平衡灵敏度和特异性。

### 3. 实验设计
*   **数据集：** 研究使用了 350 名已知患有发育障碍（DD）且基因检测结果呈阳性的参与者数据。
*   **场景：** 验证 DxFit 是否能从这些患者的真实 EHR 记录中准确找回已知的遗传病诊断。
*   **Benchmark（基准）：** 以临床确诊的基因检测结果作为金标准。
*   **对比实验：** 
    *   对比了不同语言评分阈值（0.8 vs 0.7）的效果。
    *   对比了“基因检测前”与“基因检测后”两个时间窗口的 EHR 数据表现，以观察诊断记录随时间的演变。

### 4. 资源与算力
论文中**未明确说明**具体的 GPU 型号或训练时长。由于 DxFit 主要基于预训练的词嵌入模型（BioWordVec）进行推理和本体映射，而非从头训练大型深度学习模型，因此该工具被描述为“便携式（portable）”，暗示其对计算资源的要求相对较低，可在常规服务器或高性能工作站上运行。

### 5. 实验数量与充分性
*   **实验规模：** 针对 350 名真实患者的完整 EHR 轨迹进行了测试，涵盖了多种不同的发育障碍基因。
*   **充分性：** 实验设计较为充分，不仅提供了整体的灵敏度和特异性数据，还进行了**消融性质的参数调整实验**（如阈值调整、同义词开关）。
*   **客观性：** 通过引入时间窗分析（检测前 vs 检测后），客观地展示了临床诊断行为对工具表现的影响，证明了该工具在诊断不明确的早期阶段也能具有一定的识别能力。

### 6. 主要结论与发现
*   **高性能：** 在默认参数下，DxFit 达到了 88.7% 的灵敏度和 86.2% 的特异性。
*   **优化潜力：** 通过将语言评分阈值降至 0.7 并允许同义词匹配，灵敏度可提升至 **92.7%**（特异性小幅降至 84.5%）。
*   **时间效应：** 基因检测后的 EHR 记录匹配置信度显著更高，反映了分子确诊对临床记录的修正作用。
*   **集成优势：** 结合本体映射和词嵌入的方法显著优于单一的 ICD 代码搜索，能够捕捉到更多描述性的临床记录。

### 7. 优点
*   **多模态集成：** 综合了符号逻辑（本体）和深度学习（词嵌入）的优点，覆盖面广。
*   **高度可定制：** 提供了丰富的参数接口，研究者可以根据具体疾病的流行率调整灵敏度。
*   **开源与便携：** 作为一个开源工具，它解决了罕见病研究中缺乏标准化表型提取工具的痛点。
*   **处理罕见病特异性：** 专门针对 Mondo 等罕见病本体进行了优化，比通用的医学自然语言处理工具更具针对性。

### 8. 不足与局限
*   **依赖 EHR 质量：** 如果医院的 EHR 记录极其简略或存在大量错误输入，DxFit 的效果会受限。
*   **时间滞后性：** 实验显示，在分子检测之前，很多诊断在 EHR 中并未体现，这限制了其在“早期预警”场景下的表现。
*   **验证集局限：** 实验主要集中在发育障碍（DD）领域，虽然具有代表性，但在其他类型的罕见病（如代谢病或成人起病的遗传病）中的表现仍需进一步验证。
*   **黑盒风险：** 词嵌入相似度虽然有效，但有时缺乏可解释性，可能产生误导性的高分匹配。

（完）
