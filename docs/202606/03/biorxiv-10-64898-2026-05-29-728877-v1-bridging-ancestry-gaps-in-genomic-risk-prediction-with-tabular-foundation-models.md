---
title: Bridging Ancestry Gaps in Genomic Risk Prediction with Tabular Foundation Models
title_zh: 使用表格基础模型弥合基因组风险预测中的祖先差距
authors: "Das, A., Cui, Y."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.29.728877v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 采用上下文学习的表格基础模型改进跨祖先基因组风险预测
tldr: 基因组风险预测模型在不同祖先群体中表现不均，主要由于样本不平衡和效应异质性。本研究利用具有上下文学习能力的表格基础模型，通过指令微调框架使模型适应祖先依赖的非平稳效应，显著提升了欠采样祖先群体的预测性能。指令微调后的模型在整个祖先连续谱上实现了更稳定和更优的预测，尤其对远离上下文示例的个体效果显著。该工作为构建更公平的基因组预测模型提供了新思路。
source: biorxiv
selection_source: fresh_fetch
motivation: 基因组风险预测模型因祖先群体样本不平衡和效应非平稳性导致性能不均，限制了临床实用性。
method: 采用具有上下文学习能力的表格基础模型，并引入指令微调框架处理祖先依赖的非平稳效应。
result: 指令微调模型在欠采样祖先群体中预测性能更优，且在整个祖先连续谱上更稳定。
conclusion: 指令微调策略能有效提升表格基础模型在多样祖先群体中的泛化能力，促进公平基因组预测。
---

## 摘要
动机：用于疾病基因组预测的模型在不同人群中的表现不均，限制了临床实用性。两个因素导致了这一限制：不同祖先群体的样本可用性严重失衡，以及基因型-表型效应大小在祖先连续谱上的非平稳性。尽管具有上下文学习（ICL）能力的表格基础模型在其他领域显示出强大的样本效率，但它们对基因型到表型预测的有效性以及对祖先驱动效应异质性的鲁棒性仍不明确。结果：利用大规模、祖先多样化的生物库数据，我们展示了与传统的监督方法相比，具有ICL能力的表格基础模型减少了在采样不足的祖先群体中的性能下降。然而，我们发现，当等位基因效应大小在祖先空间内变化时，现有基于合成表格任务训练的模型会失效。将遗传祖先视为连续变量，我们引入了一种指令微调框架，该框架使模型暴露于具有祖先依赖的非平稳效应的合成任务中。经过指令微调的模型在遗传祖先连续谱上（包括在祖先空间中远离上下文范例的个体）实现了更好且更稳定的预测性能。

## Abstract
Motivation: Models deployed for genomic prediction of diseases perform unevenly across populations, limiting clinical utility. Two factors drive this limitation: large imbalances in sample availability across ancestry groups and non-stationarity of genotype-phenotype effect sizes across the ancestry continuum. While tabular foundation models with in-context learning (ICL) have shown strong sample efficiency in other domains, their effectiveness for genotype-to-phenotype prediction and their robustness to ancestry-driven effect heterogeneity remain unclear. Results: Using large, ancestrally diverse biobank data, we show that ICL-capable tabular foundation models reduce performance degradation in under-sampled ancestry groups compared to conventional supervised approaches. However, we find that prevailing models trained on existing synthetic tabular tasks fail when allele effect sizes vary across ancestry space. Treating genetic ancestry as a continuous variable, we introduce an instruction-tuning framework that exposes models to synthetic tasks with ancestry-dependent non-stationary effects. Instruction-tuned models achieve improved and more stable predictive performance across the genetic ancestry continuum, including for individuals distant from in-context exemplars in ancestry space.

---

## 论文详细总结（自动生成）

好的，根据您提供的论文摘要和元数据信息，以下是对该论文的结构化、详细中文总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：基因组风险预测模型（如多基因风险评分）在不同祖先群体间表现不均衡，严重限制了其临床实用性。
- **驱动因素**：一是不同祖先群体的样本可用性严重失衡（采样偏差）；二是基因型-表型效应大小在祖先连续谱上呈现非平稳性（即效应异质性，同一遗传变异在不同祖先背景下的效应不同）。
- **研究动机**：探索新兴的**表格基础模型（Tabular Foundation Models）**，特别是具备**上下文学习（In-Context Learning, ICL）**能力的模型，能否通过其强大的样本效率，来缓解上述跨祖先预测偏差问题，并提升在欠采样祖先群体中的预测性能。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：将遗传祖先视为连续变量，利用表格基础模型的上下文学习能力，并引入**指令微调（Instruction Tuning）**框架，使模型适应祖先依赖的非平稳效应。
- **关键步骤**：
    1. 基线模型：使用具有上下文学习能力的表格基础模型（如TabPFN等），基于大规模祖先多样化生物库数据训练/推理。
    2. 发现缺陷：传统合成表格任务训练的基础模型，在等位基因效应随祖先空间变化时表现失效。
    3. 指令微调框架：
        - 生成**合成任务**，这些任务明确包含祖先依赖的非平稳效应（即效应大小随祖先连续谱变化）。
        - 通过指令（instruction）形式，将祖先信息（如遗传主成分）作为上下文的一部分输入模型。
        - 模型在微调过程中学会利用上下文中的祖先信息，动态调整预测，从而对远离训练样本的祖先个体也能保持稳定预测。
