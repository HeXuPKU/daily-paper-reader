---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: GeneBench-Pro：评估基因组学、定量生物学和转化生物医学中的多阶段统计推理
authors: "Li, J. H., Shringarpure, S., Wong, E., Ho, A. J."
date: 2026-07-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v4.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 基因组学和转化生物医学中AI智能体的基准测试
tldr: "在基因组学、定量生物学和转化生物医学中，AI代理需进行多阶段统计推理才能得出科学结论。GeneBench-Pro基准扩展自GeneBench，包含129个难题，覆盖10个主要领域和21个子领域，每个问题仅提供简短上下文和目标，模型必须自主导航多个决策点并执行正确分析流程。评估显示，最先进的GPT-5.6 Sol Pro通过率仅31.5%，GPT-5.5为12.0%，Claude Opus 4.8为16.0%。模型常能识别局部诊断信号，但无法将推理传播到后续决策，导致选择错误路径。该基准衡量了长周期生物推理这一新兴能力，揭示了当前AI在复杂科学推理中的显著局限。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1713, \"height\": 410}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1674, \"height\": 615}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1626, \"height\": 908}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1670, \"height\": 1927}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1297, \"height\": 959}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1701, \"height\": 1563}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1726, \"height\": 1560}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1718, \"height\": 887}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 2378, \"height\": 1205}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-06-29-735386-v4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 2385, \"height\": 1187}]"
motivation: 现有基准缺乏对多步推理和决策链条的评估，GeneBench-Pro旨在测试AI在基因组学等领域的真实多阶段统计推理能力。
method: 构建129个难题，覆盖10个领域，每道题提供简短上下文与目标，要求模型自主导航多个推理分支并执行正确分析工作流。
result: "GPT-5.6 Sol Pro通过率31.5%，GPT-5.5为12.0%，Claude Opus 4.8为16.0%；模型常识别局部信号但无法全局推理。"
conclusion: GeneBench-Pro揭示了当前AI在长周期生物推理中不可靠，凸显从注意到行动的差距，是衡量该新兴能力的重要基准。
---

## 摘要
我们推出了GeneBench-Pro，这是GeneBench的扩展和改进版本，包含跨更广泛领域的更难问题。GeneBench-Pro是一个基准测试，用于评估AI agents在执行基因组学、定量生物学和转化生物医学中现实多阶段科学分析的能力，旨在捕捉计算生命科学家在需要产生结论（下游科学或转化决策依赖于该结论）时所面临的现实世界问题的复杂性。该基准包含129个评估问题，针对10个主要领域和21个终端子领域中直接实际相关的量，以基因组学为核心。与GeneBench类似，每个问题为agent提供简短的上下文、目标估计量以及极少指导；agent必须导航多个依赖决策点（即实质性的推断分叉，其中看似合理的错误选择会改变下游分析），以识别并执行正确的分析工作流，得出正确答案。与GeneBench相比，GeneBench-Pro新增了29个问题，删除了3个，并对剩余100个重叠问题中的54个进行了显著重新设计。129个问题中有82个由外部领域专家审查，其发现导致了对那些目标不够明确的问题的提示/数据修改和重新设计。10个经外部审查的问题公开发布，50个保留问题提供给Artificial Analysis进行独立第三方模型基准测试，其余作为内部保留。在对全部129个问题集的评估中，GPT-5.6 Sol在最大推理级别达到28.7%的评估级通过率，而GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线Claude Opus 4.8达到16.0%。与GeneBench一样，模型通常能完成工作流的实质部分，但在注意与行动之间存在一致差距：识别局部诊断信号但未能将影响传播到相应的分析决策。因此，模型常选择错误的估计量或坚持最初看似合理但最终错误的分析路径。因此，GeneBench-Pro衡量了一项新兴的长周期生物推理能力，该能力仍然不可靠。

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有生物学AI基准大多从精心整理的静态数据集出发，评估模型执行单一、明确定义的分析步骤的能力（如预测蛋白质结构或基因表达）。然而，现实世界中计算生命科学家面临的核心瓶颈是“多阶段统计推理”——从含有潜在错误的原始数据（如实验室测定、电子健康记录）出发，自主进行质量控制、探索性分析、模型选择、诊断、迭代修正，最终得出可影响下游科学或转化决策的结论。这种“端到端”分析尚未被充分评测。
- **背景**：尽管AI在软件工程、数学推理等领域取得长足进步，但基因组学和定量生物学中的多步、依条件而变的推理仍缺乏可靠基准。GeneBench 2026首次尝试填补这一空白，而GeneBench-Pro是其改进版。
- **整体含义**：GeneBench-Pro衡量的是AI在**长周期生物推理**中的新兴能力——能否在多个逻辑依赖的决策分岔中做出正确选择，并最终得到可复现、决策相关的定量结果。它揭示了当前最前沿模型仍然普遍存在“注意到但无法行动”的致命缺陷。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：构建129个自含式、多阶段、可评分的科学分析问题，每个问题提供一个极简提示（minimum viable prompt）和一组模拟的“脏数据”，模型必须自主推断并执行正确的分析流程，最终给出一个数值答案。评分基于该答案与可恢复的“真实目标”的接近程度。
- **关键技术细节**：
  - **全模拟数据生成**（fully simulated problems）：每个问题基于已知的因果数据生成过程（DGP）构造，使得可以从agent可见数据中唯一恢复出正确目标（例如，正确方法的最大似然估计值，而非隐藏的参数值）。这保证了评分无歧义。
  - **多决策分岔**：每个问题包含3-13个“实质推断分岔”（substantive inferential forks），即一个看似合理的错误选择会导致下游分析定性偏离正确路径。通过消融实验证明错误答案与正确答案之间存在清晰数值分离。
  - **外部科学审查**：82个问题由11位领域专家（研究生、博士后、产业科学家、教授）审查，评估目标的科学性、可识别性、方法实现和陈述合理性。审查发现的问题（如估计量未明确定义、方法实现错误、信息不充分）被逐一修正，甚至重构或淘汰问题。
  - **分级验证流程**：问题草案先由内部模型反复试跑，检查提示-评分器匹配、无意外捷径；再由外部专家审查；最后再次通过agent pilot确认。
