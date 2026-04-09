---
title: Dissecting oligogenic and polygenic indirect genetic effects through the lens of neighbor genotypic identity
title_zh: 从邻体基因型一致性的视角剖析寡基因和多基因间接遗传效应
authors: "Sato, Y., Hamazaki, K."
date: 2026-04-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.31.715746v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 间接遗传效应的GWAS和基因组预测统一方法
tldr: 本研究针对个体表型受邻居基因型影响的间接遗传效应（IGEs），提出了一种整合多基因和寡基因效应的统一分析框架。该方法借鉴物理学中的伊辛模型，利用多核混合模型简化了全基因组关联分析（GWAS）和基因组预测（GP）中的计算。通过对杨树、苹果和葡萄三种木本植物的应用，研究揭示了不同物种间的竞争遗传模式，并识别出影响苹果树干生长的关键变异位点，为解析群体遗传结构提供了高效工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-31-715746-v1/fig-001.webp\", \"caption\": \"Figures 528\", \"page\": 19, \"index\": 1, \"width\": 852, \"height\": 594}]"
motivation: 旨在开发一种统一的方法，以同时分析和预测由邻近个体基因型引起的复杂间接遗传效应（IGEs）。
method: 结合铁磁学伊辛模型，构建了一个包含两个随机效应且具有单一协方差参数的多核混合模型。
result: 在杨树和苹果中发现了显著的种间竞争证据，并成功定位了与苹果生长竞争相关的遗传变异。
conclusion: 该研究提供了一种灵活的GWAS和GP实现方案，是剖析群体表现遗传基础的有效工具。
---

## 摘要
个体表型通常取决于群体内其他个体的基因型。这些现象被称为间接遗传效应 (IGEs)，并已通过数量遗传模型与直接遗传效应 (DGEs) 区分开来。最近的研究利用高分辨率多态性数据实现了 IGEs 的基因组预测 (GP) 和全基因组关联分析 (GWAS)，但统一的方法仍然有限。在本研究中，我们使用包含两个具有单一协方差参数的随机效应的多核混合模型，整合了多基因和寡基因 IGEs。在该实现的基础上，铁磁学的伊辛模型 (Ising model) 使我们能够分别简化用于 GWAS 和 GP 的位点级和背景 IGEs。我们的模拟表明，虽然先前模型和当前模型表现出相似的性能，但当前模型可以推断 DGEs 和 IGEs 之间的权衡。通过将该方法应用于三种木本植物，我们发现了杨树和苹果树中存在基因型间竞争的证据，但在攀缘葡萄藤中的证据有限。基于 GWAS，我们还检测到了与苹果树干生长的竞争性 IGEs 相关的显著变异。我们的研究为 IGEs 的 GWAS/GP 提供了一种灵活的实现方式，从而为剖析群体表现的遗传结构提供了一个有效的工具。

## Abstract
Individual phenotypes often depend on the genotypes of other individuals within a group. These phenomena are termed  indirect genetic effects (IGEs) and have been distinguished from direct genetic effects (DGEs) using quantitative genetic models. Recent studies have utilized high-resolution polymorphism data to enable genomic prediction (GP) and genome-wide association study (GWAS) of IGEs, but unified methods remain limited. Here we integrate polygenic and oligogenic IGEs using a multi-kernel mixed model incorporating two random effects with a single covariance parameter. Underlying this implementation, the Ising model of ferromagnetics enabled us to simplify locus-wise and background IGEs for GWAS and GP, respectively. Our simulations demonstrated that, while the previous and present models exhibited similar performance, the present model can infer a trade-off between DGEs and IGEs. By applying this method to three species of woody plants, we found evidence for intergenotypic competition in aspen and apple trees, but limited evidence in climbing grapevines. Based on GWAS, we also detected significant variants associated with the competitive IGEs on the apple trunk growth. Our study offers a flexible implementation for GWAS/GP of IGEs, thereby providing an effective tool to dissect the genetic architecture of group performance.

---

## 论文详细总结（自动生成）

这篇论文题为《从邻体基因型一致性的视角剖析寡基因和多基因间接遗传效应》，由 Sato 和 Hamazaki 撰写。以下是对该研究的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：个体的表型不仅受自身基因型（直接遗传效应，DGEs）影响，还受到群体中邻近个体基因型（间接遗传效应，IGEs）的影响。现有的研究虽然已经开始利用高通量多态性数据进行 IGEs 的基因组预测（GP）和全基因组关联分析（GWAS），但缺乏一个能够同时整合“多基因背景效应”和“特定位点寡基因效应”的统一分析框架。
*   **研究动机**：IGEs 在植物竞争、社会行为和群体产量中起着关键作用。作者旨在开发一种灵活且计算高效的方法，通过借鉴物理学中的伊辛模型（Ising model），来量化邻体间基因型一致性对个体表型的影响，从而更好地理解群体表现的遗传基础。