- **技术细节**：未提供具体公式或算法伪代码，但核心是“暴露祖先依赖的非平稳合成任务”进行微调，与监督学习（如线性混合模型、LASSO回归、神经网络等）形成对比。

### 3. 实验设计
- **数据集**：使用了**大规模、祖先多样化的生物库数据**（文中未明确具体生物库名称，如UK Biobank、All of Us等，但从“large, ancestrally diverse biobank data”推断）。
- **基准（Benchmark）**：对比了**传统的监督方法**（未明确列出具体方法，如PRS-CS、LDpred2、Polygenic Risk Score基于弹网回归等常见方法）以及**现有基于合成表格任务训练的ICL表格基础模型**（未经指令微调的版本）。
- **评估场景**：
    - 在欠采样祖先群体上的性能下降。
    - 在整个遗传祖先连续谱上的预测稳定性和准确性。
    - 对于祖先空间上远离上下文示例的个体的预测性能。
- **对比方法**：主要对比了传统监督方法和未经指令微调的表格基础模型。

### 4. 资源与算力
- **文中未明确说明**使用了多少GPU型号、数量、训练时长等算力信息。仅从摘要无法获知，需要参考原论文正文的“方法”或“实验设置”部分。这里无法补充，只能指出信息缺失。

### 5. 实验数量与充分性
- **实验数量**：摘要仅描述了高维度的实验逻辑，未给出具体实验组数（如不同祖先分层、不同疾病表型、不同超参数等）。实际论文可能包含多组消融实验（如有无指令微调、不同合成任务生成策略、不同模型初始化等）。
- **充分性评估**：从摘要推断，实验旨在验证两大方面：（1）ICL表格基础模型相对于传统方法的优势；（2）指令微调框架解决效应非平稳性的有效性。但缺乏定量结果（如AUC、R²提升百分比等），因此无法直接判断实验是否充分、客观、公平。需阅读全文才能确认是否存在数据泄露、测试集划分是否严格、是否使用了多个独立数据集等。

### 6. 论文的主要结论与发现
- **主要结论**：
    1. 具有ICL能力的表格基础模型相比传统监督方法，**能减少在采样不足祖先群体中的性能下降**（体现样本效率优势）。
    2. 现有基于合成表格任务训练的表格基础模型，**在等位基因效应随祖先空间变化（非平稳性）时会失效**。
    3. 提出的**指令微调框架**能有效处理祖先依赖的非平稳效应，使模型在整个遗传祖先连续谱上取得**更好且更稳定的预测性能**，包括对于远离上下文示例的个体。
- **发现**：该工作表明了**指令微调 + 上下文学习**在公平基因组预测中的潜力，为构建更公平的跨祖先预测模型提供了新思路。

### 7. 优点
- **方法创新**：首次将指令微调与表格基础模型结合，用于处理基因组预测中的跨祖先效应异质性，思路新颖。
- **问题针对性**：直接针对“样本不平衡”和“效应非平稳性”两大痛点，而非仅仅依赖数据扩增。
- **理论意义**：为使用基础模型解决生物医学公平性问题提供了范例，有助于推动个性化医疗。
- **简洁高效**：利用上下文学习避免了对每个祖先群体单独训练模型，降低了计算开销（理论上）。

### 8. 不足与局限
- **信息不充分**：仅靠摘要无法评估实验的完整性和鲁棒性。例如，未披露使用的具体数据集、表型类型、效应大小建模方式、消融实验等。
- **可重复性受限**：未提供代码、模型权重、合成任务生成细节，实际应用可重复性未知。
- **临床落地距离**：仅在生物库数据上验证，未提及真实临床场景的测试（如前瞻性队列、不同族裔确认），且模型的可解释性可能较弱（基础模型黑盒问题）。
- **效应异质性的刻画**：摘要假设效应随祖先连续谱平滑变化，但真实遗传结构可能更复杂（如局部不适应、基因-环境交互），指令微调是否能泛化到其他形式的异质性需进一步验证。
- **计算成本**：虽然样本效率高，但指令微调和上下文推理本身可能消耗大量内存和显存（尤其大规模生物库数据），实际算力需求未说明。

（完）
