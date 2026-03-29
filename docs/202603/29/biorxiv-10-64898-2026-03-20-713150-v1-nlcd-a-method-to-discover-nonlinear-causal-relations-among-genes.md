---
title: "NLCD: A method to discover nonlinear causal relations among genes"
title_zh: NLCD：一种发现基因间非线性因果关系的方法
authors: "Easwar, A., Narayanan, M."
date: 2026-03-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.20.713150v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 孟德尔随机化和基因组学中的非线性因果关系
tldr: 区分相关性与因果关系是生物学研究的挑战，现有基于孟德尔随机化的方法多假设线性关系，限制了复杂基因网络的发现。本文提出NLCD方法，利用非线性回归和条件特征重要性评分扩展了传统的因果推断检验（CIT）。在模拟数据中，NLCD在检测非线性关系方面优于现有工具，并在酵母和人类基因组数据中成功识别出已知的和潜在的因果基因对，为揭示复杂的生物调控机制提供了有力工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-20-713150-v1/fig-001.webp\", \"caption\": \"Fig. 3. Comparison of NLCD with SOTA methods on simulated benchmark datasets. Simulated benchmarks comprising data on independent triplets vs. causal triplets (with linear, sine, or sawtooth causal relationship) were used to determine the classification performance (AUPRC) of different causal discovery methods (see also Fig. S1a for the underlying PR curves). NLCD and CIT were run using 500 permutations (see also Fig. S1b for results using 100 permutations). Sample size of n = 500 is used here.\", \"page\": 10, \"index\": 1, \"width\": 248, \"height\": 645}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-20-713150-v1/fig-002.webp\", \"caption\": \"Fig. 2. NLCD on simulated benchmark datasets. a. Example plots of the simulated A and B genes illustrate different types of gene-gene relationships, linear and nonlinear (sine and sawtooth). Shaded grey marks the overlap region between the two gene expression distributions: (A | L = 0) and (A | L = 1), with endpoints of this overlap region obtained by setting P (L = 0 | A) to 0.2 and to 0.8 and solving for A (see formula derived in Supplementary Section 1.4). b. Performance of NLCD on benchmarks, each comprising data simulated on 100 causal vs. 100 independent triplet models, on a binary (causal vs. independent) classification task is reported as Precision-Recall (PR) curves. Sample size of n = 500 is used here.\", \"page\": 9, \"index\": 2, \"width\": 481, \"height\": 641}]"
motivation: 现有的基因因果关系发现方法大多基于线性假设，难以捕捉生物系统中普遍存在的非线性调控关系。
method: NLCD通过结合非线性回归建模与条件特征重要性评分，扩展了因果推断检验（CIT）的统计框架以处理非线性数据。
result: 模拟实验显示NLCD在非线性关系检测上显著优于CIT、Findr和MRPC，并在真实酵母及人类组织数据中验证了其有效性。
conclusion: NLCD是一种能够有效识别基因间非线性因果关系的稳健方法，有助于在复杂基因组数据中构建更准确的调控网络。
---

## 摘要
区分相关性与因果关系是包括生物学在内的许多科学领域的一项基本挑战，特别是在随机对照试验等干预手段不可行且仅有观测数据的情况下。孟德尔随机化（Mendelian Randomization）框架下基于条件独立性统计检验的方法，可以检测两个均与第三个工具变量相关的观测变量之间的因果关系。然而，这些用于检测性状间因果关系的方法（例如，在同一群体中观察到的与遗传变异相关的两个基因表达或临床性状）通常假设线性关系，从而阻碍了从基因组数据中发现因果基因网络。我们开发了 NLCD，这是一种基于非线性回归建模和条件特征重要性评分的基因组数据非线性因果发现（NonLinear Causal Discovery）方法。NLCD 利用这些技术扩展了现有线性因果发现方法——因果推断检验（Causal Inference Test, CIT）中的统计检验。我们将 NLCD 与当前最先进的方法（CIT、Findr 和 MRPC）进行了基准测试。在模拟数据集上，NLCD 在检测线性关系方面的表现与大多数方法相当（NLCD 的平均 AUPRC（精准率-召回率曲线下面积）= 0.94，CIT = 0.94，Findr = 0.94，MRPC = 0.99），而在检测两个基因之间的非线性（正弦和锯齿型）关系方面优于它们（NLCD 的平均 AUPRC = 0.76，CIT = 0.60，Findr = 0.56，MRPC = 0.73）。当在酵母基因组数据集的非线性子集上进行测试以恢复涉及转录因子的已知因果关系时，NLCD 和 CIT 的表现相当，且略优于 Findr 和 MRPC（NLCD 的平均 AUPRC = 0.82，CIT = 0.81，Findr = 0.71，MRPC = 0.54）。在应用于人类基因组数据集时，NLCD 揭示了肌肉组织中活跃的因果基因对（IRF1 [->] PSME1 和 HLA-C [->] HLA-T），并阐明了在活体人类环境下的组织中发现因果基因网络的机遇与挑战。可用性：实现我们方法的代码可在以下网址获取：https://github.com/BIRDSgroup/NLCD。

