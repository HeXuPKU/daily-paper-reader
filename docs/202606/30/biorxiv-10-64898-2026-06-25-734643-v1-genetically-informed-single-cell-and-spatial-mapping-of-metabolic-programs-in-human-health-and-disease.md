---
title: Genetically informed single-cell and spatial mapping of metabolic programs in human health and disease
title_zh: 遗传信息驱动的单细胞与空间代谢图谱在人类健康与疾病中的应用
authors: "Xu, H., Huang, G., Zhang, L., Liu, W., Wu, Q., Chen, M., Zhao, D., Zhang, Y., Xu, A."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.25.734643v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 整合代谢物GWAS汇总统计与单细胞和空间转录组，绘制代谢程序图
tldr: 现有代谢模型难以直接评估个体代谢物与细胞状态的关联，尤其是外源性信号代谢物。本研究提出gmMAP框架，整合代谢物GWAS与单细胞/空间转录组，并引入约束基代谢通量模型，实现细胞和空间分辨率的代谢程序映射。该框架在肾脏发育中通过多组学数据验证，成功重建17个小鼠器官和24个人体组织的空间代谢图谱，揭示29种癌和溃疡性结肠炎的代谢重编程。gmMAP提供了一个通用工具，将遗传代谢特征与细胞状态、组织空间及疾病病理联系起来。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有转录组代谢模型无法直接评估个体代谢物（尤其外源信号代谢物）与细胞状态的关联，限制了疾病机制研究。
method: 整合代谢物GWAS汇总统计与单细胞和空间转录组，结合约束基代谢通量模型，构建gmMAP框架。
result: 在肾脏发育验证后，重建17个小鼠器官和24个人体组织的空间代谢图谱，并揭示29种泛癌和溃疡性结肠炎的代谢重编程。
conclusion: gmMAP可靠地连接遗传代谢特征与细胞状态、空间组织及疾病病理，为代谢机制研究提供通用方案。
---

## 摘要
定义细胞类型特异的内源性代谢特征、细胞水平代谢状态的空间分布以及细胞对外源代谢物的反应，对于理解疾病机制至关重要。现有基于转录组的代谢模型主要推断细胞内反应或通路水平活性，因此无法直接评估单个代谢物水平与细胞状态之间的关联，尤其是对于作为信号分子在细胞外作用而非作为代谢底物进入细胞的代谢物。本文介绍gmMAP，一个整合代谢物全基因组关联分析汇总统计与单细胞和空间转录组数据的框架，以细胞和空间分辨率绘制代谢程序。值得注意的是，gmMAP能够预测内源性代谢过程的激活，同时揭示外源代谢物与多种细胞功能状态之间的内在关联。为进一步捕获细胞代谢网络的连通性，我们纳入基于约束的代谢通量模型以评估全局代谢活性。为评估gmMAP的准确性和稳健性，我们将该框架应用于涵盖人类发育、生理稳态、炎症和癌症的代表性生物学背景。在人类肾脏发育中，gmMAP捕获了动态代谢程序，并通过配对转录组和代谢组参考数据集验证，支持其在代谢物识别和代谢流推断中的可靠性。在器官水平上，gmMAP重建了稳态和自身免疫炎症条件下17个小鼠器官的空间代谢物分布模式，并进一步扩展到24种正常人体组织，生成器官和细胞分辨率的多尺度代谢图谱。在疾病背景下，gmMAP揭示了29种泛癌细胞群的代谢重编程，并识别了溃疡性结肠炎中外源代谢物与炎症相关基质代谢重塑之间的潜在联系。总之，gmMAP能够一致地将遗传信息驱动的代谢物特征与细胞状态、空间组织结构和疾病病理联系起来。

