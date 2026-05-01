---
title: "GeneBench: Assessing AI Agents for Multi-Stage Inference Problems in Genomics and Quantitative Biology"
title_zh: GeneBench：评估人工智能代理在基因组学与定量生物学中多阶段推理问题的表现
authors: "Li, J., Ho, A."
date: 2026-04-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.22.720113v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 基因组学多阶段数据分析AI智能体基准
tldr: GeneBench是一个针对基因组学和定量生物学AI智能体的多阶段推理基准测试。它涵盖了从数据清洗、探索性分析到统计建模的完整科研流程，包含10个领域的103个评估任务。研究发现，尽管现有大模型在部分环节表现尚可，但在处理复杂推断链和纠正分析路径方面仍存在显著局限，为评估AI在真实科研场景中的可靠性提供了重要工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的生物学基准测试多侧重于知识检索或单一分析步骤，无法评估AI在处理复杂、多阶段的真实科研数据分析任务中的能力。
method: 开发了包含103个评估任务的GeneBench，通过提供分阶段数据和最小化引导的提示词，要求AI智能体在存在测量误差和偏差的现实场景中完成多步推断并得出可验证的答案。
result: "性能最强的GPT-5.5 Pro在评估中的通过率仅为33.2%，而Gemini 3.1 Pro为11.2%，且大多数模型在将诊断信号转化为正确分析决策方面表现不佳。"
conclusion: GeneBench揭示了当前AI智能体在复杂科学推理中存在“观察到信号但无法据此行动”的可靠性缺口，表明AI在自动化科学发现方面仍处于不成熟阶段。
---

## 摘要
我们介绍了 GeneBench，这是一个针对遗传学和定量生物学中真实多阶段科学数据分析的人工智能代理基准测试。现有的生物学基准测试大多衡量知识检索、常规流程执行或单个分析步骤。然而，它们未能涵盖占据计算科学家大部分时间的更广泛工作范畴：清洗和标准化检测、表型或临床数据；探索性数据分析；统计模型选择与诊断迭代；以及得出能够为下游科学或转化决策提供信息的结论。GeneBench 通过针对 10 个领域中具有直接实际相关性的指标的 103 项评估填补了这一空白，其核心是基因组学，并涵盖了其他组学和定量生物学背景。每个问题都包含一个封装的多步骤分析，配有分阶段的数据、定义感兴趣指标但提供极少引导的提示词，以及可验证的答案。解决每个问题都需要识别并应对现实中的障碍，如测量误差、选择偏差、混杂因素、质量控制（QC）失败，以及在竞争模型类别中进行选择。通过广泛的消融研究，我们验证了每个问题都有一个唯一且合理的答案。每个问题都涉及多个相互依赖的决策点；即实质性的推理分叉点，其中一个看似合理的错误选择会改变下游分析，导致错误通过推理链传播到最终的评分目标中。在初步评估中，主流 GPT 系列在 xhigh 推理设置下的 GPT-5.5 达到了 25.0% 的评估级通过率。在单独报告的 GPT Pro 运行中，GPT-5.5 Pro 达到 33.2%，GPT-5.4 Pro 达到 25.6%，GPT-5.2 Pro 达到 10.8%。即使对于报告中表现最强的两个 Pro-harness 设置，在重复运行中，分别有 60.2% 和 62.1% 的问题通过率仍低于 20%。最强的外部基准模型 Gemini 3.1 Pro 达到了 11.2%。模型通常能完成工作流的大部分内容，但在“察觉”与“行动”之间表现出一致的差距：它们能识别局部诊断信号，但未能将该含义传播到相应的分析决策中，结果导致选择了错误的估计量，或坚持最初看似合理但错误的分析路径。因此，GeneBench 衡量的是一种新兴的、但目前仍不可靠的能力。

