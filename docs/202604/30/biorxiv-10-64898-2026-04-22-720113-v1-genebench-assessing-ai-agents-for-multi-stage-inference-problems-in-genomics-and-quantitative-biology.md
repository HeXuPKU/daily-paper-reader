---
title: "GeneBench: Assessing AI Agents for Multi-Stage Inference Problems in Genomics and Quantitative Biology"
title_zh: GeneBench：评估基因组学与定量生物学中多阶段推理问题的 AI 智能体
authors: "Li, J., Ho, A."
date: 2026-04-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.22.720113v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 评估基因组学多阶段推理中的AI智能体
tldr: GeneBench是一个针对基因组学和定量生物学中多阶段科学数据分析的AI智能体基准测试。它涵盖了从数据清洗、探索性分析到统计建模的完整流程，包含10个领域的103项评估任务。研究发现，尽管当前最先进的模型在处理复杂推理链条方面有所进步，但在将诊断信号转化为正确分析决策方面仍存在显著局限，整体通过率较低。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的生物学基准测试多侧重于知识检索或单一分析步骤，无法评估AI在处理现实中复杂、多阶段的科学推理和数据分析任务时的能力。
method: 开发了包含103个评估任务的GeneBench，要求AI智能体在最小引导下处理包含测量误差、选择偏差等现实障碍的多步骤分析，并给出可验证的答案。
result: "评估显示GPT-5.5 Pro的最高通过率为33.2%，而Gemini 3.1 Pro仅为11.2%，且大多数模型在识别问题与采取相应行动之间存在明显的断层。"
conclusion: GeneBench揭示了AI在多阶段科学推理中的新兴能力尚不可靠，特别是在处理依赖性决策点和错误传播方面仍面临巨大挑战。
---

## 摘要
我们介绍了 GeneBench，这是一个针对遗传学和定量生物学中真实多阶段科学数据分析的 AI 智能体基准测试。现有的生物学基准测试大多衡量知识检索、常规流程执行或单一分析步骤。然而，它们未能涵盖占据计算科学家大部分时间的更广泛工作范畴：清洗和标准化检测、表型或临床数据；探索性数据分析；统计模型选择和诊断迭代；以及得出为下游科学或转化决策提供信息的结论。GeneBench 通过针对 10 个领域中具有直接实际相关性的指标的 103 项评估填补了这一空白，其核心以基因组学为中心，并涵盖了其他组学和定量生物学背景。每个问题都包含一个封装的多步分析，具有分阶段的数据、定义感兴趣指标但提供极少指导的提示词，以及可验证的答案。解决每个问题需要识别并处理现实中的障碍，如测量误差、选择偏倚、混杂因素、质量控制（QC）失败，以及在竞争模型类别中进行选择。通过广泛的消融研究，我们验证了每个问题都有一个唯一且合理的答案。每个问题都涉及多个相互依赖的决策点；即实质性的推理分叉，其中一个看似合理的错误选择会改变下游分析，导致错误通过推理链传播到最终的评分目标中。在初步评估中，主流 GPT 系列在 xhigh 推理设置下的 GPT-5.5 达到了 25.0% 的评估级通过率。在单独报告的 GPT Pro 运行中，GPT-5.5 Pro 达到 33.2%，GPT-5.4 Pro 达到 25.6%，GPT-5.2 Pro 达到 10.8%。即使对于报告的两个最强 Pro-harness 设置，在重复运行中，分别有 60.2% 和 62.1% 的问题通过率仍低于 20%。最强的外部基准模型 Gemini 3.1 Pro 达到了 11.2%。模型通常能完成工作流的大部分内容，但在“察觉”与“行动”之间表现出一致的差距：它们能识别局部诊断信号，但未能将该影响传播到相应的分析决策中，结果导致选择了错误的估计量，或坚持最初看似合理但错误的分析路径。因此，GeneBench 衡量的是一种新兴的、但目前仍不可靠的能力。

