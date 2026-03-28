---
title: "HViLM: A Foundation Model for Viral Genomics Enables Multi-Task Prediction of Pathogenicity, Transmissibility, and Host Tropism"
title_zh: HViLM：一种用于病毒基因组学的基础模型，可实现致病性、传播性和宿主趋性的多任务预测
authors: "Davuluri, R. V., Dutta, P., Vaska, J., Surana, P., Sathian, R., Chao, M., Zhou, Z., Liu, H."
date: 2026-03-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.18.712700v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 用于全病毒基因组分析的基础模型
tldr: HViLM是首个针对全病毒基因组分析的基础模型，通过在500万条病毒序列上对DNABERT-2进行持续预训练构建。该模型在HVUE基准测试的致病性、宿主趋性和传播能力预测任务中均达到SOTA水平，并展现出强大的跨家族泛化能力。研究还通过注意力机制揭示了病毒免疫逃逸的生物学机制，为应对新兴病毒威胁提供了高效的计算工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-18-712700-v1/fig-001.webp\", \"caption\": \"Table 2. Performance comparison of HViLM variants and baseline genomic foundation models on HVUE benchmark tasks. All models were fine-tuned using identical LoRA-based procedures on the same data splits. Metrics computed on held-out test sets. Bold indicates best performance per dataset. HViLM variants consistently outperform baselines across pathogenicity classification, host tropism prediction, and transmissibility assessment tasks.\", \"page\": 6, \"index\": 1, \"width\": 1025, \"height\": 825}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-18-712700-v1/fig-002.webp\", \"caption\": \"Figure 2: HViLM Identifies Host Transcription Factor Binding Site Mimicry Through Attention-Guided Motif Discovery in Pathogenic Coronaviruses. (A) AAAAAATT matches Foxq1 (1.20× local enrichment, p=3.9×10⁻¹⁰), regulating respiratory epithelial tropism. (B) TATTAA matches Irf1 (1.27× global, p=9.9×10⁻⁸), controlling interferon responses. (C) TAATAA matches ZNF354A (19 bp overlap, q=0.056), regulating immune pathways. (D) TTTTATTA motif shows robust enrichment and also matches Irf1 binding site, demonstrating convergent evolution of independent sequences for immune evasion. Dark blue shading indicates high-attention regions; sequence logos show MEMEderived viral motifs aligned with JASPAR vertebrate transcription factor consensus sequences.\", \"page\": 9, \"index\": 2, \"width\": 1014, \"height\": 470}]"
motivation: 现有的病毒风险评估方法多针对特定病毒且需重复训练，难以快速应对新兴病毒在全球健康领域的威胁。
method: 在涵盖45个病毒家族的500万条非冗余序列上预训练HViLM模型，并利用LoRA微调技术在HVUE基准上进行多任务评估。
result: "模型在致病性、宿主趋性和传播性预测中分别达到95.32%、96.25%和97.36%的准确率，显著优于现有基准模型。"
conclusion: HViLM作为一种通用的病毒基因组基础模型，能够有效捕捉生物学特征并实现跨病毒家族的精准风险评估。
---

## 摘要
动机：新型病毒病原体的出现对全球健康构成了严重威胁，然而目前的病毒风险评估计算方法主要针对特定病毒，且针对每种新威胁都需要进行大量的重新训练。迫切需要能够跨多个流行病学相关维度（致病性、宿主趋性和传播性）快速表征新兴病毒的计算方法，以为公共卫生响应提供信息并指导实验优先级的确定。

