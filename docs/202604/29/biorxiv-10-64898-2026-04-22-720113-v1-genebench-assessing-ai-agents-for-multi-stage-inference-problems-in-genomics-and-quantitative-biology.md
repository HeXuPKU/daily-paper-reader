---
title: "GeneBench: Assessing AI Agents for Multi-Stage Inference Problems in Genomics and Quantitative Biology"
title_zh: GeneBench：评估 AI 智能体在基因组学和定量生物学中多阶段推理问题的表现
authors: "Li, J., Ho, A."
date: 2026-04-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.22.720113v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 针对遗传学多阶段科学数据分析的AI智能体基准测试
tldr: "GeneBench是一个针对基因组学和定量生物学中多阶段科学数据分析的AI智能体基准测试。它包含103个评估任务，涵盖数据清洗、统计建模和科学决策等真实科研环节。研究发现，即使是目前最先进的模型（如GPT-5.5 Pro）在处理复杂的推理链和错误传播时仍面临巨大挑战，最高准确率仅为33.2%，揭示了AI在处理实际科研推理任务中的局限性。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的生物学基准测试多侧重于知识检索或单一分析步骤，无法评估AI在处理复杂、多阶段的真实科研数据分析任务中的能力。
method: 开发了包含10个领域、103个评估任务的GeneBench，要求AI智能体在极少指导下完成从原始数据处理到得出科学结论的全流程分析。
result: "评估显示GPT-5.5 Pro的最高通过率为33.2%，而Gemini 3.1 Pro仅为11.2%，大多数模型在将诊断信号转化为正确分析决策方面表现不佳。"
conclusion: GeneBench衡量了一种尚不可靠的新兴能力，即AI在复杂科研推理中的决策一致性，为未来生物信息学AI智能体的发展提供了重要参考。
---

## 摘要
我们推出了 GeneBench，这是一个针对遗传学和定量生物学中真实多阶段科学数据分析的 AI 智能体基准测试。现有的生物学基准测试大多衡量知识检索、常规流水线的执行或单个分析步骤。然而，它们未能涵盖占据计算科学家大部分时间的更广泛工作范畴：清洗和标准化检测、表型或临床数据；探索性数据分析；统计模型选择和诊断迭代；以及得出为下游科学或转化决策提供信息的结论。GeneBench 通过针对 10 个领域中具有直接实际相关性的指标的 103 项评估填补了这一空白，其核心以基因组学为中心，并覆盖了其他组学和定量生物学背景。每个问题都包含一个封装的多步骤分析，配有分阶段的数据、定义感兴趣指标但提供极少引导的提示词，以及可验证的答案。解决每个问题需要识别并处理现实中的障碍，如测量误差、选择偏差、混杂因素、质量控制（QC）失败，以及在竞争的模型类别中进行选择。通过广泛的消融研究，我们验证了每个问题都有唯一的合理解答。每个问题都涉及多个相互依赖的决策点；即实质性的推理分叉，其中一个看似合理的错误选择会改变下游分析，导致错误通过推理链传播到最终的评分目标。在初步评估中，主流 GPT 系列在 xhigh 推理设置下的 GPT-5.5 达到了 25.0% 的评估级通过率。在单独报告的 GPT Pro 运行中， GPT-5.5 Pro 达到 33.2%，GPT-5.4 Pro 达到 25.6%，GPT-5.2 Pro 达到 10.8%。即使对于报告的两个最强 Pro-harness 设置，在重复运行中，分别有 60.2% 和 62.1% 的问题通过率仍低于 20%。最强的外部基准模型 Gemini 3.1 Pro 达到了 11.2%。模型通常能完成工作流的大部分，但在“察觉”与“行动”之间表现出一致的差距：它们能识别局部诊断信号，但未能将含义传播到相应的分析决策中，结果选择了错误的估计量，或坚持最初看似合理但错误的分析路径。因此，GeneBench 衡量的是一种新兴但目前仍不可靠的能力。

