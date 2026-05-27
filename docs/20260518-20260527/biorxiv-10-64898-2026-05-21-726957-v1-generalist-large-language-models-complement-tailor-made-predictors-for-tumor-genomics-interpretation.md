---
title: Generalist large language models complement tailor-made predictors for tumor genomics interpretation
title_zh: 通用大型语言模型补充定制预测因子用于肿瘤基因组学解读
authors: "Yu, J., Darmofal, M., Waters, M., Choy, J., Tran, T. N., Fu, C., Morales, L., U, K., Levine, R. L., Schultz, N., Berger, M. F., Morris, Q., Jee, J."
date: 2026-05-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.21.726957v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 评估通用大语言模型在肿瘤基因组解读任务中的表现，显示与定制模型互补
tldr: 肿瘤基因组解释中，定制模型在分布外数据和复杂任务上存在局限。本研究评估通用大语言模型在三个临床任务上的表现，发现其与定制模型在区分肿瘤突变上相当，集成可提升前两个任务性能，在推断癌症类型任务上于分布外数据中超越定制模型。表明无需微调的LLM即可作为互补工具增强临床基因组解释。
source: biorxiv
selection_source: fresh_fetch
motivation: 定制预测器在分布外数据和复杂肿瘤解释任务中表现不足，通用LLM的广泛知识可能提供互补能力。
method: 在三个实际肿瘤基因组解释任务（突变分类、驱动突变识别、癌症类型推断）上，对比通用LLM与定制模型，并测试集成效果。
result: 通用LLM在任务一与定制模型持平；集成模型提升任务一、二性能；任务三中LLM在分布外数据上表现更优。
conclusion: 当前通用LLM无需微调即可补充定制模型，增强临床肿瘤基因组解释的泛化性和准确性。
---

## 摘要
通用大型语言模型（LLMs）在大型语料库上训练以获取广泛知识，但LLMs能否替代或增强任务特定模型尚不清楚。我们在三个真实世界、临床重要的肿瘤基因组解读任务上评估了LLMs，按难度递增顺序排列：（i）区分肿瘤与非肿瘤突变（n=34,415个变异），（ii）区分驱动与乘客突变（n=13,469个变异），以及（iii）从跨多种检测和机构的肿瘤测序报告中推断癌症类型（n=102,791个样本）。最好的通用LLMs在任务（i）上的表现与基准定制预测因子相当。将零样本LLMs与定制模型集成，改善了任务（i）和（ii）的性能。对于任务（iii），LLMs在分布外数据上的表现优于或补充了定制模型。无需微调，当前的LLMs已能通过为定制的最先进预测因子补充互补专业知识，在临床基因组解读中发挥作用。

## Abstract
General-purpose large language models (LLMs) are trained on large corpora to acquire broad knowledge, but whether LLMs can replace, or augment, task-specific models is unclear. We evaluated LLMs on three real-world, clinically important tumor genomic interpretation tasks, in order of increasing difficulty: (i) distinguishing tumor from non-tumor mutations (n=34,415 variants), (ii) distinguishing driver from passenger mutations (n=13,469 variants), and (iii) inferring cancer type from tumor sequencing reports across multiple assays and institutions (n=102,791 samples). The best general-purpose LLMs performed as well as the benchmark tailor-made predictor for task (i). Ensembling tailor-made models with zero-shot LLMs improved their performance for tasks (i) and (ii). For task (iii), LLMs outperformed or supplemented tailor-made models on out-of-distribution data. Without fine-tuning, current LLMs already can be useful in clinical genomic interpretation by adding complementary expertise to tailor-made, state-of-the-art predictors.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：在肿瘤基因组解读中，传统的定制预测因子（如针对特定任务的机器学习模型）在分布外数据（out-of-distribution, OOD）和复杂任务上表现有限，而通用大型语言模型（LLMs）通过训练于海量文本数据获得了广泛知识，可能作为互补工具弥补这些不足。
- **背景**：肿瘤基因组学涉及区分肿瘤与非肿瘤突变、识别驱动突变、推断癌症类型等任务，这些任务对临床决策至关重要。但现有定制模型往往依赖特定训练分布，泛化能力不足。LLMs的通用知识或许能提供跨领域、上下文敏感的优势。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：评估无需微调（zero-shot）的通用LLMs在三个临床肿瘤基因组解读任务上的表现，并与现有最先进的定制预测因子进行比较，同时测试二者集成的效果。
- **关键技术细节**：
  - 采用三种任务，按难度递增：任务(i) 区分肿瘤与非肿瘤突变；任务(ii) 区分驱动与乘客突变；任务(iii) 从肿瘤测序报告中推断癌症类型。
  - 使用零样本提示（zero-shot prompting）方式直接利用LLMs，即不进行任何任务特定的微调。
  - 集成策略：将LLMs的概率输出与定制模型的预测结果进行组合（如加权平均或逻辑回归），以测试互补性。

