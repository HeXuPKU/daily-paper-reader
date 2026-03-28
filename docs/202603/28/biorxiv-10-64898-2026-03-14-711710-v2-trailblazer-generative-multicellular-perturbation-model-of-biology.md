---
title: "TRAILBLAZER: generative multicellular perturbation model of biology"
title_zh: TRAILBLAZER：生成式多细胞生物学扰动模型
authors: "Nener, J., Selvamani, P., Badarinarayan, S. S., Chandramohan, N., Grzybowski, A. T."
date: 2026-03-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.14.711710v2.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 生成式多细胞扰动模型与单细胞基础模型
tldr: 现有的单细胞基础模型往往忽略了多细胞背景，导致在预测系统级干预反应时泛化能力不足。本文提出了 TRAILBLAZER，这是一种生成式多细胞扰动模型，结合了多细胞 Transformer 编码器、超球面潜空间和计数感知解码器。该模型将组织视为协调系统，通过潜空间几何结构实现生物学意义上的向量运算，从而在保持单细胞分辨率的同时，实现了对患者级干预反应的准确零样本预测，为药物发现提供了模拟框架。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-14-711710-v2/fig-001.webp\", \"caption\": \"Fig. 2 | Set transformers as attention-based permutation-invariant encoders for cell sets. a, Induced Set Attention based encoders capture all-to-all cell interactions by leveraging induction point attention, while reducing time complexity from O(n2) to O(nm). b, Equal error rate (lower better) for correct treatment classification based on fixed cell set size (50 cells) for cell sets scRNA-seq inferred by networks trained on groups of 1, 5, 50 and 500 cells, “original” set indicates ground truth cell set. c, Energy distance of genes, mean of 25 cells per cell type, for reconstruction of scRNA-seq of unseen donors (N=3), calculated every 100 steps of the training on sets of 1, 5, 50 and 500 cells, for 90 treatments and 9 donors. In all runs, the network sees exactly 1000 cells in each forward pass, independent of cell set size. Latent shaping was not applied. d, same as c, but the minimal energy distance for each cell set size. e, the network was trained on the task of clustering sets of cells by treatment, trained on sets of 1, 5, 50 and 500 cells, for each run batches have the same amount of states to cluster per forward pass. The cosine similarity was measured for cell samples between treatments (higher better), or f, within treatment (lower better). g, Same as (f) but mean euclidean distance for cell samples between treatments (higher better), or h, within treatment (lower better). All measurements use the PARSE PBMCs dataset.\", \"page\": 6, \"index\": 1, \"width\": 504, \"height\": 627}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-14-711710-v2/fig-002.webp\", \"caption\": \"Fig. 5 | TRAILBLAZER stratifies individual patients' response to α-PD-1 treatment. a, Graphical abstract for virtual patient treatment, scRNA-seq data for an unseen group of patients is passed to the perturbation model to generate counterfactual dataset subsequently passed to multicellular classifier to measure efficacy of the treatment, pertinent to figures (b-e) for virtual treatment of breast cancer patients with anti-PD-1. b, ROC curves for predicting the response of naive breast cancer patients to α-PD-1 treatment. c, We trained a multicellular respondent/non-respondent classifier on a single-cell α-PD-1 dataset, labels reflect eventual clinical response to the anti-PD-1 treatment. For each patient, we predicted response probabilities for samples of 100 cells, repeated sampling 100 times, and showing underlying distribution as a violin plot. d, We have used TRAILBLAZER to apply α-PD-1 treatment in silico and repeated classification as in (c). e, As in (d) but after IL-10 treatment. f, Graphical abstract for virtual drug screening, initial and target multicellular states are used to calculate a phenotype vector compared to mechanism vectors with cosine similarity to rank treatments most likely moving in direction of desired health outcome. g, TRAILBLAZER’s top five zero-shot predictions for treatments augmenting ɑ-PD-1 response, derived from scRNA-seq biopsies of breast cancer patients treated with ɑ-PD-1. Success was assessed by literature review corroborating treatment efficacy. Predictions are shown for unseen patients. h, Same ranking task as in (g), performed with the CELLFLOW neural network on the identical data foundation, harmonized with TRAILBLAZER’s harmonizer module.\", \"page\": 10, \"index\": 2, \"width\": 982, \"height\": 733}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-14-711710-v2/fig-003.webp\", \"caption\": \"Fig. 3 | Application of latent space shaping using biological priors. a, To improve generalizability of TRAILBLAZER, the latent space of the network is shaped using a “Mechanism segmentation network” trained on a hypersphere manifold, and where healthy, unperturbed states are pushed towards the center and sick and perturbed states are put on the surface of the hypersphere. b, UMAP projection of the latent space for PARSE dataset’s 5 random treatments without latent shaping, and c, with latent shaping. d, same as b but view of 5 random donors without latent shaping, and e, with latent shaping. f, Average k-rank of treatment rediscovery for unseen donors based on cosine similarity of latent embeddings (lower better). g, Minimum energy distance for network without and with latent shaping calculated for each gene, averaged across 25 cells per cell type, for reconstruction of scRNA-seq of unseen donors (N=3), trained on sets of 500 cells. All measurements use the PARSE PBMCs scRNA-seq dataset.\", \"page\": 8, \"index\": 3, \"width\": 984, \"height\": 392}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-14-711710-v2/fig-004.webp\", \"caption\": \"Fig. 1 | TRAILBLAZER: Multicellular architecture for foundational models of biology. a, In multicellular organisms, sets of cells are working together to produce phenotypic presentations such as treatment response and disease progression. TRAILBLAZER operates on sets of cells to build uniform and traversable hypersphere latent representation of multicellular disease and treatment processes; it is coupled with multicellular classifiers to help with navigating the phenotypic space. b, Uniform disease-treatment phenotypic perturbation space can be applied to discover treatments by presenting initial and target patient phenotypes, or it can be used to identify patients phenotypes in response to treatments in virtual clinical trials, lastly multicellular architecture offers unbiased view of each cell importance to the process. c, TRAILBLAZER uses Induced Set Attention Blocks (ISAB)25 to efficiently capture relationships of large sets of cells’ biological variables such as scRNA-seq, and utilizes latent shaping with biological priors to improve generalizability by organizing latent space on a plan of hypersphere with healthy states in the center.\", \"page\": 4, \"index\": 4, \"width\": 984, \"height\": 789}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-14-711710-v2/fig-005.webp\", \"caption\": \"Fig. 6 | TRAILBLAZER’s cell attention can be used to aid granular analysis of diseases and treatments. a, The interpretability of the model predictions is afforded by multicellular phenotype classifier, trained to recognize desirable and undesirable cell states (e.g. responsiveness to treatment). It is capable of assessing cells’ state contribution to a disease/phenotype (cell importance), and it measures cells’ similarity to a desired state after treatment (responsiveness). b, The TRAILBLAZER phenotype classifier’s multicellular architecture outperforms the single-cell architectures of state-of-the-art models (Geneformer, scGPT, scVI). Models were trained on multilabel disease classification using patients’ scRNA-seq data, then evaluated on unseen patients. Performance was measured as F1 score of disease classification across training epochs. c, An example of TRAILBLAZER’s inferred importance of each cell type for the naive breast cancer patients, for a patient resistant to anti-PD-1 (left), and responsive (right). d, TRAILBLAZER AI predicted treatments improving anti-PD-1 patient responsiveness clustered by target cell populations. The average treatment responsiveness of each cell type is calculated across all patients (N=9). Treatments are clustered into four groups based on their predicted mechanism of action and are sorted from left to right based on the overall cosine similarity of cell states to positive patient outcomes. e, TRAILBLAZER AI models the contribution of each cell to anti-PD-1 patient responsiveness, an example of anti-PD-1/IL-15 effect on tumor micro-environment. A detailed view with single-cell resolution shows cells present before (1st column, top row) and after treatment (2nd column, top row), the importance of each cell to the state (middle row), and the treatment responsiveness of each cell (bottom row).\", \"page\": 12, \"index\": 5, \"width\": 979, \"height\": 618}]"
motivation: 针对现有单细胞模型忽略多细胞背景且在跨供体或新干预措施下泛化能力差的问题，寻求构建可扩展的系统级预测模型。
method: 提出 TRAILBLAZER 模型，采用多细胞 Transformer 编码器、显式超球面潜空间和计数感知生成解码器来建模组织协调性。
result: 该模型实现了对扰动反应的准确零样本预测，并能以患者分辨率对候选免疫调节剂进行排名，同时支持对未知药物的推断。
conclusion: TRAILBLAZER 为机制感知的多细胞反应模拟建立了实用框架，为开发用于治疗发现的预测性基础模型开辟了道路。
---

