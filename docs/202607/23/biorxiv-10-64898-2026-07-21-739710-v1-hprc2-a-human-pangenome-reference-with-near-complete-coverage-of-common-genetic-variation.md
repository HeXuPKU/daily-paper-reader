---
title: "HPRC2: A human pangenome reference with near-complete coverage of common genetic variation"
title_zh: HPRC2：近乎完整覆盖常见遗传变异的人类泛基因组参考
authors: "Lucas, J. K., Hebbar, P., Liao, W.-W., Macias-Velasco, J. F., Novak, A. M., Asri, M., Balacco, J. R., Blair, A. P., Ebler, J., Gardner, J. M. V., Geleta, M., Groza, C., Guarracino, A., Heringer, P., Hickey, G., Lu, S., Marin, M. G., Markovic, C., Mastoras, M., Mayoud, C., McNulty, B., Menendez, J. M., Minkina, A., Mohanty, S. K., Monlong, J., Munson, K. M., Oshima, K. K., Porubsky, D., Ranallo-Benavidez, T. R., Seligmann, W. E., Shemirani, R., Violich, I., Yoo, D., Zhuo, X., Albracht, D., Alexandrov, I. A., Allen, J., Alsheikh-Ali, A. A., Andrews, C., Antipov, D., Antonacci-Fulton, L., Arguell"
date: 2026-07-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.21.739710v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: "提供捕获常见变异的泛基因组参考,支持与GWAS整合"
tldr: "传统单一参考基因组难以全面表征群体遗传变异。HPRC2通过优化样本选择算法，整合460个高质量单倍型，覆盖All of Us队列中超过99%的常见变异。利用长读长测序和新型组装工具，实现了数千条端粒到端粒染色体，并将结构错误和碱基错误减半。该资源不仅提供了泛基因组坐标系统，还首次匹配了大规模长读长泛转录组和泛表观基因组，推动了基因组分析的进步。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-21-739710-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 1200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-21-739710-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1777, \"height\": 1123, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-21-739710-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1710, \"height\": 2201, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-21-739710-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1740, \"height\": 2247, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-21-739710-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1751, \"height\": 1583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-21-739710-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1712, \"height\": 1175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-21-739710-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1670, \"height\": 1748, \"label\": \"Figure\"}]"
motivation: 克服单一参考基因组的固有局限，整合群体中存在的遗传变异以更全面地代表人类基因组多样性。
method: 采用优先覆盖常见变异的样本选择算法，结合高覆盖长读长与超长读长测序，使用现代组装和抛光工具生成高质量单倍型。
result: "构建460个单倍型，覆盖超过99%的常见变异，实现数千条T2T染色体，结构不可靠区域和单个碱基错误较HPRC1减半。"
conclusion: 提供了更全面、更精确的人类泛基因组参考，包括泛转录组和泛表观基因组，并衍生出新的分析工具与应用，提升了对非参考变异的研究能力。
---

## 摘要
泛基因组参考通过整合群体中存在的变异，克服了任何单个参考基因组固有的局限性。我们展示了人类泛基因组参考联盟（HPRC）的第二版（HPRC2），这是一个公开可用的第二阶段泛基因组，与HPRC第一版（HPRC1）相比，基因组数量增加了约五倍，并且在基因组完整性、连续性和准确性方面有可测量的改进。通过采用优先考虑常见变异覆盖的有原则的算法选择样本，HPRC2贡献了460个单倍型，共同捕获了All of Us研究计划第8版队列中观察到的超过99%的常见变异。结合高覆盖度的长读长和超长读长以及现代组装和抛光工具，我们生成了数千个端粒到端粒（T2T）染色体，并且与HPRC1相比，结构不可靠区域的数量以及每个单倍型的个体碱基错误均减半。我们用全基因组多重比对和基因注释来补充这些组装，并推导出正式的泛基因组坐标系统以处理非参考变异，证明单个人类基因组包含超过十万个无法用现有参考基因组简洁描述的变异。我们还首次展示了这种规模下匹配的长读长支持的泛转录组和泛表观基因组，提供了覆盖每个基因组的连续局部祖先估计，并概述了一系列利用泛基因组资源改进基因组学分析的新工具和应用。

