---
title: Evaluating the cross-species transferability and scaling of sequence-to-function predictions in AlphaGenome
title_zh: 评估AlphaGenome中跨物种序列-功能预测的可转移性与缩放性
authors: "Ramarao-Milne, P., Ma, S., Sng, L., MacPhilamy, C., Yeap, H. L., Oh, K. P., Kuiper, M., Lu, Q., Speight, R., Bauer, D. C."
date: 2026-07-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.10.737654v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 评估深度序列到功能模型，与GWAS变异效应预测相关
tldr: "AlphaGenome在人类数据上表现良好，但在小鼠数据上预测能力因任务而异：定量表达效应预测方向正确但强度压缩约100倍，而剪接位点破坏预测跨物种准确（AUC >0.96）。为此开发了AI代理评分方法，自动评估预测置信度，区分稳健的序列识别与未精细定位的调控变异。该方法通过负责任AI层包裹，确保未成熟创新安全使用，符合国际标准。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737654-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1812, \"height\": 1004, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737654-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1774, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737654-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1749, \"height\": 1467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737654-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 804, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737654-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1408, \"height\": 847, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-10-737654-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1739, \"height\": 862, \"label\": \"Figure\"}]"
motivation: 评估AlphaGenome跨物种预测的可迁移性及缩放差异，验证其在不同任务和物种间的泛化能力。
method: 在小鼠数据上测试AlphaGenome的序列到功能预测，并开发AI代理置信度评分以自动识别不可靠结果。
result: 定量表达效应预测弱且压缩100倍，剪接位点识别跨物种一致（AUC 0.96 vs 0.98），表明任务依赖性。
conclusion: 需区分预测任务类型，利用负责任AI层包裹未成熟模型，确保安全使用并符合伦理标准。
---

## 摘要
直接从DNA序列预测分子表型的深度学习模型为解读基因组变异提供了强大框架。最近，AlphaGenome作为一种深度序列-功能架构被提出，能够预测历史上需要实验才能获得的观测结果。尽管该模型表现出高准确性，但主要基于针对参考基因组的人类变异进行评估。在此，我们测试了其在小鼠数据上的性能——这是AlphaGenome训练的另一个物种，尽管其特征数比人类少五倍（1128对5930）。我们证明AlphaGenome的预测性能因功能任务不同而有显著差异。具体而言，在重建单倍型和单变异两种模式下，预测的定量表达效应方向性较弱，且相对于经验基准压缩了约100倍。相比之下，典型剪接位点破坏的识别在小鼠和人类中具有几乎相同的准确性（AUC 0.96对0.98），预测效应大小无跨物种差异。我们为AI智能体开发了一种评分方法，以自主评估AlphaGenome预测置信度，并准确区分AlphaGenome稳健的跨物种序列级识别能力与其在解读未精细定位调控变异时的当前局限性。这展示了如何通过围绕调用包裹一层负责任AI层来拦截有缺陷的结果，从而安全地利用仍在开发中的GenAI创新，同时遵守国际标准，如澳大利亚自愿性AI安全标准（VAISS）。