## Abstract
Defining cell-type-specific endogenous metabolic features, the spatial distribution of cell-level metabolic states and cellular responses to exogenous metabolites is essential for understanding disease mechanisms. Existing transcriptome-based metabolic models primarily infer intracellular reaction or pathway-level activities, and therefore cannot directly assess associations between individual metabolite levels and cellular states, particularly for metabolites that act extracellularly as signalling molecules rather than entering cells as metabolic substrates. Here we introduce gmMAP, a framework that integrates metabolite GWAS summary statistics with single-cell and spatial transcriptomes to map metabolic programmes at cellular and spatial resolution. Notably, gmMAP enables the prediction of endogenous metabolic process activation while also revealing intrinsic associations between exogenous metabolites and diverse cellular functional states. To further capture the connectivity of cellular metabolic networks, we incorporated a constraint-based metabolic flux model to evaluate global metabolic activity. To evaluate the accuracy and robustness of gmMAP, we applied the framework across representative biological contexts spanning human development, physiological homeostasis, inflammation and cancer. In human kidney development, gmMAP captured dynamic metabolic programmes and was validated using paired transcriptomic and metabolomic reference datasets, supporting its reliability in metabolite identification and metabolic-flow inference. At the organ level, gmMAP reconstructed spatial metabolite distribution patterns across 17 mouse organs under homeostatic and autoimmune inflammatory conditions, and further extension to 24 normal human tissues generated a multi-scale metabolic atlas at both organ and cellular resolutions. In disease settings, gmMAP revealed metabolic reprogramming across 29 pan-cancer cell populations and identified potential links between exogenous metabolites and inflammation-associated stromal metabolic remodelling in ulcerative colitis. Together, gmMAP can consistently connect genetically informed metabolite traits with cell states, spatial tissue organization and disease pathology.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

现有转录组代谢推断方法（如Compass、scFEA）主要基于酶表达和反应网络，**无法直接评估单个代谢物水平与细胞状态的关联**，特别是对于**外源性信号代谢物**（如微生物衍生代谢物、激素、药物等），它们可能不进入细胞作为底物，而是通过受体等机制发挥功能。此外，这些方法受单细胞数据稀疏性、技术噪声、mRNA-蛋白不一致性等限制。因此，亟需一种能够结合群体遗传学、单细胞和空间转录组，实现**细胞级和空间级代谢物性状映射**的通用框架。

## 2. 方法论：核心思想、关键技术细节

**核心思想**：整合代谢物GWAS汇总统计（来自Chen et al. 2023，1091个代谢物水平和309个代谢物比率）与单细胞/空间转录组数据，利用MAGMA将GWAS信号转换为基因水平关联Z分数，构建**基因程序**（up/down signatures），结合基因表达噪声加权，通过**加权AUCell样富集策略（sc-wAUCell）** 计算每个细胞/空间点的代谢物关联分数。再通过**一对比其余AUROC框架**识别细胞类型特异性代谢物关联。同时，引入**酶约束、比率整合的代谢流势能模型（gmMAP-flux）**，利用代谢物分数、酶表达、亚细胞区室、辅因子等先验知识推断**通路级代谢流方向和可行性**。此外，开发了**gmMAP-spatial、gmMAP-pseudotime、gmMAP-perturb、gmMAP-drug**等下游模块，分别用于空间映射、伪时间动态、扰动预测和药物匹配。

## 3. 实验设计：数据集、场景与基准

- **验证数据集**：人类肾脏发育单细胞RNA-seq（Hochane et al.）与匹配的空间代谢组（Wang et al.），包含22种细胞类型，作为正交基准评估gmMAP代谢物预测准确性。
- **器官水平**：小鼠全身体空间转录组（稳态和LPS炎症，17个器官），以及24种正常人体组织（Tabula Sapiens，483,152细胞）。
- **疾病场景**：29种癌症类型的泛癌单细胞图谱（4,146,975细胞），溃疡性结肠炎结肠单细胞数据（366,650细胞），以及DSS结肠炎小鼠空间转录组。
- **基准/对比方法**：与Compass、scFEA、scMetabolism等现有单细胞代谢分析方法比较（主要在引言和讨论中提及，未在正文中展示定量对比）。
- **药物匹配**：收集12种代谢调节药物（如二甲双胍、辛伐他汀、GLP-1激动剂等）的转录组扰动数据用于gmMAP-drug。

**实验充分性**：覆盖发育、稳态、炎症、癌症多个场景，使用了多种独立验证（空间代谢组、体外实验、动物模型、ATAC-seq），实验设计较全面客观。

## 4. 资源与算力

文中**未明确说明**使用的GPU型号、数量和训练时长。仅提及代码在GitHub上开源（https://github.com/Xulab-collab/gmMAP）。推测MAGMA、单细胞分析、scTour、U Cell等为轻量级计算，但大规模泛癌和空间转录组分析可能需要一定计算资源。此外，Metabolism-AI使用了LLM（DeepSeek），但未提算力。

