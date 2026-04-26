---
title: "GeneBench: Assessing AI Agents for Multi-Stage Inference Problems in Genomics and Quantitative Biology"
title_zh: GeneBench：评估 AI 智能体在基因组学和定量生物学中多阶段推理问题的表现
authors: "Li, J., Ho, A."
date: 2026-04-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.22.720113v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 评估用于遗传学和定量生物学多阶段科学数据分析的AI智能体
tldr: GeneBench是一个针对基因组学和定量生物学中多阶段科学数据分析的AI智能体基准测试。它包含103个评估任务，涵盖数据清洗、统计建模和推断等真实科研环节。研究发现，即使是目前最先进的模型在处理具有依赖性的决策点和复杂干扰因素时仍表现欠佳，揭示了AI在复杂科学推断任务中尚不可靠。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的生物学基准测试多侧重于知识检索或单一分析步骤，无法评估AI在处理真实、多阶段且具有挑战性的科学数据分析任务中的能力。
method: 开发了包含10个领域、103个评估任务的GeneBench，通过提供原始数据和最小化引导，要求AI智能体独立完成从数据预处理到得出科学结论的全流程。
result: "评估显示GPT-5.5 Pro的最高通过率仅为33.2%，且模型普遍存在“能发现问题但无法据此修正决策”的执行鸿沟。"
conclusion: GeneBench证明了当前AI智能体在处理复杂科学推断时仍不可靠，特别是在多步决策链的整合和错误传播控制能力上亟待提升。
---

## 摘要
我们推出了 GeneBench，这是一个针对遗传学和定量生物学中真实多阶段科学数据分析的 AI 智能体基准测试。现有的生物学基准测试大多衡量知识检索、常规流水线执行或单一分析步骤，未能涵盖占据计算科学家大部分时间的工作范畴：清洗和标准化检测、表型或临床数据；探索性数据分析；统计模型选择与诊断迭代；以及得出能为下游科学或转化决策提供依据的结论。GeneBench 通过针对 10 个领域中具有直接实际相关性的指标的 103 项评估填补了这一空白，其核心是基因组学，并涵盖了其他组学和定量生物学背景。每个问题都包含一个封装的多步骤分析，配有分阶段的数据、定义目标指标但提供极少引导的提示词，以及可验证的答案。解决每个问题都需要识别并处理现实中的障碍，如测量误差、选择偏差、混杂因素、质控（QC）失败，以及在竞争模型类别中进行选择。通过广泛的消融研究，我们验证了每个问题都有唯一的、站得住脚的答案。每个问题都涉及多个相互依赖的决策点，即实质性的推理分叉点，其中一个看似合理的错误选择会改变下游分析，导致错误通过推理链传播到最终的评分目标中。在初步评估中，主流 GPT 系列在 xhigh 推理设置下的 GPT-5.5 达到了 25.0% 的评估级通过率。在单独报告的 GPT Pro 运行中，GPT-5.5 Pro 达到 33.2%，GPT-5.4 Pro 达到 25.6%，GPT-5.2 Pro 达到 10.8%。即使对于报告中表现最强的两个 Pro-harness 设置，在重复运行中，分别有 60.2% 和 62.1% 的问题通过率仍低于 20%。最强的外部基准模型 Gemini 3.1 Pro 达到了 11.2%。模型通常能完成工作流的大部分内容，但在“察觉”与“行动”之间表现出一致的差距：它们能识别局部诊断信号，但未能将该含义传递到相应的分析决策中，结果导致选择了错误的估计量，或坚持最初看似合理但错误的分析路径。因此，GeneBench 衡量的是一种新兴的、但目前仍不可靠的能力。

## Abstract
We introduce GeneBench, a benchmark for AI agents on realistic multi-stage scientific data analysis in genetics and quantitative biology. Existing biology benchmarks mostly measure knowledge retrieval, execution of routine pipelines, or a single analysis step. Yet they do not capture the broader scope of work that occupies much of computational scientists' time: cleaning and normalizing assay, phenotype, or clinical data; exploratory data analysis; statistical model selection and diagnostic iteration; and producing a conclusion that informs a downstream scientific or translational decision. GeneBench addresses this gap with 103 evaluations targeting quantities of direct practical relevance across 10 domains, with a genomics-centered core and adjacent coverage in other 'omics and quantitative biology settings. Each problem comprises an encapsulated multi-step analysis with staged data, prompts that define a quantity of interest while otherwise providing minimal guidance, and verifiable answers. Solving each problem requires identifying and addressing realistic obstacles such as measurement error, selection bias, confounding, QC failures, and choosing among competing model classes. Through extensive ablation studies, we verify that each problem admits a single defensible answer. Each problem involves multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, such that errors propagate through the inferential chain and into the final graded target. In initial evaluations, the mainline GPT family reaches an eval-level pass rate of 25.0% with GPT-5.5 at the xhigh reasoning setting. In separately reported GPT Pro runs, GPT-5.5 Pro reaches 33.2%, GPT-5.4 Pro reaches 25.6%, and GPT-5.2 Pro reaches 10.8%. Even for the two strongest reported Pro-harness settings, 60.2% and 62.1% of problems, respectively, remain below 20% pass rate over repeated runs. The strongest external baseline, Gemini 3.1 Pro, achieves 11.2%. Models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting: they identify local diagnostic signals but fail to propagate the implication to the corresponding analysis decision, and as a result select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench therefore measures an emerging capability that remains as yet unreliable.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **GeneBench** 的新型基准测试，旨在评估 AI 智能体在处理基因组学和定量生物学中复杂、多阶段科学数据分析任务的能力。以下是对该论文的深度结构化总结：