## Abstract
Deep learning models that predict molecular phenotypes directly from DNA sequence offer a powerful framework for interpreting genomic variation. Recently, AlphaGenome was introduced as a deep sequence-to-function architecture capable of predicting observations that historically required experiments. While the model has shown high accuracy, it was primarily evaluated on human variants scored against a reference genome. Here, we test performance on mouse data, the other species AlphaGenome was trained on although with fivefold fewer features than human (1,128 versus 5,930). We demonstrate that AlphaGenome's predictive performance varies considerably depending on the functional task. Specifically, predicted quantitative expression effects are directionally weak and compressed roughly 100-fold relative to empirical benchmarks across both reconstructed-haplotype and single-variant regimes. In contrast, canonical splice-site disruptions are recognized with near-identical accuracy in mouse and human (AUC 0.96 versus 0.98), displaying no cross-species divergence in predicted effect magnitude. We developed a scoring-approach for AI-agents to autonomously assess AlphaGenome prediction confidence and accurately differentiate between AlphaGenome's robust sequence-level recognition across species and its current limitations when interpreting un-fine-mapped regulatory variants. This demonstrates how GenAI innovations that are still under development can safely be harnessed by wrapping a responsible AI layer around the call to intercept flawed results, thereby adhering to international standards, such as the Australian Voluntary AI Safety Standard (VAISS).

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：AlphaGenome 是一个深度序列-功能（sequence-to-function）模型，能够直接从DNA序列预测分子表型（如基因表达、剪接、染色质可及性等）。该模型在人类基准上表现优秀，但对其在非人类物种（如小鼠）上的泛化能力、以及处理真实高密度分离变异（非参考基因组背景）的能力尚不清楚。
- **整体含义**：跨物种知识转移是转化基因组学的关键，但进化分歧导致调控网络差异，可能使人类训练的模型在小鼠上产生严重预测失真。因此，系统评估AlphaGenome在跨物种场景下的可靠边界，对于安全部署此类工具至关重要。同时，论文探索了通过“负责任AI层”（如澳大利亚自愿性AI安全标准VAISS）来拦截不可靠预测，实现安全使用。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：对AlphaGenome进行严格跨物种验证，区分其在不同功能任务（定量基因表达 vs. 结构剪接位点识别）上的预测保真度，并开发AI智能体评分方法自主评估预测置信度。
- **关键技术细节**：
  - 使用AlphaGenome的标准1 Mb输入上下文窗口，调用其Python客户端进行推理（仅推理，禁止微调）。
  - 定量表达预测：使用“gene-masked RNA-seq log-fold-change”评分器，返回基因×组织矩阵的预测表达变化。
  - 剪接效应预测：使用“splice-sites”评分器，最终效应定义为所有轨道最大绝对预测变化。
  - 构建任务匹配的零假设分布（随机等位基因、随机位置控制）计算经验p值，通过预设p值阈值判断预测是否被支持。
  - 开发AI智能体（LLM层）对检查点结果进行解释和审计，但统计决策由预设规则决定。

## 3. 实验设计：数据集、基准、对比方法

- **人类eQTL基准验证**：
  - 数据：GTEx全血中的精细定位eQTL（eQTL Catalogue SuSiE可信集，后验包含概率>0.9，可信集大小≤3），随机采样50个变异。
  - 对比：AlphaGenome预测效应与经验SuSiE效应大小的Spearman相关系数（ρ=0.58）和符号一致性（68%）。
- **小鼠野生群体表达差异**：
  - 数据：法国和伊朗野生小家鼠（Mus musculus domesticus）群体匹配的基因组和脾脏RNA-seq（Harr等人），关注高分化位点Ankle1和Hbb-bs。
  - 方法：构建群体特异性单倍型（将群体近固定等位基因导入mm10参考模板），预测伊朗/法国表达比，对照实际RNA-seq比（0.21和0.36 vs 预测~1.0）。
  - 控制：随机等位基因集和随机位置集（8个单倍型/位点），跨9个组织比较。
- **小鼠F1等位基因特异性表达（ASE）**：
  - 数据：CAST×PWK双列杂交的脑RNA-seq（Crowley等人），显著顺式效应（p<0.01，|效应|>0.2）。
  - 方法：
    - 单倍型级：重建CAST和PWK完整单倍型，预测表达比~1.0。
    - 单变异级：选取距TSS最近且CAST与PWK不同、PWK与参考一致的单变异，预测CAST vs 参考效应，与经验顺式方向比较（n=50和n=150）。
  - 结果：符号一致性64%（n=50, p=0.065）；预测效应大小压缩约100倍（中位绝对预测效应0.028（人类） vs 0.005（小鼠））。
- **剪接位点破坏预测**：
  - 数据：GENCODE v44（人类560,888边界）和vM23（小鼠552,514边界）。随机采样25个边界/物种。
  - 三类突变：规范GT/AG破坏、+5bp剪接区域、距边界≥40bp的远端对照。
  - 结果：人类AUC=0.98，小鼠AUC=0.99；规范效应大小无显著差异（Mann-Whitney p≈0.26）。