## Abstract
We introduce GeneBench, a benchmark for AI agents on realistic multi-stage scientific data analysis in genetics and quantitative biology. Existing biology benchmarks mostly measure knowledge retrieval, execution of routine pipelines, or a single analysis step. Yet they do not capture the broader scope of work that occupies much of computational scientists time: cleaning and normalizing assay, phenotype, or clinical data; exploratory data analysis; statistical model selection and diagnostic iteration; and producing a conclusion that informs a downstream scientific or translational decision. GeneBench addresses this gap with 103 evaluations targeting quantities of direct practical relevance across 10 domains, with a genomics-centered core and adjacent coverage in other  omics and quantitative biology settings. Each problem comprises an encapsulated multi-step analysis with staged data, prompts that define a quantity of interest while otherwise providing minimal guidance, and verifiable answers. Solving each problem requires identifying and addressing realistic obstacles such as measurement error, selection bias, confounding, QC failures, and choosing among competing model classes. Through extensive ablation studies, we verify that each problem admits a single defensible answer. Each problem involves multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, such that errors propagate through the inferential chain and into the final graded target. In initial evaluations, the mainline GPT family reaches an eval-level pass rate of 25.0% with GPT-5.5 at the xhigh reasoning setting. In separately reported GPT Pro runs, GPT-5.5 Pro reaches 33.2%, GPT-5.4 Pro reaches 25.6%, and GPT-5.2 Pro reaches 10.8%. Even for the two strongest reported Pro-harness settings, 60.2% and 62.1% of problems, respectively, remain below 20% pass rate over repeated runs. The strongest external baseline, Gemini 3.1 Pro, achieves 11.2%. Models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting: they identify local diagnostic signals but fail to propagate the implication to the corresponding analysis decision, and as a result select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench therefore measures an emerging capability that remains as yet unreliable.



O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=46 SRC="FIGDIR/small/720113v1_ufig1.gif" ALT="Figure 1">
View larger version (13K):
org.highwire.dtl.DTLVardef@1299c82org.highwire.dtl.DTLVardef@e22bd0org.highwire.dtl.DTLVardef@aa7ec9org.highwire.dtl.DTLVardef@169cdd9_HPS_FORMAT_FIGEXP  M_FIG C_FIG

---

## 论文详细总结（自动生成）

这篇论文介绍了 **GeneBench**，一个专门为评估 AI 智能体在基因组学和定量生物学中处理**多阶段、复杂科学推理能力**而设计的基准测试。

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **研究动机**：现有的生物学 AI 基准测试（如 GeneTuring, LAB-Bench）大多侧重于知识检索、执行常规代码管道或单一分析步骤。然而，现实中的科学研究是高度迭代且充满歧义的，科学家大部分时间花在清洗脏数据、处理质量控制（QC）失败、选择统计模型以及根据中间诊断结果调整分析路径上。
*   **核心问题**：当前的 AI 智能体是否具备“科研品味”和判断力，能够从原始、有误差的数据出发，通过一系列相互依赖的决策，最终得出能够指导临床或转化决策的准确结论？
*   **整体含义**：GeneBench 旨在填补“简单任务”与“端到端科学发现”之间的鸿沟，衡量 AI 在处理具有现实挑战性的多阶段推理问题时的可靠性。

### 2. 论文提出的方法论
*   **核心思想**：构建“级联式”（Cascaded）问题。每个问题包含多个**决策点（Decision Points）**，上游的决策（如数据过滤、模型选择）会直接影响下游分析的有效性。
*   **关键技术细节**：
    *   **最小可行提示词（Minimal Viable Prompt）**：仅定义科学目标和输出格式，不提供具体的方法指导或工作流暗示。
    *   **构造性模拟数据**：使用模拟而非历史真实数据，以确保：(1) 存在唯一的、可识别的正确答案；(2) 能够精确控制误差（如测量误差、选择偏倚、混杂因素）；(3) 能够通过消融实验验证错误路径的必然失败。
    *   **决策点设计**：每个问题包含 3 到 13 个决策点（中位数为 6 个），涵盖数据清洗、探索性分析（EDA）、统计建模、诊断迭代等。
