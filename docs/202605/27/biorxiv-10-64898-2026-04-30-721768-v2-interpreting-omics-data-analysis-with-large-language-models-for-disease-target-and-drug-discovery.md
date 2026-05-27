---
title: Interpreting Omics Data Analysis with Large Language Models for Disease Target and Drug Discovery
title_zh: 利用大语言模型解释组学数据分析以进行疾病靶点与药物发现
authors: "XU, Z., Chen, W., Ren, W., Xu, T., Amaechin, S., Khan, R., Chen, Y., Province, M., Payne, P., Li, F."
date: 2026-05-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.30.721768v2.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: LLM框架用于解读组学数据，匹配医学大语言模型和组学信号
tldr: 生物医学发现中，组学数据分析需结合文献知识，但纯文本大语言模型缺乏定量证据。本文提出可溯源的Text-to-Target框架，通过模态感知融合策略，将LLM检索的候选基因与组学数据拓扑约束结合，在阿尔茨海默病和胰腺癌中分别得到34/75个候选基因和14/23个策略组合。结果在DepMap和CRISPRbrain数据库中显著富集，且全程可审计，为双病种靶点优先排序提供了可复现的架构。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有LLM仅基于文本输出结果，缺乏组学定量证据支撑，无法可靠地为疾病靶点和药物发现排序。
method: 提出Text-to-Target框架，通过模态感知融合将候选基因分为三类，并在拓扑约束下进行分阶段假设与策略生成。
result: 在PDAC和AD中分别获得75/34个候选基因及23/14个策略组合，靶点和策略均获得DepMap/CRISPRbrain显著支持。
conclusion: 该框架实现了组学数据与LLM检索的可解释融合，支持双病种靶点优先排序及文献-机制一致性更新。
---

## 摘要
在生物医学科学发现中，综合文献中的已有知识是解释数值组学数据分析以进行疾病靶点识别和药物发现的重要组成部分。单独使用大语言模型（LLMs）可以快速从生物医学文本中检索疾病机制，但仅靠文本输出缺乏队列特异性定量证据，对于靶点和药物优先级排序而言通常泛化且不可靠。在此，我们提出了一种来源感知的文本到靶点框架，该框架将模式约束的多模型LLM检索与数值组学数据分析相结合。关键设计在于一种模态感知融合步骤：将候选对象划分为重叠支持的锚点、仅检索的隐藏枢纽以及网络涌现的新颖节点，然后在拓扑约束下将其传播到分阶段假说和策略生成中。我们在阿尔茨海默病（AD）和胰腺导管腺癌（PDAC）中评估了该模型。在PDAC中，该工作流程生成了一个平衡的75个基因候选集和一个23策略组合，在靶点水平和策略水平上均获得了显著的DepMap支持。在AD中，更严格的候选控制产生了紧凑的34个基因集和14个策略；在扩大的CRISPRbrain注册表下，靶点水平轴均显著，且策略水平富集度强。在两种疾病中，最终策略均保持了与候选池的完整来源闭合，从而实现了从检索伪像到验证输出的端到端可审计性。这些结果支持一种可迁移的发现架构，其中组学证据约束生物活性，LLM检索扩展机制搜索空间，而网络感知融合保持可解释性。该框架为双疾病靶点优先级排序提供了可重复的基础，并激励通过主动证据刷新循环实现文献-机制的一致性。