## 摘要
单细胞基础模型正通过从数百万个图谱中学习细胞状态的可迁移表示，重塑生物学研究。这些模型支持注释、去噪、跨模态映射，并且越来越多地用于预测对遗传或药物扰动的反应。尽管取得了这些进展，但大多数方法将细胞视为独立的观测值，忽略了主导组织行为的多细胞上下文。在聚合数据集上训练的模型往往难以泛化到新的供体、实验室或干预措施，部分原因是其潜空间缺乏用于组合和外推的结构。因此，强大的重构性能并不能保证对系统级反应的准确预测。本文解决的普遍问题是如何构建一个可扩展的模型，在保持单细胞分辨率并实现超越观测条件的泛化的同时，预测多细胞、患者层面的干预反应。在这里，我们展示了 TRAILBLAZER，这是一个多细胞 Transformer 编码器，耦合了显式塑造的超球面潜空间和计数感知的生成式解码器，能够在患者分辨率下实现对扰动反应的准确零样本预测以及候选免疫调节剂的排序。与之前的单细胞或伪批量（pseudo-bulk）方法相比，TRAILBLAZER 使用潜标记（latent tokens）将组织建模为协调系统，这些标记在总结和重新分配全局上下文的同时，保持了与群体规模近乎线性的扩展性。通过围绕共享的健康参考和校准的机制方向组织潜几何结构，该模型使向量算术具有生物学意义，并支持对外推至未见过的药物。总之，这些结果为多细胞反应的机制感知模拟建立了一个实用的框架，并为用于治疗发现的预测性基础模型指明了道路。