结果：我们提出了 HViLM（人类病毒组语言模型），这是首个用于全病毒基因组分析的基础模型。该模型通过在来自 VIRION 数据库、涵盖 45 个以上病毒科、9,000 个物种的 500 万条非冗余病毒序列（由 2500 万个片段在 80% 恒等性下经 MMseqs2 聚类而成）上对 DNABERT-2 进行持续预训练而构建。我们引入了人类病毒组理解评估（HVUE）基准，该基准包含跨三个预测任务（致病性分类、宿主趋性预测和传播性评估）的七个精选数据集。通过使用 LoRA 进行参数高效微调，HViLM 实现了最先进的性能，致病性、宿主趋性和传播性评估的平均准确率分别达到 95.32%、96.25% 和 97.36%。该模型展示了强大的跨科泛化能力，显著优于序列相似性基线和通用基因组基础模型。基于注意力的可解释性分析表明，HViLM 通过宿主调节元件的分子模拟捕捉到了具有生物学意义的致病性决定因素，包括针对干扰素调节因子 1 (Irf1) 以实现免疫逃逸的八个独立序列的趋同演化。

可用性：HVUE 基准数据集、训练脚本和完整实现可在 https://github.com/duttaprat/HViLM 公开获取。预训练的 HViLM-base 模型权重和微调后的任务特定变体可在 Hugging Face 获取，地址为 https://huggingface.co/duttaprat/HViLM-base。

补充信息：补充数据可在网上查阅。

## Abstract
MotivationThe emergence of novel viral pathogens poses critical threats to global health, yet current computational approaches for viral risk assessment are predominantly virus-specific and require extensive retraining for each new threat. Computational methods for rapid characterization of emerging viruses across multiple epidemiologically relevant dimensions--pathogenicity, host tropism, and transmissibility--are urgently needed to inform public health responses and guide experimental prioritization.

ResultsWe present HViLM (Human Virome Language Model), the first foundation model for panviral genomic analysis through continued pre-training of DNABERT-2 on 5 million non-redundant viral sequences (MMseqs2-clustered from 25 million chunks at 80% identity) spanning 9,000 species across 45+ viral families from the VIRION database. We introduce the Human Virome Understanding Evaluation (HVUE) benchmark comprising seven curated datasets across three prediction tasks: pathogenicity classification, host tropism prediction, and transmissibility assessment. Through parameter-efficient fine-tuning with LoRA, HViLM achieves state-of-the-art performance with average accuracies of 95.32% for pathogenicity, 96.25% for host tropism, and 97.36% for transmissibility assessment. The model demonstrates robust cross-family generalization, substantially outperforming sequence-similarity baselines and general genomic foundation models. Attention-based interpretability analysis reveals that HViLM captures biologically meaningful pathogenicity determinants through molecular mimicry of host regulatory elements, including convergent evolution of eight independent sequences targeting Interferon Regulatory Factor 1 (Irf1) for immune evasion.

AvailabilityThe HVUE benchmark datasets, training scripts, and complete implementation are publicly available at https://github.com/duttaprat/HViLM. Pre-trained HViLM-base model weights and fine-tuned task-specific variants are available on Hugging Face at https://huggingface.co/duttaprat/HViLM-base.

Supplementary informationSupplementary data are available online.

---

## 论文详细总结（自动生成）

这篇论文介绍了 **HViLM**（Human Virome Language Model），这是首个专门针对全病毒基因组分析的大规模基础模型。以下是对该研究的深度结构化总结：

### 1. 核心问题与整体含义
*   **研究背景**：新型病毒（如 SARS-CoV-2）的出现对全球公共卫生构成持续威胁。
*   **核心问题**：现有的病毒风险评估工具通常是“病毒特异性”的（仅针对某一类病毒），且在面对新发病毒时需要重新训练，缺乏泛化能力。
*   **整体含义**：研究者旨在构建一个通用的病毒基因组基础模型，能够跨越不同的病毒科，快速预测病毒的致病性、宿主趋性和传播能力，为公共卫生预警提供计算支撑。

