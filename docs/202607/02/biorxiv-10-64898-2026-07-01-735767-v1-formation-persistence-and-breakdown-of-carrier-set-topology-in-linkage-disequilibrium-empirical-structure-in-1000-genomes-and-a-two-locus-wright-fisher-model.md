---
title: "Formation, persistence, and breakdown of carrier-set topology in linkage disequilibrium: empirical structure in 1000 Genomes and a two locus Wright Fisher model"
title_zh: 连锁不平衡中载体集拓扑结构的形成、持久与破坏：千人基因组中的经验结构及双位点赖特-费希尔模型
authors: "Ichikawa, Y."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.01.735767v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 研究连锁不平衡中载体集拓扑结构，直接关联精细定位
tldr: "传统LD度量r2和D'侧重对称关联，未直接刻画载体集拓扑（嵌套/部分重叠/不相交）。本研究利用1000 Genomes Phase 3数据（156M SNP对）发现，在固定r2层内，r2难以区分嵌套与非嵌套（AUROC≈0.54-0.62），而D'更有效（AUROC≈0.90-0.92）；数据还服从r2≤pA/pB天花板约束。通过两基因座Wright Fisher模型模拟时间演化，揭示载体集拓扑的形成、可见性变化和崩溃三种运动。研究表明拓扑与可见性是LD结构的可分离轴，互为补充。"
source: biorxiv
selection_source: fresh_fetch
motivation: 传统LD度量未直接反映载体集拓扑（包含/部分重叠/不相交），而这种结构对于理解稀有变异与常见变异的关系至关重要。
method: 利用1000 Genomes Phase 3数据（MHC和NEGR1区域）分析SNP对的载体集拓扑类型，并通过两基因座Wright Fisher模型模拟时间演化过程。
result: "r2区分嵌套与非嵌套拓扑能力差（AUROC≈0.54-0.62），而D'更有效（AUROC≈0.90-0.92）；数据服从r2≤pA/pB天花板；模型展示拓扑形成、可见性变化和崩溃。"
conclusion: 载体集拓扑与可见性是LD结构的独立维度，需分别分析，二者回答互补而非可互换的问题。
---

## 摘要
双等位基因位点间的连锁不平衡通常由标量关联度量（如r²和D'）来概括。这些度量量化了等位基因关联在对称LD扫描中的可见性，但并未直接表示载体集的拓扑结构：一个变异体的携带者是否包含在另一个的携带者中、部分重叠，或完全不相交。这一区分是结构性的。在单倍型频率单纯形上，载体集包含对应于一个单倍型类缺失的边界面。在稀有常见体制下，嵌套的稀有变异进一步受限于上限r²≤pA/pB，因此完整的载体集包含可能对r²几乎不可见。本文作为Fisher几何预印本¹的配套研究，考察了这种载体集拓扑的经验和动态行为。在千人基因组计划第三阶段中，来自MHC和NEGR1区域的156,604,320个SNP对中，位于|D'|=1边界上的对跨越了广泛的r²和|C|范围。在固定的r²分层内，r²很难区分嵌套与非嵌套的载体集配置，AUROC值约为0.54至0.62，而对边界敏感的归一化D'则能更有效地分离它们，AUROC值约为0.90至0.92。经验数据也符合预测的r²≤pA/pB上限。然后，我们在同一单纯形上使用双位点赖特-费希尔模型引入时间轴。载体集拓扑通过三种相对于|D'|=1边界的运动演化：形成或持久，其中重组抑制建立并维持包含关系而不需要选择；可见性变化，其中选择或漂移沿着边界移动r²同时保持包含关系；以及破坏，其中重组脉冲引入先前缺失的单倍型并解散包含关系。第四种模式，特异性侵蚀，在保持包含关系的同时扩展伙伴载体集，从而降低P(A|B)同时保持P(B|A)和|D'|等于1。该模式表明，非对称条件概率最好被理解为载体集拓扑的诊断坐标，而非首要对象本身。总之，这些结果表明拓扑和可见性是LD结构的可分离轴。因此，基于r²的传统扫描和载体集拓扑扫描回答的是互补而非可互换的问题。