## Abstract
Single-cell foundation models are reshaping biology by learning transferable representations of cellular state from millions of profiles. These models support annotation, denoising, cross-modal mapping and, increasingly, prediction of responses to genetic or pharmacological perturbations. Despite this progress, most approaches treat cells as independent observations and ignore the multicellular context that governs tissue behavior. Models trained on aggregated datasets often fail to generalize to new donors, laboratories or interventions, in part because their latent spaces lack structure for composition and extrapolation. As a result, strong reconstruction performance does not guarantee accurate forecasting of system-level responses.

The general problem addressed here is how to construct a scalable model that predicts multicellular, patient-level responses to interventions while preserving single-cell resolution and enabling generalization beyond observed conditions.

Here we show that TRAILBLAZER, a multicellular transformer encoder coupled to an explicitly shaped hyperspherical latent space and a count-aware generative decoder, enables accurate zero-shot prediction of perturbation responses and ranking of candidate immunomodulators at patient resolution.

In contrast to prior single-cell or pseudo-bulk approaches, TRAILBLAZER models tissues as coordinated systems using latent tokens that summarize and redistribute global context while maintaining near-linear scaling with group size. By organizing latent geometry around shared healthy references and calibrated mechanistic directions, the model renders vector arithmetic biologically meaningful and supports extrapolation to unseen agents. Together, these results establish a practical framework for mechanism-aware simulation of multicellular responses and suggest a path toward predictive foundation models for therapeutic discovery.

---

## 论文详细总结（自动生成）

以下是对论文《TRAILBLAZER: generative multicellular perturbation model of biology》的结构化深度总结：

### 1. 论文的核心问题与整体含义
*   **研究动机**：现有的单细胞基础模型（Foundation Models）大多将细胞视为独立同分布（IID）的观测值，忽略了组织中细胞间的相互作用和多细胞背景（Multicellular Context）。这导致模型在面对新供体、新实验室环境或未见过的干预措施时，泛化能力差，且难以准确预测系统级的生物学反应。
*   **核心问题**：如何构建一个既能保持单细胞分辨率，又能捕捉多细胞协同行为，并具备强大外推（Extrapolation）能力的生成式模型，以预测患者级别的药物干预反应？