### 2. 论文提出的方法论
*   **核心思想**：引入“邻体基因型一致性”（Neighbor Genotypic Identity, NGI）的概念。该方法假设：如果邻居在某一特定位点拥有与目标个体相同（或不同）的基因型，这种一致性会产生正向或负向的社会压力，进而影响目标个体的表型。
*   **关键技术细节**：
    *   **伊辛模型借鉴**：利用铁磁学中的伊辛模型来描述邻近个体间的相互作用状态（相同或不同）。
    *   **多核混合模型（Multi-kernel Mixed Model）**：构建了一个包含两个随机效应（DGE 和 IGE）的线性混合模型。
    *   **单一协方差参数简化**：为了降低计算复杂度，模型将 DGE 和 IGE 的协方差矩阵通过一个单一的比例参数联系起来，使得在进行 GWAS 和 GP 时能够更快速地求解。
    *   **GWAS 与 GP 的统一**：在 GWAS 阶段，逐位点测试 NGI 的显著性；在 GP 阶段，利用全基因组范围内的 NGI 构建亲缘关系矩阵，预测个体育种值。

### 3. 实验设计
*   **数据集**：
    1.  **杨树（Aspen）**：分析其在受控环境下的生长数据。
    2.  **苹果（Apple）**：分析果园中苹果树的树干生长数据。
    3.  **葡萄（Grapevine）**：分析攀缘葡萄藤的生长表现。
*   **Benchmark（基准）**：
    *   对比了传统的仅包含 DGE 的模型。
    *   对比了经典的 IGE 模型（如 Bijma 和 Muir 提出的模型），这些模型通常基于邻居的等位基因剂量而非基因型一致性。
*   **实验场景**：通过计算机模拟验证了模型在不同遗传力、群体结构和效应大小下的统计效能（Power）和假阳性率（FDR）。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号或训练时长。
*   **实现方式**：根据文中描述，该方法主要基于 R 语言环境开发（使用了如 `lme4qtl` 或自定义的混合模型求解器），属于统计遗传学范畴，通常对算力的需求集中在 CPU 内存和多线程处理上，而非大规模深度学习所需的 GPU 算力。

### 5. 实验数量与充分性
*   **实验规模**：
    *   **模拟实验**：进行了多组参数组合的模拟，包括不同的样本量、邻居数量以及 DGE/IGE 的相关性。
    *   **真实数据**：涵盖了三种具有不同生长习性和空间分布的木本植物。
*   **充分性评价**：实验设计较为充分。通过模拟实验验证了数学模型的严谨性，通过跨物种的真实数据验证了方法的普适性。特别是对“竞争”与“协作”模式的推断，体现了实验的深度。

### 6. 主要结论与发现
*   **竞争效应的普遍性**：在杨树和苹果中发现了显著的负向 IGEs，表明这些物种在生长过程中存在强烈的基因型间竞争。
*   **物种差异**：相比之下，攀缘葡萄藤的 IGEs 证据有限，这可能与其生长方式（利用支撑物而非直接空间竞争）有关。
*   **关键变异定位**：在苹果的 GWAS 分析中，成功识别出与树干生长竞争相关的显著 SNP 位点，证明了该方法在挖掘寡基因 IGEs 方面的能力。
*   **权衡关系**：模型能够推断出 DGE 和 IGE 之间的权衡（Trade-off），即个体自身生长潜力和对邻居影响之间的遗传相关性。

### 7. 优点
*   **理论创新**：巧妙地将物理学中的伊辛模型引入数量遗传学，为描述邻体相互作用提供了直观的数学框架。
*   **计算高效**：通过简化协方差结构，解决了传统 IGE 模型在处理大规模基因组数据时计算量过大的问题。
*   **应用灵活**：一个框架同时支持 GWAS（找位点）和 GP（做预测），具有很强的实用价值。

### 8. 不足与局限
*   **空间依赖性**：该方法高度依赖于准确的空间位置信息（谁是谁的邻居），在缺乏明确空间布局的群体中难以应用。
*   **模型假设限制**：NGI 模型假设相互作用仅取决于基因型是否一致，可能忽略了更复杂的非对称相互作用（例如大个体对小个体的单向压制）。
*   **样本量需求**：尽管进行了简化，但要准确分离 DGE 和 IGE，仍然需要较大的样本量和合理的实验设计（如随机区组）。

（完）
