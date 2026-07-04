---
title: "GeneBench-Pro: Evaluating Multistage Statistical Reasoning in Genomics, Quantitative Biology, and Translational Biomedicine"
title_zh: GeneBench-Pro：评估基因组学、定量生物学和转化生物医学中的多阶段统计推理
authors: "Li, J. H., Ho, A. J."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735386v3.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 评估AI智能体在基因组学中多阶段分析能力的基准，契合医学人工智能主题
tldr: "现有基准缺乏对多阶段科学推理的评估。GeneBench-Pro扩展了基因、定量生物学和转化医学领域，包含129个难题，经外部专家审查。最强模型GPT-5.6 Sol Pro通过率仅31.5%，模型常完成大部分工作流但未能从局部信号推导出正确分析决策，揭示了长时推理能力的系统性不足。"
source: biorxiv
selection_source: fresh_fetch
motivation: 评估AI在真实多阶段科学分析中完成复杂推理的能力，弥合现有基准与实际问题之间的差距。
method: 构建包含129个难题的基准，覆盖10个领域21个子领域，要求模型在最少指导下自主执行多步推理工作流。
result: "GPT-5.6 Sol Pro通过率31.5%，GPT-5.5仅12.0%，非GPT最强基线16.0%，模型在关键决策点存在从注意到行动的差距。"
conclusion: 当前AI在长时生物推理上仍不可靠，需改进从局部信号到全局决策的推理能力。
---

## 摘要
我们推出了GeneBench-Pro，这是GeneBench的扩展和改进版本，包含覆盖更广泛领域的更难问题。GeneBench-Pro是一个基准测试，用于评估在执行基因组学、定量生物学和转化生物医学中的现实多阶段科学分析时的人工智能代理，旨在捕捉计算生命科学家在必须做出结论以支撑后续科学或转化决策时所面临的真实世界问题的复杂性。该基准包含129个评估，针对10个主要领域和21个终端子领域中直接实践相关的量，以基因组学为核心。与GeneBench类似，每个问题为代理提供简要背景、目标估计量以及极少指导；代理随后必须导航多个依赖决策点，即实质性的推断分叉，其中看似合理的错误选择会改变下游分析，以识别并执行正确的分析工作流程并得出正确答案。相对于GeneBench，GeneBench-Pro新增了29个问题，删除了3个，并对剩余的100个重叠问题中的54个进行了大幅重新设计。129个问题中有82个经过了外部领域专家的审查，他们的发现促使对目标不够明确的问题进行了提示/数据修改和重新设计。十个经过外部审查的问题公开发布，50个保留问题提供给Artificial Analysis进行独立的第三方模型基准测试，其余作为内部保留。在对全部129个问题的评估中，GPT-5.6 Sol在最大推理水平上达到28.7%的评估级通过率，而GPT-5.6 Sol Pro在单独报告的GPT Pro运行中达到31.5%。GPT-5.5达到12.0%，GPT-5.4达到8.9%，最强的非GPT基线Claude Opus 4.8达到16.0%。与GeneBench一样，模型通常能完成工作流的大部分，但在注意到和行动之间存在一致的差距：即识别出局部诊断信号，但未能将影响传播到相应的分析决策。因此，模型常常选择错误的估计量，或坚持最初看似合理但实际错误的分析路径。因此，GeneBench-Pro衡量了一种新兴的长期生物推理能力，而这种能力仍然不可靠。

## Abstract
We introduce GeneBench-Pro, an expanded and improved version of GeneBench that comprises harder problems across a wider breadth of domains. GeneBench-Pro is a benchmark for AI agents performing realistic multi-stage scientific analyses in genomics, quantitative biology, and translational biomedicine which seeks to capture the complexity of real-world problems that computational life scientists face when tasked with producing a conclusion upon which a downstream scientific or translational decision is contingent. The benchmark comprises 129 evaluations targeting quantities of direct practical relevance across 10 primary domains and 21 terminal subdomains, with a genomics-centered core. Similarly to GeneBench, each problem provides the agent with brief context, a target estimand, and minimal guidance otherwise; the agent must then navigate multiple dependent decision points; i.e., substantive inferential forks where a plausible wrong choice changes the downstream analysis, to identify and execute the correct analysis workflow and arrive at the correct answer. Relative to GeneBench, GeneBench-Pro adds 29 new problems, drops three, and introduces significantly redesigned versions of 54 of the remaining 100 overlapping problems. 82 of the 129 problems were reviewed by external domain experts, whose findings led to prompt/data modifications and redesign of those problems whose targets were not sufficiently identifiable. Ten externally reviewed problems are released publicly, 50 held-out problems were provided to Artificial Analysis for independent third-party model benchmarking, and the remainder are retained as an internal holdout. In evaluations over the full 129-problem suite, GPT-5.6 Sol reaches an eval-level pass rate of 28.7% at the max reasoning level, and GPT-5.6 Sol Pro reaches 31.5% in separately reported GPT Pro runs. GPT-5.5 reaches 12.0%, GPT-5.4 reaches 8.9%, and the strongest non-GPT baseline, Claude Opus 4.8, reaches 16.0%. As with GeneBench, models often complete substantial portions of the workflow but exhibit a consistent gap between noticing and acting by identifying local diagnostic signals but failing to propagate the implications to the corresponding analysis decision. As a result, models often select wrong estimators or persist on initially plausible but incorrect analysis paths. GeneBench-Pro therefore measures an emerging capability of long-horizon biological reasoning that remains unreliable.

