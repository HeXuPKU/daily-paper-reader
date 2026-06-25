---
title: Generative Modeling of Mouse Embryogenesis for Fate and Disease Prediction
title_zh: 小鼠胚胎发生的生成建模用于命运和疾病预测
authors: "Fan, Y., Liu, X., Wang, Y., Zeng, Z., Li, L., Qiu, X., Li, Y."
date: 2026-06-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733286v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 小鼠胚胎发生的生成式建模，用于虚拟细胞命运预测，与虚拟细胞模型生成相关
tldr: 胚胎发育由基因调控网络驱动，理解其动态可预测和工程化细胞命运。Navigo框架通过整合流匹配与RNA动力学建模，从小鼠胚胎scRNA-seq（12.4M细胞，43时间点）学习发育向量场，准确映射跨谱系轨迹。在心脏发育中，可分辨先天性心脏病亚型；在零样本扰动预测中，对6个敲除基因型有效，揭示谱系特异性补偿机制。Navigo还指导成纤维细胞重编程和转录因子组合优化，为虚拟胚胎和再生医学奠定基础。
source: biorxiv
selection_source: fresh_fetch
motivation: 理解发育基因调控动态以实现细胞命运预测与工程化，现有方法缺乏生物学基础的生成模型。
method: 融合种群水平流匹配与分子水平RNA动力学建模，构建神经微分方程学习发育向量场。
result: 在小鼠胚胎发生图谱上准确映射轨迹，成功预测心脏疾病亚型、零样本扰动效应及重编程组合。
conclusion: Navigo为发育生物学提供通用AI平台，支持疾病建模、扰动预测和理性细胞命运工程。
---

## 摘要
胚胎发育由复杂的基因调控网络协调，从发育数据中学习调控动态可以让我们理解、预测并最终工程化细胞命运。这里我们介绍Navigo（https://github.com/aristoteleo/Navigo-release），一个基于生物学的生成建模框架，通过整合群体水平的流匹配与分子水平的RNA动力学建模来学习发育向量场。Navigo准确绘制了覆盖43个时间点、包含1240万个细胞的小鼠胚胎发生单细胞RNA-seq图谱中跨谱系的发育轨迹。应用于心脏发育时，Navigo通过机制性解析区分先天性心脏病亚型的调控网络实现了疾病建模。Navigo还能以零样本方式预测扰动效应，这通过六个敲除基因型的独立体内数据验证（无需扰动特异性训练），揭示了谱系特异性的基因补偿机制。此外，Navigo指导合理的细胞命运工程，例如成纤维细胞重编程分析，包括识别促纤维化屏障以阻碍心脏命运，以及评估数百对用于神经元命运的转录因子组合（每对包含一个bHLH因子和一个POU因子）。总体而言，Navigo为扰动效应预测、疾病建模和合理细胞命运工程提供了一个可泛化的AI平台，推动面向发育生物学和再生医学的基于AI的虚拟胚胎发展。