## Abstract
Distinguishing correlation from causation is a fundamental challenge in many scientific fields, including biology, especially when interventions like randomized controlled trials are infeasible and only observational data are available. Methods based on statistical tests of conditional independence within the Mendelian Randomization framework can detect causality between two observed variables that are each associated with a third instrumental variable. However, these methods for detecting causal relationships between traits (e.g., two gene expression or clinical traits associated with a genetic variant, all observed in the same population) often assume a linear relationship, thereby hindering the discovery of causal gene networks from genomics data.We have developed NLCD, a method for NonLinear Causal Discovery from genomics data based on nonlinear regression modeling and conditional feature importance scoring. NLCD uses these techniques to extend the statistical tests in an existing linear causal discovery method called the Causal Inference Test (CIT). We benchmarked NLCD against current state-of-the-art methods: CIT, Findr, and MRPC. On simulated datasets, NLCD performs comparably to most methods in detecting linear relations (Average AUPRC (Area Under the Precision-Recall Curve) of NLCD=0.94, CIT=0.94, Findr=0.94, and MRPC=0.99), and outperforms them in detecting nonlinear (sine and sawtooth type) relations between two genes (Average AUPRC of NLCD=0.76, CIT=0.60, Findr=0.56, and MRPC=0.73). When tested on a nonlinear subset of a yeast genomic dataset to recover known causal relations involving transcription factors, NLCD and CIT performed comparable to each other and slightly better than Findr and MRPC (Average AUPRC of NLCD=0.82, CIT=0.81, Findr=0.71, and MRPC=0.54). On application to a human genomic dataset, NLCD revealed active causal gene pairs (IRF1 [-&gt;] PSME1 and HLA-C [-&gt;] HLA-T) in the muscle tissue, and clarified the promises and challenges in discovering causal gene networks in tissues under in vivo human settings.

AvailabilityThe code implementing our method is available at: https://github.com/BIRDSgroup/NLCD.

---

## 论文详细总结（自动生成）

以下是对论文《NLCD: A method to discover nonlinear causal relations among genes》的结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何在仅有观测数据的情况下，准确区分基因之间的相关性与因果关系，特别是当这种关系是非线性时。
*   **研究背景**：
    *   在生物学中，区分“致病基因”与“受疾病影响的基因”对药物研发至关重要。
    *   **孟德尔随机化（MR）**利用遗传变异（SNP）作为工具变量来推断因果，但现有的主流方法（如 CIT, Findr, MRPC）大多假设基因间是**线性关系**。
    *   然而，生物系统中存在大量非线性调控（如昼夜节律基因、反馈抑制等），线性假设会导致因果发现的效能下降或产生误报。