## Abstract
In biomedical scientific discovery, synthesizing prior knowledge from the literature is an essential component of interpreting numerical omics data analyses for disease target identification and drug discovery. Large language models (LLMs) alone can rapidly retrieve disease mechanisms from biomedical text, but text-only outputs are general and unreliable for target and drug prioritization without cohort-specific quantitative evidence. Herein, we propose a provenance-aware Text-to-Target framework that couples schema-constrained multi-model LLM retrieval with numeric omics data analysis. The key design is a modality-aware fusion step: candidates are partitioned into overlap-supported anchors, retrieval-only hidden hubs, and network-emergent novelty nodes, then propagated into staged hypothesis and strategy generation under topology constraints. We evaluate the model in Alzheimers disease (AD) and pancreatic ductal adenocarcinoma (PDAC). In PDAC, the workflow produced a balanced 75-gene candidate universe and a 23-strategy portfolio, with significant DepMap support at both target level and strategy level. In AD, stricter candidate controls yielded a compact 34-gene universe and 14 strategies; under an expanded CRISPRbrain registry, both target-level axes were significant, with strong strategy-level enrichment. Across both diseases, final strategies preserved full provenance closure to the candidate pool, enabling end-to-end auditability from retrieval artifacts to validation outputs. These results support a transferable discovery architecture in which omics evidence constrains biological activity, LLM retrieval expands mechanistic search space, and network-aware fusion preserves interpretability. The framework provides a reproducible basis for dual-disease target prioritization and motivates continuous literature-mechanism concordance with agentic evidence-refresh loops.

---

## 论文详细总结（自动生成）

### 论文结构化总结：利用大语言模型解释组学数据分析进行疾病靶点与药物发现

#### 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：在生物医学发现中，如何将来自文献的定性先验知识与来自组学数据的定量队列证据进行有效整合，以识别可靠的疾病靶点和药物组合策略。单独的LLM能快速检索机制，但缺乏定量支撑且易产生幻觉；传统的组学分析虽提供定量信号，但在机制解释上耗时且难以标准化。
- **整体含义**：提出一个可溯源、模块化的工作流，将两种证据源在拓扑约束下融合，旨在解决靶点发现中的可解释性和审计性问题，为复杂疾病如胰腺癌（PDAC）和阿尔茨海默病（AD）提供可验证的候选策略。

#### 2. 方法论
- **核心思想**：一个名为 **Text-to-Target** 的分阶段融合框架，其核心是“模态感知融合”，而非简单的列表取交集。
- **技术细节与流程**：
    1.  **双模态提取**：
        *   **LLM分支**：使用GPT-5、Gemini 2.5-pro、DeepSeek-r1 三种模型进行模式约束的文献检索，生成结构化的目标-细胞类型-机制表格（T\_LLM）。
        *   **组学分支**：利用PathFinder模型将单细胞组学差异表达信号转化为加权信号网络（V\_PF）。
    2.  **模态感知融合（候选象限构建）**：将L\_LLM和V\_PF融合，生成三个不同来源的候选基因集：
        *   Q1 (锚点): LLM和网络共同支持的基因。
        *   Q2 (隐藏枢纽): 仅LLM检索到的基因。
        *   Q3 (新颖节点): 仅网络涌现的基因。
    3.  **分阶段假设与策略生成**：
        *   **第一阶段**：LLM基于Q1和Q2构建基础机制假设。
        *   **第二阶段**：LLM在Q3节点和网络拓扑约束（如桥梁路径长度）下，将新颖节点插入并升级机制假设。
        *   **第三阶段**：基于升级后的机制表生成多靶点（2-4个）组合治疗策略。
    4.  **疾病匹配验证**：对生成的策略进行独立验证。
        *   PDAC: 使用DepMap数据库中的效应/依赖性指标进行置换检验。
        *   AD: 使用CRISPRbrain数据库中的AD vs. 非AD筛选注册表进行置换检验。

#### 3. 实验设计
- **数据集/场景**：
    *   **PDAC**：恶性与正常腺泡谱系匹配的元细胞表达矩阵（源自HCA、GEO和PDAC单核资源）。
    *   **AD**：从AD相关脑细胞状态（星形胶质细胞、小胶质细胞、谷氨酸能神经元）的疾病-对照对比中生成的元细胞表达矩阵。
- **Benchmark**：无传统意义上的对比方法，框架的自身体系就是评估基准。验证环节使用公开库（DepMap、CRISPRbrain）作为“黄金标准”来检验生成策略的生物学相关性。
- **对比方法**：论文未与其他现有方法（如仅依赖LLM或仅依赖组学的方法）进行定量对比，重点在于展示自身工作流的效果。

