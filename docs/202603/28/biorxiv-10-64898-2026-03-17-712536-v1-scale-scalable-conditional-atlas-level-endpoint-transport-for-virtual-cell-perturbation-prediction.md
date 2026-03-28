---
title: "SCALE: Scalable Conditional Atlas-Level Endpoint transport for virtual cell perturbation prediction"
title_zh: SCALE：用于虚拟细胞扰动预测的可扩展条件图谱级终点传输模型
authors: "Chen, S., Yu, L., Jin, K., Zhang, S., Wu, H., Xu, S., Qian, Q., Chen, Q., Bai, L., Sun, S., Gao, Z."
date: 2026-03-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.17.712536v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于虚拟细胞扰动预测的大规模基础模型
tldr: 本研究针对虚拟细胞扰动预测中训练效率低、高维建模不稳定及评估标准不完善的问题，提出了大规模基础模型SCALE。该模型基于BioNeMo框架显著提升了数据吞吐量，并采用结合LLaMA编码与端点监督的集合感知流架构，将预测建模为条件传输。实验表明，SCALE在保持高训练效率的同时，显著提升了生物学指标的预测精度，为大规模细胞实验模拟提供了高效且可靠的工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-17-712536-v1/fig-001.webp\", \"caption\": \"Table 1 | Benchmark for few-shot results on Tahoe-100M, PBMC and Replogle datasets under the Cell Eval metric protocol. Rows marked by † denote results reproduced in our implementation; all unmarked results are taken from PerturbDiff. Specifically, SCALE results on Tahoe-100M, PBMC and Replogle, together with STATE results on Tahoe-100M and Replogle, are reproduced in our implementation. The best result in each metric within each dataset is highlighted in bold, and the second-best result is underlined.\", \"page\": 11, \"index\": 1, \"width\": 973, \"height\": 961}]"
motivation: 针对虚拟细胞扰动预测中存在的训练推理效率低、高维稀疏空间建模不稳定以及评估指标缺乏生物学保真度等瓶颈。
method: 构建了基于BioNeMo的高效训练框架，并采用结合LLaMA编码与端点监督的集合感知流架构，将扰动预测定义为条件传输任务。
result: 在Tahoe-100M基准上，预训练速度提升12.51倍，且在PDCorr和DE Overlap等生物学关键指标上显著优于现有SOTA模型。
conclusion: 虚拟细胞模型的发展依赖于可扩展基础设施、稳定的传输建模以及符合生物学逻辑的评估体系的深度协同设计。
---

## 摘要
虚拟细胞模型旨在通过单细胞测量数据预测细胞对遗传、化学或细胞因子扰动的反应，从而实现干实验（in silico experimentation）。然而在实践中，大规模扰动预测仍受限于三个相互关联的瓶颈：低效的训练和推理流水线、高维稀疏表达空间中不稳定的建模，以及过度强调重建精度而低估生物学保真度的评估协议。在这项工作中，我们提出了一个专门用于虚拟细胞扰动预测的大规模基础模型 SCALE，共同解决了上述局限性。首先，我们构建了一个基于 BioNeMo 的训练和推理框架，显著提高了数据吞吐量、分布式可扩展性和部署效率，在相同系统设置下，预训练速度比之前的 SOTA 流水线提升了 12.51 倍，推理速度提升了 1.29 倍。其次，我们将扰动预测公式化为条件传输，并利用一种集合感知流架构来实现，该架构将基于 LLaMA 的细胞编码与面向终点的监督相结合。这种设计带来了更稳定的训练和更强的扰动效应恢复能力。第三，我们在 Tahoe-100M 数据集上使用严格的细胞级协议对模型进行了评估，该协议以具有生物学意义的指标为中心，而非仅仅关注重建。在该基准测试中，我们的模型相比 STATE 在 PDCorr 上提升了 12.02%，在 DE Overlap 上提升了 10.66%。总之，这些结果表明，推进虚拟细胞的发展不仅需要更好的生成目标，还需要可扩展基础设施、稳定传输建模和生物学保真评估的协同设计。

## Abstract
Virtual cell models aim to enable in silico experimentation by predicting how cells respond to genetic, chemical, or cytokine perturbations from single-cell measurements. In practice, however, large-scale perturbation prediction remains constrained by three coupled bottlenecks: inefficient training and inference pipelines, unstable modeling in high-dimensional sparse expression space, and evaluation protocols that overemphasize reconstruction-like accuracy while underestimating biological fidelity. In this work we present a specialized large-scale foundation model SCALE for virtual cell perturbation prediction that addresses the above limitations jointly. First, we build a BioNeMo-based training and inference framework that substantially improves data throughput, distributed scalability, and deployment efficiency, yielding 12.51x speedup on pretrain and 1.29x on inference over the prior SOTA pipeline under matched system settings. Second, we formulate perturbation prediction as conditional transport and implement it with a set-aware flow architecture that couples LLaMA-based cellular encoding with endpoint-oriented supervision. This design yields more stable training and stronger recovery of perturbation effects. Third, we evaluate the model on Tahoe-100M using a rigorous cell-level protocol centered on biologically meaningful metrics rather than reconstruction alone. On this benchmark, our model improves PDCorr by 12.02% and DE Overlap by 10.66% over STATE. Together, these results suggest that advancing virtual cells requires not only better generative objectives, but also the co-design of scalable infrastructure, stable transport modeling, and biologically faithful evaluation.

