---
title: "Interaction-finder: automated literature-based discovery of biological entity associations with quote-level provenance"
title_zh: "Interaction-finder: 基于文献自动发现带有引用级别溯源的生物学实体关联"
authors: "Chapman, T. E., Lassmann, T."
date: 2026-07-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.07.736901v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用大语言模型自动发现文献中生物实体关联
tldr: 从文献中识别生物实体关联是分子研究的基础，但手动汇编耗时费力。本文提出Interaction-finder，通过LLM引导的迭代搜索自动发现相关文献，从全文提取候选关联并生成带引用出处的排名列表。在60个主题三个领域评估中，召回已知关联数量是单次提示和现成深度研究框架的1.2-4.3倍，所有引用均经原文验证。该工具以交互式HTML报告呈现结果，代码开源。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-736901-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 282, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-736901-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1307, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-736901-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1187, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-07-736901-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1405, \"height\": 810, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-07-736901-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1575, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-07-736901-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1634, \"height\": 497, \"label\": \"Table\"}]"
motivation: 解决缺乏curated数据库时研究人员手动查阅文献识别生物实体关联的痛点，提供自动化、可验证的解决方案。
method: 采用LLM引导的迭代搜索发现文献，从全文提取候选关联并引用原文验证，生成排序列表和交互式HTML报告。
result: "在三个领域60个主题上，召回已知关联数量是基线方法的1.2-4.3倍，未验证候选得分与金标准相似，Recall@20为0.61。"
conclusion: Interaction-finder可高效自动化发现生物实体关联，提供可验证出处，性能优于现有方法，开源促进可复现研究。
---

## 摘要
识别生物学实体之间的相互作用是分子研究的基石，但从文献中整理此类列表既缓慢又繁琐。对于许多研究问题，不存在策划好的数据库，使得研究人员不得不自行查阅相关文献。我们提出了interaction-finder，这是一个自动化此过程的工具：给定主题字符串和用户定义的实体类型，它通过LLM引导的迭代搜索发现相关文献，从全文文章中提取候选关联，并生成排序列表，其中每个关联都有引用自源文本的引文段落作为支持。独立的交互式HTML报告可快速筛选结果。在三个领域（细胞类型-细胞标记物、疾病-基因和配体-受体）的60个主题上评估，interaction-finder回忆的已知关联数量是单次提示和现成的深度研究框架的1.2-4.3倍，所有提取的引文均与源文本验证。为了评估从金标准数据库中未被识别的候选对象，我们使用独立于工具推理的LLM评判器对每个候选对象进行评分。在三个领域中，未验证的候选对象得分与金标准关联相似。我们发现金标准关联在我们的排序候选对象顶部富集，总体recall@20为0.61。Interaction-finder在https://github.com/tecosaur/interaction_finder上以MIT许可证免费提供。

