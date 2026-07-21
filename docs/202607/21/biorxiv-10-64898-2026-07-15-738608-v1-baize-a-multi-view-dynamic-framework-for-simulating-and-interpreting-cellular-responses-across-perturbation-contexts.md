---
title: "BaiZe: A Multi-View Dynamic Framework for Simulating and Interpreting Cellular Responses Across Perturbation Contexts"
title_zh: BaiZe：一种用于模拟和解释扰动背景下细胞响应的多视角动态框架
authors: "Zeng, Q., Cai, W., Tian, R., Wang, Q., Zhou, D., Pan, M., Yang, H., Liu, Z., Lin, G. N., Wang, Z."
date: 2026-07-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.15.738608v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 虚拟细胞模型模拟扰动响应
tldr: 现有模型仅针对特定扰动类型或生物场景，无法泛化预测细胞响应。BaiZe提出多视图条件状态转移框架，利用对照转录组与多种扰动信息预测扰动后转录组，支持新细胞状态、多基因组合、化学结构剂量、时间阶段及跨物种预测。在多个扰动设定中有效恢复未知条件下的转录程序，结合染色质可及性数据可解释响应相关基因及通路，并实现人鼠间少量样本迁移预测。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738608-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1514, \"height\": 1870, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738608-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1458, \"height\": 1864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738608-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1514, \"height\": 1994, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738608-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1460, \"height\": 1026, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738608-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1469, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738608-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1522, \"height\": 1912, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738608-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1451, \"height\": 1859, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738608-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1496, \"height\": 1189, \"label\": \"Figure\"}]"
motivation: 现有模型局限于特定扰动类型或生物上下文，亟需一个统一框架以泛化预测不同扰动下的细胞响应。
method: BaiZe采用多视图条件状态转移模型，从对照转录组出发，结合遗传、化学、时间及可选染色质可及性信息，预测扰动后转录组。
result: 在多种扰动设定下，BaiZe有效恢复未知条件下主要的转录响应程序，并借助ATAC-seq数据提升状态转移预测，实现跨物种迁移。
conclusion: BaiZe提供了一个广泛适用的框架，用于预测和解释上下文依赖的细胞响应，并支持跨扰动场景的假设优先化。
---

## 摘要
准确预测细胞如何响应扰动对于理解细胞调控和优化实验干预至关重要，然而现有模型通常针对特定扰动类型或生物学背景设计。在此，我们提出BaiZe，一种多视角条件状态转移框架，它能够从控制状态转录组以及遗传、化学、时间以及可选的染色质可及性信息预测扰动后转录组。BaiZe将扰动响应建模为细胞状态之间的上下文依赖转换。BaiZe支持对未见过细胞状态和遗传扰动、未见多基因组合、化学结构和剂量、时间阶段以及物种背景的预测。在不同扰动设置下的基准测试表明，BaiZe能够有效恢复先前未见条件下的主要转录响应程序。整合匹配的ATAC-seq上下文进一步改进了选定的状态转换预测，并实现了对染色质区域与响应相关基因和通路的基于模型的归因。BaiZe还支持从小鼠细胞系统到人类细胞系统的扰动响应少样本迁移，并将预测转录组与候选形态学投影连接起来。为便于解释和使用，BaiZe-Agent将响应基因、通路、染色质证据、跨物种预测和投影表型组织成可追踪、可查询的扰动记录。综上，BaiZe提供了一个广泛适用的框架，用于预测和解释上下文依赖的细胞响应，并在不同扰动设置中优先排序假设。

## Abstract
Accurately predicting how cells respond to perturbations is important for understanding cellular regulation and prioritizing experimental interventions, yet existing models are often designed for specific perturbation types or biological contexts. Here we present BaiZe, a multi-view conditional state-transition framework that predicts the post-perturbation transcriptome from a control-state transcriptome together with genetic, chemical, temporal and optional chromatin-accessibility information. BaiZe models perturbation responses as context-dependent transitions between cellular states. BaiZe supports prediction across held-out cell states and genetic perturbations, unseen multi-gene combinations, chemical structures and doses, temporal stages and species contexts. Benchmarking across diverse perturbation settings demonstrates that BaiZe effectively recovers major transcriptional response programs under previously unseen conditions. Incorporating matched ATAC-seq context further improves selected state-transition predictions and enables model-based attribution of chromatin regions to response-associated genes and pathways. BaiZe also supports few-shot transfer of perturbation responses from human to mouse cellular systems and connects predicted transcriptomes to candidate morphology projections. To facilitate interpretation and use, BaiZe-Agent organizes response genes, pathways, chromatin evidence, cross-species predictions and projected phenotypes into traceable, queryable perturbation records. Together, BaiZe provides a broadly applicable framework for predicting and interpreting context-dependent cellular responses and for prioritizing hypotheses across diverse perturbation settings.

---

## 论文详细总结（自动生成）