## Abstract
Embryonic development is orchestrated by complex gene regulatory networks, and learning regulatory dynamics from developmental data could allow us to understand, predict, and ultimately engineer cell fates. Here we introduce Navigo (https://github.com/aristoteleo/Navigo-release), a biologically grounded generative modeling framework that learns a developmental vector field by integrating flow matching at the population level with RNA kinetics modeling at the molecular level. Navigo accurately maps developmental trajectories across lineages on a mouse embryogenesis scRNA-seq atlas spanning 43 time points and comprising 12.4 million cells. Applied to cardiac development, Navigo enables disease modeling by mechanistically resolving regulatory networks that distinguish congenital heart disease subtypes. Navigo also predicts perturbation effects in a zero-shot manner, as validated on independent in vivo data from six knockout genotypes without perturbation-specific training, uncovering lineage-specific gene-compensation mechanisms. Moreover, Navigo guides rational cell-fate engineering, exemplified by fibroblast reprogramming analyses, including identifying pro-fibrotic barriers to cardiac fates and evaluating hundreds of pairwise transcription factor combinations for neuronal fate, each consisting of one bHLH factor and one POU factor. Overall, Navigo provides a generalizable AI platform for perturbation-effect prediction, disease modeling, and rational cell-fate engineering, advancing toward AI-based virtual embryos for developmental biology and regenerative medicine.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）

- **核心问题**：胚胎发育由复杂的基因调控网络（GRN）驱动，但传统的单细胞转录组快照只能离散地记录细胞状态，无法揭示连续的动态过程、调控机制或系统对扰动的响应。如何从静态的时序数据中学习生成发育动态，以实现对细胞命运的预测、疾病建模和工程化改造，是发育生物学和再生医学面临的根本挑战。
- **整体含义**：构建“虚拟胚胎”是重要愿景——一个可查询、可扰动、可预测的通用AI平台，使发育生物学从回顾性观察转向前瞻性预测。本文提出的Navigo框架通过生成建模将静态快照转化为连续向量场，为理解发育机制、预测疾病、指导细胞重编程提供了通用解决方案。

---

### 论文提出的方法论

- **核心思想**：整合群体水平的**流匹配（Flow Matching）**与分子水平的**RNA动力学建模**，学习一个生物约束的发育向量场。该向量场同时捕捉细胞状态随时间演化的平滑轨迹以及转录、剪接、降解的分子机制。
- **关键技术细节**：
  - **分子层面**：利用可微分RNA速度模型，输入平滑后的未剪接（unspliced）和剪接（spliced）mRNA计数，通过MLP预测每个基因的转录率α、剪接率β、降解率γ。转录率α是细胞特异性的（依赖于成熟mRNA丰度，反映上游调控），β和γ为基因特异性常数。由此定义速度场：v_u = α − β⊙u，v_s = β⊙u − γ⊙s。
  - **群体层面**：采用**迭代再流（Rectified Flow Matching）**解决无真实对应细胞的问题。初始化随机配对，然后在每一轮迭代中：① 根据当前配对训练向量场，优化目标为最小化沿线性插值路径的预测位移与实际位移之差（公式7）；② 利用当前场进行ODE积分预测下一时刻细胞状态，再通过最近邻匹配更新配对。反复迭代使配对从杂乱交叉趋于直线连贯。
  - **模型架构**：向量场网络由多个MLP组成，输入细胞状态和条件时间，输出RNA速度。
  - **可扩展性**：采用元细胞（Metacell）策略，对每种胚胎、细胞类型和时间点进行自适应K-means聚类，保留稀有细胞的同时将数据规模减少约20倍。
- **公式或算法流程（文字说明）**：
  1. 输入：各时间点细胞群体X_i（含spliced/unspliced计数）。
  2. 初始随机配对π^(0)。
  3. 对于每轮迭代k：
     - 对每对(x_i^(t), x_j^(t+1))，定义线性插值路径x(τ) = (1-τ)x_i + τ x_j，τ∈[0,1]。
     - 以L2损失最小化位移与积分速度的差异（公式7）。
     - 训练后，用当前场对X_i进行ODE积分得到预测X̃_{i+1}。
     - 对每个X̃中的细胞，在真实X_{i+1}中找最近邻更新配对π^(k)。
  4. 收敛后得到最终向量场v(x,t)。

---

### 实验设计

- **数据集**：
  - **训练集**：小鼠胚胎发生scRNA-seq图谱（Qiu et al. 2024），包含12.4M个细胞，43个时间点（E8.5到出生，6小时间隔），190+细胞类型，26条主要谱系。
  - **验证集**：独立扰动数据集（Huang et al. 2023），包含E13.5的6个KO基因型（Atp6v0a2, Gorab, Gli2, Ttc21b, Carm1, Scn10a/11a双KO）及其野生型对照，使用sci-RNA-seq3测序。
- **基准方法**：
  - 插值任务：Moscot（最优传输）、TIGON（神经ODE+动态非平衡最优传输）、Random（随机配对线性插值）、Previous/Next（直接使用相邻时间点）。
  - GRN推断：CellOracle、Dynamo。
  - 敲除预测：CellOracle、Dynamo。
- **评估场景**：
  - **轨迹映射**：插值（预测中间时间点的表达分布）和去噪（恢复被技术噪声或采样偏差隐藏的细胞群体）。
  - **GRN理解**：通过Jacobian矩阵提取调控网络，与ChIP-Atlas数据库对比（AUROC）。
  - **疾病建模**：模拟CHD基因敲除，聚类响应向量，分析功能模块、通路富集、心室/心房标志物差异。
  - **零样本敲除预测**：对6个KO基因型预测受影响基因，与实验DEG对比（Top-50精度、相关性）。
  - **重编程预测**：模拟转录因子过表达，评估方向一致性准确性；对bHLH-POU TF组合进行系统筛选（AUROC）。

---

### 资源与算力

- 论文**未明确报告**所用GPU型号、数量以及具体训练时长。仅在方法中提到“directly training deep learning models on such large-scale data is computationally prohibitive”，并采用元细胞策略降低约20倍数据量。此外在讨论中承认“Navigo still requires substantial training time”，但未给出具体数字。

---

### 实验数量与充分性

- **实验数量丰富**：
  - 插值：覆盖0.5、1.0、2.0天间隔，两种指标（Wasserstein距离、JS散度），三种基线方法，多时间点可视化。
  - 去噪：模拟设置（100个细胞-时间对，保留20%细胞）和真实场景（肌成纤维细胞E18.25异常点），包括比例恢复、标志基因DEG F1、通路富集。
  - GRN：比较10种细胞类型，使用ChIP-Atlas基准，统计差异显著。
  - CHD：44个基因+响应向量聚类、通路富集、ASD/VSD区分、调控网络可视化。
  - 敲除预测：6个基因型×多个细胞类型，Pearson相关性、Top-50精度、扰动强度超参数敏感性（m=-5~-50）、遗传补偿分析（通过同源基因模拟）。
  - 重编程：5个靶细胞类型（AUROC/AUPRC），交叉谱系因子案例，bHLH单因子排名（10个中7个验证），bHLH-POU组合筛选（多种阈值下AUROC）。
- **充分性与公平性**：
  - 与多个代表性基线方法比较（Moscot, TIGON, Dynamo, CellOracle, Random），统计检验（Wilcoxon signed-rank）确认显著性。
  - 消融实验：对扰动强度超参数m进行了敏感性分析（图4f），对bHLH-POU组合筛选进行了编程效果阈值和表达阈值的系统扫描（图5k、补充图20-21），但缺少对模型组件（如是否去掉RNA动力学约束）的消融。
  - 实验设计客观：使用独立验证集（KO数据集与训练集来自不同研究），避免过拟合；重编程预测零样本，验证来自独立文献和系统筛选数据。

---

### 论文的主要结论与发现

1. **Navigo能准确学习发育向量场**：在插值和去噪任务上显著优于现有方法（p<0.001），并能恢复被技术噪声掩盖的生物信号。
2. **可提取生物可解释的调控网络**：Jacobian网络与ChIP-seq数据高度一致（AUROC优于CellOracle和Dynamo）。
3. **揭示CHD亚型的功能模块和机制差异**：通过模拟敲除，识别出4个功能聚类（心脏、血管、胚胎、神经），与疾病临床表现吻合；成功区分ASD（影响心房标志物）和VSD（影响心室标志物）。
4. **零样本预测遗传敲除效果**：在独立数据集上，预测的基因表达变化与实验DEG数目正相关（r=0.74），Top-50精度优于随机和CellOracle；揭示了基因家族内补偿机制（如Gli2敲除后，Gli1/Gli3的调控方向性决定哪些下游基因敏感）。
5. **指导细胞重编程**：成功预测已建立的跨谱系重编程因子（如Ascl1对心脏），识别促纤维化障碍，系统筛选bHLH-POU组合实现AUROC=0.764，且预测精度与TF表达水平正相关。

---

### 优点

1. **生物学约束强**：将RNA动力学方程（转录、剪接、降解）直接嵌入神经网络，保证向量场的生物物理合理性，而非纯数据驱动的拟合。
2. **无对应细胞要求**：通过迭代再流从群体分布推断连续轨迹，解决了scRNA-seq无真实细胞配对的关键难题。
3. **零样本泛化能力**：无需在扰动数据上训练即可预测敲除效果，并成功验证于独立数据集，体现了生成模型的真正的预测力。
4. **可扩展性好**：采用元细胞策略，在保持生物学多样性的前提下显著降低计算成本；与神经ODE相比，流匹配方法避免了向后积分，训练更高效。
5. **多场景统一框架**：同一个模型支持轨迹映射、GRN推断、疾病机制理解、扰动预测、重编程筛选，展示了通用AI平台潜力。
6. **实验验证深入**：在重编程中不仅验证已知因子，还独立识别交叉谱系调节因子，并通过系统组合筛选提供定量基准（AUROC），证明了方法的实用性。

---

### 不足与局限

1. **计算资源未公开**：未说明训练所需的GPU型号、数量及精确时长，不利于复现和资源评估。
2. **零样本扰动预测精度受限**：对于低表达基因或信号较弱的细胞-基因型组合，预测效果下降（图4b），且未在扰动数据上进行微调或训练，可能遗漏复杂效应。
3. **早期胚胎阶段缺失**：训练数据仅覆盖E8.5之后，缺少前期（植入前、原肠胚）关键事件，限制了模型的完整性和泛化性。
4. **未整合细胞增殖/死亡与谱系关系**：当前模型仅考虑基因表达向量场，不显式建模细胞增殖、死亡或谱系祖先-后代关系，这可能会影响长期预测的准确性。
5. **空间与多模态信息缺失**：未利用空间转录组学、染色质可及性等数据，无法预测组织形态发生或表观遗传调控。
6. **消融实验不足**：对模型核心组件（如是否使用RNA动力学）的贡献缺乏系统消融分析；对超参数（如m）的敏感性测试仅限于单一任务。
7. **基准方法覆盖不全面**：与Moscot、TIGON等比较时，主要集中在插值任务；在GRN和重编程预测中，与Dynamo、CellOracle的比较仅部分展示（如CHD分析中Dynamo聚类无生物意义，图3b仅AUROC比较）。
8. **风险与偏差**：训练数据来源于单个研究（Qiu et al. 2024），可能存在批次效应或特定测序偏差；CHD基因数据库可能不完全，重编程验证依赖少数文献，存在发表偏倚。

（完）
