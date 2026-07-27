---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: GeneBench-Pro：评估基因组学、定量生物学和转化医学中的多阶段统计推理
authors: "Li, J. H., Shringarpure, S., Wong, E., Ho, A. J."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v4.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 基因组AI智能体多阶段推理基准
tldr: "基因组学、定量生物学与转化医学领域的多阶段统计推理基准GeneBench-Pro被提出，包含129个实际问题，覆盖10个主要领域。模型需自主导航多个依赖决策点完成分析。最强模型GPT-5.6 Sol Pro仅达31.5%通过率，普遍存在识别局部信号但无法传播至行动的问题。该基准衡量了长期生物推理这一新兴但不可靠的能力。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1713, \"height\": 410}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1674, \"height\": 615}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1626, \"height\": 908}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1670, \"height\": 1927}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1297, \"height\": 959}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1701, \"height\": 1563}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1726, \"height\": 1560}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1718, \"height\": 887}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 2378, \"height\": 1205}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 2385, \"height\": 1187}]"
motivation: 现有基准无法反映真实多阶段科学分析的复杂性，GeneBench-Pro通过扩展更难的跨领域问题填补这一空白。
method: 构建129个评估问题，涵盖10个主领域21个亚领域，每个问题提供简要上下文和目标，要求智能体自主决策并执行正确分析流程。
result: "GPT-5.6 Sol Pro达31.5%通过率，GPT-5.5为12.0%，Claude Opus 4.8为16.0%，模型常选择错误估计量或坚持错误路径。"
conclusion: GeneBench-Pro揭示了模型在长期生物推理中仍不可靠，为评估AI在计算生命科学中的分析能力提供了关键基准。
---

## 摘要
我们推出GeneBench-Pro，这是GeneBench的扩展和改进版本，包含跨更广泛领域的更难问题。GeneBench-Pro是一个针对AI代理执行基因组学、定量生物学和转化医学中现实多阶段科学分析的基准测试，旨在捕捉计算生命科学家在需要得出下游科学或转化决策所依赖的结论时所面临的现实问题的复杂性。该基准包含129个评估，针对10个主要领域和21个终端子领域中具有直接实际相关性的指标，以基因组学为核心。与GeneBench类似，每个问题为代理提供简短的背景、目标估计量，以及极少的其他指导；代理随后必须导航多个依赖决策点，即实质性的推断分支，其中看似合理的错误选择会改变下游分析，以识别并执行正确的分析工作流程并得出正确答案。与GeneBench相比，GeneBench-Pro增加了29个新问题，删除了三个问题，并对剩余100个重叠问题中的54个进行了显著重新设计的版本。129个问题中有82个经过外部领域专家评审，其发现导致对目标不够明确的问题进行了提示/数据修改和重新设计。十个经过外部评审的问题已公开发布，50个保留问题提供给Artificial Analysis进行独立的第三方模型基准测试，其余问题作为内部保留。在完整的129个问题套件评估中，GPT-5.6 Sol在最大推理水平上达到28.7%的评估级通过率，而GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线Claude Opus 4.8达到16.0%。与GeneBench一样，模型通常完成工作流程的大部分，但在注意到和行动之间表现出持续差距：识别局部诊断信号，但未能将影响传播到相应的分析决策。因此，模型经常选择错误的估计量，或坚持最初看似合理但错误的分析路径。因此，GeneBench-Pro衡量了一种新兴的长期生物学推理能力，这种能力仍然不可靠。

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.

---

## 论文详细总结（自动生成）

# 论文总结：GeneBench-Pro

## 1. 核心问题与整体含义（研究动机和背景）

- **背景**：现有生物学AI基准（如SWE-Bench、LAB-Bench等）多从已清洗数据集开始，评估单一、明确的分析步骤，缺乏对现实世界中多阶段、迭代性科学推理的覆盖。
- **动机**：基因组学、定量生物学与转化医学中的实际分析流程包含数据质量检查、探索性分析、模型选择、诊断与修正等多个依赖决策点。当前AI在“注意到局部信号但无法将其转化为下游行动”方面存在持续差距，亟需一个能衡量这种多步统计推理能力的基准。
- **GeneBench-Pro** 是GeneBench的扩展与增强版，包含129个更难、更广领域的问题，旨在评估AI代理在真实多阶段科学分析中的端到端执行能力。

## 2. 方法论

### 核心思想
- 每个问题提供“最小可行提示”（minimal viable prompt）：简要实验背景 + 目标估计量（estimand），但不具体指导分析步骤。
- 模型需自主导航多个“依赖决策点”（inferential forks），即一个合理但错误的选择将改变下游分析路径，最终导致错误答案。
- 所有数据基于**完全模拟的数据生成过程（DGP）**构建，确保真实答案可从可见数据中恢复，且评分不受分析师偏好影响。

### 关键技术细节
- **模拟数据**：精确控制效应大小、诊断线索、噪声水平，使正确答案唯一可识别，且合理错误路径给出明显不同答案。
- **设计约束**（表1）：
  - 可恢复目标：评分基于实际可恢复的量而非隐藏生成参数。
  - 唯一可识别答案：数据与提示支持唯一可辩护的答案。
  - 多阶段推理：需经过3~13个决策点（中位数6）。
  - 工作流保真：要求模型发现表示、批次、协变量等问题后调整分析。