*   **算法流程**：AI 智能体在隔离的 Linux 容器（沙盒）中运行，配备标准科学计算库（NumPy, Pandas, SciPy 等），通过编写和执行 Python 代码来探索数据并生成最终答案。

### 3. 实验设计
*   **数据集/场景**：涵盖 10 个领域，共 103 个评估任务。
    *   **核心领域**：统计遗传学（如 GWAS 随访、因果映射）、群体遗传学（如选择压力扫描、古 DNA 分析）、定量遗传学。
    *   **相邻领域**：功能基因组学、空间转录组学、癌症基因组学、蛋白质组学、临床遗传学、法医遗传学、表观基因组学。
*   **对比方法（Baselines）**：
    *   **GPT 系列**：GPT-5, GPT-5.2, GPT-5.4, GPT-5.5（涵盖从 none 到 xhigh 的不同推理强度设置）。
    *   **GPT Pro 系列**：GPT-5 Pro 到 GPT-5.5 Pro。
    *   **外部模型**：Gemini 3.1 Pro, Kimi K2.5/K2.6, Grok 4.20, Qwen 3.6 Plus, GLM 5.1, MiMo V2/V2.5 Pro。

### 4. 资源与算力
*   **算力说明**：论文**未明确说明**训练这些模型所使用的具体 GPU 型号或数量。
*   **推理成本**：论文提到，单次尝试的 Token 消耗在数万级别，API 成本远低于 1 美元，相比人类专家（10-40 小时，数千美元成本）具有极高的经济潜力。

### 5. 实验数量与充分性
*   **实验规模**：对 103 个问题进行了大规模重复实验，每个模型-问题配置平均运行 **28.7 次**（范围 14-60 次），以确保统计显著性。
*   **消融实验**：对每个问题都进行了详尽的消融研究，验证了如果 AI 跳过 QC 或选择错误模型，其结果将显著偏离正确答案，证明了基准测试的严谨性和公平性。
*   **充分性评价**：实验设计非常充分，不仅对比了多个模型家族，还分析了推理强度（Reasoning Effort）对结果的影响，并进行了深入的错误追踪分析。

### 6. 论文的主要结论与发现
*   **整体表现低迷**：即使是最强的 GPT-5.5 Pro，通过率也仅为 **33.2%**；外部最强模型 Gemini 3.1 Pro 为 11.2%。
*   **“察觉-行动”断层（Notice-Act Gap）**：这是核心发现。AI 经常能识别出数据中的异常（如“我注意到存在批次效应”），但无法将此观察转化为正确的修正行动（如“因此我应该使用特定的校准模型”），导致分析路径最终溃败。
*   **推理链长度的影响**：随着决策点数量增加，通过率显著下降。强模型在短链条任务上表现尚可，但在长链条任务上依然不可靠。
*   **推理强度的作用**：增加推理 Token（Reasoning Effort）能显著提升 GPT 系列的表现，但仍存在大量无法解决的“长尾”难题。

### 7. 优点
*   **高度仿真**：模拟了真实科研中“脏数据”和“多步决策”的复杂性，而非简单的问答。
*   **严谨的验证机制**：通过构造性模拟确保了答案的唯一性和可验证性，避免了基准测试常见的“标签噪声”问题。
*   **决策点分解**：将复杂的科研任务分解为可量化的决策点，为未来开发过程奖励模型（PRM）提供了基础。

### 8. 不足与局限
*   **数据规模限制**：为了保证可评估性，模拟数据的规模和文档缺失程度可能仍低于真实的超大规模生物库数据。
*   **二元评分制**：目前采用“全对或全错”的二元评分，无法对完成大部分流程但最后一步出错的智能体给予部分信用（Partial Credit）。
*   **应用限制**：由于不提供特定领域的生物信息学工具包（如 PLINK, BWA），该基准测试更多衡量的是通用科学编程和统计推理能力，而非对特定生物软件的熟练程度。

（完）
