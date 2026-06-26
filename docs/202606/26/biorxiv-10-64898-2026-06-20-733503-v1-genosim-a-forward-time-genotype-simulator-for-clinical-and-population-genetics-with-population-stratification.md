---
title: "GenoSim: A Forward-Time Genotype Simulator for Clinical and Population Genetics with Population Stratification"
title_zh: GenoSim：面向临床和群体遗传学且具有群体分层的向前时间基因型模拟器
authors: "Bakar, A., Gul, R., Haq, W. u., Afghani, T."
date: 2026-06-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.20.733503v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 用于GWAS基准测试的基因型模拟器
tldr: 临床遗传学研究中真实基因型数据获取困难，尤其近亲群体缺乏大规模测序数据。GenoSim通过正向时间模拟填补这一空白，支持群体和系谱约束两种模式，1.1.1版引入基于gnomAD F_ST的Balding-Nichols群体分层，覆盖八个祖先群体。该R包提供HWE、LD、ROH、PCA等分析功能，以开源MIT许可发布，仅依赖基础R包，为临床和群体遗传学提供灵活高效的模拟工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 真实基因型数据受伦理、法规和经济限制匮乏，现有模拟器无法同时处理系谱传播、群体分层和临床导出格式。
method: 开发正向时间二倍体SNP模拟器GenoSim，包含群体模式和系谱约束模式，新增Balding-Nichols模型实现八个人群分层。
result: GenoSim 1.1.1支持基于gnomAD F_ST的群体分层、外部参考面板等位基因频率加载，以及HWE、LD、ROH、PCA等分析。
conclusion: GenoSim作为MIT许可的开源R包，整合了系谱感知、群体分层和临床兼容性，为遗传学模拟提供全面方案。
---

## 摘要
动机：临床遗传学中的下一代测序研究常常受限于人类基因型数据的稀缺，这源于伦理、监管和经济障碍。在近亲通婚群体中，这一短缺最为严重，这些群体在南亚和中东地区很常见，其中基于家系的设计需要大型谱系，而这些谱系很少被完整测序。现有的模拟器无法将谱系感知传播、现实群体分层和临床导出格式整合到一个工具中。结果：我们提出了GenoSim，一个用于二倍体SNP基因型向前时间模拟的R包。它有两种运行模式：群体模式，实现近交调整的哈迪-温伯格采样、怀特-费希尔漂变、定向选择、反复突变和跨多代的霍尔丹重组；以及谱系约束模式，该模式摄入真实的家系VCF和谱系，重建谱系中可识别的阶段，通过观察到的家系结构传播基因型，并附加合成世代。1.1.1版本通过Balding-Nichols模型增加了群体分层，该模型由gnomAD v3.1对八个祖先群体（AFR、AMR、EAS、EUR、FIN、MID、SAS、ASJ）的固定指数（F_ST）参数化、来自外部参考面板的经验等位基因频率加载以及混合队列模拟。分析功能涵盖哈迪-温伯格检验、连锁不平衡、纯合子运行、主成分分析、创始人参考和世代间F统计量以及Nei基因多样性。可用性和实现：GenoSim作为R包在https://github.com/malikbak/GenoSim上以MIT许可证提供。它需要R ≥ 4.0.0，且仅依赖基础R包（stats、utils、graphics、grDevices、tools）。

## Abstract
Motivation: Next-generation sequencing studies in clinical genetics are often limited by the scarcity of human genotype data, which stems from ethical, regulatory, and economic barriers. The shortfall is sharpest in consanguineous populations, which are common in South Asia and the Middle East, where family-based designs need large pedigrees that are rarely sequenced in full. Existing simulators do not combine pedigree-aware propagation, realistic population stratification, and clinical export formats in one tool. Results: We present GenoSim, an R package for forward-time simulation of diploid SNP genotypes. It runs in two modes: a population mode implementing inbreeding-adjusted Hardy-Weinberg sampling, Wright-Fisher drift, directional selection, recurrent mutation, and Haldane recombination across multiple generations; and a pedigree-constrained mode that ingests real family VCFs and a pedigree, reconstructs phase where the pedigree makes it identifiable, propagates genotypes through the observed family structure, and appends synthetic generations. Version 1.1.1 adds population stratification through the Balding-Nichols model parameterised by gnomAD v3.1 fixation indices (F_ST) for eight ancestry groups (AFR, AMR, EAS, EUR, FIN, MID, SAS, ASJ), empirical allele-frequency loading from external reference panels, and admixed-cohort simulation. Analysis functions cover Hardy-Weinberg testing, linkage disequilibrium, runs of homozygosity, principal component analysis, founder-referenced and between-generation F-statistics, and Nei gene diversity. Availability and implementation: GenoSim is available as an R package at https://github.com/malikbak/GenoSim under the MIT licence. It requires R [&ge;] 4.0.0 and depends only on base R packages (stats, utils, graphics, grDevices, tools).

---

## 论文详细总结（自动生成）

