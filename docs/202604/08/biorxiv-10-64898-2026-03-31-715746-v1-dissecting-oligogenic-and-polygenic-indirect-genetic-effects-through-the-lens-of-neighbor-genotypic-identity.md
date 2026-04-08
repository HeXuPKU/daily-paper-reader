---
title: Dissecting oligogenic and polygenic indirect genetic effects through the lens of neighbor genotypic identity
title_zh: 从邻体基因型一致性的角度剖析寡基因和多基因间接遗传效应
authors: "Sato, Y., Hamazaki, K."
date: 2026-04-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.31.715746v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 用于间接遗传效应GWAS和基因组预测的多核混合模型
tldr: 本研究探讨了个体表型受邻居基因型影响的间接遗传效应（IGEs）。研究者开发了一种整合多基因和寡基因IGEs的多核混合模型，利用铁磁学伊辛模型简化了全基因组关联分析（GWAS）和基因组预测（GP）中的计算。通过对杨树、苹果和葡萄三种木本植物的分析，揭示了植物间的竞争性IGEs，并识别了影响苹果树干生长的关键变异，为解析群体表现的遗传结构提供了灵活有效的工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-31-715746-v1/fig-001.webp\", \"caption\": \"Figures 528\", \"page\": 19, \"index\": 1, \"width\": 852, \"height\": 594}]"
motivation: 旨在解决现有研究中缺乏统一方法来同时分析多基因和寡基因间接遗传效应的问题。
method: 提出一种基于伊辛模型的多核混合模型，通过单一协方差参数整合直接与间接遗传效应。
result: 模拟验证了模型性能，并在杨树和苹果中发现显著的种内竞争效应，同时定位了相关的遗传变异。
conclusion: 该方法为研究群体遗传架构提供了新视角，能有效推断直接与间接遗传效应间的权衡关系。
---

## 摘要
个体表型通常取决于群体内其他个体的基因型。这些现象被称为间接遗传效应（IGEs），并已通过数量遗传模型与直接遗传效应（DGEs）区分开来。近期的研究利用高分辨率多态性数据实现了 IGEs 的基因组预测（GP）和全基因组关联分析（GWAS），但统一的方法仍然有限。在此，我们使用包含两个随机效应且具有单一协方差参数的多核混合模型，整合了多基因和寡基因 IGEs。在该实现的基础上，铁磁学的伊辛模型（Ising model）使我们能够分别简化用于 GWAS 和 GP 的位点级和背景 IGEs。我们的模拟表明，虽然先前模型与本模型表现相似，但本模型可以推断 DGEs 和 IGEs 之间的权衡。通过将该方法应用于三种木本植物，我们发现了杨树和苹果树中存在基因型间竞争的证据，但在攀缘葡萄藤中证据有限。基于 GWAS，我们还检测到了与苹果树干生长的竞争性 IGEs 相关的显著变异。我们的研究为 IGEs 的 GWAS/GP 提供了一种灵活的实现方式，从而为剖析群体表现的遗传结构提供了有效工具。

## Abstract
Individual phenotypes often depend on the genotypes of other individuals within a group. These phenomena are termed  indirect genetic effects (IGEs) and have been distinguished from direct genetic effects (DGEs) using quantitative genetic models. Recent studies have utilized high-resolution polymorphism data to enable genomic prediction (GP) and genome-wide association study (GWAS) of IGEs, but unified methods remain limited. Here we integrate polygenic and oligogenic IGEs using a multi-kernel mixed model incorporating two random effects with a single covariance parameter. Underlying this implementation, the Ising model of ferromagnetics enabled us to simplify locus-wise and background IGEs for GWAS and GP, respectively. Our simulations demonstrated that, while the previous and present models exhibited similar performance, the present model can infer a trade-off between DGEs and IGEs. By applying this method to three species of woody plants, we found evidence for intergenotypic competition in aspen and apple trees, but limited evidence in climbing grapevines. Based on GWAS, we also detected significant variants associated with the competitive IGEs on the apple trunk growth. Our study offers a flexible implementation for GWAS/GP of IGEs, thereby providing an effective tool to dissect the genetic architecture of group performance.

---

## 论文详细总结（自动生成）

这是一份关于论文《从邻体基因型一致性的角度剖析寡基因和多基因间接遗传效应》（Dissecting oligogenic and polygenic indirect genetic effects through the lens of neighbor genotypic identity）的结构化总结：

