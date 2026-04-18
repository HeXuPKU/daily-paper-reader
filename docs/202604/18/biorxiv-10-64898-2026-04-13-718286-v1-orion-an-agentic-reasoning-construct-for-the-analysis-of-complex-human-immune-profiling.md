---
title: "ORION: An agentic reasoning construct for the analysis of complex human immune profiling"
title_zh: ORION：一种用于复杂人类免疫图谱分析的智能体推理架构
authors: "Dayao, M. T., Kim, K., Khor, B., Jaech, A., van Opheusden, B., Bodansky, A., DeRisi, J."
date: 2026-04-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.13.718286v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 使用大语言模型进行组学推理和解释的多智能体框架
tldr: ORION是一个基于大语言模型的多智能体框架，旨在解决高维免疫分析数据（如PhIP-seq）解读效率低下的瓶颈。它集成了统计分析、机器学习和自动文献综述，能将原本需要数月的复杂数据分析缩短至数小时。通过在APS-1和唐氏综合征数据集上的验证，证明了其在自动化发现生物标志物和生成科学假设方面的卓越能力。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-04-13-718286-v1/fig-001.webp\", \"caption\": \"Figure 1. ORION multi-agent workflow architecture. ORION orchestrates end-to-end PhIP-82 seq analysis through three specialized agents (a Main Analysis Agent, a Literature Agent, and a 83 Supervisor Agent/orchestrator) operating in a constrained Plan → Execute → Verify loop that 84 enforces reproducibility and auditability through persisted, machine-readable intermediate 85\", \"page\": 3, \"index\": 1, \"width\": 1039, \"height\": 581}]"
motivation: 高维生物数据的快速增长与依赖专家手动整合统计、文献进行解读的低效现状之间存在严重矛盾。
method: 开发了名为ORION的多智能体推理框架，利用具备推理能力的LLM协同执行端到端的统计分析、机器学习建模及自动化文献调研。
result: ORION在2小时内重现了APS-1数月的分析成果，并成功从唐氏综合征数据中识别出具有生物学意义的候选自身抗体靶点。
conclusion: 智能体AI系统能极大地压缩复杂免疫组学数据的分析周期，将科学家的精力从数据处理转向核心生物学问题的探索。
---

## 摘要
生成高维生物数据集的能力已经超过了对其进行解释的能力。诸如噬菌体免疫沉淀测序（PhIP-seq）等技术能够实现抗体库的蛋白质组级图谱分析，但将数千个富集肽段解释为机制性假设仍然是一个劳动密集型的瓶颈，需要专家综合统计学、文献和领域知识。在此，我们介绍了 ORION（组学推理与解释编排器），这是一个多智能体框架，利用具备推理能力的大语言模型对复杂的免疫图谱数据进行端到端分析。ORION 将统计分析、机器学习和自动化文献综述整合到一个结构化的工作流中，产生的结果具有可重复性和完全可追溯性。应用于已发表的 1 型自身免疫性多内分泌腺病综合征（APS-1）PhIP-seq 数据集时，ORION 在约两小时内恢复了经典的自身抗体特征，高度重现了最初需要一到两个月人工努力才能完成的分析。为了测试在先前未见数据上的假设生成能力，我们将 ORION 应用于来自唐氏综合征患者的新型 PhIP-seq 数据集，该领域目前尚不存在蛋白质组范围的自身抗体参考。ORION 以高准确度区分了疾病样本与对照样本，确定了候选自身抗体靶点的优先级，并将其组织成涵盖免疫、肠道和神经程序的生物学连贯组，为后续实验生成了可测试的假设。这些结果表明，智能体 AI 系统可以将复杂免疫图谱数据的分析时间从数周压缩至数小时，使科学家能够将时间重新投入到基础生物学研究中。

## Abstract
The capacity to generate high-dimensional biological datasets has outpaced the ability to interpret them. Technologies such as phage immunoprecipitation and sequencing (PhIP-seq) enable proteome-scale profiling of antibody repertoires, but interpreting thousands of enriched peptides into mechanistic hypotheses remains a labor-intensive bottleneck requiring expert synthesis of statistics, literature, and domain knowledge. Here we describe ORION (Omics Reasoning & Interpretation Orchestrator), a multi-agent framework that uses reasoning-capable large language models to perform end-to-end analysis of complex immune profiling data. ORION integrates statistical analysis, machine learning, and automated literature review into a single structured workflow, producing results that are reproducible and fully traceable. Applied to a published PhIP-seq dataset from autoimmune polyendocrine syndrome type 1 (APS-1), ORION recovered the canonical autoantibody signature in approximately two hours, closely recapitulating an analysis that originally required one to two months of manual effort. To test hypothesis-generation capacity on previously unseen data, we applied ORION to a novel PhIP-seq dataset from individuals with Down syndrome, for which no proteome-wide autoantibody reference exists. ORION distinguished disease from control samples with high accuracy, prioritized candidate autoantibody targets, and organized them into biologically coherent groups spanning immune, gut, and neuronal programs, generating testable hypotheses for experimental follow-up. These results demonstrate that agentic AI systems can compress the analysis of complex immune profiling data from weeks to hours, allowing scientists to redirect their time toward the fundamental biology.