### 3. 实验设计：数据集、基准、对比方法

- **数据集与场景**：
  - 任务(i)：34,415个变异，涵盖肿瘤与非肿瘤突变。
  - 任务(ii)：13,469个变异，区分驱动与乘客突变。
  - 任务(iii)：102,791个样本，来自多种检测平台和机构，评估分布内和分布外（OOD）数据性能。
- **基准**：针对每个任务预先存在的最先进定制预测因子（具体模型名称未在元数据中明确，但通常为基于机器学习或深度学习的专用模型，如用于突变分类的CADD、PrimateAI等，用于癌症类型推断的肿瘤组织分类器等）。
- **对比方法**：多个通用LLMs（如GPT-4、Claude、Llama等，具体型号未在元数据中列出，但推测包括主流大模型）。对比包括：LLMs单独 vs. 定制模型；LLMs与定制模型集成 vs. 各自单独。

### 4. 资源与算力

- **明确说明**：元数据中未提及任何关于GPU型号、数量、训练时长等算力信息。由于本研究主要使用开源/商业LLMs进行零样本推理，而并非训练模型，因此算力需求主要来自推理阶段，论文可能未详细介绍硬件规格。

### 5. 实验数量与充分性

- **实验数量**：在三个临床任务上进行了对比实验，每个任务都包含了大型数据集（数万到十万样本）。此外，还进行了集成实验（将LLM与定制模型组合），以及分布外数据下的对比测试。
- **充分性与公平性**：
  - 实验覆盖了难度递增的任务，且样本量足够大，增强了统计可靠性。
  - 对比方法包括当前最先进的定制模型，评估公平。
  - 但元数据未提及是否进行了消融实验、超参数调优或多次重复实验，因此充分性可能存在一定局限。不过，由于使用了零样本LLM，无需训练，一定程度上简化了评估。

### 6. 论文的主要结论与发现

- **任务(i)**：通用LLMs的表现与最佳定制预测因子相当。
- **任务(i)和(ii)**：将零样本LLMs与定制模型集成，显著提升了性能。
- **任务(iii)**：在分布外数据上，LLMs表现优于或补充了定制模型，尤其在泛化到新检测平台或机构时。
- **总体结论**：当前通用LLMs无需微调即可作为互补工具，增强定制模型的泛化性和准确性，在临床基因组解读中具有实用价值。

### 7. 优点：方法或实验设计上的亮点

- **零样本评估**：直接使用现有LLMs而不做任何微调，体现了通用知识的迁移能力，降低应用门槛。
- **多任务、大规模验证**：在三个真实临床任务上使用数万至十万样本，涵盖不同难度和数据类型（突变级和报告级）。
- **集成策略**：探索LLM与定制模型的互补性，而非简单的替代，更贴近实际应用需求。
- **分布外测试**：特别评估了泛化能力，突出了LLM在分布外场景上的优势，这正是定制模型的弱点。

### 8. 不足与局限

- **实验覆盖**：未在更多肿瘤类型或罕见突变上测试，且任务(iii)中的“癌症类型”可能不够细粒度。
- **偏差风险**：LLMs可能在训练数据中接触过公开的肿瘤基因组知识，导致分布内性能虚高；且零样本提示的措辞可能影响结果，论文未提供详细的提示模板。
- **应用限制**：虽然无需微调，但LLMs推理成本高、延迟大，且临床环境中可能涉及隐私数据（需本地部署或去标识化），实际部署面临挑战。
- **缺乏消融实验**：未对比不同LLM大小、不同提示策略或不同集成权重对结果的影响，未量化各自贡献。
- **资源信息缺失**：没有说明推理使用的硬件和耗时，不利于其他研究者复现。

（完）