#### 4. 资源与算力
*   **明确说明**：论文**未明确提及**训练PathFinder模型或进行海量LLM查询所使用的具体GPU型号、数量及训练时长。论文提到使用了GPT-5, Gemini 2.5-pro, DeepSeek-r1，但未说明API调用量或本地部署资源。

#### 5. 实验数量与充分性
- **实验数量**：两种疾病各进行了一组完整的流程，每个流程内部包含多个阶段（检索、融合、生成、验证），因此可视为两个主要实验。在AD验证中，还比较了CRISPRbrain的“默认”与“扩展”两种注册表设置。
- **充分性与客观性**：
    *   **优点**：双疾病验证（PDAC高对比度，AD低对比度分布）增加了框架鲁棒性。验证阶段使用了独立的外部公共数据库（DepMap, CRISPRbrain）进行置换检验，统计方法标准。最终策略保持了“来源闭合”可审计。
    *   **不足**：
        1.  **缺乏基线对比**：未与仅用LLM、仅用PathFinder或简单的列表交集模型进行对比，虽然作者反复强调“不是简单交集”，但没有量化其优越性。
        2.  **消融实验不足**：未对Q1/Q2/Q3的单独贡献进行消融实验，以证明每个象限的必要性。
        3.  **prompt工程黑盒化**：虽然LLM检索有schema约束，但最终的策略生成高度依赖prompt设计，未讨论不同prompt变体对结果的敏感性。

#### 6. 主要结论与发现
- 该框架在PDAC和AD中都生成了平衡、可审计且生物学相关的候选基因和策略组合。
- **PDAC**：生成75基因集和23个策略。在DepMap上，靶点水平和策略水平验证均显著（策略p=0.0001），表明框架能识别具有PDAC选择性的脆弱性。
- **AD**：生成34基因集和14个策略。在扩展的CRISPRbrain注册表验证中，靶点水平和策略水平验证均显著（策略p=0.0001），表明在信号较弱的神经退行性疾病中策略同样有效。
- 最终策略的来源分布（PDAC: Q1占52.2%, Q3占39.1%; AD: Q1和Q3各占约46%）证实了网络涌现的新颖性在假设生成中的实际贡献。
- 回溯性对比显示，框架生成的序列与最新研究一致（如PDAC的EGFR-STAT3耦合），但模型受限于“经典惰性”，可能漏掉perturbation-specific（如SRC通路）的细节。

#### 7. 方法亮点与优点
- **方法创新性**：“模态感知融合”超越传统的直接列表重叠，通过象限划分（Q1/Q2/Q3）和桥梁分析，为不同来源的证据赋予了明确的角色（锚点、隐藏枢纽、新颖节点），这是最核心的亮点。
- **可解释性与可审计性**：“来源闭合”是设计原则，保证从LLM和网络论文中的每一步都可追溯，并最终可以追溯到下游策略，避免了“黑盒”风险。
- **跨疾病鲁棒性**：在信号完全不同的两种疾病（PDAC高对比度、AD低对比度分布）上验证了工作流的通用性，证明了方法的迁移能力。
- **前瞻性设计**：提出了一个“连续文献-机制一致性”框架的双循环 （agentic），将一次性分析升级为持续更新的发现系统。

#### 8. 不足与局限
- **缺乏对比基线**：未与其他方法（如简单交集、单模态模型）进行量化对比，难以判断其相比简单方法的具体提升有多大。
- **实验充分性受限**：缺少消融实验来证明各个模块（如PathFinder网络、象限划分）的必要性。结果高度依赖于prompt设计，缺乏对prompt敏感性的分析。
- **应用限制**
    *   框架主要基于转录组学，无法捕获翻译后修饰、蛋白质活性和空间微环境效应。
    *   验证数据库（DepMap, CRISPRbrain）有内在偏差（如PDAC重在成瘾性，AD验重注册表成分），可能低估某些环境介导的脆弱性。
    *   候选基因需要专家手动整理筛选，自动化流程可能积累噪声。
    *   “连续文献更新”的概念仍处于提议阶段，未实现在线运行。

（完）
