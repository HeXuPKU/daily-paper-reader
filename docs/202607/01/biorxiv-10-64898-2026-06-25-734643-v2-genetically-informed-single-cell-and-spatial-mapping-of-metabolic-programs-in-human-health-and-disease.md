---
title: Genetically informed single-cell and spatial mapping of metabolic programs in human health and disease
title_zh: 遗传信息驱动的单细胞和空间代谢程序在人类健康与疾病中的映射
authors: "Xu, H., Huang, G., Zhang, L., Liu, W., Wu, Q., Chen, M., Zhao, D., Zhang, Y., Xu, A."
date: 2026-06-30
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.25.734643v2.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 整合代谢物GWAS汇总统计与单细胞转录组
tldr: 现有转录组代谢模型主要推断细胞内反应或通路活性，无法直接评估单个代谢物与细胞状态的联系。本文提出gmMAP框架，整合代谢物GWAS数据与单细胞和空间转录组，在细胞和空间分辨率上映射代谢程序。在人类肾脏发育、17种小鼠器官及24种正常人体组织中验证，揭示了泛癌代谢重编程及溃疡性结肠炎中炎症相关基质代谢重塑。gmMAP能一致地将遗传信息代谢物特征与细胞状态、组织空间结构和疾病病理联系起来。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有代谢模型无法直接评估代谢物（尤其是细胞外信号分子）与细胞状态的内在关联。
method: 提出gmMAP，整合代谢物GWAS汇总统计与单细胞/空间转录组，结合约束代谢流模型预测代谢活性。
result: 在肾脏发育、多器官稳态及疾病中验证，重建空间代谢分布，揭示泛癌代谢重编程和结肠炎基质重塑。
conclusion: gmMAP能可靠地将遗传代谢特征与细胞状态、组织空间和病理关联，建立多尺度代谢图谱。
---

## 摘要
定义细胞类型特异的内源性代谢特征、细胞水平代谢状态的空间分布以及细胞对外源性代谢物的反应对于理解疾病机制至关重要。现有的基于转录组的代谢模型主要推断细胞内反应或通路水平的活动，因此无法直接评估单个代谢物水平与细胞状态之间的关联，特别是对于作为信号分子在细胞外起作用而非作为代谢底物进入细胞的代谢物。本文介绍gmMAP，这是一个将代谢物GWAS汇总统计与单细胞和空间转录组整合的框架，用于在细胞和空间分辨率下映射代谢程序。值得注意的是，gmMAP不仅能够预测内源性代谢过程的激活，还能揭示外源性代谢物与多种细胞功能状态之间的内在关联。为进一步捕捉细胞代谢网络的连通性，我们引入了基于约束的代谢通量模型来评估全局代谢活动。为评估gmMAP的准确性和稳健性，我们在涵盖人类发育、生理稳态、炎症和癌症的代表性生物学背景下应用该框架。在人类肾脏发育中，gmMAP捕捉了动态代谢程序，并利用配对转录组和代谢组参考数据集进行了验证，支持其在代谢物识别和代谢流推断中的可靠性。在器官水平上，gmMAP重建了稳态和自身免疫炎症条件下17个小鼠器官的空间代谢物分布模式，并进一步扩展至24种正常人体组织，生成了器官和细胞分辨率下的多尺度代谢图谱。在疾病背景下，gmMAP揭示了29种泛癌细胞群体的代谢重编程，并识别了溃疡性结肠炎中外源性代谢物与炎症相关基质代谢重塑之间的潜在联系。总之，gmMAP能够一致地将遗传信息驱动的代谢物特征与细胞状态、空间组织结构和疾病病理联系起来。

## Abstract
Defining cell-type-specific endogenous metabolic features, the spatial distribution of cell-level metabolic states and cellular responses to exogenous metabolites is essential for understanding disease mechanisms. Existing transcriptome-based metabolic models primarily infer intracellular reaction or pathway-level activities, and therefore cannot directly assess associations between individual metabolite levels and cellular states, particularly for metabolites that act extracellularly as signalling molecules rather than entering cells as metabolic substrates. Here we introduce gmMAP, a framework that integrates metabolite GWAS summary statistics with single-cell and spatial transcriptomes to map metabolic programmes at cellular and spatial resolution. Notably, gmMAP enables the prediction of endogenous metabolic process activation while also revealing intrinsic associations between exogenous metabolites and diverse cellular functional states. To further capture the connectivity of cellular metabolic networks, we incorporated a constraint-based metabolic flux model to evaluate global metabolic activity. To evaluate the accuracy and robustness of gmMAP, we applied the framework across representative biological contexts spanning human development, physiological homeostasis, inflammation and cancer. In human kidney development, gmMAP captured dynamic metabolic programmes and was validated using paired transcriptomic and metabolomic reference datasets, supporting its reliability in metabolite identification and metabolic-flow inference. At the organ level, gmMAP reconstructed spatial metabolite distribution patterns across 17 mouse organs under homeostatic and autoimmune inflammatory conditions, and further extension to 24 normal human tissues generated a multi-scale metabolic atlas at both organ and cellular resolutions. In disease settings, gmMAP revealed metabolic reprogramming across 29 pan-cancer cell populations and identified potential links between exogenous metabolites and inflammation-associated stromal metabolic remodelling in ulcerative colitis. Together, gmMAP can consistently connect genetically informed metabolite traits with cell states, spatial tissue organization and disease pathology.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：现有基于转录组的代谢模型主要推断细胞内反应或通路水平的活动，无法直接评估单个代谢物（尤其是作为信号分子的外源性代谢物）与细胞状态之间的内在关联。
- **研究动机**：理解细胞类型特异的内源性代谢特征、代谢状态的空间分布以及细胞对外源性代谢物的响应，对于揭示疾病机制至关重要。
- **整体含义**：本文提出 gmMAP 框架，通过整合代谢物 GWAS 汇总统计与单细胞/空间转录组，实现在细胞和空间分辨率上映射代谢程序，从而建立遗传信息驱动的代谢物特征与细胞状态、组织空间结构及疾病病理之间的可解释联系。

