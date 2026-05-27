---
title: "NEURA: A proof-carrying framework for hallucination-resistant neuroimaging automation"
title_zh: NEURA：一种具备证明承载能力的抗幻觉神经影像自动化框架
authors: "Xie, J., Wang, J., Wu, X., Liu, X., Mi, Y., Liu, Q., Xu, T., Liu, C., Chen, H., Guo, J."
date: 2026-05-21
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.27.721217v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 基于LLM的智能体框架实现抗幻觉的神经影像自动化
tldr: "神经影像研究依赖异构软件和多模态数据，基于大语言模型的自动化工作流易产生幻觉。NEURA框架结合疾病与工具感知规划，将自然语言问题转化为可执行分析计划，并通过形式化验证层确保任何输出均经过工具证据和领域公理检查。在包含110个任务的NeuroEval基准上，规划准确率89.5%，提升30.5%；幻觉注入实验检测所有错误且无假阳性；脊髓小脑性共济失调3型案例复现了已知病理模式。该工作将领域接地代理与证明携带验证相结合，使LLM自动化从概率性自检转变为可审计的科学计算。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有LLM驱动的神经影像工作流自动化易产生幻觉，缺乏可信验证机制，亟需防幻觉的确定性方法。
method: NEURA通过疾病与工具感知规划将自然语言问题转为可执行分析计划，并利用形式化证明启发的验证层对输出进行工具证据和领域公理检查。
result: "在NeuroEval基准上规划准确率89.5%，较直接LLM提升30.5%；幻觉注入实验检测所有错误类别且无假阳性；案例研究复现病理模式。"
conclusion: 结合领域接地代理与证明携带验证，将LLM驱动的工作流自动化从概率性自检转变为可审计的科学计算。
---

## 摘要
神经影像研究依赖于异构软件、多模态数据和多阶段统计工作流。基于大语言模型（LLM）的智能体为实现这些工作流的自动化提供了途径，但其易产生幻觉的特性限制了其在科学使用中的可信度。本文介绍NEURA，一种具备证明承载能力的抗幻觉神经影像自动化框架。NEURA将自由文本的研究问题和神经影像数据集转换为可执行的分析计划、经过验证的输出以及结构化报告。该系统将疾病感知和工具感知的规划与受形式化证明启发的确定性验证层相结合：在保留任何声称用于报告之前，必须根据工具生成的证据和领域公理进行检查。在专家策划的包含110个神经影像任务的基准测试NeuroEval上，NEURA实现了89.5%的规划准确率，相比直接使用LLM查询提升了30.5%。在受控的幻觉注入实验中，验证层在指定的公理库和信任假设下检测到了所有注入的错误类别，且无假阳性。在脊髓小脑性共济失调3型的案例研究中，NEURA复现了与既定病理学和独立专家分析一致的小脑萎缩和异常扩散模式。总之，这些发现表明，将基于领域的智能体与证明承载验证相结合，可以将LLM驱动的工作流自动化从概率性自我检查转变为可审计的科学计算。

## Abstract
Neuroimaging research depends on heterogeneous software, multimodal data and multistage statistical workflows. Large language model (LLM)-based agents offer a route to automate these workflows, but their susceptibility to hallucination limits their credibility in scientific use. Here we introduce NEURA, a proof-carrying framework for hallucination-resistant neuroimaging automation. NEURA converts free-text research questions and neuroimaging datasets into executable analysis plans, validated outputs and structured reports. The system combines disease- and tool-aware planning with a deterministic verification layer inspired by formal proof: before any claim is retained for reporting, it must be checked against tool-derived evidence and domain axioms. On NeuroEval, an expert-curated benchmark of 110 neuroimaging tasks, NEURA achieved 89.5% planning accuracy, a 30.5% improvement over direct LLM queries. In a controlled hallucination-injection experiment, the verification layer detected all the injected error classes under the specified axiom bank and trust assumptions, with no false positives. In case studies of spinocerebellar ataxia type 3, NEURA reproduced cerebellar atrophy and abnormal diffusion patterns consistent with established pathology and independent expert analyses. Together, these findings show that coupling domain-grounded agency with proof-carrying verification can turn LLM-driven workflow automation from probabilistic self-checking into auditable scientific computation.

---

## 论文详细总结（自动生成）

## 论文详细总结

### 1. 核心问题与整体含义（研究动机和背景）
- **问题**：神经影像研究依赖异构软件、多模态数据和多阶段统计工作流，基于大语言模型（LLM）的智能体虽然可以自动化这些流程，但易产生**幻觉**（hallucination），导致其输出在科学场景中缺乏可信度。
- **背景**：现有的LLM自动化方法缺乏确定性验证机制，输出无法被审计和复现，限制了其在严谨科学研究中的应用。
- **整体含义**：NEURA通过将**领域接地代理**（domain-grounded agency）与**证明承载验证**（proof-carrying verification）相结合，将LLM驱动的工作流自动化从“概率性自我检查”转变为“可审计的科学计算”，从根本上提升了可靠性和防幻觉能力。

