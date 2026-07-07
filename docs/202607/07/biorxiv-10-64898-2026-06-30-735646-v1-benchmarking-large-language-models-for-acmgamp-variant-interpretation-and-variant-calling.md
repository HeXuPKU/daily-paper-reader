---
title: Benchmarking large language models for ACMG/AMP variant interpretation and variant calling
title_zh: 对用于ACMG/AMP变异解读和变异调用的大语言模型进行基准测试
authors: "Corpas, M."
date: 2026-07-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.30.735646v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 在基因组学中评估大语言模型在变异解读和变异检出上的表现
tldr: 目前大型语言模型在基因组变异解读和调用中被广泛使用，但仅用准确率评估无法反映系统安全性和故障来源。本文提出ClawBench框架，通过时间盲真值集和证据合约，从有效性、安全性、来源和可重复性等多维度评估模型。结果显示危险误分类罕见且模型无关，但捏造证据可被测量并通过执行消除；不同变异类别受不同流程层限制；开源模型在结构输出和来源一致性上存在差距。该框架为基因组AI工作流提供了更全面的安全评估方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有评估仅关注准确率，无法定位故障来源或判断系统安全性，亟需多维度评估框架。
method: 构建ClawBench，包含时间盲真值集（标签在模型训练截止后出现）和证据合约（阻断循环证据），评估有效性、安全、来源和可重复性。
result: 危险误分类罕见且模型无关；证据捏造可测量且被执行消除；不同变异类别（如功能缺失vs罕见错义）受不同层限制；本地模型来源一致性差。
conclusion: 基因组AI评估必须超越准确率，关注执行验证与多维指标，以保障临床安全与可靠性。
---

## 摘要
智能体大语言模型越来越多地用于基因组工作流程，从变异调用到临床解读，然而它们仅通过准确性进行评价，单一数字无法说明系统是否安全，也无法说明工作流程中失败源自何处。我们提出了ClawBench，这是一个框架，它将每个结果归因于在标准流程的两半中产生该结果的架构层。两个设计选择消除了使智能体基因组学难以评估的混淆因素：一个时间盲法真实数据集，其中每个评分的ClinVar标签仅在所测试每个模型的训练截止日期之后才首次可用；以及一个故障封闭的证据合约，阻止证据与真实标签循环。我们在一个约束梯度下对有效性、安全性、来源和可重复性进行评分，而不仅仅是准确性，该梯度将正确性从模型的先验知识转移到已执行、验证的代码中。我们展示了三件事。首先，危险的错误分类是罕见且与模型无关的，是执行架构的受控前提条件，而非前沿水平，而捏造的证据是可测量的，并通过执行被中和。第二，不同的变异类别受不同层级的速率限制：功能丧失变异受确定性组合器阈值的限制，而罕见错义变异受证据形成的限制，其中证据获取是不对称且有上限的，而强度分配是一个可恢复的层，天真的强度许可提示会混淆它。第三，对于变异调用，不同方法的分歧不在于模型能否规划流程（所有模型都能做到），而在于信任属性、固定、来源、可审计性和可重复性，这些属性单调地向经过验证的执行方向提升；并且一个本地开权重模型再现了安全性结果，但满足结构化输出和来源合约的频率远低于前沿模型，这是一种合规性差距，而非能力或安全性差距。端到端连接将整个工作流程中的失败归因，将遗漏的调用与传播的基因型错误以及正确调用但错误解读的变异区分开来。

## Abstract
Agentic large language models are increasingly used across the genomic workflow, from variant calling to clinical interpretation, yet they are evaluated by accuracy alone, a single figure that cannot say whether a system is safe or where in the workflow a failure originates. We present ClawBench, a framework that attributes each outcome to the architectural layer that produced it across both halves of the canonical pipeline. Two design choices remove the confounds that make agentic genomics hard to evaluate: a temporally blinded truth set, in which every scored ClinVar label first became available only after the training cutoff of every model tested, and a fail-closed evidence contract that blocks evidence circular with the truth label. We score validity, safety, provenance and reproducibility, not accuracy alone, under a constraint gradient that relocates correctness from a model's prior into executed, validated code. We show three things. First, dangerous misclassification is rare and model-invariant, a controlled precondition of the executed architecture rather than a frontier, while fabricated evidence is measurable and is neutralised by execution. Second, different variant classes are rate-limited by different layers: loss-of-function variants by the deterministic combiner threshold, and rare missense by evidence formation, where evidence acquisition is asymmetric and capped and strength assignment is a recoverable layer that naive strength-licensing prompts confound. Third, for variant calling the arms separate not on whether a model can plan a pipeline, which all do, but on trust properties, pinning, provenance, auditability and reproducibility, which climb monotonically toward validated execution; and a local open-weight model reproduces the safety result yet meets the structured-output and provenance contract far less often than frontier models, a conformance gap rather than a capability or safety gap. An end-to-end join attributes failures across the whole workflow, separating a missed call from a propagated genotype error from a correctly called but misinterpreted variant.

---

## 论文详细总结（自动生成）

# 论文总结：Benchmarking large language models for ACMG/AMP variant interpretation and variant calling