## 5. 实验数量与充分性

- **肾脏开发验证**：空间代谢组vs gmMAP预测，显示高度一致性（图2a-f）；单细胞与空间代谢组聚类对比，以及podocyte特异性代谢程序验证（图2g-m）。
- **近端肾小管分化**：gmMAP-pseudotime和gmMAP-flux揭示了代谢转型（图3），并与已知文献一致。
- **小鼠全身空间映射**：在LPS炎症下验证了肝脏磷脂重塑、脑区神经递质代谢物等（图4）。
- **人类多组织代谢图谱**：对24个组织、8个细胞模块进行了聚类和关联分析（图5）。
- **泛癌**：识别了29种癌症的代谢模块和微生物-胆汁酸轴（图6），并通过gmMAP-drug预测了各癌症的逆转药物。
- **溃疡性结肠炎**：发现DCA通过TGR5受体激活CXCL1⁺成纤维细胞，并通过体外实验（qPCR）、体内DSS模型、ATAC-seq、免疫荧光等进行了多层面验证（图7-8）。
- **消融实验**：对基因签名大小（1000基因）进行了基准测试（补充图S2）。
总体实验丰富、相互验证充分，结论可靠。

## 6. 主要结论与发现

1. gmMAP能够可靠地从单细胞转录组推断代谢物相关的细胞程序，空间代谢组数据验证了其准确性。
2. 肾脏发育中，gmMAP捕获了细胞类型特异的代谢程序（如podocyte的氨基酸/脂质/类固醇代谢），并揭示了近端肾小管分化中的代谢转换（糖酵解→脂肪酸氧化）。
3. 在小鼠全身空间转录组中，gmMAP成功定位了组织特异性代谢物（如肝脏脂质区带，脑区谷氨酸、胱硫醚等），并检测到炎症诱导的肝脏磷脂重塑。
4. 人类多组织图谱显示免疫细胞具有保守的跨组织代谢特征，而基质细胞代谢更具组织特异性。
5. 泛癌分析揭示了共享的癌症代谢模块（如微生物-胆汁酸-基质轴），并与代谢调节药物建立了可逆性连接。
6. 在溃疡性结肠炎中，gmMAP发现DCA（微生物衍生代谢物）通过TGR5受体激活CXCL1⁺炎性成纤维细胞，而乳酸作为代谢放大器增强TNF-α诱导的CXCL1表达，涉及HIF1A和表观遗传重塑。
7. gmMAP-drug可优先筛选可能逆转肿瘤代谢状态的药物（如二甲双胍、辛伐他汀等）。

## 7. 优点

- **创新性整合**：首次将代谢物GWAS遗传信息与单细胞/空间转录组结合，突破了仅依赖酶表达的传统代谢推断局限。
- **覆盖广泛**：可处理内源、外源、微生物、激素等多种代谢物类型，同时支持代谢物比率分析。
- **多模块集成**：提供从细胞/空间映射、伪时间动态、扰动预测到药物匹配的完整分析流程。
- **多尺度验证**：通过空间代谢组、体外实验、动物模型、ATAC-seq等手段进行严格验证，增强可信度。
- **开源可复现**：代码和部分数据公开，便于社区使用。

## 8. 不足与局限

- **依赖GWAS质量**：代谢物遗传信号弱或采样不足时，基因程序可靠性下降。
- **推断而非测量**：gmMAP预测的是代谢物关联的转录程序，并非直接代谢物浓度或通量，需要实验验证。
- **循环代谢物偏差**：血浆代谢物GWAS可能不完全反映组织局部浓度。
- **仍受转录组噪声影响**：尽管降低了对单个酶的依赖，但基因检测深度、批次效应等仍会影响结果。
- **未详细对比其他方法**：仅在讨论中定性比较，缺乏定量基准（如与Compass、scFEA在同一数据集上的AUROC/相关性对比）。
- **算力未披露**：缺乏大规模分析的计算资源透明性。
- **部分结论临床转化有限**：如GLP-1相关药物预测需谨慎解读，缺乏直接肿瘤干预证据。

（完）