### 2. 方法论：核心思想、关键技术细节
- **核心思想**：将自然语言研究问题转换为可执行分析计划，并对任何输出进行**形式化验证**，确保只有通过工具证据和领域公理检查的声明才能被报告。
- **关键技术细节**：
  - **疾病感知与工具感知规划**：系统首先理解研究问题和数据集，结合疾病领域知识和可用工具，生成可执行的逐步分析计划。
  - **形式化证明启发的确定性验证层**：在输出最终报告之前，所有中间声明必须经过两层检查：
    1. **工具证据**：验证结果是否由真实工具（如FSL、SPM等）运行产生，而非LLM捏造。
    2. **领域公理**：检查结果是否符合神经影像学领域的基本公理（如统计显著性阈值、解剖学一致性等）。
  - **结构化报告生成**：经过验证的声明被组织为结构化报告，确保可审计和可复现。
- **算法流程（文字说明）**：输入（自由文本问题+影像数据集）→ 疾病与工具感知规划器 → 可执行分析计划 → 执行工具 → 输出结果 → 验证层（工具证据 + 领域公理）→ 合格声明保留 → 结构化报告输出。

### 3. 实验设计：数据集、基准和对比方法
- **数据集/场景**：
  - **NeuroEval基准**：专家策划的包含110个神经影像任务的评测集，涵盖多种常见分析场景。
  - **幻觉注入实验**：故意在输出中注入多种错误类别，测试验证层的检测能力。
  - **案例研究**：脊髓小脑性共济失调3型（SCA3）的神经影像分析，复现已知病理模式。
- **对比方法**：与“直接LLM查询”（即不经过NEURA验证层直接让LLM回答）进行对比。
- **公平性**：NeuroEval基准由领域专家手工策划，确保了任务的专业性和客观性；幻觉注入实验使用已知错误类别，避免偏倚。

### 4. 资源与算力
- **明确说明**：论文内容中**未提及**具体的GPU型号、数量、训练时长或推理算力细节。仅描述了方法本身，未提供硬件资源消耗信息。

### 5. 实验数量与充分性
- **实验数量**：
  - NeuroEval基准上的**整体规划准确率**评估（110个任务）。
  - 幻觉注入实验（检测多种错误类别，结果无假阳性）。
  - 一个案例研究（SCA3）。
- **充分性评价**：
  - 规划准确率评估覆盖了110个任务，样本量足够，结果显著（89.5% vs 直接LLM的59%？差值30.5%）。
  - 幻觉注入实验验证了验证层的**零假阳性**能力，但未说明注入的错误类别数量及具体测试次数。
  - 案例研究仅验证了一个疾病，泛化性有限。
  - **总体较充分，但缺乏跨中心/跨数据集泛化测试和多疾病验证**。

### 6. 主要结论与发现
- NEURA在NeuroEval上规划准确率达**89.5%**，比直接LLM查询提升**30.5%**。
- 验证层在幻觉注入实验中**检测所有注入错误类别**，且**无假阳性**，证明了其抗幻觉的有效性。
- 在SCA3案例中，NEURA成功复现了小脑萎缩和异常扩散模式，与已有病理学知识和独立专家分析一致。
- 结论：将领域接地代理与证明承载验证相结合，可将LLM驱动的工作流自动化从概率性自我检查转变为**可审计的科学计算**。

### 7. 优点
- **方法创新性**：首次将**形式化证明**思想引入LLM驱动的神经影像自动化，提供确定性验证，而非依赖概率性自我纠错。
- **抗幻觉能力强**：通过工具证据和领域公理双重检查，从根本上杜绝虚构结果。
- **可审计性**：输出结构化报告，每个声明均可追溯至具体工具执行和公理检查，适合科研诚信需求。
- **性能显著**：规划准确率大幅提升，且验证层无假阳性，实用性强。

### 8. 不足与局限
- **实验覆盖有限**：案例研究仅聚焦一种疾病（SCA3），未在多疾病、多中心数据集上验证泛化性。
- **幻觉注入实验细节不足**：未说明注入错误的具体数量、类型分布以及验证的统计稳定性。
- **资源消耗未报告**：缺乏对计算成本（GPU需求、推理时间）的量化，难以评估落地可行性。
- **依赖领域公理库**：公理库的完备性和正确性直接影响验证效果，需领域专家持续维护。
- **信任假设**：论文提到验证层在“指定的公理库和信任假设”下有效，意味着若公理库不完善或工具本身有误，则可能失效。
- **未讨论失败案例**：未分析NEURA在哪些任务上规划失败或验证误判的情况，不利于后续改进。

（完）