- **算法流程示意**（非公式，流程文字说明）：
  1. 用户（agent）获得一个隔离的工作空间，内含：极简提示（定义科学问题、目标估计量）、多张数据表格（如样本表、质控表、测定表）、标准科学计算库（numpy, pandas, scipy, statsmodels, lifelines, PLINK等）。
  2. Agent必须自主探索数据，识别数据质量问题（如批次效应、缺失值、拷贝数模拟、杂合子相位问题），做出QC阈值决策，选择合适统计模型/估计量，拟合模型并诊断残差/异常值，必要时回溯修改前序决策。
  3. 最终输出一个JSON对象，包含所有指定字段和自由文本推理。
  4. 评分器根据预设容忍度比较输出与已知正确值，二进制判定通过/失败。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **基准构成**：GeneBench-Pro包含129个问题，覆盖10个主要领域：统计遗传学、群体遗传学、数量遗传学、临床变异解释、药物基因组学、产前与生殖遗传学、癌症体细胞基因组学、微生物与宏基因组学、法医遗传学、以及分子和组学层（调节QTL、转录组/表观基因组、空间/染色质、功能基因组学、蛋白质组学）。每个问题针对一个实际决策相关的目标量（如残余携带风险、遗传力、因果效应、治疗效果等）。
- **评估数据**：所有数据均为模拟生成，但力求模拟真实实验室或临床系统的输出形式（如具有批次标记、质控样本、缺失值、系统性偏差等）。不使用真实历史数据集。
- **对比方法**：
  - **GPT系列**：GPT-5.2, GPT-5.4, GPT-5.5, GPT-5.6 Luna/Terra/Sol，每个模型测试多个推理级别（none/low/medium/high/xhigh/max）。还有对应的GPT Pro (Extended)版本（5-10倍计算量）。
  - **非GPT模型**：Claude Opus 4.8（多种推理级别）、Gemini 3.1 Pro / 3.5 Flash、Grok 4.3、GLM 5.1/5.2、Kimi K2.6/K2.7 Code、DeepSeek V4 Flash/Pro、MiMo V2.5 Pro、Tencent HY3 Preview、MiniMax M2.7/M3、Qwen 3.7 Plus/Max。共计60个模型配置。
- **实验设置**：每个模型-问题对执行10次独立尝试（标准评估）或5次（Pro/Claude Opus）。排除容器、工具、响应格式错误的尝试。主要指标为未加权逐问题通过率。

### 4. 资源与算力：如果文中有提到，请总结使用了多少算力。若未明确说明，也请指出这一点

- **明确说明**：论文未提及训练模型所需的GPU型号、数量或训练时长。评估环境描述为“Linux环境，Docker容器，配备Python和R科学计算库”，没有提供硬件细节（如GPU类型、显存、节点数）。
- **开放性**：由于该基准主要是评估（inference）而非训练，文中未讨论评估所消耗的计算资源时间或成本。唯一隐含的信息是：模型推理次数=60个配置×129个问题×5-10次运行≈数万次调用，但具体资源未量化。

### 5. 实验数量与充分性：大概做了多少组实验、是否充分、客观、公平

