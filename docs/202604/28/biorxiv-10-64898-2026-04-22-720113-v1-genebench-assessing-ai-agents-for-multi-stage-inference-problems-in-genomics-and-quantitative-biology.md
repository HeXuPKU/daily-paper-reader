---
title: "GeneBench: Assessing AI Agents for Multi-Stage Inference Problems in Genomics and Quantitative Biology"
title_zh: GeneBench：评估基因组学与定量生物学中多阶段推理问题的 AI 智能体
authors: "Li, J., Ho, A."
date: 2026-04-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.22.720113v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于遗传学多阶段科学数据分析的AI智能体
tldr: 针对现有生物学基准测试仅侧重知识检索或单一分析步骤的局限，本文提出了 GeneBench，一个专注于基因组学和定量生物学多阶段推理问题的 AI 智能体基准。该基准包含 103 个评估任务，涵盖数据清洗、统计建模及科学决策等真实科研流程。实验显示，即使是目前最先进的模型（如 GPT-5.5 Pro）在处理复杂推理链时仍面临巨大挑战，揭示了 AI 在科学数据分析中“观察到信号但无法正确决策”的局限性。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的生物学基准缺乏对计算科学家日常工作中复杂、多阶段数据分析和推理能力的评估。
method: 开发了包含 10 个领域、103 个评估任务的 GeneBench，要求 AI 智能体在最小引导下处理包含测量误差和偏差的真实科研数据并得出可验证的结论。
result: "最强模型 GPT-5.5 Pro 的通过率仅为 33.2%，且大多数模型在识别出局部诊断信号后，往往无法将其转化为正确的后续分析决策。"
conclusion: GeneBench 衡量了一种新兴但尚不可靠的 AI 能力，证明了当前 AI 在处理具有依赖性的多步骤科学推理任务时仍存在显著短板。
---

## 摘要
我们介绍了 GeneBench，这是一个针对遗传学和定量生物学中真实多阶段科学数据分析的 AI 智能体基准测试。现有的生物学基准测试大多衡量知识检索、常规流水线的执行或单个分析步骤。然而，它们未能涵盖占据计算科学家大部分时间的更广泛工作范畴：清洗和标准化检测、表型或临床数据；探索性数据分析；统计模型选择和诊断迭代；以及得出能为下游科学或转化决策提供信息的结论。GeneBench 通过针对 10 个领域中具有直接实际相关性的指标的 103 项评估填补了这一空白，其核心以基因组学为中心，并涵盖了其他组学和定量生物学背景。每个问题都包含一个封装的多步分析，涉及分阶段的数据、定义感兴趣指标但提供极少指导的提示词，以及可验证的答案。解决每个问题需要识别并处理现实中的障碍，如测量误差、选择偏差、混杂因素、质量控制（QC）失败，以及在竞争模型类别中进行选择。通过广泛的消融研究，我们验证了每个问题都有一个唯一且合理的答案。每个问题涉及多个相互依赖的决策点；即实质性的推理分叉，其中一个看似合理的错误选择会改变下游分析，导致错误通过推理链传播到最终的评分目标中。在初步评估中，主流 GPT 系列在 xhigh 推理设置下的 GPT-5.5 达到了 25.0% 的评估级通过率。在单独报告的 GPT Pro 运行中，GPT-5.5 Pro 达到 33.2%，GPT-5.4 Pro 达到 25.6%，GPT-5.2 Pro 达到 10.8%。即使对于报告中两个最强的 Pro-harness 设置，在重复运行中，分别有 60.2% 和 62.1% 的问题通过率仍低于 20%。最强的外部基准模型 Gemini 3.1 Pro 达到了 11.2%。模型通常能完成工作流的大部分内容，但在“察觉”与“行动”之间表现出一致的差距：它们能识别局部诊断信号，但未能将该含义传播到相应的分析决策中，结果导致选择了错误的估计量，或坚持最初看似合理但错误的分析路径。因此，GeneBench 衡量的是一种目前仍不可靠的新兴能力。

## Abstract
We introduce GeneBench, a benchmark for AI agents on realistic multi-stage scientific data analysis in genetics and quantitative biology. Existing biology benchmarks mostly measure knowledge retrieval, execution of routine pipelines, or a single analysis step. Yet they do not capture the broader scope of work that occupies much of computational scientists time: cleaning and normalizing assay, phenotype, or clinical data; exploratory data analysis; statistical model selection and diagnostic iteration; and producing a conclusion that informs a downstream scientific or translational decision. GeneBench addresses this gap with 103 evaluations targeting quantities of direct practical relevance across 10 domains, with a genomics-centered core and adjacent coverage in other  omics and quantitative biology settings. Each problem comprises an encapsulated multi-step analysis with staged data, prompts that define a quantity of interest while otherwise providing minimal guidance, and verifiable answers. Solving each problem requires identifying and addressing realistic obstacles such as measurement error, selection bias, confounding, QC failures, and choosing among competing model classes. Through extensive ablation studies, we verify that each problem admits a single defensible answer. Each problem involves multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, such that errors propagate through the inferential chain and into the final graded target. In initial evaluations, the mainline GPT family reaches an eval-level pass rate of 25.0% with GPT-5.5 at the xhigh reasoning setting. In separately reported GPT Pro runs, GPT-5.5 Pro reaches 33.2%, GPT-5.4 Pro reaches 25.6%, and GPT-5.2 Pro reaches 10.8%. Even for the two strongest reported Pro-harness settings, 60.2% and 62.1% of problems, respectively, remain below 20% pass rate over repeated runs. The strongest external baseline, Gemini 3.1 Pro, achieves 11.2%. Models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting: they identify local diagnostic signals but fail to propagate the implication to the corresponding analysis decision, and as a result select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench therefore measures an emerging capability that remains as yet unreliable.



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/720113v1_ufig1.gif" ALT="Figure 1">
View larger version (13K):
org.highwire.dtl.DTLVardef@d01278org.highwire.dtl.DTLVardef@6c9b44org.highwire.dtl.DTLVardef@4595c8org.highwire.dtl.DTLVardef@6ca390_HPS_FORMAT_FIGEXP  M_FIG C_FIG