## 一、核心问题与整体含义（研究动机与背景）

- **核心问题**：当前大型语言模型（LLMs）在基因组学领域（如ACMG/AMP变异解读和变异调用）被广泛使用，但评估仅依赖“准确率”这一单一指标，无法判断系统是否安全，更无法定位工作流程中失败的具体来源（是模型本身、证据获取、强度赋值还是组合器阈值）。
- **关键挑战**：
  - 现有公开知识库如ClinVar的标签可能已被模型训练集记忆，导致测试结果衡量的是“回忆”而非“推理”。
  - 模型输出的证据若源自与真值标签相同的数据源，会造成循环论证，虚增表现。
  - 临床变异解读本身困难（文献[7]指出，9个实验室对同一99个变异的解读一致性仅为34~71%），评估中需区分“任务固有难度”与“模型行为错误”。
- **研究含义**：需要一个能够**归因**每个结果（如“意义不明确”，VUS）到具体架构层（安全/证据形成/决策形成）的评估框架，超越单一准确率，提供可信赖性判断。

## 二、方法论

### 核心思想
ClawBench框架通过两个关键设计消除混淆因子，将正确性从模型的先验知识逐步转移到**已执行、已验证的代码**中，并以分层归因标签代替分数。

### 关键技术细节
1. **时间盲真值集（Temporal Blinding）**：
   - 仅当ClinVar标签的**首次可用日期**严格在所有测试模型的训练截止日期（加上90天安全边际）之后时才被纳入。
   - 排除那些无法证明首次可用日期的变异（故障封闭）。
   - 有效截止日期 = 2025-11-29（GPT-5.2的2025-08-31 + 90天）。
   - 结果：6,929个时间盲变异（206个为重新分类变异）。

2. **故障封闭证据合约（Fail-Closed Evidence Contract）**：
   - 在技能执行（skill-execution）条件下，模型输出需通过机器可读合约验证。
   - 禁止证据来自与真值标签相同来源（如PP5、BP6等断言代码永远禁止；PS1和PM5在来自ClinVar时禁止；来自ClinGen Variant Curation Expert Panels和LOVD的来源也禁止）。
   - 任何违反均导致提交无效（而非默认乐观解释）。

3. **约束梯度（Constraint Gradient）**：
   - 三个条件逐步转移正确性：
     - **自由提示（free）**：模型从自身先验返回分类。
     - **技能推理（skill-reasoning）**：模型基于固定规范推理。
     - **技能执行（skill-execution）**：模型仅返回结构化ACMG代码，由确定性组合器处理。
   - 加一个真值提供条件作为上限对照。

4. **确定性组合器**：
   - 两个组合器：Richards规则计数逻辑 和 Tavtigian点系统。
   - 通过对比分离“阈值效应”与“证据效应”。

5. **分层归因**：
   - 每个变异得到四类标志：安全清洁（safety_clean）、组合器敏感（combiner_sensitive）、赋值不稳定（assignment_unstable）、证据不足（evidence_insufficient）。
   - 优先级：dangerous > evidence_insufficient > combiner_sensitive > assignment_unstable > resolved。

## 三、实验设计

### 数据集
- **解释真相集**：ClinVar GRCh38，仅纳入时间盲变异（6,929个），通过自动分型分为A、B、C三层：A层（功能丧失/常见，预测高自动性，894个）、B层（错义/其他蛋白改变，2,906个）、C层（同义/内含子等，3,129个）。
- **调用真相集**：Genome in a Bottle（GIAB）样本（HG002、Ashkenazi、East Asian），仅chr20，使用GA4GH基准协议通过rtg vcfeval评分。

### 实验场景与对比模型
1. **解释实验**：
   - **Tier-A试点**：231个A层变异，3个前端模型（GPT-5.2, Claude Sonnet 4.5, Gemini 2.5 Flash），3个条件，5次重复。
   - **归因语料库**：281个变异×3模型 = 843条记录（对条件B和C之间差异归因）。
   - **获取实验**：27个B层罕见错义变异（24个确定+3个VUS对照），对比薄证据（仅分子后果和群体等位基因频率）与富集证据（添加Ensembl VEP校准预测因子如REVEL、AlphaMissense）。
   - **校准实验**：在获取实验基础上，添加指令强制使用ACMG 2015强度基线（PM2为中等而非ClinGen SVI 2020的弱支持）。
   - **开权重模型**：Qwen 3.6 35B，本地部署，同样231个A层变异，1次重复。

2. **调用实验**：
   - 四个支臂：自由代理、技能推理、技能执行（调用已验证的nf-core/sarek + GATK HaplotypeCaller）、手动运行对照。
   - 预注册8个失败标签和确定性分类器。

3. **端到端归因**：
   - 仅16个chr20变异重叠（都是良性的，且被正确调用），故作为机制验证而非完整结果展示。

### 实验数量与充分性
- 解释实验：至少9个（model×condition）主细胞组，各5次重复，共约1,155次独立提示。
- 获取/校准实验：24个确定变异×5次重复×2~3个条件。
- 调用实验：每个支臂1次单样本运行。
- 充分性评价：
  - 优点：时间盲确保无污染；多模型、多条件、多重复；分层归因设计渐近。
  - 不足：开权重实验仅1次重复；调用实验仅限于chr20；端到端重叠不丰富；未使用控制刺入变异。

