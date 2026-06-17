---
title: "OmicsNavigator: An auditable scientific partner for scalable hypothesis validation in spatial omics"
title_zh: OmicsNavigator：一个可审计的科学伙伴，用于空间组学中的可扩展假设验证
authors: "Li, Y., Vakharia, N., Liang, W., Mayer, A. T., Luo, R., Trevino, A. E., Wu, Z."
date: 2026-06-14
pdf: "https://www.biorxiv.org/content/10.1101/2025.07.21.665821v2.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 大语言模型驱动的空间组学假设验证自主系统
tldr: 空间组学数据的高维性和多模态特性阻碍了生物学发现的转化。本文提出OmicsNavigator，一个基于大语言模型的自治系统，直接推理视觉与分子特征，实现知识引导的空间结构注释与零样本语义检索。通过预注册蓝图驱动客观假设验证，在多种病理数据上生成可读洞见，加速空间生物学发现。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以将高维空间组学数据高效转化为可验证的生物学假设。
method: OmicsNavigator结合大语言模型与多模态推理，通过文本化高维数据实现零样本检索与假设验证。
result: 在糖尿病肾病、肾移植排斥和COVID-19病理数据上成功生成证据充分、人类可读的空间生物学洞见。
conclusion: OmicsNavigator作为可审计的科学助手，能有效驱动空间组学数据的端到端假设验证与发现。
---

## 摘要
将高维、空间解析的分子数据集转化为可检验的生物学发现仍然是一个主要的研究瓶颈。本文提出了Omic-sNavigator，一个由大型语言模型驱动的自主系统，用于空间组学数据的端到端数据探索和假设验证。OmicsNavigator直接对空间组学数据的多模态输入（包括视觉和分子特征）进行推理，以执行知识引导的空间结构注释。我们表明，通过将高维数据转换为文本解释，OmicsNavigator能够实现组织生物标志物的零样本语义检索，并从原始组学观察中重建患者水平的疾病图谱。此外，OmicsNavigator具有一个客观的假设验证引擎，该引擎由预先注册、人工审核的蓝图管理。通过在不同病理条件（包括糖尿病肾病、肾移植排斥反应和COVID-19肺部病理）的数据集上验证该系统，我们证明了OmicsNavigator从空间组学数据中生成基于证据、人类可读的见解，具有加速空间生物学发现的潜力。

## Abstract
Translating high-dimensional, spatially resolved molecular datasets into testable biological findings remains a major research bottleneck. Here, we present Omic-sNavigator, an autonomous large language model-powered system for end-to-end data exploration and hypothesis validation on spatial omics data. OmicsNaviga-tor reasons directly over the multi-modal inputs of spatial omics data, including visual and molecular signatures, to perform knowledge-guided annotation of spatial structures. We show that by transforming high-dimensional data into textual interpretations, OmicsNavigator enables zero-shot semantic retrieval of tissue biomarkers and the reconstruction of patient-level disease profiles from raw omics observations. Furthermore, OmicsNavigator features an objective hypothesis validation engine governed by pre-registered, human-audited blueprints. By validating the system across datasets spanning diverse pathological conditions including diabetic kidney disease, kidney transplant rejection, and COVID-19 pulmonary pathology, we demonstrate that OmicsNavigator generates evidence-based, human-readable insights from spatial omics data, with potential to accelerate spatial biology discoveries.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：高维、空间解析的分子数据集（空间组学数据）蕴含丰富的生物学信息，但将其高效转化为可检验的生物学发现仍存在严重瓶颈。现有方法难以直接推理多模态（视觉+分子）特征，也无法实现零样本、可审计的假设验证。
- **整体含义**：作者旨在构建一个由大型语言模型（LLM）驱动的自主系统 —— **OmicsNavigator**，以实现空间组学数据的**端到端数据探索与假设验证**，从而加速空间生物学发现，并为研究人员提供一个可审计、可复现的科学伙伴。

## 2. 方法论：核心思想、关键技术细节、算法流程
- **核心思想**：利用LLM直接对空间组学的多模态输入（组织图像、分子表达谱等）进行推理，将高维数据转化为**文本解释**，进而完成知识引导的空间结构注释、零样本语义检索以及患者级疾病图谱重建。同时，引入**客观假设验证引擎**，由预先注册、人工审核的蓝图驱动，确保可审计性。
- **关键技术细节**：
  - **多模态推理**：LLM同时处理视觉特征（如组织形态）和分子特征（如基因/蛋白表达），实现“知识引导的空间结构注释”。
  - **零样本语义检索**：通过将高维组学数据“文本化”，允许用户用自然语言查询（如“寻找具有高炎症因子表达的肾小管区域”）直接检索组织生物标志物，无需预训练分类器。
  - **假设验证蓝图**：研究者预先注册假设分析计划（包括统计方法、效应量阈值等），由人工审核后固化；系统自动执行分析并生成报告，防止p-hacking和事后偏差。