- **对比方法**：无外部模型对比。论文仅验证AlphaGenome自身在跨物种任务间的差异，并与已发表的人类基准结果复现一致。

## 4. 资源与算力

论文未明确说明训练或推理使用的GPU型号、数量或训练时长。唯一相关提及：AlphaGenome通过Python客户端进行推理，仅用于推断，不进行微调（因平台禁止）。作者未报告计算资源的具体细节。

## 5. 实验数量与充分性

- **实验组数**：主要包括四大类实验：
  1. 人类eQTL复现（1组，50变异）。
  2. 小鼠野生群体表达（2个位点×9个组织×多种控制单倍型）。
  3. 小鼠F1 ASE单变异分析（50变异和150变异两档）。
  4. 剪接位点预测（人类和小鼠各25边界×3类突变）。
- **充分性评价**：
  - 实验设计合理，覆盖了两种功能类型（定量 vs. 确定性）、两种物种（人类vs. 小鼠）、两种变异模式（精细定位的eQTL vs. 未精细定位的群体/单倍型）。
  - 但样本量有限：人类eQTL仅50个变异；小鼠单变异分析n=50/150，未达到统计显著；剪接位点各25个边界。作者承认这是限制。
  - 消融实验：对小鼠野生群体使用了随机等位基因和随机位置控制，排除了突变密度混淆；但未对剪接预测进行多物种扩增或更多边界采样。
  - 总体而言，实验覆盖了关键对比，但样本量和统计效力可进一步优化（尤其表达预测部分）。公平性方面，所有分析均使用相同管道和预设随机种子，确保可重复。

## 6. 主要结论与发现

- **功能依赖的跨物种性能分离**：
  - 剪接位点破坏：预测跨物种鲁棒，AUC≈0.96-0.99，效应大小无物种差异（短距离、确定性序列规则良好转移）。
  - 定量表达效应：在小鼠中方向弱、效应压缩约100倍。无论是群体单倍型还是F1单变异测试，预测比接近1.0而经验比达0.2-0.36，方向一致性不显著偏离随机。
- **驱动因素**：训练数据不平衡（小鼠功能基因组轨道数仅为人类1/5）、缺乏等效的精细定位数据集、跨物种调控网络差异。
- **负责任AI框架可行**：通过预设经验p值检查点（区分预测是否显著分离于控制），能够自动标记不可靠预测（如小鼠表达预测），支持VAISS准则。LLM解释层进一步提供审计记录。
- **启示**：对于非人类应用，需优先生成高分辨率功能基因组数据，并考虑迁移学习或跨物种整合；同时序列-功能模型本身受限于局部顺式窗口，未来需整合宏观反式调控信息。

## 7. 优点

- **任务分离设计**：明确区分“短程确定性规则”（剪接）与“长程定量调控”（表达），揭示了模型能力的本质差异。
- **严格跨物种比对**：人类和小鼠使用完全相同的管道和评分器，控制对比公平。
- **负责任AI机制**：提出可操作的验证检查点（经验p值+LLM解释），实现AI输出的自动安全筛选，符合国际标准。
- **公开可复现**：代码、数据获取脚本、交互式分析笔记本均开源。

## 8. 不足与局限

- **样本量有限**：人类eQTL仅50变异；小鼠单变异分析n=50/150，未达到统计显著；剪接位点仅各25边界，限制了一般性推断。
- **小鼠精细定位缺失**：由于缺乏高质量小鼠eQTL精细数据，单变异选择依赖TSS近端启发式，可能引入噪声，导致相关性被低估。
- **群体分析因果推断不足**：无法确定观察到的群体表达差异是否由局部顺式变异驱动，可能导致假阴性。
- **剪接基准为设计突变**：使用人为设计的规范破坏而非自然分离变异，后者可能受选择压力影响，因此该测试仅反映序列识别能力，非自然变异效应。
- **负责任AI层初步**：仅能判断是否统计上不可区分于随机，对于更细微的错误或不同track可能需要扩展。
- **无多模型对比**：未与Enformer或其他序列-功能模型进行比较，无法评估AlphaGenome的相对优势或劣势。
- **计算资源未报告**：无法评估模型可扩展性。

（完）
