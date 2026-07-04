---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: GeneBench-Pro：评估基因组学、定量生物学与转化生物医学中的多阶段统计推理
authors: "Li, J. H., Ho, A. J."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v2.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 用于评估基因组学AI智能体多阶段推理的基准，直接关联智能体与基因组学主题
tldr: "基因基准测试GeneBench推出扩展版GeneBench-Pro，旨在评估AI在基因组学、定量生物学和转化生物医学中的多阶段科学推理能力。该基准包含129个具有实际意义的评估问题，覆盖10个主领域和21个终端子领域，要求AI代理自主完成多步分析并得出正确结论。评测显示，最强模型GPT-5.6 Sol Pro仅达31.5%的通过率，而GPT-5.5和Claude Opus 4.8分别为12.0%和16.0%。模型虽能识别局部诊断信号，但常未能将影响传递至全局分析决策，暴露了长期推理的可靠性缺口。该基准为衡量和提升AI的复杂生物学推理能力提供了关键测试平台。"
source: biorxiv
selection_source: fresh_fetch
motivation: 捕捉计算生命科学家在真实多阶段分析中的推理复杂性，评估AI在科学决策中的自主导航能力。
method: 构建129个多阶段推理问题，涉及10个主领域和21个终端子领域，要求AI自主设计并执行正确分析流程获得结论。
result: "最强模型GPT-5.6 Sol Pro通过率31.5%，GPT-5.5仅12.0%，模型常无法将局部信号转化为全局分析决策。"
conclusion: GeneBench-Pro揭示了AI在长时程生物学推理中的不可靠性，为提升模型科学推理能力提供了重要基准。
---

## 摘要
我们推出GeneBench-Pro，它是GeneBench的扩展与改进版本，涵盖了更广泛领域中的更难问题。GeneBench-Pro是一个基准测试，用于评估AI代理在基因组学、定量生物学和转化生物医学中执行现实多阶段科学分析的能力，旨在捕捉计算生命科学家在需要做出下游科学或转化决策所依赖的结论时所面临的现实问题的复杂性。该基准包含129项评估，针对10个主要领域和21个终端子领域中直接实际相关的量，以基因组学为核心。与GeneBench类似，每个问题为代理提供简要背景、目标估计量以及极少的其他指导；代理随后必须导航多个依赖决策点，即实质性的推断分叉，其中看似合理的错误选择会改变下游分析，以识别并执行正确的分析工作流程，得出正确答案。与GeneBench相比，GeneBench-Pro新增了29个问题，删除了3个，并对剩余100个重叠问题中的54个进行了显著重新设计。129个问题中有82个经过外部领域专家评审，根据评审结果，对目标不够明确的问题进行了提示/数据修改和重新设计。十个经过外部评审的问题公开发布，50个保留问题提供给了Artificial Analysis进行独立的第三方模型基准测试，其余作为内部保留集。在全部129个问题的评估中，GPT-5.6 Sol在最大推理级别达到28.7%的评估级通过率，GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线Claude Opus 4.8达到16.0%。与GeneBench一样，模型通常能完成工作流程的大部分，但在注意到和行动之间存在持续差距：它们能识别局部诊断信号，但未能将影响传播到相应的分析决策。因此，模型经常选择错误的估计量，或坚持初始看似合理但错误的分析路径。因此，GeneBench-Pro衡量了一种新兴的、但尚不可靠的长期生物推理能力。

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.

---

## 论文详细总结（自动生成）

# GeneBench-Pro 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：当前 AI 基准测试（如 SWE-Bench、生物学知识测试等）大多评估孤立的、预设好的任务步骤，而真实科研中，计算生命科学家需要面对**多步、迭代、充满不确定性的分析流程**：从潜在有错误的原始数据出发，进行质量控制（QC）、探索性数据分析（EDA）、选择模型、诊断、修正，最终得出影响科学或转化决策的结论。这种“端到端”的多阶段统计推理能力在现有基准中严重缺失。
- **整体含义**：GeneBench-Pro 旨在衡量 AI 代理**是否能在仅提供最小提示的情况下，自主导航多个依赖决策点（inferential forks），识别并执行正确的分析流程，最终得到目标估计量**。它填补了从“执行单个步骤”到“完成完整科学分析”之间的评估空白，反映了基因学、定量生物学和转化医学中实际面临的瓶颈。