### 1. 核心问题与研究动机
*   **研究背景**：现有的生物学 AI 基准测试（如 GeneTuring, LAB-Bench）大多侧重于知识检索、常规流水线执行或单一分析步骤。
*   **核心问题**：真实的科学研究是一个迭代且开放的过程，涉及数据清洗、质控（QC）、统计模型选择、诊断迭代以及最终决策。目前的 AI 评估缺乏对这种“端到端”和“多阶段推理”能力的衡量。
*   **研究动机**：基因组学数据量巨大且分析复杂，已成为生物医学发现的瓶颈。评估 AI 是否能像人类科学家一样处理具有“干扰因素”和“决策分叉”的真实分析任务具有重要的科学和经济价值。

### 2. 方法论：GeneBench 的设计与构建
*   **核心思想**：构建具有“级联结构”的任务。上游的决策（如数据过滤、模型调整）会直接影响下游分析的有效性，从而模拟真实的科研逻辑。
*   **关键技术细节**：
    *   **决策点（Decision Points）**：每个问题包含 3 到 13 个实质性的推理分叉点（中位数为 6）。
    *   **最小化引导提示（Minimal Viable Prompt）**：仅定义科学问题和目标指标，不提供具体的方法指导或工作流提示。
    *   **构造性模拟数据**：使用模拟而非历史真实数据，以确保：(1) 答案是唯一可识别且可验证的；(2) 能够精确控制干扰因素（如测量误差、选择偏差、混杂因素）。
    *   **沙盒环境**：提供标准的科学计算库（NumPy, Pandas, SciPy 等），但不提供专门的生物信息学工具包，要求 AI 必须从底层逻辑实现分析。

### 3. 实验设计
*   **数据集与场景**：涵盖 10 个领域，共 103 个评估任务。
    *   **核心领域**：统计遗传学（如 GWAS 随访、因果映射）、群体遗传学、定量遗传学、功能基因组学。
    *   **相邻领域**：空间转录组学、癌症基因组学、蛋白质组学、临床遗传学、法医遗传学、表观基因组学。
*   **对比方法**：
    *   **GPT 系列**：GPT-5、5.2、5.4、5.5 及其对应的 Pro 版本（不同推理强度设置）。
    *   **外部基准**：Gemini 3.1 Pro、Kimi K2.5/K2.6、Grok 4.20、Qwen 3.6 Plus、GLM 5.1、MiMo V2/V2.5 Pro。

### 4. 资源与算力
*   **算力说明**：论文未明确提及训练这些模型所使用的具体 GPU 型号或数量。
*   **推理成本**：文中提到，单次尝试的 Token 消耗通常在数万级别。按当前 API 费率计算，单次尝试成本远低于 1 美元，比人类专家（每小时 100-200 美元，耗时 10-40 小时）低 3-4 个数量级。

### 5. 实验数量与充分性
*   **实验规模**：对 103 个问题进行了大量重复实验，每个配置平均运行 28.7 次（范围 14-60 次），以确保统计显著性。
*   **消融实验**：对每个问题都进行了广泛的消融研究，验证了如果 AI 在任何一个决策点做出错误选择，最终答案都会显著偏离目标，证明了评分的严谨性。
*   **公平性**：所有模型都在相同的 Docker 容器环境中运行，无法访问互联网，仅依赖内置知识和提供的文件。

### 6. 主要结论与发现
*   **性能天花板**：目前最强的模型 GPT-5.5 Pro 的通过率仅为 **33.2%**，而最强的外部模型 Gemini 3.1 Pro 为 11.2%。
*   **“察觉-行动”鸿沟（Notice-Act Gap）**：这是最重要的发现。模型通常能识别出数据中的异常或诊断信号（例如“注意到存在批次效应”），但往往无法将这一发现转化为正确的修正行动（例如“未能据此调整统计模型”），导致分析路径最终溃败。
*   **推理链长度的影响**：随着决策点数量的增加，通过率显著下降。强模型在短链任务上表现尚可，但在长链任务中极易因错误累积而失败。
*   **能力演进**：从 GPT-5 到 GPT-5.5，随着推理能力的增强，模型在处理复杂科学决策方面的表现有稳步提升，但仍远未达到可靠水平。

### 7. 优点与亮点
*   **高度仿真**：不同于以往的“玩具数据集”，GeneBench 引入了现实中令人头疼的障碍（如 statin 药物对 LDL 胆固醇水平的掩盖效应、样本选择偏差等）。
*   **科学严谨性**：通过消融实验确保了答案的唯一性和路径依赖性，避免了 AI 通过“走捷径”或“猜测”获得正确答案。
*   **领域覆盖广**：不仅限于基础遗传学，还扩展到了癌症、法医和临床等具有实际应用背景的领域。

### 8. 不足与局限
*   **数据规模限制**：为了保证可验证性，使用了模拟数据，可能无法完全捕捉真实世界大规模组学数据中的所有噪声和极端异常。
*   **评分机制单一**：目前采用二元（Pass/Fail）评分，无法对 AI 在中间步骤的表现给予“过程性奖励”或部分分数。
*   **应用限制**：由于不提供专门的生信工具包，该基准测试更多衡量的是 AI 的统计推断和编程能力，而非其调用复杂专业软件的能力。

（完）