- **评分**：二进制通过/不通过，依据预先设定的数值容差，所有字段必须同时满足。
- **外部科学评审**：82个问题经11位领域专家评审，确保真实性、科学合理性和目标可识别性。

### 算法流程（文字说明）
1. 模型获得隔离工作区，包含提示、多张数据表格（类似实际从实验室或EHR系统获得的数据）和标准Python科学栈。
2. 模型必须依次执行：质量控制 → 探索性分析 → 选择统计模型 → 估计 → 诊断 → 必要时修正并重新分析 → 输出最终JSON结果。
3. 评分脚本自动检查所有输出字段是否在容差范围内。

## 3. 实验设计

### 数据集/场景
- 129个问题，覆盖10个主领域（如统计遗传学、群体遗传学、定量遗传学、临床遗传学、药物基因组学、癌症体细胞基因组学、微生物基因组学、法医遗传学等），21个终端子领域。
- 每个问题包含5个左右的数据表格（如筛查名册、控制样本、目标元数据、检测观察值等）。

### Benchmark
- 全129问题套件；另外设置公开子集（10个问题）、Artificial Analysis子集（50个问题）和内部保留子集（69个问题）。

### 对比方法
- **GPT系列**：GPT-5.2、5.4、5.5、5.6 Luna/Terra/Sol，每个有多个推理等级（none, low, medium, high, xhigh, max）。
- **GPT Pro（Extended）**：对应Pro版本。
- **非GPT基线**：Claude Opus 4.8、Gemini 3.1 Pro/3.5 Flash、Grok 4.3、GLM 5.1/5.2、Kimi K2.6/K2.7 Code、DeepSeek V4 Flash/Pro、MiMo V2.5/V2.5 Pro、Qwen 3.7 Plus/Max、MiniMax M2.7/M3、Tencent HY3 Preview等。

## 4. 资源与算力

- 论文**未明确说明**使用的GPU型号、数量或训练时长。仅提及运行环境为Linux Docker容器，包含标准科学Python库（NumPy, pandas, scipy, scikit-learn, statsmodels, lifelines等）以及第三方基因组工具（PLINK 2.0, bedtools, pysam等），无网络访问。
- 未提供训练代价或推理开销的详细数据，图4C仅报告了GPT主系列的平均token使用量（GPT-5.6 Sol max约33.2k tokens）。

## 5. 实验数量与充分性

- 共60个模型配置，每个模型-问题对运行10次独立尝试（Pro和Claude Opus为5次），总计约129×60×10 ≈ 77,400次运行（实际因排除无效尝试略有减少）。
- 实验设计充分且公平：
  - 覆盖广泛领域和难度层次。
  - 外部专家评审增加科学有效性。
  - 通过消融研究验证错误路径的数值分离。
  - 提供置信区间（分层bootstrap）和分布分析（0%、0-10%、10-50%、≥50%通过率）。
- 潜在偏差：公开子集和AA子集的通过率与全套件存在差异（AA子集更困难），可能引入选择偏差。

## 6. 主要结论与发现

- **总体性能低**：最强的GPT-5.6 Sol Pro仅31.5%通过率（全套件），GPT-5.5为12.0%，非GPT最佳Claude Opus 4.8为16.0%。
- **推理等级提升效果显著**：GPT-5.6 Sol从none的3.7%升至max的28.7%。
- **“注意到-行动”差距**：模型普遍能识别局部诊断信号（如批次效应、异常值），但无法将其影响传播到下游模型选择和估计，从而继续执行错误路径。
- **大量未解决问题**：GPT-5.6 Sol仍有45.7%的问题通过率为0%，而GPT-5.2这一比例为77.5%，说明强模型将更多问题从“全失败”推向“部分成功”。
- **决策点数量与性能相关**：问题越复杂（决策点越多），模型越容易失败。

## 7. 优点

- **模拟数据优势**：确保答案可识别、评分可靠，避免了真实数据中多个合理答案导致评分混淆的问题。
- **多阶段推理设计**：真实反映实际科研工作流，捕捉链条式的统计判断。
- **外部评审机制**：82个问题经领域专家审核，大大提高问题的科学合理性和目标可识别性。
- **广泛领域覆盖**：从经典群体遗传学到临床、癌症、微生物、法医等，覆盖当前最重要的应用场景。
- **清晰的评分标准**：二进制通过率避免主观评分，且通过消融证明错误答案的数值显著不同。
- **公开子集与独立第三方基准**：10个问题开源，50个问题交由Artificial Analysis独立测试，确保了可复现性和外部验证可能性。

## 8. 不足与局限

- **模拟数据与现实差距**：构造数据虽能控制难度，但可能无法完全反映真实数据中不可预见的文档缺失、尺度噪声、特殊人为错误等。
- **二进制评分丢失信息**：未能捕获部分正确（如解决了多个决策点但最后一步失败）的有用信息，未来可考虑阶段级评分或部分学分制。
- **公开子集可能被过拟合**：开源10个问题可能被用于调整模型行为，从而影响公平性。
- **计算资源未报告**：缺乏GPU型号、数量、能耗等细节，不利于可重复性和成本估算。
- **领域覆盖不均衡**：部分子领域只有少数问题（如法医遗传学仅2题），可能影响领域特定结论的统计可靠性。
- **模型版本依赖**：基准基于特定日期前的模型版本，后续模型可能由于训练数据污染或更新导致性能变化（已通过内部保留集部分缓解）。

（完）