### 2. 方法论
TRAILBLAZER 结合了多细胞编码、几何潜空间塑造和生成式解码三大核心技术：
*   **多细胞 Transformer 编码器**：采用**诱导集合注意力块（ISAB）**。通过少量的“诱导标记”（Inducing Tokens）作为中转，实现细胞间的全局信息交换。其计算复杂度从 $O(N^2)$ 降低至近乎线性的 $O(N \cdot M)$（$N$ 为细胞数，$M$ 为标记数），支持处理临床规模的细胞样本。
*   **机制分割网络（Mechanism Segmentation Network）**：在主模型训练前，先训练一个独立的编码器，将不同干预措施映射到超球面上的单位向量，形成一个**冻结的机制库（Mechanism Library）**。
*   **潜空间塑造（Latent Shaping）**：
    *   **几何约束**：将健康/对照状态推向超球面中心，将扰动/疾病状态推向球面。
    *   **向量算术**：通过潜空间向量加减法模拟干预（如：对照组潜变量 + 机制向量 = 扰动组潜变量）。
*   **计数感知解码器**：使用**零膨胀负二项分布（ZINB）**头来重构基因表达计数，并引入 **FiLM（特征线性调制）** 层来处理批次效应和数据集特有的“风格”。

### 3. 实验设计
*   **数据集**：
    *   **PARSE PBMCs**：包含 90 种处理、12 个供体的 1000 万个细胞（子集化为 100 万用于训练）。
    *   **乳腺癌临床数据**：接受 Pembrolizumab（anti-PD-1）治疗的患者单细胞数据。
    *   **CELLxGENE**：用于跨疾病分类的基准测试。
*   **Benchmark 与对比方法**：
    *   **扰动预测对比**：CellFlow、STACK、LPM（大型扰动模型）。
    *   **疾病分类对比**：Geneformer、scGPT、scVI。
*   **实验场景**：零样本（Zero-shot）和少样本（Few-shot）扰动预测、患者疗效分层、虚拟药物筛选（药物联用排名）。

### 4. 资源与算力
*   **算力说明**：论文未明确给出具体的 GPU 型号、数量或总训练时长。
*   **效率提及**：作者强调了模型在“标准 GPU”上即可运行，且展示了推理延迟和显存占用随细胞数量增加呈近线性增长的曲线（Ext. Fig. 2），证明了其在临床应用中的可行性。

### 5. 实验数量与充分性
*   **实验规模**：涵盖了从 PBMC 扰动到真实癌症临床队列的多个维度。
*   **消融实验**：非常充分。作者对比了不同细胞群体大小（1, 5, 50, 500 细胞）对重构精度的影响，验证了“多细胞背景越多，预测越准”的假设。同时对比了有无“潜空间塑造”和“细胞类型平衡采样”的效果。
*   **客观性**：通过固定每批次处理的总细胞数（如 1000 个）来确保对比的公平性，证明性能提升源于多细胞逻辑而非单纯的数据量增加。

### 6. 主要结论与发现
*   **多细胞优势**：增加细胞群体上下文能显著降低重构误差（能量距离），并提高干预措施的识别率。
*   **零样本预测**：TRAILBLAZER 在未见过的干预（如 IL-15）预测任务中，表现显著优于 CellFlow 和 STACK。
*   **临床价值**：模型成功预测了乳腺癌患者对 anti-PD-1 的反应，并准确排出了与 anti-PD-1 具有协同作用的候选药物（如 IL-15, IFN-$\gamma$），这些发现与现有文献高度一致。
*   **可解释性**：通过注意力权重（Cell Importance），模型能识别出哪些细胞群体（如特定的 T 细胞亚群）主导了治疗反应。

### 7. 优点
*   **架构创新**：将集合 Transformer 与超球面几何学习结合，解决了单细胞模型缺乏系统观的问题。
*   **泛化能力**：通过机制向量的线性组合，实现了对未知干预和药物联用的有效外推。
*   **实用性**：计算效率高，能够处理包含成千上万个细胞的真实患者样本。

### 8. 不足与局限
*   **精度权衡**：引入潜空间几何塑造（Shaping）虽然提升了泛化和语义能力，但会导致单细胞层面的重构精度（重构紧密度）略微下降。
*   **线性假设**：模型假设干预效果在潜空间是线性可加的，这可能无法完全捕捉复杂的非线性生物学相互作用（如超加性或拮抗作用）。
*   **数据依赖**：高度依赖上游的数据协调（Harmonization）质量；且目前主要在免疫系统验证，在其他组织（如缺乏细胞间频繁通讯的组织）中的优势尚待证明。
*   **基因限制**：实验中主要使用了高变基因（HVG），可能会丢失一些关键的稀有标记基因信息。

（完）
