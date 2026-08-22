---
title: Automating scientific annotations for open transcriptomic profiles via multi-stage agents
title_zh: 通过多阶段智能体实现开放转录组谱的自动化科学注释
authors: "Zhang, X., Paithankar, S., Pu, J., Murtaza, M. S., Shankar, R., Leshchiner, D., Koirala, S., Palmer, Z., Nault, R., Li, X., Xie, Y., Chen, B."
date: 2026-08-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.08.19.745739v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 基于大语言模型的多阶段智能体流程GEOMeta自动化清洗约60万GEO转录组样本元数据，是大语言模型智能体与大规模基因组模型的核心应用。
tldr: 公共转录组数据库中数百万样本的元数据异构且不一致，严重制约数据重用。GEOMeta构建了基于大语言模型的多阶段智能体工作流，将元数据检索、任务特异信息抽取、字段标准化、本体映射与质量控制分离，为约60万个人类bulk RNA-seq样本自动生成标准化注释。在性别、年龄、组织和疾病预测基准上验证了注释可用性，并前瞻性注释了最新提交的GEO研究。结果表明开源Flash模型在接近推理模型性能的同时将成本降低一个数量级，为公共组学数据提供了可扩展、可复现的注释框架。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745739-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1724, \"height\": 1438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745739-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1772, \"height\": 1447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745739-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1687, \"height\": 1327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745739-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1680, \"height\": 1531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745739-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1712, \"height\": 846, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-08-19-745739-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1564, \"height\": 1053, \"label\": \"Figure\"}]"
motivation: 公共转录组元数据异构且信息分散，阻碍大规模数据重用，亟需自动化且可扩展的注释工具。
method: 基于LLM的多阶段智能体流程，分离元数据检索、信息提取、字段标准化、本体映射与质量控制，实现端到端自动注释。
result: 为约60万人类bulk RNA-seq样本生成标准化注释，预测性别等属性有效，开源Flash模型达到高质量且成本降低一个数量级。
conclusion: GEOMeta提供可扩展的元数据资源和可复现框架，促进公共转录组数据的再利用，降低注释成本。
---

## 摘要
公共转录组数据库包含数百万个样本，然而其大规模复用受到异质且不一致报告的元数据的阻碍。在基因表达综合库（GEO）中，关键的生物学信息通常分布在研究层面和样本层面的记录中，需要依赖上下文的解读。这里我们提出了GEOMeta，一个基于大型语言模型（LLM）的多阶段工作流，配备任务专用智能体，用于自动化GEO元数据整理。该流程将元数据检索、任务特定信息提取、字段标准化、本体映射和质量控制分离开来。利用GEOMeta，我们为约60万个人类批量RNA-seq样本生成了标准化注释。为展示其效用，我们对转录组表示模型进行了基准测试，用于从转录组嵌入中预测性别、年龄、组织和疾病。我们进一步前瞻性地注释了新提交的GEO研究，并评估了22个前沿LLM。最近的开源Flash模型在注释质量上达到了与领先推理模型相当的水平，同时将成本降低了一个数量级。GEOMeta为元数据整理提供了可扩展的资源和可复现的框架。

## Abstract
Public transcriptomic repositories contain millions of samples, yet their large-scale reuse is hindered by heterogeneous and inconsistently reported metadata. In the Gene Expression Omnibus (GEO), key biological information is often distributed across study- and sample-level records, requiring context-dependent interpretation. Here we present GEOMeta, a large language model (LLM)-based multi-stage workflow with task-specialized agents for automated GEO metadata curation. The pipeline separates metadata retrieval, task-specific information extraction, field standardization, ontology mapping and quality control. Using GEOMeta, we generated standardized annotations for approximately 600,000 human bulk RNA-seq samples. To demonstrate its utility, we benchmarked transcriptome representation models for predicting sex, age, tissue and disease from transcriptome embeddings. We further prospectively annotated newly submitted GEO studies and evaluated 22 frontier LLMs. Recent open-source Flash models achieved annotation quality comparable to leading reasoning models while reducing costs by an order of magnitude. GEOMeta provides a scalable resource and reproducible framework for metadata curation.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义

- **背景**：公共转录组数据库（如GEO）存储了数百万人类样本，是生物医学研究的重要数据资源；然而这些数据的**元数据质量参差不齐、字段异质性强**，且关键生物学信息通常分散在研究层面（study-level）与样本层面（sample-level）的记录中，需要依赖上下文解读。
- **核心问题**：元数据的**异质性和不一致性**严重阻碍了大规模数据重用（如跨研究比较、元分析、深度学习模型的训练与验证）。
- **整体含义**：亟需一个**自动化、可扩展、标准化**的元数据注释管线，将海量原始、混乱的元数据转化为规范、机器可读、可挖掘的结构化注释，从而释放公共转录组数据的潜在价值。

## 2. 论文提出的方法论

- **核心思想**：利用大型语言模型构建**多阶段智能体工作流（GEOMeta）**，通过任务专用智能体将复杂的元数据整理过程分解为多个可独立优化、可质量控制的子任务。
- **算法/流程（文字描述）**：
  1. **元数据检索（Metadata Retrieval）**：从GEO数据库中自动获取研究层面和样本层面的原始元数据记录。
  2. **任务特定信息抽取（Task-Specific Information Extraction）**：由任务专用智能体从非结构化或半结构化文本中抽取目标生物学特征（如性别、年龄、组织、疾病状态）。
  3. **字段标准化（Field Standardization）**：对抽取结果进行格式统一与归一化，解决别名、缩写、大小写等异质性问题。
  4. **本体映射（Ontology Mapping）**：将标准化字段映射到受控词汇表或生物医学本体（如Uberon组织本体、疾病本体等）。
  5. **质量控制（Quality Control）**：通过规则校验、逻辑一致性检查及人工/自动抽检，确保注释准确性和可靠性。