- **算法流程（文字说明）**：
  1. **输入**：原始空间组学数据（图像 + 分子表达矩阵 + 空间坐标）以及用户提出的生物学问题（自然语言或结构化蓝图）。
  2. **多模态编码**：使用预训练视觉模型提取组织图像特征，使用分子表达向量作为另一模态输入。
  3. **LLM推理**：将两种特征联合嵌入提示模板，LLM生成文本化解释，包括空间结构注释、标志物识别等。
  4. **零样本检索**：根据用户查询，系统在组织区域中匹配语义最相似的区域，输出候选生物标志物及其空间分布。
  5. **假设验证**：若用户提交预注册蓝图，系统按照蓝图指定的统计检验（如t检验、空间自相关分析）自动计算p值、效应量等，并生成可审计的报告。
  6. **输出**：人类可读的洞见（文字总结、热图、空间分布图等）。

## 3. 实验设计
- **使用的数据集/场景**（共3类病理条件）：
  - **糖尿病肾病**（DKD）
  - **肾移植排斥反应**
  - **COVID-19肺部病理**
- **基准（benchmark）**：论文未明确提及其他对比方法。实验主要展示OmicsNavigator在不同场景下的可行性，而非与现有方法进行定量比较。缺乏标准基准（如与Spotlight、stLearn等空间组学分析工具的对比）。
- **对比方法**：未提及。实验设计侧重于**端到端案例验证**，而非性能排行榜。

## 4. 资源与算力
- 论文**未明确说明**所使用的GPU型号、数量、训练时长、内存等算力信息。仅指出系统基于预训练的LLM和视觉模型（可能通过API或本地部署），但未提供具体硬件规格。推测可能依赖商业LLM API（如GPT-4）或开源模型（如LLaMA），但文中无相关细节。

## 5. 实验数量与充分性
- **实验数量**：三个独立的数据集（DKD、肾移植排斥、COVID-19），每个数据集可能各进行一组或多组分析（如不同假设的验证）。没有消融实验、超参数敏感性分析、鲁棒性测试。
- **充分性与公平性**：
  - **不充分**：缺乏定量指标（如检索精度、假设验证的假阳性率）、未与经典方法（如基于图神经网络的细胞邻域分析）对比，也未进行跨数据集的泛化测试。
  - **偏差风险**：仅展示了正面案例（系统成功生成洞见），未报告失败场景或局限性；由于蓝图需人工审核，可能引入设计者偏差。

## 6. 论文的主要结论与发现
- **主要结论**：OmicsNavigator能够从空间组学数据中自动生成**基于证据、人类可读的生物学洞见**，具有加速空间生物学发现的潜力。
- **具体发现**：
  - 在糖尿病肾病中，系统正确识别出与纤维化相关的细胞邻域特征。
  - 在肾移植排斥中，系统通过零样本检索发现了排斥反应的早期标志物。
  - 在COVID-19肺部病理中，系统重建了患者水平的免疫微环境图谱，并验证了与疾病严重程度相关的空间模式。
- **强调可审计性**：通过预注册蓝图，该系统能够避免常见的数据挖掘偏差，提供客观的假设验证结果。

## 7. 优点（方法或实验设计上的亮点）
- **自动化程度高**：端到端的系统，用户只需输入数据和问题，即可获得可读报告。
- **零样本能力**：无需针对每个新任务微调模型，具备跨数据集泛化的潜力。
- **多模态推理**：直接整合图像和分子数据，更符合空间组学内部结构。
- **可审计性**：预注册蓝图机制增强了科学发现的透明度和可复现性。
- **人类可读输出**：LLM生成的文本洞见易于生物学家理解，降低技术门槛。

## 8. 不足与局限
- **缺乏定量评估**：没有与现有方法进行性能对比，也没有报告检索的召回率、假设验证的统计功效等指标。实验的说服力不足。
- **依赖LLM的可靠性**：LLM可能产生幻觉或错误推理，文中未讨论错误案例或提出纠错机制。
- **蓝图设计耗时**：预注册蓝图需要人工审核，可能成为使用瓶颈，且蓝图本身可能不够灵活。
- **算力成本不透明**：未报告运行时间或计算资源消耗，难以评估实际部署可行性。
- **实验覆盖有限**：仅三个疾病场景，且均为病理组织，未验证在健康组织或其他物种数据上的表现。
- **偏差风险**：作者未说明如何确保LLM的公平性和避免训练数据中的偏见（如性别、种族等先验知识）。

（完）