## Abstract
Linkage disequilibrium between two biallelic loci is usually summarized by scalar association measures such as r2 and D'. These measures quantify how visible an allelic association is to a symmetric LD scan, but they do not directly represent the topology of carrier sets: whether the carriers of one variant are contained within, partially overlap with, or are disjoint from the carriers of the other. This distinction is structural. On the haplotype frequency simplex, carrier set inclusion corresponds to a boundary face where one haplotype class is absent. In the rare common regime, a nested rare variant is further constrained by the ceiling r2[&le;] pA/pB, so that complete carrier-set inclusion can remain nearly invisible to r2. Here, as a companion to the Fisher-geometry preprint 1, we examine the empirical and dynamic behavior of this carrier set topology. In 1000 Genomes Phase 3, across 156,604,320 SNP pairs from the MHC and NEGR1 regions, pairs on the |D'|=1 boundary span a wide range of r2 and |C|. Within fixed r2 strata, r2 poorly distinguishes nested from non-nested carrier set configurations, with AUROC values of approximately 0.54 to 0.62, whereas the boundary sensitive normalization D' separates them much more effectively, with AUROC values of approximately 0.90 to 0.92. The empirical data also obey the predicted r2 [&le;] pA/pB ceiling. We then introduce a temporal axis using a two-locus Wright Fisher model on the same simplex. Carrier set topology evolves through three motions relative to the |D'|=1 boundary: formation or persistence, in which recombination suppression establishes and maintains inclusion without requiring selection; visibility change, in which selection or drift moves r2 along the boundary while preserving the inclusion relation; and breaking, in which a recombination pulse introduces the previously absent haplotype and dissolves inclusion. A fourth mode, specificity erosion, expands the partner carrier set while preserving inclusion, thereby lowering P(A|B)while keeping P(B|A)and |D'| equal to one. This mode shows that asymmetric conditional probabilities are best understood as diagnostic coordinates for carrier-set topology, not as the primary object itself. Together, these results show that topology and visibility are separable axes of LD structure. Conventional r2 based scans and carrier-set topology scans therefore answer complementary, not interchangeable, questions.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：传统的连锁不平衡（LD）度量（如r²和D'）只量化了等位基因关联的“可见性”（即关联强度），但没有直接反映两位点之间“载体集”的拓扑关系——即一个变异携带者集合是否嵌套在另一个中、部分重叠，还是完全不相交。这种拓扑信息对于理解稀有变异与常见变异的关系、精细定位以及进化动态至关重要。
- **整体含义**：作者指出，LD结构应被分解为两个可分离的轴：**载体集拓扑**（包含/部分重叠/不相交）和**可见性**（关联的统计强度）。传统研究侧重可见性，而忽略了拓扑，导致对LD结构的理解不完整。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过单倍型频率单纯形上的几何表示，将载体集包含映射到单一单倍型类缺失的边界面（即|D'|=1的边界）。利用这一边界，可以将SNP对按拓扑类型分类：嵌套（一个载体集完全包含另一个）、部分重叠、不相交。
- **关键技术细节**：
  - 使用**1000 Genomes Phase 3**数据中的MHC和NEGR1区域，枚举所有SNP对（共156,604,320对），计算r²、D'、|C|（协方差绝对值）等指标，并标注其拓扑类型（基于单倍型频率）。
  - 在固定r²分层内，用**AUROC**评估r²和D'区分嵌套与非嵌套拓扑的能力。
  - 发现了经验数据服从的理论上限：**r² ≤ pA/pB**，其中pA是第一个等位基因频率，pB是第二个（且pA ≤ pB）。
  - 使用**双位点赖特-费希尔模型**（Wright-Fisher model）进行时间演化模拟，在单纯形上追踪载体集拓扑的四种运动模式：形成/持久、可见性变化、破坏、特异性侵蚀。