## Abstract
Identifying interactions between biological entities is a cornerstone of molecular research, but assembling such lists from the literature is slow and tedious. For many research questions, no curated database exists, leaving researchers to survey the relevant literature themselves. We present interaction-finder, a tool that automates this process: given a topic string and user-defined entity types, it discovers relevant literature through LLM-guided iterative search, extracts candidate associations from full-text articles, and produces a ranked list where every association is backed by quoted passages verified against the source text. A self-contained interactive HTML report enables rapid triage of the results. Evaluated across 60 topics in three domains (celltype-cellmarker, disease-gene, and ligand-receptor), interaction-finder recalls 1.2-4.3x as many known associations as single-shot prompting and an off-the-shelf deep-research framework, with all extracted quotes verified against source text. To assess candidates unrecognised from the gold-standard databases, we scored each candidate using an independent LLM judge blind to the tool's reasoning. Across the three domains, unverified candidates score similarly to gold-standard associations. We find the gold-standard associations are enriched at the top of our ranked candidates, with an overall recall@20 of 0.61. Interaction-finder is freely available at https://github.com/tecosaur/interaction_finder under an MIT licence.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：研究人员在探索特定生物学实体（如基因、疾病、细胞标记物）之间的关联时，经常面临缺乏策划数据库的困境，必须手动查阅大量文献，速度慢、效率低。现有文献挖掘工具要么需要预组装语料库，要么依赖预定义实体类型，要么缺乏可验证的出处。
- **整体含义**：论文提出一个端到端自动化工具，从自然语言主题描述出发，自动发现相关文献、提取候选关联，并为每个关联提供经过原文验证的引用段落，最终生成交互式HTML报告供专家快速筛选。这填补了从“研究问题”到“带出处的证据列表”之间的自动化缺口。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：通过LLM引导的迭代搜索自动发现文献，利用LLM从全文提取实体和关联，并对每个关联的引用进行原文匹配验证，确保可溯源性。最终输出排序的候选关联列表，每个关联附带验证后的引用和上下文。
- **关键技术细节**：
  - **迭代LLM引导搜索**：不依赖预组语料，而是先从主题出发检索综述文章，使用多种关键词提取算法（YAKE、RAKE、TF-IDF、KeyBERT）提取关键词，经LLM过滤后生成多样化搜索查询。支持PubMed、SearXNG、Perplexica、OpenAI web search等后端。LLM反射器判断搜索覆盖度，共进行最多5轮关键词发现和3轮搜索，可在达到满意覆盖或识别出缺口后提前停止。
  - **引用验证**：LLM提取引用后，通过统一格式化、模糊匹配（最小相似度0.75）、局部词序列校准定位原文位置。不合格匹配被分析失败模式并重试，仍无法匹配的引用被视为幻觉并剔除。匹配率达到98%。
  - **实体与关联提取**：文章分块后，LLM识别指定类型的实体及其支持引用。实体通过多轮合并进行标准化（包括同义词合并）。候选对通过“两个语义块内共现”识别，并由LLM评估关联性。LLM同时给出证据质量评分（1-9）和主题相关性评分（1-5）。
  - **跨文档整合与排序**：跨文档一致支持的关联直接接受，其余（包括矛盾证据）由LLM评判决定接受/拒绝。最终排序默认采用“按支持文档数的衰减和（recency-weighted sum）”，兼顾整体召回和近期关联的优先展示。
  - **交互式报告**：自包含HTML文件，无外部依赖。包含可排序筛选的候选列表、按文档的证据详请、引用在原文中的高亮上下文，以及LLM推理链。

## 3. 实验设计：数据集、场景、对比方法

- **数据集与场景**：
  - 三个领域共60个主题：
    - 细胞类型-细胞标记物（CellMarker 2.0数据库，20个细胞类型主题）
    - 疾病-基因（Human Phenotype Ontology，20个疾病主题）
    - 配体-受体（Ramilowski等人网络，20个配体主题）
  - 每个主题关联的金标准数据集来自第三方手动策划数据库。
- **对比方法**：
  - **单次提示（Single-shot prompting）**：直接问LLM“列出与Y相关的所有X”，依赖模型世界知识。
  - **DeerFlow（Deep Exploration and Efficient Research Flow）**：现成的深度研究框架，可进行迭代检索和综合。
  - 每个基线在每个主题上运行5次，评估鲁棒性。
  - Interaction-finder使用GPT-5-mini（基线使用GPT-5-mini或GPT-4.1-mini，因网站速率限制），但单次提示和interaction-finder使用同一模型。
- **评价指标**：
  - 金标准召回率（gold-standard recovery）：从参考数据集找回的已知关联比例。
  - 金标准分数（gold-standard fraction）：候选列表中有多少匹配金标准。
  - **额外实验**：
    - **跨领域污染测试**：向每个主题注入20篇来自另一领域的文章，检验管道特异性。
    - **独立合理性评分**：使用独立LLM评判器（GPT-5）对金标准、构造负例、未验证候选进行1-9分合理性评分，评估未验证候选的质量。采用混合模型估计真正阳性比例。

## 4. 资源与算力

- 文中未提及具体的GPU型号、数量或训练时长。
- 主要计算资源依赖于商业LLM API（如GPT-5-mini、GPT-5）。作者对比了不同模型成本：处理一个主题，GPT-5-mini约0.74美元，GPT-5约63美元（约85倍差异）。整个60主题评估处理约一万篇文章，总API费用低于300美元。
- 未提及自有计算集群或模型训练过程，全部为推理阶段的API调用。

## 5. 实验数量与充分性

- **实验数量**：主实验在三个领域共60个主题上进行；每个基线（单次提示、DeerFlow）在每个主题运行5次（共5×60×2=600次运行）；跨领域污染测试为每个主题注入20篇其他领域文章（共60×20=1200篇污染文档）；独立合理性评分对每个主题的候选进行（数量按主题而异）。
- **充分性与公平性**：
  - 实验设计比较全面：覆盖三个不同类型的生物学关联域，对比了两种有代表性的基线方法，并进行了多轮运行评估随机性。
  - 鲁棒性分析：对一个代表性主题重复运行5次，召回率标准差5-17%，表明不同主题间差异远大于同一主题随机性。
  - 污染测试检验了管道的特异性；合理性评分通过独立评判器（不同于提取模型）克服了金标准不完整的问题。
  - 作者承认基线使用不同模型（GPT-4.1-mini vs GPT-5-mini）可能引入偏差，并在补充材料中比较了模型效应。
  - 总体实验设计客观、相对公平，但未与更多专门文献挖掘工具（如SPIRES、FuncFetch）直接比较，因为那些工具需要预组语料或固定关系类型，任务设置不同。

