---
title: "PanvaR: An R package for fine-mapping and visualizing results from genome-wide association studies"
title_zh: PanvaR：一个用于全基因组关联研究结果精细定位和可视化的R包
authors: "Luebbert, C., Dhakal, R., Ozersky, P., Lee, S., Mockler, T. C., Baxter, I."
date: 2026-07-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.15.738769v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 用于GWAS精细映射和结果可视化的R包
tldr: GWAS可识别与性状关联的SNP，但受连锁不平衡影响难以直接定位因果基因。PanvaR是一个R包，集成现有细映射工具，无缝进行GWAS后续分析，输出每个SNP的LD和效应预测，并结合附近基因位置生成精简候选基因列表。它提供交互式与静态可视化图表及结果表格。该工具旨在桥接GWAS与基因发现，加速定量遗传研究中的关键步骤。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738769-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1615, \"height\": 957, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738769-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1548, \"height\": 923, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738769-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1681, \"height\": 988, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738769-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1653, \"height\": 1277, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-15-738769-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1651, \"height\": 1273, \"label\": \"Figure\"}]"
motivation: 减少GWAS与基因发现间的鸿沟，加速定量遗传研究中细映射与候选基因筛选的分析流程。
method: 集成LD计算、SNP效应预测及基因注释，自动处理GWAS峰值，输出包含LD信息、效应值和候选基因的富集列表，并提供可视化功能。
result: 生成交互式与静态可视化图，以及包含LD、效应预测和候选基因的表格，辅助用户快速定位因果基因。
conclusion: PanvaR作为R包无缝整合细映射流程，有效增强GWAS后分析效率，助力作物基因组研究中基因发现的快速迭代。
---

## 摘要
全基因组关联研究（GWAS）使用统计模型将单核苷酸多态性（SNP）与感兴趣的表型相关联。这种对整个基因组的扫描识别出与表型相关的区域，但由于连锁不平衡（LD），仅靠GWAS无法确定导致表型变异的单个基因。相反，需要对GWAS区域进行精细定位，这需要使用额外的工具和软件。随着多种农作物中更多泛基因组资源的引入（Guo et al. 2025; Hufford et al. 2021），这些精细定位工作的准确性正在提高，为利用关于等位基因变异的新信息进行基因发现提供了机会（Shi et al. 2023; Della Coletta et al. 2021）。PanvaR是一个旨在整合现有软件和资源，以无缝步骤执行GWAS和精细定位的工具。对于每个识别的GWAS峰，panvaR输出每个SNP的LD和SNP效应预测信息，并通过叠加附近基因的位置，生成一个精炼的可能候选基因列表。我们已将PanvaR实现为一个R包“panvaR”，它运行分析函数，创建交互式和静态可视化，并输出结果表格。该工具旨在弥合GWAS与基因发现之间的差距，加速数量遗传学研究中的一个重要步骤。

## Abstract
Genome-wide association studies (GWAS) use statistical models to correlate single nucleotide polymorphisms (SNPs) to a phenotype of interest. This scan of the entire genome identifies regions of association with a phenotype, but due to linkage disequilibrium (LD), GWAS on their own cannot identify single genes responsible for phenotypic variation. Rather, fine-mapping of GWAS regions is required, necessitating the use of additional tools and software. With the introduction of more pangenomic resources in a number of crops (Guo et al. 2025; Hufford et al. 2021), the fidelity of these fine-mapping efforts is growing, presenting the opportunity to leverage new information about allelic variation towards gene discovery (Shi et al. 2023; Della Coletta et al. 2021). Panvar is a tool developed to integrate existing software and resources to perform GWAS and fine-mapping in one seamless step. For each identified GWAS peak, panvaR outputs information about LD and SNP effect prediction for each SNP and by layering locations of nearby genes, creates a refined list of possible candidate genes. We have implemented Panvar as an R package, "panvaR", which runs the analysis functions, creates interactive and static visualizations, and outputs results tables. This tool seeks to bridge the gap between GWAS and gene speeding up an important step of quantitative genetic studies.

---

## 论文详细总结（自动生成）

### 论文核心问题与整体含义（研究动机和背景）
- **核心问题**：全基因组关联研究（GWAS）能够识别与性状关联的基因组区域，但由于连锁不平衡（LD），一个GWAS峰可能包含成百上千个基因，无法直接确定因果基因。需要精细定位（fine-mapping）来缩小候选范围，但现有工具分散，数据整合（如LD、SNP效应预测、基因注释等）繁琐耗时，缺乏一个物种无关的、集成化的分析可视化平台。
- **整体含义**：随着泛基因组资源的丰富，研究者有机会利用全序列变异信息进行更准确的基因发现，但如何高效地从大量多态性中筛选因果基因成为瓶颈。PanvaR作为一个R包，旨在将GWAS后续的精细定位流程整合为单一、无缝的步骤，加速从关联信号到候选基因的过渡，为作物基因组研究和育种提供实用工具。

### 论文提出的方法论
- **核心思想**：通过整合多种数据类型（SNP的LD、p值、效应预测等）和基因注释信息，对单个GWAS位点（以tag SNP为中心）定量评分并可视化，自动生成精简的候选基因列表。
- **关键技术细节**：
  1. **输入**：需提供基因型文件（VCF或PLINK格式）、基因注释文件（位置和注释）、以及感兴趣的位点（通常是一个tag SNP）。
  2. **预处理**（`make_panvar_inputs()`）：使用PLINK2进行可选的质量控制（如MAF和缺失率过滤），并标准化输入格式。
  3. **可选重跑GWAS**（`panvar_mvp_gwas()`）：调用rMVP包运行广义线性模型（GLM）或混合线性模型（MLM），为后续精细定位补充p值信息。
  4. **生成SNP与基因表**（`make_panvar_tables()`）：围绕tag SNP定义窗口（例如±75 kb），计算每个SNP的LD（相对于tag SNP）、距离、p值。提供函数将SNP级指标聚合成基因级指标（默认取基因区域内SNP的最大值）。支持生成**SNP评分**：先将各指标统一方向（如p值取倒数）、进行min-max归一化，再取加权或不加权的均值（默认使用p值、距离、LD，权重相等）。
  5. **可视化**（`plot_panvar()`）：绘制垂直方向的曼哈顿图，点颜色和形状可由用户定义变量（如LD）；右侧显示基因位置和标签，基因标签旁的点颜色可表示基因级重要性（如评分）；底部有SNP密度毯状图。
  6. **交互式界面**：提供Shiny应用（`panvar_shiny()`），允许用户上传数据、调整参数并交互查看结果。