# BaiZe：一种用于模拟和解释扰动背景下细胞响应的多视角动态框架 —— 中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：现有单细胞扰动响应预测模型通常针对特定扰动类型（如单一基因敲除、药物处理）或特定生物学背景设计，缺乏统一框架来泛化预测多样化的扰动场景（包括新细胞状态、多基因组合、新化合物/剂量、时间过程、跨物种迁移），难以为虚拟细胞（virtual cell）研究提供可比较、可解释的预测。
- **整体含义**：作者提出 BaiZe，旨在将不同扰动任务统一为“从对照状态到扰动后状态的转录组转移”问题，利用条件扩散模型生成响应残差，并结合多模态数据（RNA、ATAC、化学结构、时间标签等）增强预测，同时通过可解释归因、跨物种少样本迁移、形态学投影和自然语言查询接口（BaiZe-Agent）提供完整的假设生成与验证工具链。

## 2. 方法论
### 2.1 核心思想
- 将细胞响应建模为**条件状态转移**：给定对照细胞转录组，结合扰动条件，预测转录组变化残差（Δ），再恢复扰动后转录组。
- 采用**多视图条件编码**：统一处理单基因、多基因组合、化合物（Morgan指纹+剂量）、时间/状态标签、可选染色质可及性（ATAC-seq）等条件输入。
- 使用**条件扩散模型**生成响应残差，与确定性分支（均值头+基因先验头）结合，以分离主要变化与随机残差。

### 2.2 关键技术细节
- **模型架构**：
  - **细胞背景编码器**：将对照RNA表达映射为潜表征。
  - **条件编码器**：对扰动信息（基因嵌入、Morgan指纹、剂量、时间、ATAC潜表征等）进行编码。
  - **解码器**：包含确定性分支（预测主变化）和残差扩散分支（通过去噪扩散预测扰动特异性残差）。最终预测为：  
    Δx̂ = μ_det + λ_res · r̂_res，  
    扰动后转录组 = 对照转录组 + Δx̂。
- **残差扩散目标**：将观测变化与确定性预测之差作为残差目标，进行前向加噪和反向去噪，损失为均方误差。
- **条件扩散推理**：生成时先算确定性均值，再采样残差，按比例相加。
- **支持跨物种**：利用Ensembl一对一同源基因对齐人类与小鼠基因空间（15,520基因），进行零样本或少样本迁移。
- **ATAC归因**：通过特征重要性评分（类似梯度/注意力）定位与预测改善相关的染色质峰（启动子、基因体、远端），并连接至校正基因与通路。

### 2.3 算法流程（文字说明）
1. 预处理：对照与扰动细胞RNA（log1p归一化），配对/匹配的ATAC低维嵌入，条件编码（基因ID、指纹、剂量、时间/状态标签）。
2. 训练：输入对照RNA+条件→背景编码+条件编码→确定性头预测主变化→扩散头预测残差→总损失（均值误差+扩散误差）。验证集选取checkpoint。
3. 推理：给定对照细胞（RNA ± ATAC）和条件，计算确定性预测，经反向扩散生成残差，相加得到完整响应Δ，再加至对照得到扰动后转录组。

## 3. 实验设计
### 3.1 使用的数据集/场景
| 场景 | 数据集 | 任务 | 分割策略 |
|------|--------|------|----------|
| 未知细胞状态 | Human embryo 10x Multiome (GSE218314) | HYPO/VE细胞状态 | 留出HYPO/VE仅测试 |
| 未见遗传扰动 | Adamson Perturb-seq (GSE90546) | ER stress相关CRISPR | 留出部分扰动（如三基因） |
| 多基因组合 | Norman Perturb-seq (GSE133344) | 双基因、三基因组合 | 按基因覆盖程度分层留出 |
| 药物结构+剂量 | Sci-Plex (GSE139944) | 10,100,1000,10000 nM | 随机细胞、未见药物、留出K562/A549细胞系 |
| ATAC辅助 | MultiPerturb-seq (GSE277747) | SMARCA4,BAZ1B等 | RNA-only vs RNA+ATAC |
| 时间预测 | HSPC time-course multiome (GSE305370) | Day2→Day3/7/10 | 留出供体13176 |
| 跨物种 | 人CD8 T细胞(GSE218988)→小鼠TIL(GSE203593) | ARID1A,PDCD1 | 零样本、5%/10%小鼠少样本 |
| SNP映射 | Replogle K562 CRISPRi | HIF1A | 33个适应细胞，97个留出测试 |

### 3.2 Benchmark
- 通用指标：全基因/前K响应基因（Top20/50）上的**Delta Pearson相关系数**、**均方误差（MSE）**、**反向方向率（ODR）**。优先在Δ空间评估。
- 对比方法：scGPT、Geneformer、scGen、Ridge回归（线性基线）、GEARS、UCE、直接加和基线（组合任务）、MorphDiff（形态投影）。
- 每个任务均与任务匹配的基线（如GEARS用于遗传、CPA/chemCPA用于药物等文献提及但未全部复现，文中主要对比了GEARS与Ridge）。

### 3.3 对比方法列表
- 未见细胞状态：scGPT [21], Geneformer [20], scGen [10], Ridge [25]
- 未见遗传扰动：GEARS [16], Ridge
- 组合预测：直接加和（expression-space addition）
- 药物：简化为与简单线性基线比较，实际上主要展示BaiZe自身在多个设置下的表现
- 跨物种：平均响应迁移、scGPT、UCE、BaiZe RNA-only
- ATAC消融：RNA-only、RNA+ATAC、不同ATAC引导尺度、shuffled ATAC