## 2. 方法论：核心思想、关键技术细节、算法流程

- **核心思想**：构建一系列**自洽、可验证的多步推理问题**，每个问题基于**完全模拟的数据生成过程（DGP）**，使得：
  - 目标估计量在代理可见数据中可恢复（而非隐藏参数）；
  - 只有一条唯一可辩护的分析路径能产生正确答案；
  - 错误的、但看似合理的分析路径会产生明显不同的结果（通过消融验证）。
- **关键技术细节**：
  - **问题结构**：每个问题包含一个**最小可行提示**（minimal viable prompt），仅提供实验背景和需估计的目标（estimand），不指定具体工作流；附带多组**阶段性文件**（staged files），模拟来自实验室或临床系统的原始数据。
  - **决策点数量**：每个问题包含 3–13 个实质性推断分叉（中位数 6），每个分叉处一个看似合理的错误选择会改变下游分析结果。
  - **评分机制**：二进制分级——只有当所有目标字段在指定容差内均正确时才算通过；不使用部分学分。
  - **验证流程**：外部领域专家审核（82/129 个问题）、消融实验（确保错误路径与正确答案有数值分离）、多轮前沿模型试运行与 trace 分析（确保无捷径或泄露）。
- **算法流程（文字说明）**：
  1. 从真实世界分析模式出发，明确目标估计量。
  2. 模拟数据，使得正确答案可从代理可见数据中恢复。
  3. 构造最小可行提示（不泄露流程）。
  4. 对每个问题，执行一系列消融：故意在关键决策点做出错误选择，验证最终结果是否明显偏离正确答案。
  5. 通过外部专家评审修正 prompt、数据或 DGP。
  6. 最终在隔离的 Docker 环境中运行代理，限制网络访问，只允许标准科学计算库和基因组学工具（如 numpy, pandas, PLINK 等）。

## 3. 实验设计：数据集 / 场景、基准、对比方法

- **数据集/场景**：共 **129 个问题**，覆盖 **10 个主领域**（统计遗传学、群体进化遗传学、定量遗传学、临床变异解读、药物基因组学、产前/生殖遗传学、癌症体细胞基因组学、微生物宏基因组、法医遗传学、分子及多组学）和 **21 个终端子领域**（见图 2）。所有问题基于模拟数据。
  - 公开发布子集：10 个经过外部评审的问题（含 prompt、数据、评分器、详细报告）。
  - 第三方外部基准子集：50 个保留问题供 Artificial Analysis 使用。
  - 内部保留集：其余 69 个问题。
- **对比方法**：评估了 **60 个模型配置**，包括：
  - GPT 系列：GPT-5.2, 5.4, 5.5, 5.6 Luna/Terra/Sol，及其 GPT Pro（Extended）变体。
  - 非 GPT 模型：Claude Opus 4.8, Gemini 3.1 Pro / 3.5 Flash, Grok 4.3, GLM 5.1/5.2, Kimi K2.6/K2.7 Code, DeepSeek V4 Flash/Pro, MiMo V2.5/V2.5 Pro, Tencent HY3 Preview, MiniMax M2.7/M3, Qwen 3.7 Plus/Max。
- **评估设置**：每个模型-问题对进行 **10 次独立尝试**（Pro 和 Claude Opus 为 5 次），排除容器/工具/格式错误后计算通过率。报告平均通过率及 95% 分层自助法置信区间。

## 4. 资源与算力

- **文中未明确说明所使用的 GPU 型号、数量或训练时长**。评估是在 Docker 容器中运行，环境包含标准科学计算库和基因组学工具。模型推理使用 OpenAI 内部评估框架，但具体的 GPU 资源细节（如 A100/H100 数量、推理时间）未披露。仅提到“计算资源由模型提供方和平台行为决定”，且无统一的墙钟时间预算。
- **注意**：此信息在原文中不完整，我们如实指出未明确说明。