- **实验数量**：60个模型配置，129个问题，总计约(60×129×5-10)次独立运行。每个问题运行次数足够（标准10次，Pro/Claude 5次），可以计算有意义的通过率和置信区间。
- **充分性**：实验设计比较充分，覆盖了主流前沿模型的多版本和推理级别设置；包括了模型间的比较（GPT vs 非GPT）、模型内推理级别的影响（none到max）、以及不同评估集（全部129题、公开发布10题、AA保留50题、内部保留69题）的细分报告。
- **客观性**：使用二进制评分，标准严格（只有所有字段都满足容忍度才算通过）。通过分层bootstrap计算95%置信区间，考虑问题间和运行间变异。外部科学审查进一步减少了设计偏差。
- **公平性**：所有模型在同一评估平台（Docker容器，无网络，预装标准库）上运行，提示和文件完全相同。Pro版本的更多计算量单独报告。非GPT模型按照各自推荐或合理的推理级别设置（如Claude Opus 4.8测试了low/medium/high/xhigh/max，论文在结果中报告最高通过率版本）。
- **潜在不足**：仅评估了“一次性通过率”，没有评估部分进展；没有测试不同提示变体的鲁棒性；模型版本可能已经过时（论文发布于2026年7月）。

### 6. 论文的主要结论与发现

- **性能现状**：最强模型GPT-5.6 Sol Pro在最大推理下通过率仅为31.5%；GPT-5.6 Sol为28.7%；Claude Opus 4.8为16.0%；大多数非GPT模型低于10%。即使是最先进系统，仍有约70%的问题无法正确解决。
- **关键失败模式**：模型通常能“注意到”问题中的诊断线索（如批次效应、异常值、基因型-表型不一致），但无法将其含义传播到下游分析决策。它们经常坚持使用错误的方法或估计量，无法根据信号调整分析路径。论文称之为“注意-行动差距”（notice-act gap）。
- **规模化趋势**：更强的模型（GPT-5.6 Sol vs GPT-5.5）显著提高了通过率，但主要进步在于更有效地将局部诊断转化为全局方法改变，而非仅仅识别信号的能力。
- **推理级别影响**：增加推理级别（从none到max）大幅提升GPT家族模型的通过率（GPT-5.6 Sol从3.7%升至28.7%），表明“慢思考”对该类任务至关重要。
- **基准饱和度**：30.2%的问题在最强模型行中达到50%以上通过率，但45.7%的问题仍为0%通过率，表明该基准仍极具挑战性。

### 7. 优点：方法或实验设计上的亮点

- **全模拟确保可评分性**：通过模拟数据，每个问题的“正确答案”是唯一可恢复的，避免了真实数据多解或模糊导致的评分困难。这是GeneBench系列最突出的设计优势。
- **多阶段决策分岔设计**：问题强制模型在多个依赖决策点做出正确选择，而非单一步骤，真实反映了实际科研中的“花园分叉小径”。
- **严格的验证与外部审查**：82个问题经过11位领域专家审查，修正了模糊估计量、方法实现错误、信息不充分等问题，增强了基准的科学可信度。
- **分层公开与防污染**：采用三级发布（10题公开、50题给Artificial Analysis、69题内部保留），降低了benchmark污染风险，同时允许第三方独立评估。
- **清晰记录设计约束**：表1总结了7条设计原则（如可恢复目标、唯一可识别答案、最小可行提示、多阶段推理、消融支持等），提高了基准设计的透明度和可复现性。
- **定性分析“注意-行动”差距**：通过手动检查模型推理摘录，揭示了失败的具体机制，不仅给出数字排名，还提供理解模型行为方向的洞察。

### 8. 不足与局限

- **模拟数据与真实世界的差距**：论文承认虽然模拟数据可以控制难度和唯一性，但无法复现真实研究中的文档缺口、数据规模、不可预测的实验室特异性偏差。因此GeneBench-Pro的分数可能高估或低估模型在真实世界中的能力。
- **二进制评分丢失信息**：只记录全对/全错，无法反映部分正确（如解决了前几个决策分岔但最后一步出错）。论文提及未来版本可增加阶段级或rubric评分。
- **模型版本时效性**：论文基于2026年上半年版本的模型（GPT-5.6, Claude Opus 4.8等），随着模型快速迭代，具体数字可能过时。但基准本身作为“尺子”仍有价值。
- **基准难度分布不均匀**：许多问题通过率极低（<1%），可能只测量了极少数能力或者存在隐含的难题设计缺陷（尽管已通过审查）。
- **缺乏对提示措辞的敏感性分析**：同题多个不同措辞的提示未测试，可能影响模型表现。
- **计算资源未报告**：除了Pro版本比标准版使用更多计算外，没有给出每次评估的具体算力消耗，使得他人难以复现或评估成本。
- **外部审查的潜在偏见**：虽然审查增强了科学性，但评审者可能引入个人偏好，且仅84个候选问题被审查，并非全部129题。不过主要影响已修正。

（完）