## Abstract
A pangenome reference overcomes the inherent limitation of any individual reference genome by integrating the variation present in a population. We present the Human Pangenome Reference Consortium's (HPRC) Release 2 (HPRC2), an openly available, second phase pangenome that is an approximately fivefold expansion in genome number over HPRC Release 1 (HPRC1) and measurable improvement in genome completeness, contiguity, and accuracy. Selecting samples with a principled algorithm prioritising common variant coverage, HPRC2 contributes 460 haplotypes that together capture over 99% of common variation observed in the All of Us Research Program v8 cohort. Combining high-coverage long and ultra-long reads with modern assemblers and polishers, we produce thousands of telomere-to-telomere (T2T) chromosomes, and relative to HPRC1 halve the number of structurally unreliable regions as well as individual base errors per haplotype. We complement the assemblies with whole genome multiple alignments and gene annotations, and derive formal pangenome coordinate systems for addressing off-reference variation, demonstrating that individual human genomes contain more than one hundred thousand variants not succinctly described with respect to existing reference genomes. We also present the first matched long-read backed pantranscriptome and panepigenome at this scale, provide continuous local-ancestry estimates spanning every genome, and outline a host of new tools and applications that leverage the pangenome resource for improved genomics analysis.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **核心问题**：传统的单一线性参考基因组（如 GRCh38）无法全面捕捉人类群体中存在的遗传变异，尤其是结构变异和稀有变异，导致对非参考变异的研究受限、参考偏差严重。
- **研究背景**：虽然已有 T2T-CHM13 实现了无间隙单倍体参考，但群体层面的变异仍然缺失。HPRC 的第一版（HPRC1）构建了包含 94 个单倍型的泛基因组，但仍不够完善。
- **整体含义**：HPRC2 旨在构建一个更大、更准确、更全面的第二版人类泛基因组参考，覆盖常见变异的绝大部分，并提供匹配的转录组和表观基因组数据，推动更公平、更精确的基因组分析。

## 2. 方法论：核心思想、关键技术细节、算法流程
- **样本选择 – MaxVar 算法**：
  - 基于 1000 Genomes Project 已有短读基因型数据，采用迭代贪心算法。
  - 每一轮枚举当前参考中未覆盖的常见双等位变异，按个体能新增覆盖的变异数量降序排列，选择排名最高的样本加入参考。
  - 重复直至达到目标单倍型数量（HPRC2 共 460 个单倍型，其中 HPRC1 的 88 个为基础）。
  - 覆盖度定义为在参考面板中至少有一个携带者（ATF ≥ 1%）。
- **测序与组装**：
  - 数据来源：PacBio HiFi、Oxford Nanopore Ultra-Long (ONT UL)、Illumina Hi-C。
  - 组装工具：Hifiasm（v0.19.7/0.19.9），部分样本用 Verkko 补充（针对 Y 染色体和近端着丝粒短臂）。
  - 抛光：DeepPolisher（encoder-only transformer），结合 PHARAOH 管道修正相位错误。
  - 后处理：去除 EBV、衔接子污染；重新组装线粒体。
- **泛基因组对齐**：
  - 三种互补表示：Minigraph（结构变异分辨率）、Minigraph-Cactus (MC)（碱基级，主要针对可比对区域）、IMPG/PGGB（参考无关，涵盖所有序列包括着丝粒）。
- **泛基因组坐标系**：
  - **Pantree**：构建最小生成树，索引非参考变异（SNP、indel、SV）。
  - **GRef (Graph Reference)**：扩展线性参考，添加一组顶点不相交的非参考插入序列 contigs，允许在标准 VCF 中表达嵌套变异。

## 3. 实验设计：数据集、基准、对比方法
- **数据集**：
  - 训练/选择：1000 Genomes Project 样本（多数，N≈3202 用于后期基因型填充）。
  - 覆盖度评估：All of Us Research Program v8 队列（约 44 万样本）。
  - 基准测试：HG002（T2T 完美参考）、GIAB v5.0 基准、GIAB v3.6 基因组背景分层。
  - 更不用说额外功能数据：PacBio Kinnex RNA-seq（206 样本）、Fiber-seq（38 样本）、甲基化数据（所有样本）。
- **基准与对比**：
  - 将 HPRC2 与 HPRC1 进行比较，同时与 HGSVC3 以及其他现有的 1000G 短读 callset 进行了对比。
  - 变异调用基准：合并 14 个不同 caller（4 个基于组装，10 个基于 HiFi 读数），保留 ≥2 个 caller 支持的变异作为联合地面真值集。
  - 对比方法：线性参考 vs 泛基因组图（vg-DeepVariant、Sentieon）。
  - eQTL 分析：使用 430 个 1000G 样本，比较 1000G 单独 callset 与合并 HPRC2+1000G callset。

## 4. 资源与算力
- 论文未明确列出 GPU 型号、数量、训练时长等具体算力使用细节。
- 提及计算资源包括：
  - NIH HPC Biowulf 集群。
  - AWS 云计算（免费托管、UCSC 获得 AWS 积分）。
  - DeepPolisher 使用 encoder-only transformer，通常需要 GPU；Sentieon 和 DeepVariant 也依赖 GPU。
  - 整个流程涉及大量比对、组装、抛光、注释和 QC，但未给出具体硬件规格或运行时间。