---

## 论文详细总结（自动生成）

这篇论文介绍了 **GeneBench**，这是一个专门为评估 AI 智能体在基因组学和定量生物学中处理复杂、多阶段推理能力而设计的基准测试。

以下是对该论文的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **研究动机**：现有的生物学 AI 基准测试（如 MedQA 或基础生物信息流水线测试）大多侧重于知识检索或单一分析步骤的执行。然而，现实中的科学研究涉及大量“非结构化”的工作：数据清洗、处理测量误差、识别选择偏差、统计模型选择以及根据中间结果调整策略。
*   **核心问题**：当前的 AI 智能体是否具备在缺乏详细指令的情况下，自主完成从原始数据到科学结论的完整推理链条的能力？
*   **整体含义**：GeneBench 旨在衡量 AI 扮演“自主计算科学家”的潜力，特别是在处理具有相互依赖决策点的复杂任务时的可靠性。

### 2. 方法论：核心思想与关键技术细节
*   **核心思想**：构建“封装的多步分析”任务。每个任务不仅是一个编程问题，更是一个科学决策问题。
*   **任务结构**：
    *   **分阶段数据**：提供包含现实噪声（如 QC 失败、混杂因素）的真实或高度模拟的科研数据。
    *   **最小引导提示词**：仅定义最终感兴趣的科学指标，不提供具体的算法步骤。
    *   **推理分叉（Inferential Forks）**：设计多个关键决策点。如果 AI 在早期步骤（如数据清洗）做出看似合理但错误的决策，错误会随推理链传播，导致最终答案错误。
*   **覆盖领域**：涵盖 10 个领域，以基因组学为核心，延伸至蛋白质组学、临床数据分析和定量生物学。
*   **验证机制**：通过广泛的消融研究确保每个问题都有唯一且在科学上可辩护的正确答案。

### 3. 实验设计
*   **数据集/场景**：包含 103 个评估任务，涉及测量误差处理、选择偏差校正、统计模型迭代等。
*   **对比方法（被测模型）**：
    *   **GPT 系列**：GPT-5.5 Pro、GPT-5.4 Pro、GPT-5.2 Pro，以及不同推理设置（如 xhigh）下的版本。
    *   **外部基准**：Gemini 3.1 Pro。
*   **评估指标**：评估级通过率（Eval-level pass rate），即模型在多次尝试中正确完成整个推理链的比例。

### 4. 资源与算力
*   **算力说明**：论文未详细列出训练这些模型所使用的具体 GPU 型号或时长（因为主要评估的是闭源商业模型 API）。
*   **评估成本**：实验涉及对 GPT 和 Gemini 系列模型的大量调用，特别是在“Pro-harness”设置下进行的重复运行，显示了较高的推理算力消耗。

### 5. 实验数量与充分性
*   **实验规模**：103 个精心设计的任务，每个任务进行多次重复实验以排除随机性影响。
*   **充分性**：
    *   **消融实验**：进行了广泛的消融研究以验证问题的唯一解。
    *   **多样性**：覆盖了 10 个不同的生物学子领域，确保了评估的广泛性。
    *   **客观性**：采用可验证的数值或结论作为评分标准，减少了主观评价的偏差。

### 6. 主要结论与发现
*   **性能瓶颈**：即使是最先进的模型（GPT-5.5 Pro），通过率也仅为 **33.2%**，而 Gemini 3.1 Pro 仅为 **11.2%**。
*   **“察觉”与“行动”的脱节**：模型表现出一种普遍的局限性——它们能识别出局部的诊断信号（例如意识到数据存在质量问题），但无法将这一发现转化为正确的后续分析决策（例如仍坚持使用错误的估计量）。
*   **错误传播**：在多阶段推理中，AI 极易在“推理分叉”处选错路径，导致后续步骤全部失效。
*   **不可靠性**：对于超过 60% 的问题，即使是最强的模型，其重复运行的通过率也低于 20%，证明当前 AI 在处理复杂科学推理时仍极不稳定。

### 7. 优点
*   **高度贴近实战**：不同于简单的代码生成，它模拟了科学家处理“脏数据”和复杂统计决策的真实过程。
*   **严谨的推理链设计**：通过“推理分叉”设计，有效区分了“机械执行”与“深度理解”。
*   **填补空白**：为评估 AI 在定量生物学这一专业领域的自主科研能力提供了首个高难度基准。

### 8. 不足与局限
*   **模型覆盖**：主要集中在顶级闭源模型，对开源模型（如 Llama 系列）的评估相对较少。
*   **领域局限**：虽然涵盖了 10 个领域，但生物学博大精深，某些前沿或极度细分的领域可能尚未覆盖。
*   **静态性风险**：作为公开基准，未来可能面临数据污染（Data Contamination）风险，即模型在训练阶段可能接触到类似的任务。

（完）