## 四、资源与算力

- **论文中未明确提及使用的GPU型号、数量、训练时长或总计算量**。
- 所有模型通过API（付费端点：GPT-5.2、Claude Sonnet 4.5、Gemini 2.5 Flash）或本地推理服务（Qwen 3.6 35B，冻权重）调用。
- 未提供具体硬件配置或能耗数据。

## 五、主要结论与发现

1. **安全性是受控前提条件**：危险误分类（致病性↔良性）罕见（0.3%~2.2%），且模型无关。
2. **捏造证据可被测量并通过执行中和**：在技能执行条件下，经证据合约审查后，伪装的跨模型捏造证据（0%~17%）转化为安全弃权（VUS），而非危险调用。
3. **不同变异类别受不同层限制**：
   - 功能丧失（LoF）变异：74%组合器敏感（Richards规则 vs Tavtigian点系统差异，集中在致病性/Likely致病边界）。
   - 罕见错义变异：55%证据不足（分子后果+AF不足以分类），其次是赋值不稳定和强度校准程度。
4. **获取是真实但不对称且有限制的层**：富集证据仅解决良性侧（7/24变异离开证据不足类别），而致病性侧完全无法解决（上限仅9/24）。
5. **强度赋值是可恢复层，但天真的强度许可提示脆弱**：确定性再评分（PM2从弱→中等）恢复2个致病性变异，对良性无损失；但再提示方式会使其错误应用到良性变异导致退化。
6. **信任是架构属性，而非模型属性**：在调用实验中，所有模型都能规划流程，但信任属性（固定、来源、可审计性、可重复性）沿约束梯度单调提升。
7. **开源模型再现安全性但未满足来源合约**：Qwen 3.6 35B的危险误分类率为0%，但92.6%的提交因缺失置信度字段或来源标识符被拒绝（合规性差距，非能力或安全差距）。

## 六、优点

1. **时间盲真值集**：保证测试标签在模型训练截止后才可用，消除记忆污染，提升评估可靠性。
2. **故障封闭证据合约**：阻断循环证据，使捏造证据可量化（可报告捏造率）并转化为安全状态，而非被掩盖。
3. **分层归因架构**：将单个准确率分数分解为安全、证据获取、赋值、强度校准、组合器阈值等独立可测量的层，使失败来源可定位。
4. **约束梯度设计**：逐步从模型先验移至执行、验证代码，系统化地揭示每个层对最终结果贡献。
5. **确定性组合器对比**：利用Richards规则与Tavtigian点系统分离阈值效应和证据效应，机制分析清晰。
6. **开源模型纳入**：确保框架不依赖付费端点，同时暴露了合规性差距（来源/结构化输出遵守）这一真实维度。
7. **实验可复制性**：真值集与实验脚本均发布，具有内容哈希和文件名校验和，可逐比特重现。

## 七、不足与局限

1. **实验覆盖范围有限**：
   - 调用实验仅限Y染色体20（chr20）开发试点，未提供全基因组基准。
   - 端到端归因仅16个良性重叠变异，缺少含有真正致病变异的临床队列或受控刺入。
   - 开权重实验仅1次重复，多重复再现性或更强模式诱导能否缩小合规差距未知。
2. **偏差风险**：
   - 时间盲只控制标签的记忆，不控制底层信息（如分子后果、群体频率、基因-疾病证据），这些可能仍在本前出现过。
   - 归因语料库的变异样本可能不代表所有功能丧失/错义变异分布。
   - 获取实验只针对一个模型（Claude Sonnet 4.5），虽然校准实验扩展了GPT-5.2，但仅涉及两个模型。
   - 调用实验的祖系分析仅包括欧洲、阿什肯纳兹犹太人和东亚样本，缺少非洲、南亚或印第安基因组，未形成真正的人群覆盖。
3. **统计推断力不足**：校正实验的结论是“确定性计算器算法”，而非抽样变化（只有24个确定变异，作者仅报告计数而非推断统计量）。
4. **应用限制**：该框架虽可移植到任何实验室的智能体流程，但需要模型结构化输出遵循特定的契约（如ACMG代码、置信度字段、来源标识符），目前在开源模型上严重受限。
5. **平台依赖**：前端模型实验依赖商业API，存在有限的负截断（rate-limit）和可能的隐藏节流假象（作者声称已通过指数退避和失败重试分类缓解）。

## 结论总结
ClawBench提供了一个超越单一准确率的、多维度归因框架，能系统化评估LLM在临床基因组学工作流程中的安全性与可靠性。研究发现，安全性是受控前提条件，捏造证据可被执行测量和中和，信任是架构属性而非模型属性，开源模型主要面临合规性差距而非能力差距。虽然存在范围限制（仅染色体20、开权重单次重复、缺乏致病性端到端案例），但其方法论贡献在于分离和测量导致看似相同输出背后截然不同的故障模式。

（完）