## Abstract
We introduce GeneBench, a benchmark for AI agents on realistic multi-stage scientific data analysis in genetics and quantitative biology. Existing biology benchmarks mostly measure knowledge retrieval, execution of routine pipelines, or a single analysis step. Yet they do not capture the broader scope of work that occupies much of computational scientists time: cleaning and normalizing assay, phenotype, or clinical data; exploratory data analysis; statistical model selection and diagnostic iteration; and producing a conclusion that informs a downstream scientific or translational decision. GeneBench addresses this gap with 103 evaluations targeting quantities of direct practical relevance across 10 domains, with a genomics-centered core and adjacent coverage in other  omics and quantitative biology settings. Each problem comprises an encapsulated multi-step analysis with staged data, prompts that define a quantity of interest while otherwise providing minimal guidance, and verifiable answers. Solving each problem requires identifying and addressing realistic obstacles such as measurement error, selection bias, confounding, QC failures, and choosing among competing model classes. Through extensive ablation studies, we verify that each problem admits a single defensible answer. Each problem involves multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, such that errors propagate through the inferential chain and into the final graded target. In initial evaluations, the mainline GPT family reaches an eval-level pass rate of 25.0% with GPT-5.5 at the xhigh reasoning setting. In separately reported GPT Pro runs, GPT-5.5 Pro reaches 33.2%, GPT-5.4 Pro reaches 25.6%, and GPT-5.2 Pro reaches 10.8%. Even for the two strongest reported Pro-harness settings, 60.2% and 62.1% of problems, respectively, remain below 20% pass rate over repeated runs. The strongest external baseline, Gemini 3.1 Pro, achieves 11.2%. Models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting: they identify local diagnostic signals but fail to propagate the implication to the corresponding analysis decision, and as a result select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench therefore measures an emerging capability that remains as yet unreliable.



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/720113v1_ufig1.gif" ALT="Figure 1">
View larger version (13K):
org.highwire.dtl.DTLVardef@e93df8org.highwire.dtl.DTLVardef@e375a9org.highwire.dtl.DTLVardef@141c352org.highwire.dtl.DTLVardef@7e4f9a_HPS_FORMAT_FIGEXP  M_FIG C_FIG

---

## 论文详细总结（自动生成）

以下是对论文《GeneBench: Assessing AI Agents for Multi-Stage Inference Problems in Genomics and Quantitative Biology》的深度结构化总结：

### 1. 核心问题与研究背景
*   **研究动机**：尽管 AI 在软件工程和基础科学领域取得了显著进展，但现有的生物学基准测试（如 GeneTuring, LAB-Bench）多侧重于知识检索或单一分析步骤。
*   **核心问题**：真实世界的科学研究是一个**多阶段、迭代且充满歧义**的过程，包括数据清洗、质量控制（QC）、统计模型选择、诊断迭代以及得出转化决策。目前的 AI 评估缺乏对这种“端到端”复杂推断能力的衡量。
*   **背景**：随着测序成本下降，基因组学的瓶颈已从数据生成转向下游的计算分析。人类遗传学证据已成为药物研发的关键，因此评估 AI 自动化此类分析的能力具有极高的科学和经济价值。

### 2. 方法论：GeneBench 的核心思想与设计
*   **核心思想**：构建一个包含 **103 个评估任务** 的基准测试，模拟科学家从原始、有误差的数据到得出结论的完整工作流。
*   **关键技术细节**：
    *   **级联决策点（Cascaded Decision Points）**：每个问题包含 3 到 13 个相互依赖的决策点（中位数 6 个）。上游的错误选择（如错误的 QC 阈值）会传播并导致最终答案错误。
    *   **最小可行提示（Minimal Viable Prompt）**：仅提供科学问题和目标估计量，不提供具体的方法引导，强迫 AI 独立进行科学判断。
    *   **构造性模拟（Constructive Simulation）**：使用模拟数据而非历史真实数据，以确保：(1) 答案是唯一可识别的；(2) 能够精确控制混杂因素、测量误差和偏差；(3) 避免模型通过记忆训练数据获胜。
    *   **阈值鲁棒性**：设计确保合理的分析选择（如微小的 QC 阈值差异）不会改变最终评分结果，从而专注于评估科学推理而非运气。