---

## 论文详细总结（自动生成）

这是一份关于论文《ORION: An agentic reasoning construct for the analysis of complex human immune profiling》的结构化总结：

### 1. 核心问题与整体含义
*   **研究背景**：随着高维生物组学技术（如 PhIP-seq 噬菌体展示免疫沉淀测序）的普及，数据生成速度已远超人类的解读能力。
*   **核心问题**：从数万个富集肽段中提取生物学意义需要专家综合统计学、机器学习和海量文献知识，这一过程通常耗时数月，成为免疫组学研究的严重瓶颈。
*   **研究动机**：开发一个能够自动化执行端到端分析、推理并生成科学假设的 AI 框架，以实现复杂免疫图谱数据的快速、可重复解读。

### 2. 方法论
ORION 是一个基于**多智能体推理（Multi-agent Reasoning）**的框架，其核心思想是通过多个专门化的 AI 智能体协同工作，模拟人类专家的分析流程。
*   **核心架构**：
    *   **主分析智能体 (Main Analysis Agent)**：负责数据清洗、差异分析、定量推理和初步机制解释。
    *   **文献智能体 (Literature Agent)**：专门检索 PubMed、UniProt、Human Protein Atlas 等数据库，提取蛋白质功能、组织表达及疾病关联。
    *   **监督智能体 (Supervisor Agent)**：充当“主编”角色，根据预设的 9 项清单（如归一化合理性、分析深度、逻辑严密性等）对分析结果进行审计和反馈，不合格则触发重试。
*   **关键技术细节**：
    *   **计划-执行-验证循环**：智能体在受限循环中运行，所有操作记录在 SQLite 数据库中，确保过程可追溯。
    *   **代码执行环境**：在沙盒化的 Python 环境中自动编写并运行统计脚本（如逻辑回归、随机森林）。
    *   **数据处理**：支持 AG-bead（非特异性结合）归一化，能够识别并剔除实验伪影。

### 3. 实验设计
*   **数据集与场景**：
    1.  **APS-1（1 型自身免疫性多内分泌腺病综合征）**：使用已发表的数据作为**基准测试（Benchmark）**，验证 ORION 能否找回已知的经典自身抗体特征。
    2.  **唐氏综合征（DS）**：使用全新的、未公开的 PhIP-seq 数据集（包含 105 名患者和 103 名对照），测试系统在未知生物学领域的假设生成能力。
*   **对比方法**：
    *   **效率对比**：对比人类专家手动分析所需的时间（数月 vs 数小时）。
    *   **模型对比**：在分类任务中对比了 L1 正则化逻辑回归与随机森林模型的性能。

### 4. 资源与算力
*   **算力说明**：文中未详细列出具体的 GPU 型号或集群规模，但明确使用了 OpenAI 的推理模型（提及 GPT-5.2 及 GPT-5.2 pro，注：这可能是基于特定版本或未来版本的表述）。
*   **运行耗时**：
    *   APS-1 分析：**2 小时 16 分钟**（人类专家需 1-2 个月）。
    *   唐氏综合征分析：**1 小时 41 分钟**。

### 5. 实验数量与充分性
*   **实验规模**：针对两个大型疾病队列进行了深度分析，涵盖了超过 56 万个肽段和近 2 万个蛋白质。
*   **充分性评估**：
    *   **客观性**：通过 5 折分层交叉验证（StratifiedKFold）评估分类性能，确保结果不是过拟合。
    *   **公平性**：引入了 AG-bead 归一化对比实验，证明了系统识别实验偏差的能力。
    *   **局限性**：虽然在两个案例上表现卓越，但尚未在更多类型的组学数据（如单细胞转录组）上进行大规模横向对比。

### 6. 主要结论与发现
*   **效率提升**：ORION 将复杂免疫分析的时间压缩了约 **500 到 1000 倍**。
*   **生物学发现**：在唐氏综合征研究中，ORION 识别出 AUC 达 0.911 的分类特征，并发现了涉及 IL17F（免疫）、MGAM（肠道）和 NTM（神经）的新型候选自身抗体靶点。
*   **科学价值**：证明了智能体 AI 可以从海量噪声数据中提取连贯的生物学程序，并提出具有实验可行性的后续研究建议。

### 7. 优点
*   **高度自动化与可追溯**：不仅给出结论，还保留了完整的计算日志和推理链条，方便人类审计。
*   **领域知识集成**：成功将干实验（统计建模）与湿实验背景（文献综述）无缝整合。
*   **强大的泛化潜力**：框架设计具有通用性，理论上可扩展至其他高维组学领域。

### 8. 不足与局限
*   **幻觉风险**：尽管有监督智能体，LLM 仍可能生成错误的生物学解释，必须经过实验验证。
*   **数据污染疑虑**：对于已发表的 APS-1 数据，模型可能在预训练阶段见过相关结论，这可能影响对其“推理”能力的纯粹评估。
*   **成本问题**：大规模调用高性能推理 API 的成本可能较高，限制了其在资源匮乏实验室的普及。
*   **验证依赖**：AI 生成的是“假设”而非“事实”，最终仍需依赖传统的细胞实验或临床样本验证。

（完）