# GenoSim：面向临床和群体遗传学且具有群体分层的向前时间基因型模拟器

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：临床遗传学研究中真实基因型数据获取困难，源于伦理、法规和经济障碍。近亲通婚群体（如南亚、中东）尤其缺乏大规模测序数据，基于家系的设计需要大型谱系，但这些谱系很少被完整测序。
- **现有不足**：现有的模拟器无法将谱系感知传播、现实群体分层和临床导出格式整合到一个工具中。
- **整体含义**：开发一个开源R包GenoSim，通过向前时间模拟填补人工基因型数据的空白，支持群体模式和谱系约束模式，并新增基于gnomAD F_ST的Balding-Nichols群体分层，覆盖多个祖先群体，为临床和群体遗传学提供灵活高效的模拟工具。

## 2. 方法论

### 核心思想
- 基于向前时间模拟二倍体SNP基因型，分为两种运行模式：群体模式和谱系约束模式。
- 新增群体分层机制：通过Balding-Nichols模型，利用gnomAD v3.1的固定指数（F_ST）参数化，支持八个祖先群体，并可加载外部参考面板的等位基因频率及混合队列模拟。

### 关键技术细节
- **群体模式**：实现近交调整的哈迪-温伯格采样、Wright-Fisher漂变、定向选择、反复突变和跨多代的Haldane重组。
- **谱系约束模式**：摄入真实家系VCF和谱系，重建可识别的阶段，通过观察到的家系结构传播基因型，并附加合成世代。
- **群体分层**：Balding-Nichols模型由gnomAD v3.1的F_ST值参数化，涉及群体：AFR（非洲）、AMR（美洲混血）、EAS（东亚）、EUR（欧洲）、FIN（芬兰）、MID（中东）、SAS（南亚）、ASJ（阿什肯纳兹犹太人）。
- **分析功能**：包括哈迪-温伯格检验、连锁不平衡（LD）、纯合子运行（ROH）、主成分分析（PCA）、创始人参考和世代间F统计量、Nei基因多样性。

### 算法流程（文字说明）
1. 用户指定运行模式（群体或谱系约束）。
2. 若为群体模式，按HWE采样初始等位基因频率，施加漂变、选择、突变和重组，跨越指定世代。
3. 若为谱系约束模式，加载真实VCF和谱系，重建基因型阶段，按孟德尔规则传播，并可添加合成世代。
4. 可选群体分层：加载gnomAD F_ST参数和/或外部等位基因频率参考面板，生成多个亚群及混合队列。
5. 输出基因型数据（可导出为VCF等临床格式），并提供后续分析功能。

## 3. 实验设计

- **使用的数据集/场景**：未明确描述具体的实验数据集或验证场景。文中仅提及功能实现，未提供基准测试或仿真对比。
- **Benchmark**：未提及与同类工具（如SLiM、pedigreeSim、HAPGEN2等）的对比实验。
- **对比方法**：无对比信息。论文属于方法介绍性文章，侧重于工具功能描述和可用性。

## 4. 资源与算力

- **文中未明确说明**使用的GPU型号、数量、训练时长等计算机资源。该工具为R包，运行在CPU上，依赖基础R包，算力需求较低，但作者未报告运行时测试的具体硬件或时间。

## 5. 实验数量与充分性

- **实验数量**：无独立实验组。论文没有提供模拟准确性、效率或与真实数据一致性的定量评估。
- **充分性**：不充分。缺少与现有模拟器的比较实验，也没有使用真实或模拟数据集验证其生物学的合理性（如分层模拟的F_ST与目标值的一致性、系谱传播的正确性等）。作为纯粹的方法介绍，实验部分欠缺，缺少客观性评估。

## 6. 主要结论与发现

- 成功开发了GenoSim 1.1.1版本，支持基于gnomAD F_ST的群体分层、外部参考面板等位基因频率加载、混合队列模拟。
- 为临床遗传学模拟提供统一框架，整合系谱感知、群体分层和临床兼容格式。
- 以MIT许可开源发布，依赖基础R包，便于广泛使用。

## 7. 优点

- **功能整合**：唯一同时支持谱系感知传播、现实群体分层和临床导出格式的模拟器，填补现有工具空白。
- **开源易用**：基于R语言，仅依赖基础R包，安装门槛低，MIT许可有利于社区贡献。
- **群体分层现实性**：使用gnomAD v3.1的F_ST参数，基于真实人群数据，使模拟更接近真实遗传结构。
- **两种模式灵活**：群体模式适合大规模随机模拟，谱系约束模式适合基于真实家系的研究。
- **内置分析功能**：提供HWE检验、LD、ROH、PCA等常用分析，减少后处理需求。

## 8. 不足与局限

- **缺乏实验验证**：未提供任何模拟与真实数据的比较，也未与现有主流模拟器（如SLiM、msprime、pedigreeSim等）进行性能或准确性对比，不足以让读者评估其可靠性。
- **实验覆盖不足**：没有展示不同参数设置下的结果，没有消融实验验证各模块的贡献，也没有测试大规模模拟的扩展性。
- **应用限制**：当前仅支持SNP，不支持INDEL或CNV；群体模式基于Wright-Fisher模型，对于复杂的人口学历史（如瓶颈、扩张、迁徙）可能模拟能力有限；谱系约束模式依赖真实VCF的相位重建，低测序深度数据可能影响重建质量。
- **文档与测试**：论文仅描述功能，未提供示例运行结果或性能基准，用户需自行探索。
- **偏差风险**：群体分层仅基于gnomAD的八个群体，未覆盖更多精细亚群或混合群体动态参数；F_ST固定值可能无法反映实时漂变。

（完）
