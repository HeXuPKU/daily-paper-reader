---
title: "GeneBench: Assessing AI Agents for Multi-Stage Inference Problems in Genomics and Quantitative Biology"
title_zh: GeneBench：评估基因组学与定量生物学中多阶段推理问题的 AI 智能体
authors: "Li, J., Ho, A."
date: 2026-04-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.22.720113v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 评估基因组学和定量生物学中多阶段推理的AI智能体
tldr: GeneBench是一个针对基因组学和定量生物学AI智能体的多阶段推理基准测试。它包含103个评估任务，涵盖数据清洗、统计建模等真实科研流程，旨在填补现有基准在复杂科学数据分析能力评估上的空白。测试显示，即使是顶尖模型在处理具有依赖性的决策链时仍表现欠佳，揭示了AI在科学推理中的局限性。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的生物学基准主要侧重于知识检索或单一分析步骤，无法评估AI在处理复杂、多阶段的真实科学数据分析任务中的能力。
method: 开发了包含10个领域、103个评估任务的GeneBench，通过提供原始数据和最小化引导，要求AI智能体独立完成从数据预处理到得出科学结论的全流程。
result: "评估显示GPT-5.5 Pro的最高通过率为33.2%，而Gemini 3.1 Pro仅为11.2%，模型普遍难以将识别到的局部信号转化为正确的全局分析决策。"
conclusion: GeneBench证明了当前AI智能体在处理多阶段科学推理任务时仍不可靠，特别是在复杂决策链的维护和错误传播控制方面存在显著挑战。
---

## 摘要
我们介绍了 GeneBench，这是一个针对遗传学和定量生物学中真实多阶段科学数据分析的 AI 智能体基准测试。现有的生物学基准测试大多衡量知识检索、常规流水线的执行或单个分析步骤。然而，它们未能涵盖占据计算科学家大部分时间的工作范畴：清洗和标准化检测、表型或临床数据；探索性数据分析；统计模型选择和诊断迭代；以及得出能为下游科学或转化决策提供信息的结论。GeneBench 通过针对 10 个领域中具有直接实际相关性的指标的 103 项评估填补了这一空白，其核心是基因组学，并涵盖了其他组学和定量生物学背景。每个问题都包含一个封装的多步分析，配有分阶段的数据、定义感兴趣指标但提供极少引导的提示词，以及可验证的答案。解决每个问题都需要识别并处理现实中的障碍，如测量误差、选择偏差、混杂因素、质量控制（QC）失败，以及在竞争的模型类别中进行选择。通过广泛的消融研究，我们验证了每个问题都有一个唯一且合理的答案。每个问题都涉及多个相互依赖的决策点；即实质性的推理分叉，其中一个看似合理的错误选择会改变下游分析，导致错误在推理链中传播并影响最终的评分目标。在初步评估中，主流 GPT 系列在 xhigh 推理设置下的 GPT-5.5 达到了 25.0% 的评估级通过率。在单独报告的 GPT Pro 运行中，GPT-5.5 Pro 达到 33.2%，GPT-5.4 Pro 达到 25.6%，GPT-5.2 Pro 达到 10.8%。即使对于报告的两个最强 Pro-harness 设置，在重复运行中，分别有 60.2% 和 62.1% 的问题通过率仍低于 20%。最强的外部基准模型 Gemini 3.1 Pro 达到了 11.2%。模型通常能完成工作流的大部分内容，但在“察觉”与“行动”之间表现出一致的差距：它们能识别局部诊断信号，但未能将该含义传播到相应的分析决策中，结果选择了错误的估计量，或坚持最初看似合理但错误的分析路径。因此，GeneBench 衡量的是一种目前仍不可靠的新兴能力。

## Abstract
We introduce GeneBench, a benchmark for AI agents on realistic multi-stage scientific data analysis in genetics and quantitative biology. Existing biology benchmarks mostly measure knowledge retrieval, execution of routine pipelines, or a single analysis step. Yet they do not capture the broader scope of work that occupies much of computational scientists' time: cleaning and normalizing assay, phenotype, or clinical data; exploratory data analysis; statistical model selection and diagnostic iteration; and producing a conclusion that informs a downstream scientific or translational decision. GeneBench addresses this gap with 103 evaluations targeting quantities of direct practical relevance across 10 domains, with a genomics-centered core and adjacent coverage in other 'omics and quantitative biology settings. Each problem comprises an encapsulated multi-step analysis with staged data, prompts that define a quantity of interest while otherwise providing minimal guidance, and verifiable answers. Solving each problem requires identifying and addressing realistic obstacles such as measurement error, selection bias, confounding, QC failures, and choosing among competing model classes. Through extensive ablation studies, we verify that each problem admits a single defensible answer. Each problem involves multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, such that errors propagate through the inferential chain and into the final graded target. In initial evaluations, the mainline GPT family reaches an eval-level pass rate of 25.0% with GPT-5.5 at the xhigh reasoning setting. In separately reported GPT Pro runs, GPT-5.5 Pro reaches 33.2%, GPT-5.4 Pro reaches 25.6%, and GPT-5.2 Pro reaches 10.8%. Even for the two strongest reported Pro-harness settings, 60.2% and 62.1% of problems, respectively, remain below 20% pass rate over repeated runs. The strongest external baseline, Gemini 3.1 Pro, achieves 11.2%. Models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting: they identify local diagnostic signals but fail to propagate the implication to the corresponding analysis decision, and as a result select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench therefore measures an emerging capability that remains as yet unreliable.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **GeneBench** 的新型基准测试，旨在评估 AI 智能体在基因组学和定量生物学中处理复杂、多阶段科学数据分析任务的能力。