### 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - 主要经验数据：1000 Genomes Phase 3的**MHC区域**和**NEGR1区域**的SNP对（共156,604,320对）。
- **基准**：
  - 没有显式的外部基准数据集。方法的核心是评估不同LD度量对拓扑类型的区分能力。
- **对比方法**：
  - 对比了r²与D'在相同数据上的表现，计算AUROC来比较它们区分嵌套与非嵌套载体集的能力。
  - 此外，还对比了不同r²分层下的表现（r²从0.1到1.0的多个区间）。

### 4. 资源与算力

- 论文未明确提及使用的GPU型号、数量或训练时长。所有分析可能仅在CPU上进行（LD计算和模拟），因此无法提供具体算力信息。
- 注：由于是生物信息学统计分析，通常不需要大规模GPU算力。

### 5. 实验数量与充分性

- **实验数量**：
  - 在经验数据中，仅使用了MHC和NEGR1两个基因组区域，但涉及1.56亿个SNP对，统计量充分。
  - 模拟实验：双位点赖特-费希尔模型模拟了多种参数组合（如不同重组率、选择系数、种群大小），但未列出具体的参数网格数量。
- **充分性**：
  - 经验数据的覆盖范围有限（仅两个区域，且都是高LD区域），可能不具有全基因组代表性。
  - 模拟实验未系统扫描所有可能参数空间，结论偏向定性。总体而言，实验设计初步但合理，但不够全面。

### 6. 论文的主要结论与发现

- **经验发现**：
  - 在固定r²分层内，r²区分嵌套与非嵌套载体集的能力非常弱（AUROC ≈ 0.54–0.62），而D'能力较强（AUROC ≈ 0.90–0.92）。这说明D'对边界拓扑更敏感。
  - 经验数据严格服从理论天花板 r² ≤ pA/pB。
- **模拟发现**：
  - 载体集拓扑可以通过四种动态模式演化：（1）**形成/持久**（重组抑制建立包含关系）；（2）**可见性变化**（选择或漂移改变r²但保持包含）；（3）**破坏**（重组脉冲引入缺失单倍型，解散包含）；（4）**特异性侵蚀**（扩展伙伴载体集而降低P(A|B)但保持D'=1）。
- **总体结论**：拓扑和可见性是LD结构的两个可分离轴，传统基于r²的扫描和基于载体集拓扑的扫描回答互补而非可互换的问题。

### 7. 优点

- **理论创新**：首次系统地将载体集拓扑作为LD分析的独立维度，提出了明确的几何解释（单纯形边界面）。
- **方法严谨**：利用AUROC客观评估度量性能，并揭示r²的拓扑盲点。
- **动态视角**：通过Wright-Fisher模型引入时间维，揭示了拓扑的四种演化模式，特别是“特异性侵蚀”这一此前未被识别的模式。
- **解释力强**：将条件概率P(A|B)和P(B|A)解释为拓扑的诊断坐标而非首要对象，提供了新的理解框架。

### 8. 不足与局限

- **数据覆盖局限**：仅分析了两个基因组区域（MHC和NEGR1），虽然SNP对数量大，但可能存在区域特异性（如MHC的高LD结构特殊）。未在全基因组范围验证。
- **缺乏选择压力检验**：模拟中提及选择作用，但未详细测试不同选择强度对拓扑的影响。
- **缺乏与其他LD度量的比较**：仅对比r²和D'，未涉及D、r、r²的其他变体（如r²校正版）或基于LD的聚类方法。
- **未提供可重复性代码**：论文未公开代码或详细参数，可能增加复现难度。
- **应用限制**：目前属于方法论探讨，未提供具体的精细定位或GWAS应用案例，实用性待验证。

（完）