### 2. 论文提出的方法论
- **核心思想**：将代谢物 GWAS 汇总统计与单细胞和空间转录组数据整合，利用统计关联和约束代谢流模型，在细胞和空间水平上预测代谢活性。
- **关键技术细节**：
  - **代谢物-基因关联推导**：通过 GWAS 汇总统计获得代谢物相关的遗传变异，进而映射到单细胞转录组中相关基因的表达模式。
  - **内源性代谢预测**：利用转录组数据推断细胞内代谢过程的激活与否。
  - **外源性代谢物关联**：识别外源性代谢物（如信号分子）与细胞功能状态之间的内在关联，无需代谢物进入细胞。
  - **约束代谢流模型**：引入基于约束的代谢网络通量分析（如 FBA 或类似方法），评估全局代谢活性，捕捉细胞代谢网络的连通性。
- **算法流程**（文字说明）：
  1. 输入：代谢物 GWAS 汇总统计、单细胞转录组数据、空间转录组数据。
  2. 通过 GWAS 汇总统计提取每个代谢物相关的遗传信号。
  3. 将遗传信号投影至单细胞转录组表达矩阵，利用统计模型（如回归或富集分析）计算每个细胞/细胞类型的代谢物特征得分。
  4. 结合约束代谢流模型，推断细胞内代谢通量的变化。
  5. 输出：细胞和空间分辨率的代谢程序图谱，包括内/外源性代谢物活性、代谢通量分布。

### 3. 实验设计
- **使用数据集与场景**：
  - **人类肾脏发育**：使用配对转录组和代谢组参考数据集，验证代谢物识别和代谢流推断的可靠性。
  - **多器官稳态**：17 个小鼠器官（正常与自身免疫炎症条件）的空间转录组数据。
  - **正常人体组织**：24 种正常人体组织，生成多尺度代谢图谱（器官和细胞分辨率）。
  - **疾病背景**：29 种癌症类型的泛癌细胞群体的转录组数据；溃疡性结肠炎患者的肠道组织数据。
- **基准（Benchmark）**：文中未明确列出单一 benchmark 方法，但通过“配对转录组和代谢组参考数据集”进行验证，表明使用了真实代谢物测量作为金标准。
- **对比方法**：文中未提及与其他方法的直接对比；但指出现有代谢模型仅推断细胞内反应/通路活性，而 gmMAP 能评估单个代谢物与细胞状态的关联，暗示其优势。

### 4. 资源与算力
- 文中**未明确说明**使用的 GPU 型号、数量或训练时长等算力资源。仅提到框架本身，未描述计算硬件或训练开销。因此无法总结算力细节。

### 5. 实验数量与充分性
- **实验数量**：覆盖了多个独立场景：
  - 人类发育（肾脏）配对验证实验。
  - 17 种小鼠器官 × 2 种条件（稳态与炎症）。
  - 24 种正常人体组织。
  - 29 种癌症类型。
  - 溃疡性结肠炎疾病模型。
- **充分性与客观性**：
  - 场景覆盖发育、稳态、炎症和癌症，具有广泛代表性。
  - 使用配对代谢组数据验证肾脏发育结果，提高了可靠性。
  - 但缺少与其他方法的直接定量比较（如基准指标、消融实验等），且未报告统计显著性指标（如 p 值、置信区间）。实验设计较丰富，但在严格性和客观对比方面略有不足。

### 6. 论文的主要结论与发现
- gmMAP 框架能够可靠地利用遗传信息驱动的代谢物特征与细胞状态、组织空间结构和疾病病理建立关联。
- 在人类肾脏发育中，gmMAP 成功捕捉动态代谢程序，且经配对代谢组数据验证。
- 在多器官水平，重建了稳态和炎症条件下小鼠器官的空间代谢分布，并扩展至 24 种人体组织，生成多尺度代谢图谱。
- 在疾病中，揭示了 29 种泛癌细胞群体的代谢重编程，并发现溃疡性结肠炎中外源性代谢物与炎症相关基质代谢重塑的潜在联系。

### 7. 优点
- **方法创新**：首次将代谢物 GWAS 汇总统计与单细胞/空间转录组整合，同时处理内源和外源性代谢物，填补了现有转录组代谢模型无法关联单个代谢物与细胞状态的空白。
- **多尺度映射**：从细胞到器官、从稳态到疾病，提供跨尺度的代谢程序可视化。
- **验证扎实**：在肾脏发育中使用配对代谢组数据验证，提升了结果可信度。
- **应用广泛**：涵盖人类发育、多种器官、泛癌和炎症疾病，展示了方法的通用性。

### 8. 不足与局限
- **缺乏基准对比**：未与其他代谢推断方法（如基于通路的模型或机器学习方法）进行定量比较，难以量化相对优势。
- **算力与实现细节缺失**：未提供计算资源、训练时间、超参数等，可复现性受限。
- **统计评估不足**：未给出关联的显著性检验（如 FDR 校正 P 值），仅定性描述。
- **偏差风险**：GWAS 汇总统计可能受人群、样本量、代谢物测量误差影响，文中未讨论这些潜在偏差。
- **应用限制**：主要依赖转录组和 GWAS 数据，不能直接反映蛋白质/代谢物丰度或酶活性，推断结果需要额外实验验证。

（完）