---

## 论文详细总结（自动生成）

# 论文总结：GeneBench-Pro：评估基因组学、定量生物学和转化生物医学中的多阶段统计推理

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：在生命科学领域（基因组学、蛋白质组学、转录组学等），数据生成成本快速下降，但下游计算和分析已成为主要瓶颈。现有AI评测大多针对孤立的、清理好的数据集和明确定义的单一分析任务（图1A），未能涵盖现实科研工作流程的核心——即从原始、有噪声的数据出发，经过多步数据质量检查、探索性分析、模型选择、诊断修正等**迭代且依赖上下文的决策链**，最终得出可指导下游科学或转化决策的结论（图1B）。
- **整体含义**：GeneBench-Pro旨在填补这一评估空白，衡量AI智能体在真实多阶段分析中执行**多步、有条件依赖的统计推理**的能力，这一能力目前对前沿模型而言仍然不可靠。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：构建包含129个问题的评估套件，每个问题都是一个自包含的多步分析任务。提供（1）模拟的、带有噪声的真实感数据集（类似实验室或临床产出）；（2）最小可行提示（仅给出实验背景和目标估计量，不描述具体分析步骤）。智能体必须自主完成数据清洗、质量控制和预分析、模型选择与推理、诊断与修正等步骤，最终给出正确数值答案。
- **关键技术细节**：
  - **模拟数据驱动**：所有问题基于构造性模拟，已知完整因果结构，从而确保正确答案可恢复（即从智能体可见数据中可识别），且错误分析路径会被正确区分。
  - **多决策点级联**：每个问题包含3–13个实质性推断分叉（中位数6个），即那些如果在某个点做出错误选择会导致最终答案发生质变的关键决策。
  - **外部科学评审**：82个问题经过11位领域专家（研究生、博士后、产业科学家、教授）评审，评估目标可识别性、方法实现正确性、现实性等，并根据反馈修正问题（修改提示、数据生成过程、甚至完全重新设计）。
  - **严格验证**：通过消融实验确保所有看似合理但错误的简化路径会得到显著不同且错误的结果；通过多轮前沿模型试跑和轨迹分析消除无意数据泄漏、替代正确路径等。
  - **评分**：二元及格/不及格评分，基于预设容差内恢复目标估计量。只保留正确的JSON输出，容器或工具错误等无效试次被排除。

## 3. 实验设计：数据集/场景、基准、对比方法

- **数据集/场景**：
  - **领域覆盖**：10个主要领域，21个终端子领域。核心为遗传学（统计遗传学、群体遗传学、定量遗传学等），扩展到分子组学、临床和转化基因组学、药物基因组学、癌症基因组学、微生物基因组学、法医遗传学等。
  - **问题素材**：模拟数据来自典型现实分析模式（非教科书式问题），例如：携带者筛查中的残留风险估计、药物遗传学时间-事件分析、条件性细胞类型遗传力评估、桥校准肽段pQTL等。
- **基准（benchmark）**：GeneBench-Pro本身即为新基准，包含129个问题。公开10个问题（含详细报告），50个问题交由Artificial Analysis独立评测，剩余69个为内部保留。
- **对比方法**：
  - **GPT系列**：GPT-5.2、5.4、5.5、5.6 Luna/Terra/Sol，以及对应的Pro（Extended）版本（内部使用更高计算资源）。
  - **非GPT模型**：Claude Opus 4.8、Gemini 3.5 Flash、Grok 4.3、GLM 5.2、Kimi K2.6、DeepSeek V4 Pro、MiMo V2.5 Pro、Tencent HY3、MiniMax M3、Qwen 3.7 Max等共60个模型配置。
  - **推理水平**：对GPT系列内部分为none、low、medium、high、xhigh、max多个推理强度。