- **算法流程（文字说明）**：
  1. 输入基因型和注释文件，指定tag SNP。
  2. 格式化输入并可选重跑GWAS。
  3. 在tag SNP周围设定窗口，计算该窗口内所有SNP的LD、p值、距离等指标。
  4. (可选) 对SNP级指标进行归一化并加权平均得到SNP评分。
  5. 将SNP评分聚合到基因（或基因±缓冲区域）上，得到基因级评分。
  6. 输出包含SNP和基因信息的表格，并生成整合的可视化图表。

### 实验设计
- **数据集/场景**：
  - **案例一**：绿色狗尾草（*Setaria viridis*）的落粒性表型，使用Mamidi et al. (2020) 的数据和已发表的*SvLes1*基因（Sevir.5G085400）。
  - **案例二**：高粱（*Sorghum bicolor*）的非结构性碳水化合物水平，使用Brenton et al. (2020) 的数据和已发表的*Sobic.004G301500*基因（编码液泡铁转运蛋白）。
- **Benchmark**：未设立独立的基准数据集或与其他精细定位工具（如Bayesian方法、弹性网等）进行定量对比。验证方式为检查已知因果基因在PanvaR输出中的排名。
- **对比方法**：无直接方法对比。文中仅提及Mamidi等人使用snpEff寻找蛋白破坏性变异，而PanvaR额外整合了LD信息；Brenton等人通过候选基因列表筛选，PanvaR利用DNA语言模型（Plant Caduceus）的SNP保守性分数进行聚合排名。

### 资源与算力
- 论文**未明确说明**使用的计算资源（如GPU型号、数量、训练时长等）。PanvaR主要依赖PLINK2和rMVP进行SNP操作和GWAS，这些在普通CPU服务器上即可运行。文中的案例可能仅用到了标准计算节点，但具体规格不详。

### 实验数量与充分性
- **实验数量**：仅两个案例，每个案例展示一个GWAS峰的分析结果。
- **充分性**：两个案例覆盖了不同物种（禾本科）和表型，成功复现了已知基因（分别排名第二和第五），初步验证了工具的有效性。但实验数量较少，缺少：
  - 与其他精细定位方法的系统比较。
  - 不同参数设置（如窗口大小、评分加权模式）的消融实验。
  - 对假阳性/假负率的评估。
  - 在更多物种或复杂性状上的测试。
- **客观性与公平性**：作者是工具开发者，选择已发表基因作为验证案例，并非盲测，存在一定的偏差风险。但结果较为保守（未声称总是第一），整体较为客观。

### 论文的主要结论与发现
- PanvaR能有效整合LD、p值、距离、以及用户自定义的SNP重要性指标（如DNA语言模型得分），并自动聚合为基因级评分，帮助用户在GWAS峰中快速筛选候选基因。
- 在两个案例中，已知因果基因均排在候选列表前列（分别为第2和第5），表明该方法能够复现已发表的精细定位结果。
- 工具设计注重易用性和灵活性：支持任意物种、可集成新指标、提供交互式和静态图表，并可通过Shiny界面降低使用门槛。
- PanvaR填补了从GWAS到基因发现之间的数据整合空白，是一个有用的补充工具，但输出仍需人工审查。

### 优点
1. **集成性强**：将PLINK（LD计算）、rMVP（GWAS）、基因注释、自定义评分整合在一个包内，减少数据转换和脚本编写的麻烦。
2. **灵活性高**：用户可任意添加新的SNP级或基因级定量指标（如功能预测得分、表达QTL等），并通过评分系统融入分析。
3. **可视化直观**：垂直曼哈顿图结合基因侧栏，同时显示SNP和基因信息，信息密度高；Shiny版本支持交互式探索。
4. **物种无关**：不依赖特定物种的参考基因组，只要有基因注释文件即可使用。
5. **可扩展性**：未来可集成更复杂的LD结构可视化或统计精细映射结果作为额外决策层。

### 不足与局限
1. **依赖单tag SNP，忽略复杂LD结构**：仅以单个lead SNP为中心计算LD，无法展示全配对LD矩阵或检测“合成关联”（稀有变异与常见变异连锁、多基因控制等）导致假阳性。
2. **缺乏统计推断**：采用启发式加权平均评分，而非贝叶斯或Frequentist统计精细映射方法，不能提供因果后验概率或置信集。文中也提到统计工具在植物中的验证尚不充分，但PanvaR并未实现此类方法。
3. **实验结果有限**：仅两个案例，未进行系统基准测试或大规模验证，其在不同物种、不同遗传结构下的性能未知。易用性提升的效果缺乏定量评估（如节省时间、复现准确率等）。
4. **对用户自定义指标的质量依赖性高**：评分优劣完全取决于用户提供的指标，若指标噪声大或错误，可能误导候选基因排序。
5. **人工审查仍必要**：作者明确指出工具输出应手动检查，排名靠前的基因不一定为因果基因，存在假阴性风险。

（完）