---

## 论文详细总结（自动生成）

以下是对论文《SCALE: Scalable Conditional Atlas-Level Endpoint transport for virtual cell perturbation prediction》的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
虚拟细胞模型的核心目标是通过计算模拟（*in silico*）预测细胞在受到遗传（基因敲除）、化学（药物）或细胞因子扰动后的转录组反应。然而，现有模型面临三大瓶颈：
*   **效率低下**：在大规模单细胞图谱数据上，现有的训练和推理流水线难以扩展，计算成本极高。
*   **建模不稳定**：单细胞数据具有高维、稀疏的特性，传统的生成模型在捕捉复杂的扰动效应时容易出现训练不稳定或模式崩溃。
*   **评估标准偏差**：现有的评估协议往往过度关注均方误差（MSE）等重建指标，而忽视了生物学上的保真度（如差异表达基因的重合度）。

**SCALE** 的提出旨在通过协同设计高效的基础设施、稳定的传输建模和生物学导向的评估体系，解决上述挑战。

### 2. 论文提出的方法论
SCALE 模型采用了以下核心技术：
*   **条件传输（Conditional Transport）建模**：将扰动预测定义为一个从控制组（Control）细胞分布到扰动组（Perturbed）细胞分布的条件传输任务。
*   **集合感知流架构（Set-aware Flow Architecture）**：
    *   **LLaMA 编码器**：借鉴大语言模型 LLaMA 的架构进行细胞状态编码，增强对高维基因表达特征的提取能力。
    *   **端点监督（Endpoint-oriented Supervision）**：不同于传统的扩散模型，该模型采用流匹配（Flow Matching）思想，直接对预测的终点状态进行监督，提高了训练的稳定性。
*   **BioNeMo 框架集成**：基于 NVIDIA 的 BioNeMo 平台构建，利用优化的分布式训练算子和数据并行策略，极大提升了数据吞吐量。

### 3. 实验设计
*   **数据集**：
    *   **Tahoe-100M**：一个包含约一亿个单细胞的大规模基准数据集，用于预训练和大规模评估。
    *   **PBMC & Replogle**：用于验证模型在不同生物场景和少样本（Few-shot）迁移学习下的表现。
*   **Benchmark 与指标**：采用 **Cell Eval** 协议，重点关注：
    *   **PDCorr**（Perturbation-specific Pearson Correlation）：衡量预测扰动方向的准确性。
    *   **DE Overlap**（Differentially Expressed Overlap）：衡量预测的差异表达基因与真实实验结果的重合度。
*   **对比方法**：包括当前最先进的（SOTA）模型，如 **STATE**、**PerturbDiff** 等。

### 4. 资源与算力
*   **算力平台**：明确提到使用了 **BioNeMo** 框架进行分布式扩展。
*   **效率提升**：在相同的系统设置下，SCALE 的**预训练速度提升了 12.51 倍**，**推理速度提升了 1.29 倍**。
*   *注：摘要中未给出具体的 GPU 型号（如 H100/A100）和具体数量，但强调了其在分布式可扩展性上的显著优势。*

### 5. 实验数量与充分性
*   **实验规模**：在 Tahoe-100M 这一亿级规模的数据集上进行了测试，这在同类研究中属于极大规模。
*   **实验维度**：涵盖了预训练性能对比、少样本迁移学习实验以及针对不同生物学指标的消融分析。
*   **客观性**：通过在多个独立数据集（PBMC, Replogle）上复现 SOTA 模型（如 STATE）的结果并进行对比，确保了实验的公平性和客观性。

### 6. 主要结论与发现
*   **性能领先**：SCALE 在生物学关键指标上显著优于现有模型。在 Tahoe-100M 基准上，**PDCorr 提升了 12.02%**，**DE Overlap 提升了 10.66%**。
*   **效率突破**：证明了通过优化底层计算框架（BioNeMo），可以实现数量级的训练加速，使大规模虚拟细胞模拟成为可能。
*   **建模范式**：证实了将扰动预测视为“条件传输”并结合流匹配架构，比传统的生成式建模更适合处理高维稀疏的生物数据。

### 7. 优点
*   **高扩展性**：解决了大规模单细胞数据训练的工程难题，支持图谱级（Atlas-level）的建模。
*   **生物学保真度高**：不盲目追求重建精度，而是通过优化架构提升了对生物学扰动效应的捕捉能力。
*   **端到端优化**：从底层算子到高层算法再到评估指标进行了全栈式的协同设计。

### 8. 不足与局限
*   **框架依赖**：模型高度依赖 BioNeMo 等特定高性能计算框架，对于缺乏此类基础设施的研究机构可能存在迁移门槛。
*   **稀疏性挑战**：尽管有所改进，但在极端稀疏的单细胞数据中，如何完全消除噪声并精准预测罕见细胞类型的反应仍是挑战。
*   **泛化边界**：对于完全未见过的（Out-of-distribution）新型化学扰动，模型的预测能力仍需进一步验证。

（完）