## 4. 资源与算力
- 论文中**未明确说明**所使用的GPU型号、数量、训练时长等具体算力信息。仅在Funding部分提及国家科学基金支持，未提供硬件细节。因此需要指出：**本文未披露模型的训练资源与耗时**。

## 5. 实验数量与充分性
### 5.1 实验数量
- 覆盖10个以上独立任务/数据集（包括6大类扰动场景、多个留出设置）。包含多种消融实验（ATAC引导尺度、RNA vs RNA+ATAC、shuffled ATAC、确定性分支消融、组合策略对比、零样本 vs 5%/10%少样本、不同引导尺度）。
- 每个任务均报告多个指标（Pearson、MSE、TopK Delta Pearson、ODR），部分给出单细胞与聚合级结果。
- 形态投影为示例性，无定量验证。

### 5.2 充分性与公平性
- **优点**：实验设计较为全面，覆盖了主流单细胞扰动预测的多个困难场景；使用了response-focused指标而非仅全转录组相似度；在跨物种、时间预测等新场景进行了开创性评估。
- **潜在不足**：
  - 部分任务未与所有最新基线全面对比（如药物任务未与chemCPA直接比较；组合任务仅与加和基线比较，未与CPA等对比）。
  - 跨物种对比中，UCE使用零样本嵌入作为输入，而非直接进行扰动预测，比较不完全公平。
  - 形态投影无配对显微镜数据验证，仅为演示。
  - 未提供多次随机种子运行的统计误差棒（文中提及“点估计不完全表征不确定性”）。
  - 各任务分开训练，未展示单一预训练模型统一预测所有扰动类型的能力。

## 6. 主要结论与发现
1. **统一框架有效**：BaiZe在7个异构扰动场景下均能恢复主要转录响应程序，性能优于或持平现有专门模型。
2. **ATAC上下文提升预测**：尤其在时间预测和染色质调控因子扰动中，RNA+ATAC模型改善Top20 Delta Pearson和方向一致性；归因分析显示启动子区域峰贡献最大，并可用于发现候选调控连接（如NRG1-ERBB4）。
3. **少样本跨物种迁移**：零样本预测有一定效果（Top20 Delta Pearson ~0.43），但5%~10%的小鼠扰动细胞适应后显著提升（~0.86），证明少量目标物种数据可校准系统性差异。
4. **药物响应可推广**：能预测未见分子结构/剂量的药物响应，但对不同细胞系泛化性差异大（K562较好，A549较差），表明细胞上下文重要性。
5. **时间预测**：利用时间匹配的ATAC可显著改善沿分化轨迹的转录预测，恢复造血谱系特异性基因表达程序（如MkP中巨核细胞/凝血相关基因）。
6. **SNP提示功能**：以rs2057482为线索模拟HIF1A抑制，预测的缺氧应答基因（LDHA,PDK1,BNIP3）与独立CRISPRi实验一致，证明模型可用于遗传线索驱动假设。
7. **BaiZe-Agent**：提供自然语言接口，便于非专家探索预测结果。

## 7. 优点
- **设计统一性**：将多种扰动类型（遗传、化学、时间、ATAC、跨物种）纳入同一条件状态转移框架，便于扩展和比较。
- **残差扩散策略**：分离确定性主变化与扩散残差，既能保留主要响应趋势，又能捕获残差波动，降低生成不稳定。
- **响应聚焦评估**：坚持在Δ空间用TopK Delta Pearson、ODR等指标，避免被全局相似性掩盖。
- **多模态归因**：基于ATAC特征重要性连接染色质峰与校正基因，并提供可解释的调控假设（如NRG1-ERBB4）。
- **跨物种少样本策略**：利用人类数据预训练+少量目标物种数据适应，实用性强。
- **交互式Agent**：降低用户使用门槛，增强结果可解释性。

## 8. 不足与局限
- **缺少统一预训练模型**：每个基准任务分开训练，未展示一个模型同时支持所有扰动类型的泛化能力。
- **基线对比不全面**：在药物任务中未与CPA/chemCPA等专门模型定量对比；组合任务仅与简单加和基线比较；跨物种任务中UCE的使用方式可能需要更公平对齐。
- **缺乏统计不确定性**：未提供多次重复运行的误差范围，点估计可能掩盖波动（文中承认这一点）。
- **形态投影无验证**：MorphDiff生成图像无配对显微镜数据，仅为概念演示。
- **SNP分析仅备选验证**：仅使用一组CRISPRi数据验证，未进行多重假设检验校正。
- **数据预处理依赖**：模型性能对对照匹配、基因空间对齐、ATAC匹配方法敏感；仅使用一对一同源基因可能忽略了物种特异性基因和调控元件。
- **ATAC归因并非因果证据**：虽然提供模型级归因，但需要实验验证才能建立因果联系。
- **BaiZe-Agent不进行新预测**：仅能查询预存结果，不支持实时推理或新分析。

（完）