## 3. 实验设计

- **处理数据规模**：约 **600,000 个人类 bulk RNA-seq 样本**（来自GEO）。
- **应用基准（Benchmark）**：利用GEOMeta生成的标准化注释，训练/评估**转录组表示模型**（transcriptome representation models），用于从转录组嵌入中预测以下4个生物学属性：
  - **性别**（Sex）
  - **年龄**（Age）
  - **组织**（Tissue）
  - **疾病**（Disease）
- **LLM对比评估**：在GEOMeta流程中，评估了**22个前沿大语言模型**的表现，包括专有推理模型与开源模型。
- **前瞻性验证**：对**新提交的GEO研究**进行前瞻性自动注释，验证工作流在“未来数据”上的泛化能力。
- **代表对比结论**：开源 **Flash 系列模型**在注释质量上达到与领先推理模型（如o1等）相当的水平，但**成本降低约一个数量级**。

## 4. 资源与算力

- **文中未明确报告**具体的GPU型号、GPU数量、训练时长或推理总计算量等硬件资源信息。
- 仅在成本层面指出：Flash开源模型相比顶级推理模型，注释成本降低约10倍；但未给出绝对成本数值（如美元金额或GPU小时数）。
- 需要指出的是，600k规模的元数据注释主要依赖于LLM推理而非模型训练，推理侧的计算开销未量化说明。

## 5. 实验数量与充分性

- **主要实验组**：
  1. 大规模注释实验：约60万样本的批量注释流水线运行。
  2. 4个下游预测任务（性别、年龄、组织、疾病）的转录组表示模型基准测试。
  3. 22个前沿LLM的对比评估。
  4. 对新提交GEO研究的前瞻性注释实验。
- **充分性评价**：
  - **优点**：任务覆盖了分类（性别、组织）和回归/时序（年龄）、复杂语义（疾病）多种类型，对比了22个模型，并做了前瞻性验证，实验设计较为全面。
  - **潜在不足**：缺少对错误注释的**细粒度人工评估**（如分层抽样的人工审核率）、没有明显的**消融实验**（如去掉某个阶段的效果）、对模型**幻觉风险**的定量分析也未见报告。在可获取的文本范围内，对“公平性”（如超参数设置的一致性、相同预算/温度设置等）未做详细说明。

## 6. 论文的主要结论与发现

- GEOMeta能够为约**60万人类bulk RNA-seq样本**生成高质量的标准化元数据注释，证明LLM多智能体流程在亿级数据整理任务上的可行性。
- 标准化注释可以有效支持下游转录组表示模型的训练与评估（性别、年龄、组织、疾病预测均展示应用价值）。
- **开源Flash模型在质量上接近/媲美前沿推理模型**，但推理成本降低一个数量级，表明**高性价比的开源方案**在当前元数据任务上已具备足够的实用能力。
- GEOMeta提供了一个**可复现、可扩展**的元数据整理框架与标准化数据资源，有助于加速公共转录组数据的再利用和跨研究整合。

## 7. 优点

- **模块化多阶段设计**：将元数据检索、信息抽取、标准化、本体映射和质控分离，便于各阶段的独立优化、调试与替换，显著增强流程的鲁棒性和可维护性。
- **大规模实用性验证**：在60万真实样本上完成了端到端的注释，不仅仅停留在概念验证或小型数据集，证明了系统的工程可扩展性。
- **成本意识的模型选型**：系统性地比较了22个LLM，明确展示了开源轻量级模型在成本与质量之间的优异平衡，为资源有限的科研团队提供了实际可行的方案。
- **前瞻性验证**：对新提交的GEO研究进行注释，这一设置模拟了真实部署场景，增强了对工作流泛化能力的说服力。
- **数据与代码可复现**：论文声称提供可复现框架和资源，有利于后续社区的使用与改进。

## 8. 不足与局限

- **数据覆盖范围有限**：仅覆盖GEO中的人类bulk RNA-seq样本，未涉及单细胞RNA-seq、其他物种或其他公共数据库（如ArrayExpress、SRA），结论的普适性有待验证。
- **LLM自身幻觉风险**：基于LLM的自动抽取可能产生**“看似合理实则错误”**的注释，尤其当原始元数据本身缺失、模糊或存在编造信息时；文本中未见对幻觉率的系统性量化及纠错机制。
- **基准任务的间接性**：通过“预测性别/年龄/组织/疾病”的间接方式来验证元数据质量，预测性能受转录组表示模型自身的建模能力影响，**不能完全等同于元数据注释准确性**。
- **人工审核与误差分析不足**：缺少对最终注释结果的大规模人工抽检或与金标准数据集的系统性对比（如GTEx/TCGA的已知临床元数据），质量评估的直接证据较弱。
- **缺少消融分析**：没有说明每个阶段（如本体映射、质量控制）各自对最终性能的贡献或影响，工程上无法判断哪些模块是瓶颈。
- **算力资源细节缺失**：对于运行完整管线所需的计算资源和时间开销未作量化，不利于其他研究者在类似规模上复现。

（完）
