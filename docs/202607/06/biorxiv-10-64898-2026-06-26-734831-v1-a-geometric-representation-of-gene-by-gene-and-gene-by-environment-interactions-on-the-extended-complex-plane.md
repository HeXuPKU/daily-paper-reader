---
title: A geometric representation of gene-by-gene and gene-by-environment interactions on the extended complex plane
title_zh: 扩展复平面上基因-基因和基因-环境互作的几何表示
authors: "Karagiannis, J."
date: 2026-07-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.26.734831v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 基因-环境相互作用的几何表示，直接匹配需求10中的基因-环境交互信号
tldr: 现有统计方法能检测基因-基因和基因-环境交互作用，但缺乏统一的数学框架。本研究利用缓冲概念构建测量系统，在扩充复平面（黎曼球面）上通过复数变换表示交互作用，并将交互作用定义为观察值与预期值的偏差。提出公式zobs - zexp量化任何基因-环境交互作用，为组合遗传和环境变化下的表型值确定提供了明确通用的方法。
source: biorxiv
selection_source: fresh_fetch
motivation: 缺乏统一的几何框架描述遗传与环境因素的联合效应，现有统计方法虽可检测交互作用但无法在同一尺度上综合表示。
method: 基于缓冲概念构建测量系统，在扩充复平面（黎曼球面）上通过复数变换计算中性值，将交互作用定义为观察值与预期值的偏差。
result: 提出了公式zobs - zexp，其中zobs和zexp为复数，可量化任何基因-环境交互作用的效应。
conclusion: 该方法参数化定义了表型的“状态空间”，为组合遗传和环境变化的表型值确定提供明确通用方法。
---

## 摘要
基因型与表型变异之间的关系由遗传和环境因素的复杂互作决定。尽管存在能够检测此类互作的统计方法，但缺乏一个公理化的数学框架来无缝描述遗传修饰和环境暴露在共同尺度上的联合效应。在本报告中，利用缓冲概念构建了一个测量系统，使得基因-基因和基因-环境互作能够在扩展复平面（即作为黎曼球面上的投影）上进行几何表示。通过这种方式，任何此类互作或其组合都可以精确定义并量化为通过适用复变换计算出的中性值的偏差。按此概念化后，该框架的参数化定义了给定可测量表型沿实维和虚维的“状态空间”，从而建立了一种明确且广泛适用的方法，用于确定在遗传和/或环境变量组合变化时预期的表型值。值得注意的是，通过应用这些方法，可以使用方程[公式]来量化任何基因-环境互作的效应，其中zobs和zexp是表示用缓冲参数和b表示的给定基因型观察和预期表型的复数。

## Abstract
The relationship between genotypic and phenotypic variation is determined by the complex interaction of genetic and environmental factors. While statistical methods capable of detecting such interactions exist, an axiomatic mathematical framework that seamlessly describes the combined effects of genetic modifications and environmental exposures on a common scale is lacking. In this report, buffering concepts are used to construct a measurement system that enables the geometric representation of both gene-by-gene and gene-by-environment interactions on the extended complex plane (i.e., as projections on the Riemann sphere). In this manner, any such interaction, or combination thereof, can be precisely defined and quantified as the deviation from the neutral value calculated through the applicable complex transformation. When thus conceptualized, the frameworks parameterization defines the "state space" of a given measurable phenotype along both the real and imaginary dimensions, thus establishing an unambiguous and broadly applicable method for determining the phenotypic value expected upon combinatorial changes in genetic and/or environmental variables. Remarkably, by applying these methods, it is possible to quantify the effects of any gene-by-environment interaction using the equation, [Formula], where zobs and zexp are complex numbers representing the observed and expected phenotypes of a given genotype expressed in terms of the buffering parameters,  and b.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：基因-基因（GxG）和基因-环境（GxE）互作的定量描述缺乏统一的数学框架。现有统计方法虽能检测互作，但对“中性表型”的定义存在歧义，且无法在同一尺度上同时处理遗传与环境的组合效应。
- **背景**：传统遗传学中，GxG互作通常基于加性/乘性模型定义偏差，GxE互作则通过反应规范比较统计差异，但两者缺乏公理化数学基础。作者试图利用“缓冲”概念（此前工作）和复变函数理论，构建一个兼容GxG和GxE的几何表示系统。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：将表型值的测量扩展至二维复数空间，利用缓冲参数（ŧ, b）和（T, B）定义表型的“状态空间”，在扩展复平面（黎曼球面）上通过复数变换计算中性预期值，并将互作定义为观察值与预期值的偏差。
- **关键技术细节**：
  - **缓冲参数**：基于sigma函数(σ)、转移函数(τ)、缓冲函数(β)定义。ŧ = τ/σ, b = β/σ, 且 ŧ + b = 1；T = τ/β, B = β/τ, 且 T·B = 1。
  - **环境缩放因子**：a = σ_new(x) / σ_ref(x)，表示环境引起的表型比例变化。
  - **复数表示**：令 z = ŧ + i·b（实部ŧ，虚部b），则参考环境中所有可能表型对应直线 ŧ + b = 1；环境变化后直线变为 ŧa + ba = a。类似地，Z = T + i·B 对应双曲线 T·B = a²。
  - **中性预期**：对于给定基因型在环境a下的预期复数 z_exp = z_MT · a（MT为突变体在参考环境中的复数）。
  - **互作量化**：GxE互作表现为 z_obs 与 z_exp 之间的偏差。文中提出多种度量：线性位移 ℓdisp、角位移 θdisp、三角形面积 A_GxE = Im(z̄_obs · z_exp)/2。该面积公式是核心结果，仅需观察和预期复数即可计算。
  - **扩展**：对于T/B参数体系，互作面积 Λ_GxE = (a²/2)·ln(T_exp / T_obs)。并通过黎曼球面（扩展复平面）的立体投影解决完美转移/完美缓冲时的奇点问题。