## Abstract
We introduce GeneBench, a benchmark for AI agents on realistic multi-stage scientific data analysis in genetics and quantitative biology. Existing biology benchmarks mostly measure knowledge retrieval, execution of routine pipelines, or a single analysis step. Yet they do not capture the broader scope of work that occupies much of computational scientists time: cleaning and normalizing assay, phenotype, or clinical data; exploratory data analysis; statistical model selection and diagnostic iteration; and producing a conclusion that informs a downstream scientific or translational decision. GeneBench addresses this gap with 103 evaluations targeting quantities of direct practical relevance across 10 domains, with a genomics-centered core and adjacent coverage in other  omics and quantitative biology settings. Each problem comprises an encapsulated multi-step analysis with staged data, prompts that define a quantity of interest while otherwise providing minimal guidance, and verifiable answers. Solving each problem requires identifying and addressing realistic obstacles such as measurement error, selection bias, confounding, QC failures, and choosing among competing model classes. Through extensive ablation studies, we verify that each problem admits a single defensible answer. Each problem involves multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, such that errors propagate through the inferential chain and into the final graded target. In initial evaluations, the mainline GPT family reaches an eval-level pass rate of 25.0% with GPT-5.5 at the xhigh reasoning setting. In separately reported GPT Pro runs, GPT-5.5 Pro reaches 33.2%, GPT-5.4 Pro reaches 25.6%, and GPT-5.2 Pro reaches 10.8%. Even for the two strongest reported Pro-harness settings, 60.2% and 62.1% of problems, respectively, remain below 20% pass rate over repeated runs. The strongest external baseline, Gemini 3.1 Pro, achieves 11.2%. Models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting: they identify local diagnostic signals but fail to propagate the implication to the corresponding analysis decision, and as a result select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench therefore measures an emerging capability that remains as yet unreliable.



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/720113v1_ufig1.gif" ALT="Figure 1">
View larger version (13K):
org.highwire.dtl.DTLVardef@cb14a7org.highwire.dtl.DTLVardef@b8fe18org.highwire.dtl.DTLVardef@1321065org.highwire.dtl.DTLVardef@1d262c8_HPS_FORMAT_FIGEXP  M_FIG C_FIG

---

## 论文详细总结（自动生成）

这是一份关于论文《GeneBench: Assessing AI Agents for Multi-Stage Inference Problems in Genomics and Quantitative Biology》的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：现有的生物学 AI 基准测试（如 GeneTuring, LAB-Bench）大多侧重于知识检索、执行常规流水线或单一分析步骤，无法衡量 AI 在处理真实科研中**多阶段、迭代式数据分析**的能力。
*   **研究背景**：在基因组学等领域，科学家的主要工作并非简单的代码执行，而是处理带有误差的原始数据、进行质量控制（QC）、选择统计模型、根据诊断结果调整假设，并最终得出影响临床或转化决策的结论。
*   **整体含义**：论文提出了 **GeneBench**，旨在评估 AI 智能体在极少人工引导下，能否独立完成从原始“脏数据”到科学决策的全流程推理。

### 2. 方法论：核心思想与技术细节
*   **核心思想**：通过构建“级联式”（Cascaded）推理任务，模拟真实的科研决策链。每个任务都包含多个相互依赖的**决策点（Decision Points）**，上游的错误会传播至下游，导致最终答案失效。
*   **关键技术细节**：
    *   **任务结构**：包含 103 个评估任务，涵盖 10 个领域。每个任务提供：(1) 最小化提示词（仅定义目标，不提供操作指南）；(2) 模拟的原始数据集（包含测量误差、选择偏差、混杂因素等）；(3) 可验证的定量答案。
    *   **决策点设计**：任务包含 3 到 13 个决策点（中位数为 6）。例如，在 LDL 胆固醇 GWAS 任务中，智能体必须依次完成：表型重建（处理药物掩盖）、选择偏差修正（加权处理）、变异位点 QC（过滤不合格数据）、最后进行关联分析。
    *   **环境配置**：智能体在隔离的 Linux 容器中运行，配备标准科学计算库（NumPy, Pandas, SciPy 等），但不提供专门的生物信息学工具包，迫使模型依赖通用推理和基础算法实现。