## 4. 资源与算力

- 论文**未明确说明**训练模型所用的GPU型号、数量、训练时长等。仅提及评测运行环境：Linux Docker容器，配备Python和R科学计算库，无互联网访问，智能体只能使用提示、本地文件、预装软件和内部知识。
- 对于GPT Pro (Extended) 运行，提到是“单独报告的GPT Pro运行”，但具体算力细节未披露。
- 注意：作者来自OpenAI，但论文未公开训练计算量；评测本身可能消耗了大量推理算力，但未量化。

## 5. 实验数量与充分性

- **实验数量**：
  - 60个模型配置 × 129个问题 × 10次独立尝试（标准评估）/ 5次（Pro和Claude） = 总计约7.7万次有效尝试（过滤无效试次后）。
  - 59个问题经过外部专家审查（82个接受审查，但最终保留82个），10个公开，50个交给第三方。
  - 每个问题都经历了多轮内部消融验证（验证错误路径的分离度）、多轮前沿模型试跑和轨迹分析。
- **充分性与公平性**：
  - **充分性**：实验数量庞大，覆盖多种模型家族和推理水平，包括消融分析（如降低推理强度后的通过率变化）、子集分析（公开集、外部审查集等）等。通过层次化bootstrap计算置信区间。
  - **客观性**：采用二元客观评分，基于机器可执行的预设容忍度，避免了主观判断。外部专家审查进一步增加了问题设计的科学合理性。
  - **公平性**：所有模型在同一评测框架下运行，无统一时钟时间限制，但依赖于各自提供商的平台行为。Pro模型使用了更多计算资源，因而单独报告。

## 6. 主要结论与发现

- **总体通过率低**：最强模型GPT-5.6 Sol Pro最高通过率仅为31.5%（max推理）；主线GPT-5.6 Sol为28.7%；非GPT最强Claude Opus 4.8为16.0%；早期GPT-5.2仅4.9%。
- **认知到行动的差距**：模型往往能发现数据质量问题或统计异常信号（“注意到”），但无法将此信号转化为下游方法选择的改变（“行动”）。表现为选择错误的估计量、坚持错误的分析路径。定性上类似人类专家-新手差异。
- **推理强度有显著影响**：对于GPT-5.6 Sol，从无推理（3.7%）到max推理（28.7%），通过率大幅提升，但随推理强度增加提升速度放缓（图4C）。
- **存在大量未解决问题**：即使在最强模型中，仍有45.7%的问题通过率为0%（图4B），表明评估远未饱和。
- **公开/第三方子集表现较低**：人工分析子集通过率通常低于完整套件，可能与问题难度选择有关。

## 7. 优点

- **填补评估空白**：聚焦于真实科研中最关键的“多步、有条件的统计推理”能力，而非简单的知识问答或单步分析执行。
- **严格的构造验证**：使用模拟数据确保答案可恢复，通过消融验证错误路径的分离，避免开放性真实数据中常见的“多路径合理”问题，使评分更可靠。
- **外部专家评审**：82个问题经领域专家评估，增加了问题的现实性和科学有效性，避免了基准设计者的主观偏差。
- **分层发布模式**：公开10个+第三方50个+内部保留，兼顾透明度、独立评测和抗污染。
- **详细的定性分析**：通过模型轨迹分析揭示“注意到-行动”差距，为后续模型改进提供明确方向。

## 8. 不足与局限

- **模拟数据与现实差距**：尽管模拟数据控制良好，但无法完全复现真实研究中的文档缺口、数据规模、研究特异性不规则性等。因此评估的是“受控环境下的复杂推理”，而非完全现实的科研工作。
- **二元评分丢失中间信息**：只给最终结果通过/不通过，丢弃了正确执行部分步骤但最后一步失败的宝贵过程信息。作者也承认未来可添加阶段级评分。
- **模型非统一计算预算**：不同模型（尤其是Pro/Extended）使用了不同计算量，对比时需谨慎。
- **未公开全部问题**：内部保留的69个问题缺乏第三方验证，可能影响长期可靠性。
- **领域覆盖仍有限**：尽管扩展到10个领域，但未覆盖所有组学类型（如代谢组学、脂质组学等），部分子领域问题数较少（如法医遗传学仅2个）。
- **可能存在的智能体协作/工具调用偏差**：智能体只能使用预装库和离线命令，不能实时查询外部数据库或使用专有工具，可能不利于依赖外部知识的模型。
- **算力披露不足**：缺乏训练和推理阶段的详细算力信息，不利于成本-效益分析。

---

（完）