以下是对该论文的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：现有的生物学 AI 基准测试（如 GeneTuring, LAB-Bench）大多侧重于知识检索、执行单一分析步骤或运行标准流水线。然而，真实的科学研究包含大量“灰色地带”：清洗杂乱数据、处理测量误差、选择统计模型、进行诊断迭代以及根据结果做出转化决策。
*   **研究动机**：随着测序成本下降，数据分析而非数据生成已成为生物医学发现的瓶颈。作者认为，评估 AI 是否能像人类科学家一样进行“端到端”的推理（即在面对不确定性和错误数据时做出正确的判断链）至关重要。

### 2. 方法论：核心思想与技术细节
*   **核心思想**：构建“级联式”（Cascaded）推理任务。每个问题都包含多个相互依赖的**决策点（Decision Points）**（中位数为 6 个，范围 3-13 个）。如果 AI 在上游的质量控制（QC）或模型选择上出错，错误会传播到最终结果。
*   **关键技术细节**：
    *   **最小可行提示词（Minimal Viable Prompt）**：仅定义科学目标和输出格式，不提供具体的方法引导或工作流提示。
    *   **构造化模拟数据**：使用模拟而非历史真实数据，以确保：(1) 存在唯一的、可恢复的地面真值（Ground Truth）；(2) 能够精确控制混杂因素、选择偏差和技术噪声；(3) 确保答案不会因模型记忆训练数据而泄露。
    *   **决策点设计**：涵盖数据过滤、偏倚校正、模型比较、诊断信号识别等。例如，在 LDL 胆固醇 GWAS 任务中，AI 必须识别药物掩盖效应、样本选择偏差和基因型 QC 失败。

### 3. 实验设计
*   **数据集/场景**：包含 103 个评估任务，覆盖 10 个领域：统计遗传学、群体遗传学、定量遗传学、功能基因组学、空间转录组学、癌症基因组学、蛋白质组学、临床遗传学、法医遗传学和表观基因组学。
*   **对比方法（Baselines）**：
    *   **GPT 系列**：GPT-5, GPT-5.2, GPT-5.4, GPT-5.5 及其对应的 Pro 版本。
    *   **外部模型**：Gemini 3.1 Pro, Grok 4.20, Kimi K2.6, Qwen 3.6 Plus, GLM 5.1, MiMo V2.5 Pro 等。
*   **评估指标**：二元通过率（Pass Rate）。只有当 AI 提交的所有关键数值指标（如效应值、均值、索引等）都在校准的容差范围内时，才视为通过。

### 4. 资源与算力
*   **算力说明**：论文未明确提及模型训练所需的 GPU 型号或时长（因为这是一篇评估基准论文）。
*   **推理成本**：文中提到，单次 AI 尝试的成本（基于 API 费率）通常在 1 美元以下，比人类专家（估计每题需 10-40 小时，成本数千美元）低 3-4 个数量级。
*   **Token 消耗**：高性能模型在处理每个问题时平均消耗数万个 Token（例如 GPT-5.5 xhigh 约为 24.8k tokens，GLM 5.1 约为 95.5k tokens）。

### 5. 实验数量与充分性
*   **实验规模**：对 103 个问题进行了大量重复实验，每个模型-问题配置平均运行 28.7 次（总计运行数千次），以获得稳定的通过率估计。
*   **消融实验**：对每个问题都进行了详尽的消融研究，验证了如果跳过任何一个关键决策步骤（如不进行偏倚校正或使用错误的 QC 阈值），最终答案将显著偏离真值。
*   **公平性**：所有模型都在相同的 Docker 容器环境中运行，配备标准的 Python 科学计算库（NumPy, Pandas, SciPy 等），且均无法访问互联网。

### 6. 主要结论与发现
*   **性能梯队**：GPT-5.5 Pro 表现最强（通过率 33.2%），其次是 GPT-5.4 Pro (25.6%)。外部模型中 Gemini 3.1 Pro 表现最好（11.2%）。
*   **“察觉-行动”差距（Notice-Act Gap）**：这是论文最重要的发现。模型往往能识别出数据中的异常（如“我注意到存在批次效应”），但无法将其转化为正确的修正行动（如“因此我应该使用加权回归”），导致分析路径最终偏离。
*   **推理链长度的影响**：随着决策点数量增加，所有模型的通过率均显著下降。对于 7 个以上决策点的复杂任务，大多数模型接近 0% 的通过率。
*   **推理努力的作用**：增加模型的推理时长（Reasoning Effort）能显著提升性能，但仍存在大量无法解决的“长尾”难题。

### 7. 优点
*   **高度仿真**：模拟了科学家在实验室或临床中遇到的真实“肮脏”数据，而非清洗好的玩具数据集。
*   **严谨的验证**：通过消融实验确保了问题的唯一解和科学合理性，避免了 AI 通过“走捷径”或猜测得分。
*   **领域广泛**：不仅限于基础遗传学，还扩展到了癌症、法医和空间组学等前沿领域。

### 8. 不足与局限
*   **数据规模限制**：为了保证在沙盒环境中运行，数据规模相对较小，未能完全模拟超大规模生物银行（如 UK Biobank）的计算压力。
*   **二元评分的局限**：目前的评分系统是“全或无”，无法对完成了一半正确步骤的模型给予部分分数（尽管作者表示未来会引入过程奖励模型）。
*   **工具限制**：AI 仅限于使用通用 Python 库，无法使用特定的生物信息学工具（如 PLINK, BWA），这可能限制了某些高度专业化任务的解决。

（完）