### 3. 实验设计
*   **数据集/场景**：涵盖统计遗传学、群体遗传学、功能基因组学、空间转录组学、癌症基因组学、蛋白质组学、临床遗传学等 10 个子领域。
*   **对比方法（Baselines）**：
    *   **GPT 系列**：GPT-5、GPT-5.2、GPT-5.4、GPT-5.5（包含不同推理强度设置：none 到 xhigh）。
    *   **GPT Pro 系列**：专门针对智能体优化的 Pro 版本。
    *   **外部模型**：Gemini 3.1 Pro、Kimi K2.6、Grok 4.20 (thinking)、Qwen 3.6 Plus、GLM 5.1、MiMo V2.5 Pro 等。
*   **评估指标**：二元通过率（Pass Rate），即模型输出的定量结果必须在预设的科学容差范围内。

### 4. 资源与算力
*   **算力说明**：文中**未明确说明**训练这些模型所使用的具体 GPU 型号或数量。
*   **推理成本**：提到了推理时的 Token 消耗。强力模型（如 GPT-5.5 xhigh）平均每个问题消耗约 2.48 万个 Token。作者指出，单次尝试的 API 成本远低于 1 美元，比人类专家（成本数千美元）低 3-4 个数量级。

### 5. 实验数量与充分性
*   **实验规模**：共 103 个问题，每个模型-问题配置平均运行 **28.7 次**（范围 14-60 次），以确保统计显著性。
*   **消融实验**：对每个问题进行了详尽的消融研究，验证了如果跳过任何一个关键决策步骤（如不进行 QC 或不修正偏差），将无法得到正确答案，证明了测试集的严谨性和答案的唯一性。
*   **客观性与公平性**：所有模型均在相同的隔离沙盒环境中测试，使用统一的评分脚本，实验设计较为客观。

### 6. 主要结论与发现
*   **性能阶梯**：GPT-5.5 Pro 表现最强，通过率为 **33.2%**；GPT-5.5 (xhigh) 为 25.0%。外部模型中 Gemini 3.1 Pro 表现最好（11.2%），其余多在 10% 以下。
*   **“察觉-行动”差距（Notice-Act Gap）**：这是核心发现。模型往往能通过 EDA 察觉到数据中的异常（如“我发现数据存在偏差”），但无法将此观察转化为正确的修正行动（如“因此我应该使用逆概率加权”），导致推理链断裂。
*   **推理链长度影响**：性能随决策点数量增加而显著下降。模型在处理 3-4 个决策点的任务时尚可，但在 7 个以上决策点时几乎全部失败。
*   **能力尚不可靠**：即使是最强的模型，仍有约 60% 的问题通过率低于 20%，表明 AI 自动化端到端科学分析的能力仍处于早期阶段。

### 7. 优点与亮点
*   **高度仿真**：不同于以往的“干净”数据集，GeneBench 引入了现实中的“脏数据”特征（如药物干扰、样本选择偏差），极具实战价值。
*   **抗过拟合**：通过构造性模拟数据而非直接使用历史公开数据，降低了模型通过记忆训练数据来“刷分”的风险。
*   **决策点分解**：将复杂的科学分析拆解为可量化的决策路径，为理解 AI 的推理失败提供了细粒度的视角。

### 8. 不足与局限
*   **数据规模限制**：虽然模拟了数据复杂性，但受限于计算环境，数据规模（如样本量）尚未达到真实生物库（如 UK Biobank）的量级。
*   **评分机制单一**：目前采用二元（对/错）评分，无法对完成部分步骤的模型给予“过程性奖励”或部分分数。
*   **应用限制**：任务主要集中在定量分析，尚未涵盖湿实验设计、文献综合评述等更具发散性的科研环节。
*   **时间偏差**：论文标注日期为 2026 年，可能包含对未来模型能力的预测或特定预研背景，需注意其时效性参考。

（完）