## 6. 主要结论与发现

1. **召回性能优越**：Interaction-finder在三个领域召回已知关联的比例分别是：细胞类型-细胞标记物65%、配体-受体48%、疾病-基因26%，均显著高于单次提示（28%、24%、6%）和DeerFlow（22%、41%、5%），提升幅度1.2-4.3倍。
2. **引用验证可靠**：196,000条支持引用中98%成功匹配到原文，其余被剔除，幻觉率低。较小模型（GPT-5-nano）匹配失败率13%，金标准召回率44%，远低于GPT-5-mini（2%匹配失败、78%召回）。
3. **污染抵抗能力强**：注入的跨领域文章只有6.5%产生实体、5%产生共现对、3.3%进入评判阶段；其产生的111个对仅占全部76,316个对的0.15%，且大部分是合理关联（包括一些金标准关联）。
4. **未验证候选质量高**：独立合理性评分显示，未验证候选的得分分布与金标准阳性高度重叠，经混合模型估计，真正阳性比例在78%-98%之间（配体-受体最高），说明大多数非金标准输出仍具生物学意义。
5. **排序有效性**：金标准关联富集在排名顶部，总体recall@20为0.61；采用衰减排序后对2020年后关联的recall@20从0.41提升至0.57。
6. **成本效益**：使用GPT-5-mini即可获得与GPT-5相近的性能，但成本降低85倍，适合大规模应用。

## 7. 优点

- **端到端自动化**：从“主题描述”直接到“带出处证据列表”，完全无需手动构建语料库，极大降低人工负担。
- **可验证的出处**：每一对关联都链接到通过原文验证的引用段落，并包含在上下文中高亮显示，便于专家快速核查，有效对抗LLM幻觉。
- **交互式报告**：自含HTML报告，无需额外依赖，支持搜索、过滤、排序，适合分享和协作。
- **通用性**：不限于预定义的实体类型或关系类别，用户可指定任意实体类型（如环境化学物、表观遗传位点等），可扩展到缺乏策划数据的领域。
- **韧性好**：跨领域污染测试表明管道特异性高，即使检索中包含不相关文章，也能通过实体提取阶段的筛选有效过滤。
- **证据质量透明**：LLM推理链和评分细节保留在报告中，支持理性判断。
- **开源和可复现**：代码开源（MIT协议），检查点可保存，便于重跑和验证。

## 8. 不足与局限

1. **全文访问瓶颈**：仅43%的检索文章能获取全文，其余只能使用摘要，导致提取潜力降低。这是外部限制，未来随开放获取扩大有望缓解。
2. **金标准召回受限**：疾病-基因领域召回仅26%，部分是因为金标准很大（每主题平均82个已知关联），而有限文献无法全面覆盖；另外一些关联源于间接本体关系，文献未直接陈述。因此召回率不适合作为绝对性能指标。
3. **实体合并误差**：过度合并或未合并会导致虚假对或分散证据，影响精度和召回。
4. **LLM随机性**：5-17%的召回标准差虽小于主题间差异，但在高精度需求下仍不可忽视。作者采取了引用验证、确定性实体合并、行为锚点评分等部分约束，但随机性未完全消除。
5. **金标准不完整问题**：金标准分数作为精度类比非常保守，因为有些真实关联未被收录。虽然用混合模型估计了真正阳性比例，但该估计依赖LLM评判器，且评判器与提取模型同族（GPT-5 vs GPT-5-mini），存在潜在偏差。作者补充了GPT-4.1评分结果一致，部分缓解此问题。
6. **未与其他专门文献挖掘系统比较**：如SPIRES、FuncFetch、SciLinker等，因为它们需要预组语料或仅支持单一关系类型，任务设置不一，但缺少这类对比限制了全面性。
7. **成本与模型大小权衡**：虽然推荐使用GPT-5-mini，但对于更差模型（如GPT-5-nano）性能下降明显，用户需注意模型选择。
8. **潜在应用限制**：对于非常狭窄或文献极少的主题，搜到的文章数量可能不够，导致覆盖率低。作者指出配体-受体域中一些配体仅有0-1个已知受体，导致召回率呈双峰分布。

（完）