### 3. 实验设计
*   **覆盖领域**：涵盖 10 个领域，以遗传学为核心（群体遗传学、统计遗传学、功能基因组学等），并扩展至癌症基因组学、蛋白质组学、临床遗传学和空间转录组学。
*   **对比方法**：
    *   **GPT 系列**：GPT-5, 5.2, 5.4, 5.5（包括 mainline 和 Pro 版本，涵盖不同推理强度设置）。
    *   **外部基准**：Gemini 3.1 Pro, Kimi K2.6, Grok 4.20, Qwen 3.6 Plus, GLM 5.1, MiMo V2.5 Pro 等。
*   **评估指标**：二元通过率（Pass Rate），即模型给出的数值估计必须在预设的容差范围内。

### 4. 资源与算力
*   **算力说明**：论文未提及模型训练所需的具体 GPU 数量或时长，因为这是一篇评估（Evaluation）论文。
*   **推理成本**：文中提到单次尝试的 Token 消耗在数万级别。例如，GLM 5.1 平均消耗 95.5k tokens，GPT-5.5 (xhigh) 平均消耗 24.8k tokens。
*   **经济性对比**：人类专家完成一个任务约需 10-40 小时（成本数千美元），而 AI 尝试成本不到 1 美元，显示了自动化分析的巨大潜在价值。

### 5. 实验数量与充分性
*   **实验规模**：共 103 个问题，每个模型配置平均进行 **28.7 次重复实验**（范围 14-60 次），以确保统计显著性。
*   **消融实验**：对每个问题都进行了详尽的消融研究（如附录中的 LDL GWAS 案例），验证了如果跳过任何一个关键步骤（如不进行偏倚校正或错误的 QC），模型将无法得出正确答案。
*   **客观性**：通过独立审查科学有效性和目标可识别性，确保评估的是推理能力而非对提示词的敏感度。

### 6. 主要结论与发现
*   **性能天花板**：目前最强的模型 **GPT-5.5 Pro 仅达到 33.2% 的通过率**，外部最强模型 Gemini 3.1 Pro 为 11.2%。
*   **“察觉-行动”差距（Notice-Act Gap）**：这是论文最重要的发现。模型通常能识别出数据中的异常信号（如“存在批次效应”），但无法将其转化为正确的修正行动（如“应用特定的校正模型”），导致分析路径最终偏离。
*   **推理链长度相关性**：随着决策点数量增加，通过率显著下降。强模型在短链任务上表现良好，但在长链任务中容易崩溃。
*   **推理强度的作用**：增加推理努力（Reasoning Effort）能显著提升 GPT 系列的表现，但仍存在大量（约 60%）任务处于“无法解决”的尾部。

### 7. 优点
*   **高度仿真**：不同于以往的玩具数据集，GeneBench 引入了测量误差、选择偏差和混杂因素等真实科研障碍。
*   **结构化评估**：通过决策点分解，精准定位了 AI 在科学推理中的薄弱环节。
*   **严谨的验证**：通过构造性模拟和消融研究，确保了评分的客观性和唯一性。

### 8. 不足与局限
*   **数据规模限制**：虽然模拟了复杂性，但数据规模（样本量和特征数）仍小于真实的生物库级别数据。
*   **评分机制单一**：目前采用二元（对/错）评分，无法对完成部分步骤的模型给予“过程性奖励”或部分分数。
*   **模型覆盖**：由于服务条款限制，未包含 Anthropic 等部分主流厂商的模型。
*   **现实鸿沟**：模拟数据虽然复杂，但仍无法完全替代真实科研中缺失文档、极端异常值和非结构化数据的混乱程度。

（完）