### 3. 实验设计

- **数据集/场景**：本文为纯理论数学论文，**未涉及任何具体实验数据集、模拟场景或实证验证**。
- **基准与对比方法**：未对比任何已有方法（如统计回归、反应规范分析等）。仅从数学上推导并展示几何表示的直观性。
- **说明**：作者在Discussion中指出该框架为未来遗传分析提供了工具，但未进行任何实际数据分析或仿真。

### 4. 资源与算力

- **未提及**：文中没有涉及任何计算资源、GPU型号、数量或训练时长。所有推导均为数学解析，未使用机器学习或大规模计算。

### 5. 实验数量与充分性

- **无实验**：本文无任何实验（包括数值仿真、消融研究或案例应用）。因此无法评估实验的充分性与公平性。
- **局限性**：作为理论提案，缺乏对实际数据集或生物实例的验证，其有效性和可操作性尚待后续检验。

### 6. 论文的主要结论与发现

- 通过缓冲参数和复数表示，可以构建一个统一的几何框架，在扩展复平面（黎曼球面）上表示GxG和GxE互作。
- 任何GxE互作均可通过三角形面积公式 A_GxE = Im(z̄_obs · z_exp)/2 量化，该公式仅依赖于观察与预期的复数。
- 环境变化表现为直线的缩放，遗传变化表现为点上移动，而互作则表现为相角偏移。
- 该框架还自然定义了一种新的测量尺度——“关系尺度”（relational scale），它比比率尺度更高阶，能解析相位相等性，并对应SIM(2)群。
- 将GxG视为a=1时的特例，首次实现了GxG与GxE的协谐数学描述。

### 7. 优点

- **数学严密性**：从基本缓冲函数出发，通过公理化推导，给出了互作的明确几何定义。
- **统一性**：首次在同一个复数空间内同时处理遗传变异与环境变化，并能区分“中性”与“互作”。
- **直观性**：通过黎曼球面的立体投影，将奇点（完美转移/缓冲）纳入表示，避免了数学上的不连续。
- **可扩展性**：公式极简（如面积公式），易于推广到多基因、多环境场景。

### 8. 不足与局限

- **缺乏实证验证**：论文未提供任何真实或模拟数据示例，无法证明该框架在现实生物学情境中的有效性、鲁棒性或可操作性。
- **计算复杂性**：对于T/B体系，弧长L_disp需数值积分（非初等函数），可能增加应用难度。
- **假设限制**：框架依赖于“环境独立影响”假设（即环境仅通过缩放因子a作用于所有基因型），与现实可能不符（如环境可能改变缓冲关系本身）。
- **可测量性**：需要精确估计σ、τ、β等函数，在实际实验中可能难以获取，尤其是对于复杂表型。
- **未讨论随机噪声**：没有考虑表型测量误差或生物学随机性对参数估计的影响。

（完）