### 2. 方法论
*   **核心思想**：利用大规模未标记的病毒基因组数据进行“持续预训练”（Continued Pre-training），使模型掌握病毒序列的通用生物学特征，再通过微调适配具体任务。
*   **关键技术细节**：
    *   **基础架构**：基于 **DNABERT-2**（一种基于 Transformer 的基因组语言模型）。
    *   **预训练数据**：从 VIRION 数据库中提取了涵盖 45 个以上病毒科、9,000 个物种的 2500 万条基因组片段。
    *   **数据去冗余**：使用 **MMseqs2** 算法在 80% 序列恒等性下进行聚类，最终获得 500 万条非冗余序列进行训练。
    *   **微调技术**：采用 **LoRA**（低秩自适应）技术进行参数高效微调，在保持基础模型知识的同时，以极小的计算开销适配下游任务。
    *   **可解释性**：利用注意力机制（Attention Maps）识别病毒序列中的关键基序（Motifs），并将其与已知转录因子结合位点进行比对。

### 3. 实验设计
*   **基准测试 (Benchmark)**：引入了 **HVUE**（人类病毒组理解评估）基准，包含 7 个精选数据集。
*   **预测任务**：
    1.  **致病性分类**：区分人类病原体与非人类病原体。
    2.  **宿主趋性预测**：预测病毒倾向于感染人类还是动物。
    3.  **传播性评估**：区分高传播力与低传播力病毒。
*   **对比方法**：
    *   通用基因组基础模型：DNABERT-2、Nucleotide Transformer (NT)、HyenaDNA。
    *   传统基准：基于序列相似性的方法（如 BLAST 变体）。

### 4. 资源与算力
*   **算力说明**：论文摘要和核心内容中未明确列出具体的 GPU 型号、数量或总训练时长。但考虑到 500 万条序列的持续预训练规模，通常需要工业级计算集群（如多节点 A100 或 H100 服务器）。
*   **开源资源**：作者公开了 HVUE 数据集、训练脚本、HViLM-base 模型权重以及微调后的任务模型（托管于 GitHub 和 Hugging Face）。

### 5. 实验数量与充分性
*   **实验规模**：涵盖了 3 大类任务、7 个数据集，涉及 45+ 病毒科。
*   **充分性**：
    *   **跨科泛化实验**：验证了模型在未见过的病毒科上的表现，证明了其强大的泛化能力。
    *   **消融/对比实验**：将 HViLM 与多种主流基因组大模型进行了同口径对比（均使用 LoRA 微调），确保了比较的公平性。
    *   **生物学验证**：通过注意力机制发现的基序与 JASPAR 数据库中的转录因子匹配，增强了实验结果的客观性和生物学可信度。

### 6. 主要结论与发现
*   **性能领先**：HViLM 在致病性（95.32%）、宿主趋性（96.25%）和传播性（97.36%）预测上均达到 SOTA（最先进）水平。
*   **跨家族泛化**：模型能够有效识别新发病毒的风险，即使这些病毒与训练集中的序列差异较大。
*   **生物学机制揭示**：模型识别出病毒通过“分子模拟”宿主调节元件（如 Irf1 干扰素调节因子结合位点）来实现免疫逃逸的现象，这解释了其高致病性的来源。

### 7. 优点
*   **首创性**：填补了全病毒基因组通用基础模型的空白。
*   **高效性**：通过 LoRA 微调，使得下游应用不需要昂贵的计算资源即可实现高性能。
*   **可解释性强**：不仅给出了预测结果，还通过注意力机制定位了具有生物学意义的基因基序，实现了“白盒化”。

### 8. 不足与局限
*   **数据偏差风险**：尽管使用了去冗余技术，但 VIRION 数据库本身可能存在采样偏差（研究较多的病毒序列更多），可能影响模型对罕见病毒的判断。
*   **长序列限制**：虽然 DNABERT-2 优化了长度处理，但对于极长的病毒基因组，Transformer 的上下文窗口限制仍可能导致部分全局信息的丢失。
*   **实验验证**：目前发现的免疫逃逸基序主要基于计算推断，尚需进一步的湿实验（Wet-lab）验证其功能。

（完）