### 1. 核心问题与整体含义
该研究关注的是**间接遗传效应（Indirect Genetic Effects, IGEs）**，即一个体的表型不仅受自身基因型（直接遗传效应，DGEs）影响，还受到群体内相邻个体基因型的影响。
*   **研究动机**：虽然 IGEs 在进化生物学和动植物育种中至关重要，但现有的全基因组关联分析（GWAS）和基因组预测（GP）方法往往将多基因（背景）效应与寡基因（特定位点）效应分开处理，缺乏一个统一且计算高效的框架来同时评估这两者，并量化 DGE 和 IGE 之间的权衡关系（如竞争或协作）。

### 2. 方法论
研究者提出了一种基于**多核混合模型（Multi-kernel Mixed Model）**的新方法，其核心创新点在于引入了物理学中的**伊辛模型（Ising model）**概念：
*   **核心思想**：利用“邻体基因型一致性”来简化复杂的个体间相互作用。将 IGE 建模为邻居基因型对目标个体表型的影响。
*   **关键技术细节**：
    *   **统一模型**：构建了一个包含两个随机效应（DGE 和 IGE）的线性混合模型。
    *   **单一协方差参数**：通过定义一个特定的协方差结构，模型能够用一个参数来推断 DGE 和 IGE 之间的相关性（$\rho$）。
    *   **伊辛模型应用**：在 GWAS 中，利用伊辛模型简化位点级的 IGE 计算；在 GP 中，利用它构建亲缘关系矩阵（GRM）的变体，以捕捉背景遗传相互作用。
    *   **算法流程**：首先通过最大似然法估计方差分量，随后进行位点扫描（GWAS）或表型预测（GP）。

### 3. 实验设计
*   **数据集**：
    1.  **模拟数据**：用于验证模型在不同遗传力、样本量和 DGE-IGE 相关性下的统计效能和参数估计准确性。
    2.  **真实植物数据**：包括欧洲山杨（Aspen）、苹果（Apple）和葡萄（Grapevine）三种木本植物的生长数据。
*   **Benchmark 与对比方法**：
    *   对比了传统的仅考虑 DGE 的模型。
    *   对比了经典的 Bijma-Muir IGE 模型。
    *   评估了模型在识别竞争（负相关）与协作（正相关）效应方面的表现。

### 4. 资源与算力
*   论文中**未明确说明**具体的硬件配置（如 GPU 型号、数量）或具体的训练时长。
*   但文中提到，该方法通过简化协方差结构，旨在降低 IGE 分析中的计算负担，使其在大规模基因组数据集上更具可行性。

### 5. 实验数量与充分性
*   **实验规模**：进行了大量的模拟实验，涵盖了多种生物学场景。在真实数据应用中，选择了三种具有不同生长习性和种植密度的木本植物，具有较好的代表性。
*   **充分性与客观性**：实验设计较为全面，不仅验证了模型的预测精度，还通过 GWAS 定位了具体的遗传变异。通过对不同物种的对比，客观地展示了模型在不同生物学背景下的适用性（例如在葡萄中未发现显著 IGE，这与其攀缘生长特性相符）。

### 6. 主要结论与发现
*   **模型效能**：新模型在预测准确性上与现有复杂模型相当，但在解释 DGE 和 IGE 之间的权衡关系上更具优势。
*   **生物学发现**：
    *   在**杨树和苹果**中发现了显著的**竞争性 IGEs**（DGE 与 IGE 呈负相关），表明生长势强的个体倾向于抑制邻居的生长。
    *   在**葡萄**中 IGE 证据有限，说明植物的生长形态会影响间接遗传效应的强度。
*   **GWAS 成果**：在苹果中识别出了与树干生长竞争效应相关的显著遗传位点，为分子育种提供了潜在靶点。

### 7. 优点
*   **理论创新**：跨学科引入伊辛模型，简化了 IGE 的数学表达。
*   **灵活性**：统一了 GWAS 和 GP 框架，既能处理全基因组背景效应，也能定位单个主效基因。
*   **可解释性**：能够直观地推断个体间是“竞争”还是“互助”，这对理解群体表现（Group Performance）具有重要意义。

### 8. 不足与局限
*   **空间假设限制**：模型高度依赖于对“邻居”的定义（空间距离），对于非空间接触的相互作用（如化学信号、复杂社会行为）可能覆盖不足。
*   **物种局限性**：目前主要在木本植物中验证，在动物群体或一年生农作物中的普适性仍需进一步验证。
*   **计算复杂度**：尽管有所简化，但在处理超大规模群体（如数十万个体）时，多核混合模型的矩阵运算仍可能面临挑战。

（完）