## 5. 实验数量与充分性

- **实验数量**：60 个模型配置 × 129 个问题 × 5–10 次重复，总计数万次独立运行。另包括 82 个问题的外部专家评审，每个问题有完整的消融验证和 trace 分析。
- **充分性**：实验覆盖了多个主流闭源和开源系列，场景多样（10 大领域），且采用了严格的外部评审和消融设计，确保问题唯一可解。然而，由于使用了模拟数据而非真实数据，可能无法完全代表真实世界中的噪声、文档缺失和特异性。此外，二进制评分忽略了部分正确但未完全成功的进展。总体而言，实验设计是系统、严格且公平的。

## 6. 主要结论与发现

- **整体性能较低**：最强模型 GPT-5.6 Sol Pro 在最大推理级别下平均通过率仅为 **31.5%**，常规 GPT-5.6 Sol 为 28.7%，GPT-5.5 为 12.0%，最强非 GPT 模型 Claude Opus 4.8 为 16.0%。基准远未饱和。
- **“注意到-行动”差距**：模型通常能完成大部分工作流，也能识别局部诊断信号，但**不能将这些信号的影响传播到下游分析决策**，导致要么选择错误估计量，要么坚持最初看似合理但最终错误的路径。
- **推理级别提升有帮助**：GPT 系列中，提升推理级别（从 none 到 max）显著提高通过率（如 GPT-5.6 Sol 从 3.7% 升至 28.7%），但仍有大量问题为零通过。
- **领域差异**：不同子领域之间通过率存在差异，但论文未提供细分统计。
- **从人工到自动化的成本效益**：文中估算，一个人类专家完成一个典型 GeneBench-Pro 问题需 10–40 小时，人力成本数千美元；当前 AI 虽不可靠，但部分自动化已具潜在价值。

## 7. 优点：方法或实验设计上的亮点

1. **模拟数据保证可验证性**：使用完全受控的 DGP 可以精确调整难度，确保错误路径与正确答案数值分离，且目标在代理数据中可恢复，避免了真实数据中多解性带来的评分歧义。
2. **多步决策链设计**：每个问题包含 3–13 个实质性推断分叉，真正测量了“端到端”科学推理，而非单一步骤。
3. **外部专家评审**：82 个问题经领域专家审核，提高了问题的科学有效性和目标可识别性。
4. **分层开放策略**：10 个公开问题 + 50 个第三方保留子集 + 内部保留集，兼顾透明度与抗污染性。
5. **广泛模型评估**：覆盖了前沿 GPT 系列和众多开源/闭源模型，结论具有一般性。
6. **清晰的评分原则**：如表 1 所示，明确了七条设计约束（如目标可恢复性、唯一可辩护答案、消融支持等），为高性能科学推理基准提供了方法论模板。

## 8. 不足与局限

1. **模拟数据的局限性**：模拟数据虽然可控，但无法复现真实数据中的所有意外情况（如文档缺失、实验特异性、研究人员的隐性知识等）。这可能使基准低估了真实世界的复杂度。
2. **二进制评分忽略中间进展**：一个代理解决了大部分决策点但最后一步失败被判为零分，丢失了有用的诊断信息。未来可考虑阶段式评分。
3. **领域覆盖有限**：尽管已有 10 个领域，但主要仍围绕基因组学核心，未涵盖例如系统生物学、成像组学等其他定量生物学分支。
4. **计算资源未明确**：未报告 GPU 型号、推理时间、成本等，增加了复现和公平比较的难度。
5. **可能存在的任务泄露风险**：虽然采取隔离环境，但模型可能通过预训练数据接触到类似分析模式（如公开的 PDF 包含问题描述）。
6. **缺少“学会”过程的测试**：基准关注一次运行结果，不测量模型是否能通过自我修正或学习改进。
7. **非随机分层**：公开发布、Artificial Analysis 子集和内部保留集并非随机划分，可能引入选择偏差（论文也指出 AA 子集通过率较低）。

（完）