### 2. 方法论：核心思想与关键技术
NLCD（NonLinear Causal Discovery）通过扩展传统的因果推断检验（CIT）框架，引入了非线性建模能力。
*   **核心思想**：针对一个三元组 $(L, A, B)$——其中 $L$ 是遗传变异，$A$ 和 $B$ 是基因表达性状，通过四个统计检验来验证是否存在 $L \to A \to B$ 的因果链。
*   **关键技术细节**：
    1.  **非线性回归（NLR）建模**：弃用线性回归，改用核脊回归（KRR）、支持向量回归（SVR）或人工神经网络（ANN）来捕捉 $A$ 与 $B$ 之间的复杂函数关系。
    2.  **条件特征重要性（CFI）评分**：这是 NLCD 的核心创新。用于执行“条件独立性检验”（即在已知 $A$ 的情况下，$L$ 是否与 $B$ 独立）。CFI 通过衡量在非线性模型中移除或改变 $L$ 对预测 $B$ 的影响程度来打分。
    3.  **四个统计检验**：
        *   Test 1: $L$ 与 $B$ 是否相关。
        *   Test 2: 在给定 $B$ 的情况下，$L$ 是否与 $A$ 相关。
        *   Test 3: 在 $L$ 的不同分层下，$A$ 与 $B$ 是否持续相关。
        *   Test 4: **关键检验**，验证 $L \perp B | A$（即 $A$ 是否完全解释了 $L$ 对 $B$ 的影响）。
    4.  **置换检验（Permutation Test）**：通过多次随机打乱数据生成经验 p 值，最终取四个检验中最大的 p 值作为因果显著性的度量。

### 3. 实验设计
*   **数据集与场景**：
    *   **模拟数据集**：构建了线性、正弦（Sine）、锯齿（Sawtooth）和抛物线（Parabola）四种关系模型，涵盖等方差和不等方差场景。
    *   **酵母基因组数据**：包含 1012 个酵母分离株的基因型和表达谱。
    *   **人类 GTEx (v8) 数据**：分析了 10 个样本量最大的组织（如骨骼肌、全血等）。
*   **Benchmark 与对比方法**：
    *   对比了三种最先进（SOTA）的方法：**CIT**（线性基准）、**Findr**（基于贝叶斯框架）和 **MRPC**（基于 PC 算法的 MR 扩展）。
    *   评估指标：精准率-召回率曲线下面积（AUPRC）。

### 4. 资源与算力
*   **算力说明**：文中未明确提及具体的 GPU 型号或训练时长。
*   **计算复杂度分析**：作者指出 NLCD (KRR 版本) 的运行时间随样本量 $n$ 呈**立方增长** ($O(n^3)$)，并随置换次数线性增长。对于人类 GTEx 数据，使用了 1000 次置换并结合了 EPEPT 算法来加速小 p 值的估计。

### 5. 实验数量与充分性
*   **实验规模**：
    *   模拟实验涵盖了多种样本量（300, 500, 1000）和多种非线性函数。
    *   酵母实验使用了 1752 对已知的转录因子-靶基因（TF-TG）作为正样本，并构建了平衡的负样本集。
    *   人类数据分析了 10 个组织，并应用了严格的映射（Mappability）过滤。
*   **充分性评价**：实验设计较为全面，不仅验证了非线性场景下的优越性，还证明了在线性场景下 NLCD 依然稳健（不输于线性方法）。通过 10 次不同随机种子的重复实验，保证了结果的客观性。

### 6. 主要结论与发现
1.  **非线性优势**：在正弦和锯齿型模拟数据中，NLCD 的 AUPRC（0.76）显著高于 CIT（0.60）和 Findr（0.56）。
2.  **线性稳健性**：在线性模拟中，NLCD 与 SOTA 方法表现持平（AUPRC ~0.94）。
3.  **真实数据验证**：在酵母数据中，NLCD 成功识别出具有非线性特征的调控对；在人类肌肉组织中，识别出 $IRF1 \to PSME1$ 等已知因果关系。
4.  **方向性识别**：NLCD 能够有效区分因果方向（$A \to B$ vs $B \to A$）。

### 7. 优点
*   **灵活性**：模型无关（Model-agnostic），可以灵活嵌入各种非线性回归算法。
*   **突破限制**：解决了传统 MR 方法在处理非线性生物信号时的“盲区”问题。
*   **处理异质性**：相比 CIT，NLCD 在处理不同基因型下性状方差不等（Unequal Variance）的情况时表现更佳。

### 8. 不足与局限
*   **计算开销**：由于涉及非线性模型训练和大量置换检验，在大规模样本或全基因组关联研究（GWAS）级别的数据上计算成本较高。
*   **样本量依赖**：在人类数据应用中，发现 NLCD 需要较大的样本量（接近 1000）才能克服弱工具变量和多重假设检验校正的影响。
*   **数据质量敏感**：人类组织中的因果发现极易受到基因序列映射错误（Cross-mappability）的影响，产生假阳性，需要严格的后期过滤。

（完）
