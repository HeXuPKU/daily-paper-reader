---
title: Dissecting oligogenic and polygenic indirect genetic effects through the lens of neighbor genotypic identity
title_zh: 从邻体基因型一致性的视角剖析寡基因和多基因间接遗传效应
authors: "Sato, Y., Hamazaki, K."
date: 2026-04-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.31.715746v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 用于间接遗传效应GWAS和基因组预测的多核混合模型
tldr: 本研究针对间接遗传效应（IGEs）缺乏统一分析方法的问题，提出了一种基于伊辛模型的多核混合模型。该方法整合了多基因和寡基因IGEs，能够同时进行全基因组关联分析（GWAS）和基因组预测（GP）。通过对杨树、苹果和葡萄等木本植物的分析，揭示了种内竞争的遗传基础，并识别出影响苹果树干生长的关键变异，为解析群体表现的遗传结构提供了灵活有效的工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-31-715746-v1/fig-001.webp\", \"caption\": \"Figures 528\", \"page\": 19, \"index\": 1, \"width\": 852, \"height\": 594}]"
motivation: 旨在解决现有研究中缺乏统一方法来同时进行间接遗传效应（IGEs）的基因组预测和全基因组关联分析的问题。
method: 借鉴物理学中的伊辛模型，开发了一种包含两个随机效应且具有单一协方差参数的多核混合模型，用于简化位点级和背景IGEs的计算。
result: 模拟显示该模型能有效推断直接与间接遗传效应间的权衡，并在杨树和苹果中发现了显著的种内竞争证据及相关遗传变异。
conclusion: 该研究提供了一个灵活的IGEs分析框架，有助于深入理解社会性或群体环境下的复杂性状遗传架构。
---

## 摘要
个体表型通常取决于群体内其他个体的基因型。这些现象被称为间接遗传效应（IGEs），并已通过数量遗传模型与直接遗传效应（DGEs）区分开来。近期的研究利用高分辨率多态性数据实现了 IGEs 的基因组预测（GP）和全基因组关联研究（GWAS），但统一的方法仍然有限。在本文中，我们利用包含两个随机效应及单一协方差参数的多核混合模型，整合了多基因和寡基因 IGEs。在该实现的基础上，铁磁学的伊辛模型（Ising model）使我们能够分别简化用于 GWAS 和 GP 的位点级和背景 IGEs。我们的模拟表明，虽然先前模型与当前模型表现相似，但当前模型可以推断 DGEs 和 IGEs 之间的权衡。通过将该方法应用于三种木本植物，我们在杨树和苹果树中发现了基因型间竞争的证据，但在攀缘葡萄藤中证据有限。基于 GWAS，我们还检测到了与苹果树干生长的竞争性 IGEs 相关的显著变异位点。我们的研究为 IGEs 的 GWAS/GP 提供了一种灵活的实现方式，从而为剖析群体表现的遗传结构提供了有效工具。

## Abstract
Individual phenotypes often depend on the genotypes of other individuals within a group. These phenomena are termed  indirect genetic effects (IGEs) and have been distinguished from direct genetic effects (DGEs) using quantitative genetic models. Recent studies have utilized high-resolution polymorphism data to enable genomic prediction (GP) and genome-wide association study (GWAS) of IGEs, but unified methods remain limited. Here we integrate polygenic and oligogenic IGEs using a multi-kernel mixed model incorporating two random effects with a single covariance parameter. Underlying this implementation, the Ising model of ferromagnetics enabled us to simplify locus-wise and background IGEs for GWAS and GP, respectively. Our simulations demonstrated that, while the previous and present models exhibited similar performance, the present model can infer a trade-off between DGEs and IGEs. By applying this method to three species of woody plants, we found evidence for intergenotypic competition in aspen and apple trees, but limited evidence in climbing grapevines. Based on GWAS, we also detected significant variants associated with the competitive IGEs on the apple trunk growth. Our study offers a flexible implementation for GWAS/GP of IGEs, thereby providing an effective tool to dissect the genetic architecture of group performance.

---

## 论文详细总结（自动生成）

这篇论文题为《从邻体基因型一致性的视角剖析寡基因和多基因间接遗传效应》，由日本北海道大学和千叶大学的研究人员合作完成。以下是对该论文的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：个体的表型不仅受自身基因型（直接遗传效应，DGEs）影响，还受周围邻体基因型（间接遗传效应，IGEs）的影响。虽然 IGEs 在进化和育种中至关重要，但目前缺乏一个统一的统计框架来同时处理**多基因**（背景遗传效应）和**寡基因**（单个大效应位点）的 IGEs。
*   **研究背景**：现有的 IGEs 分析方法通常将基因组预测（GP）和全基因组关联分析（GWAS）分开处理。此外，如何准确衡量 DGEs 和 IGEs 之间的遗传权衡（协方差）也是一个挑战。