## 5. 实验数量与充分性
- **主要实验组**：
  - MaxVar 覆盖度曲线（常见变异 AF≥1%、稀有+常见 AF≥0.1%）—— 迭代贪心，分步评估。
  - 组装质量评估：N50、AUN、QV（Illumina k-mer 法）、结构错误检测（HMM-Flagger + NucFlag 联合）、T2T 染色体计数。
  - 变异图对比：GC 增长、位点组成（SV / small variant）、召回率/精确率（分 GIAB 区域，如 easy、tandem repeat、SD 等）。
  - Pantree/GRef 坐标系下的非参考变异计数。
  - 片段重复（SD）验证（短读深度）、转座子插入（MEI）鉴定、VNTR 多样性、着丝粒/端粒分析。
  - 泛转录组：CAT2 与 Ensembl 注释一致性、基因拷贝数变异、参考分化转录本（RDT）、TE 相关转录本。
  - 泛表观组：CpG 增长、甲基化 mQTL、Fiber-seq 染色质可及性分析。
  - 应用：PanGenie 填充 3202 样本、医学相关基因（273 个 + HLA/KIR）、RCCX、D4Z4 阵列分类、eQTL 关联改善。
- **充分性与公平性**：
  - 实验覆盖广泛，但部分分析依赖于特定参数（如 AF≥1% 判断“常见”）。
  - 变异基准使用了严格的合并策略（≥2 caller 支持），减少假阳/假阴。
  - 消融/对比：HPRC1 vs HPRC2、线性参考 vs 泛基因组、不同测序平台（Illumina、Roche SBX-D、Element AVITI、Complete Genomics）。
  - 可能的偏差：所有样本来自 1000G（部分人群代表性有限），All of Us 主要美国人群，未包含大洋洲、中非等。

## 6. 主要结论与发现
- HPRC2 覆盖 All of Us 队列中 **>99% 的常见小变异**，且未来还需约 932 个单倍型才可能达到 99.9%。
- 组装质量显著提升：**错误率减半**（平均 QV 从 52.5 提高到 55），结构不可靠区域从 6.9% 降至 3.1%。约 59% 的染色体被组装为 T2T 重叠群或支架。
- 提供三种互补泛基因组表示和两个新坐标系（Pantree, GRef），发现每个单倍型平均约 **14.3 万“非参考”变异**（2.6% 的变异无法在单一线性参考中表达）。
- 片段重复（SD）总长度达 **382.7 Mb**（占基因组的 12%），其中 63% 由 >90% 的单倍型共享。
- 泛转录组：平均每个单倍型携带 126 个基因拷贝数变异；检测到 68,681 个参考分化转录本（RDT），与 578 个基因相关。
- 泛表观组：新增 1760 万个非参考 CpG（相对 T2T-CHM13 增加 51.9%）；鉴定 80,854 个启动子 mQTL，其中 10.2% 位于复杂结构区域；发现 51,111 个非参考开放染色质峰（FIRE peaks），占一致性峰的 9%。
- 应用表明：泛基因组鉴定的变异可提升 eQTL 发现能力（893 个 eGenes 改善 ≥20% p-value），并帮助医学相关区域的基因型分型（如 RCCX、D4Z4）。

## 7. 优点
- **样本选择有原则**：MaxVar 直接优化变异覆盖，避免依赖种族/民族代理变量。
- **多技术整合**：HiFi + ONT UL + Hi-C/trio 组装，结合 DeepPolisher 抛光，获得高质量。
- **资源全面**：包括组装、比对图、注释、转录本、甲基化、染色质可及性、局部祖先估计，一站式资源。
- **开放性**：公共领域数据，支持 AWS Open Data，附带数据使用最佳实践（ELSI）。
- **新颖坐标系**：Pantree 和 GRef 为非参考变异提供可寻址的标准化表示，兼容现有 VCF 格式。
- **丰富应用示范**：展示了在变异检测、医学区域分析、eQTL 中的增益，结果稳健。

## 8. 不足与局限
- **组装局限性**：
  - 34% 的活性 α-卫星着丝粒阵列仍不完整或含错误。
  - 近端着丝粒短臂仅 6.8% 被连续无误组装。
  - Y 染色体 q 臂重复区域和高相似片段重复仍有残留错误（约 12.5 Mb/单倍型无法验证）。
  - LCLs 端粒长度不代表原初组织，端粒参考有待改进。
- **变异覆盖的不足**：
  - 稀有变异（AF 0.1%~1%）覆盖度仅 83%，需要数千样本才能达到 >99%。
  - 不包括大洋洲、东非、中非等未充分代表的人群；仅基于 1000G 和 All of Us 数据。
- **技术限制**：
  - 短读长结合图变异的离参考变异检测不够完善（仅捕获少数，大部分需长读长）。
  - 部分重复区域（如 rDNA 阵列）仍无法有效组装。
- **偏差风险**：
  - 群体标签（如 1000G 原标签）可能隐含争议，论文虽尝试用 PCLAI 局部祖先代替但仍有风险。
  - eQTL 分析仅使用 LCLs 和单细胞类型；其他组织/细胞类型未涵盖。
- **未来方向**：第三阶段计划扩大新招募样本，改善难以组装的区域，改进对齐方法以覆盖卫星序列，并优化工具集成。

（完）