### 2. 论文提出的方法论
*   **核心思想**：借鉴物理学中描述磁偶极子相互作用的**伊辛模型（Ising model）**，将邻体间的基因型相互作用类比为磁体间的物理作用。
*   **关键技术细节**：
    *   **多核混合模型（MKMM）**：构建了一个包含固定效应（用于 GWAS）和随机效应（用于 GP）的线性混合模型。
    *   **固定效应**：定义了三个参数：$\beta_s$（自身效应）、$\beta_n$（邻体效应）和 $\beta_{sn}$（自身与邻体的交互效应）。
    *   **随机效应与协方差**：利用两个随机效应项分别代表多基因 DGEs 和 IGEs，并引入一个单一的协方差参数 $\rho_{12}$ 来捕捉两者之间的遗传相关性。
    *   **核矩阵构建**：除了标准的亲缘关系矩阵 $K_1$，还定义了基于邻体基因型相似性的加权核矩阵 $K_2$ 以及反映非对称相互作用的交叉核矩阵 $K_{12}$ 和 $K_{21}$。
*   **算法流程**：基于 RAINBOW 算法优化权重，通过限制最大似然法（REML）估计方差组分，并利用特征值分解加速 GWAS 计算。

### 3. 实验设计
*   **数据集/场景**：
    1.  **基准模拟**：使用 SLiM 3 软件模拟了 30 组独立的基因组数据，设置不同的 DGE-IGE 协方差（$\rho = 0, \pm 0.3, \pm 0.6$）。
    2.  **真实数据应用**：
        *   **美洲颤杨（Aspen）**：WisAsp 项目数据，包含 800 多株个体，分析防御化学物质和生长性状。
        *   **苹果（Apple）**：REFPOP 项目数据，涵盖欧洲 6 个地点、2 万多株个体，分析花期和树干生长。
        *   **葡萄（Grape）**：INNOVINE 项目数据，包含 3600 多株个体，分析果实品质和产量。
*   **Benchmark**：对比了包含与不包含协方差参数 $\rho$ 的模型在预测准确度（$R^2$、MAE）和 GWAS 检测效力（AUC、灵敏度）上的表现。

### 4. 资源与算力
*   **算力说明**：论文提到计算资源由东京大学人类基因组中心的 **Shirokane 超级计算机**提供。
*   **具体细节**：文中未明确列出具体的 GPU/CPU 型号、数量或具体的训练时长。

### 5. 实验数量与充分性
*   **实验规模**：进行了 30 次独立的模拟迭代，并在三种具有不同空间结构和生物学特性的木本植物上进行了验证。
*   **充分性评价**：实验设计较为充分。模拟实验覆盖了从负相关到正相关的多种遗传架构场景；真实数据跨越了多年份、多地点，增强了结论的普遍性。对比实验（包含 vs 不包含协方差）客观地展示了新模型的适用范围。

### 6. 论文的主要结论与发现
*   **模型有效性**：新模型能准确估计 DGE-IGE 的协方差方向。在正相关场景下，引入协方差能显著提升基因组预测的准确性。
*   **生物学发现**：
    *   在**杨树和苹果**中发现了显著的负遗传协方差，证实了树木间的**种内竞争**，且这种竞争随树龄增长而加强。
    *   在**葡萄**中，IGEs 的影响较小，可能与其垂直生长方式和较大的种植间距有关。
    *   **GWAS 成果**：在苹果第 7 号染色体上识别出两个与树干生长竞争相关的显著 IGE 变异位点，并定位了潜在的候选基因（如蛋白激酶超家族蛋白）。

### 7. 优点
*   **理论创新**：首次将伊辛模型引入 IGEs 的混合模型框架，为理解基因型间的空间相互作用提供了直观的物理类比。
*   **功能集成**：一个模型同时实现了方差组分剖析、基因组预测和关联分析，提高了分析效率。
*   **灵活性**：模型可扩展到动物群体（如笼养动物）或不同空间尺度的植物交互分析。

### 8. 不足与局限
*   **数值稳定性**：在处理**负协方差**时，估计值的波动较大，且由于加权核矩阵可能非正定，需要进行矩阵近似处理，这可能影响估计精度。
*   **数据依赖性**：该方法高度依赖精确的空间位置元数据，若缺乏空间信息则无法应用。
*   **计算复杂性**：尽管有加速算法，但处理超大规模群体（如数万个体以上）且包含复杂空间权重时，计算开销依然较高。

（完）
