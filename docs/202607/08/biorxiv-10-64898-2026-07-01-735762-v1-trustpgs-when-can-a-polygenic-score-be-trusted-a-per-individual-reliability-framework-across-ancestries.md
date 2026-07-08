---
title: "TrustPGS: When can a polygenic score be trusted? A per-individual reliability framework across ancestries"
title_zh: TrustPGS：多基因评分何时可信？一个跨祖先的个体可靠性框架
authors: "Onawole, A., Adegoke, R. A., Amoo, O."
date: 2026-07-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.01.735762v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 提出TrustPGS框架，提供跨祖先的个体水平多基因评分可靠性判断
tldr: "多基因评分在跨种族个体预测中缺乏可靠性指标，尤其对祖源未充分代表的人群危害最大。TrustPGS框架通过贝叶斯后验样本集合一致性和最大效应LD块方向一致性，为每个个体生成可信标签。在1000 Genomes和Simons Genome Diversity Project上，对十个性状测试发现百分位秩重标定能在五个性状中保持非欧洲人群富集因子>1，而三个性状因分布形状差异无法修复。该框架提供了可检验的每性状可靠性基础，避免单一可移植性承诺的误导。"
source: biorxiv
selection_source: fresh_fetch
motivation: 多基因评分的群体准确度无法告知临床医生单一个体预测的可靠性，尤其对祖先代表性不足的人群这一缺口最为致命。
method: 提出TrustPGS框架，基于SBayesRC贝叶斯后验样本集合的共识和最大幅度LD块的方向一致性，在1000 Genomes队列上校准，并测试跨种群转移的三种策略。
result: "百分位秩重标定在五个性状（阿尔茨海默病、乳腺癌、BMI、LDL胆固醇、收缩压）上保持非欧洲人群富集因子>1；三个性状（冠心病、身高、精神分裂症）因分布形状差异无法修复，两个性状表现居中。"
conclusion: TrustPGS为临床决策提供每性状可检验的可靠性标签基础，而非单一的跨种群可移植性承诺，有效识别何时何地可信任多基因评分。
---

## 摘要
多基因评分总结了某一性状的遗传易感性，但群体水平的准确度指标无法告诉临床医生，一个给定的预测对他们面前的个体是否可靠。这一差距对祖先群体在发现队列中代表性不足的个体影响最大，正是那些错误信任决策会带来最高临床成本的患者。我们提出了TrustPGS框架，该框架告知临床医生和下游模型哪些个体预测可信、哪些不可信，从而让多基因评分能够为临床决策提供信息，而不是无论每个预测的支持程度如何都一律采纳。该框架依赖于在发现队列上校准的两个维度：贝叶斯后验样本集的一致性，以及最大连锁不平衡区块的方向一致性。我们在1000 Genomes Project第三阶段队列中计算了十种多基因性状的SBayesRC后验样本分数，并测试了由此产生的信任标签是否无需重新校准即可迁移至祖先多样化的Simons Genome Diversity Project，比较了严格应用欧洲阈值、百分位等级重缩放以及队列内重新校准三种方法。百分位等级重缩放保留了十种性状中五种（阿尔茨海默病、乳腺癌、体重指数、低密度脂蛋白胆固醇和收缩压）在非欧洲人群中的富集因子大于1，这些性状的欧洲队列和目标队列分布虽有偏移但形状相似。三种性状（冠状动脉疾病、身高和精神分裂症）的分布差异在于形状而非位置，这种模式可归因于发现队列偏差，且重新校准也无法修复；另外两种性状（2型糖尿病和受教育程度）表现出中间行为：一种情况是存在但从未富集，另一种情况是看似成功但排名映射正确揭示其为伪影。由于这些模式中的每一种在做出个体水平断言之前都可以被检测到，TrustPGS为临床医生和下游模型提供了一个可证伪的、基于性状的基础，用于决定在新人群中何时可以信任可靠性标签，而不是一个沉默地成立或失败的单一可移植性承诺。

## Abstract
Polygenic scores summarise genetic predisposition to a trait, but a population-level accuracy figure cannot tell a clinician whether a given prediction is reliable for the person in front of them. This gap is most consequential for individuals whose ancestry is under-represented in the discovery cohort, precisely the patients for whom a wrong trust call carries the highest clinical cost. We present TrustPGS, a framework that tells clinicians and downstream models which individual predictions can be trusted and which cannot, so that polygenic scores can inform clinical decisions rather than being acted on uniformly regardless of how well-supported each prediction is. The framework rests on two axes calibrated on a discovery cohort, the consensus of a Bayesian posterior-sample ensemble and the directional agreement of the top-magnitude linkage-disequilibrium blocks. We computed SBayesRC posterior-sample scores for ten polygenic traits in the 1000 Genomes Project phase-3 cohort and tested whether the resulting trust labels transfer, without recalibration, to the ancestrally diverse Simons Genome Diversity Project, comparing strict application of the European cutoffs, percentile-rank rescaling, and within-cohort recalibration. Percentile-rank rescaling preserved an enrichment factor above one in non-European populations for five of ten traits (Alzheimer disease, breast cancer, body mass index, LDL cholesterol, and systolic blood pressure), traits whose European and target-cohort distributions were shifted but comparable in shape. Three traits (coronary artery disease, height, and schizophrenia) carried distributions that differed in shape rather than location, a pattern traceable to discovery-cohort bias that recalibration could not repair either, and two further traits (type 2 diabetes and educational attainment) showed intermediate behaviour, present but never enriched in one case, and an apparent success that rank-mapping correctly unmasked as artefactual in the other. Because each of these patterns is detectable before any individual-level claim is made, TrustPGS gives clinicians and downstream models a falsifiable, per-trait basis for deciding when a reliability label can be trusted on a new population, rather than a single portability promise that holds or fails silently.

---

## 论文详细总结（自动生成）

## 论文中文详细总结

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：多基因评分（PGS）在群体水平上具有预测准确性，但无法告知临床医生**单个个体**的预测是否可靠。尤其对于祖先群体在发现队列中代表性不足的患者，错误的信任判断会带来最高的临床成本。
- **整体含义**：现有PGS研究主要关注群体级准确度或贝叶斯后验不确定性量化，但缺少一个**直接的个体级决策规则**。作者提出TrustPGS框架，为每个PGS预测生成一个“可信/不可信”标签，使临床医生和下游模型能够区分哪些预测可以依赖、哪些需要谨慎对待，而不是不加区分地全部使用。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：基于两个维度（轴）的联合判断：
  - **集合共识（Consensus）**：从SBayesRC的每个SNP后验均值和标准误中抽取K=20个后验样本，计算每个个体的PGS集合（ensemble），定义`cv_ratio = std(pgs_ensemble) / pop_std`，其中`pop_std`是发现队列中集合均值PGS的标准差。低`cv_ratio`意味着不同后验样本对该个体的评分高度一致，视为“高共识”。
  - **顶部区块方向一致性（Agreement）**：将基因组划分为1 Mb的LD区块（共2697块），对每个个体和每个后验样本，计算每个区块的贡献（中心化剂型×后验beta），取贡献幅度前10%的区块，计算这些区块方向与个体整体偏离方向一致的比例`agreement_frac`。高比例意味着驱动该评分的基因组区域在该个体的方向上一致。
- **校准规则**：在1000G欧洲（EUR）亚组上确定两个轴的经验分位数阈值：共识阈值为`cv_ratio`的**30%分位数**，一致性阈值为`agreement_frac`的**70%分位数**。由此得到四个象限：
  - 情景A：高共识 + 高一致性（可靠）
  - 情景B：高共识 + 低一致性
  - 情景C：低共识 + 高一致性
  - 情景D：低共识 + 低一致性（不可靠）
- **关键流程**：
  - 使用SBayesRC（当前最佳贝叶斯收缩方法）提供后验均值和标准误。
  - 对每个个体构建K=20的后验样本PGS集合，计算`cv_ratio`和`agreement_frac`。
  - 通过模拟表型（`y = g + noise`，设定遗传力h²=0.4）计算预测误差，评估情景A个体的富集因子（EF@0.5，预测误差≤0.5 SD的比例相对于全体基线的比值）。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集**：
  - **发现队列**：1000 Genomes Project phase-3（1000G，n=2504，五个超级群体：AFR、AMR、EAS、EUR、SAS）。用于校准阈值。
  - **测试队列**：Simons Genome Diversity Project（SGDP，n=345，142个群体，映射到1000G超级群体加上大洋洲OCN）。用于评估跨祖先迁移。
- **基准与对比**：
  - 没有设置外部基线模型（如其他个体不确定性方法），因为该框架是首次提出。内部对比通过**三种校准机制**实现：
    1. **严格迁移（Strict OOD）**：直接使用1000G EUR阈值和pop_std。
    2. **百分位等级重缩放（Rank-mapped OOD）**：在SGDP上应用与EUR相同百分位位置的自定义阈值（即重新映射分布位置），保留形状信息。
    3. **队列内重新校准（Within-cohort recalibration）**：在SGDP的EUR亚组（n=75）上重新拟合两个阈值。
  - 此外，还在1000G内部检验了情景A在非欧洲超级群体中的富集因子，作为内部验证。
- **性状**：10个性状，覆盖三种遗传架构（高度多基因数量性状、主要效应位点疾病、精神行为性状）。具体包括：身高、BMI、T2D、CAD、乳腺癌、阿尔茨海默病、LDL胆固醇、收缩压、精神分裂症、受教育程度。所有权重来自SBayesRC的公开数据。

### 4. 资源与算力

- 文中提到使用了昆士兰大学研究计算中心的 **Bunya超级计算机**，但**未明确说明GPU型号、数量、训练时长或总计算量**。仅提及“由昆士兰大学研究计算中心的Bunya超级计算机提供资源支持”，未提供具体算力细节。

### 5. 实验数量与充分性

- **实验数量**：
  - 10个性状 × 3种校准机制 = 30个主要实验组合。
  - 每个组合计算了每个超级群体（最多5个，但OCN和AMR因样本量小被标记）的富集因子（EF@0.5），以及情景A人数。
  - 额外提供了不同阈值（0.5、1.0、2.0 SD）下的富集因子（见补充表S2）。
  - 还有在1000G内部的内部验证（10个性状×5超级群体）。
  - 分布形状诊断（图3）：为每个性状绘制了CDF曲线用于诊断可迁移性。
- **充分性**：
  - **优点**：覆盖多种遗传架构和多个祖先群体，并且明确区分了三种迁移情景，给出了可诊断失败的机制。
  - **不足**：SGDP每个超级群体样本量较小（EUR仅75，AFR 93，EAS 48，SAS 75），许多超群体内情景A的n<5，导致富集因子估计不稳定（作者也标记了这些单元格）。未使用更大的独立非欧洲队列（如All of Us、H3Africa、GenomeAsia 100K）进行验证。此外，仅在1000G一个发现队列上校准，未重复随机分割或交叉验证。
  - **消融实验**：没有对共识轴和一致性轴各自的重要性进行消融（例如仅使用一轴的效果），但在讨论中提及了两个轴缺一不可的逻辑。对顶部区块阈值（5%、10%、20%）进行了测试说明，但未作为主要实验结果。
  - 作者承认存在轻微的“样本内泄露”（校准在完整EUR集合上而非分割），但声明跨祖先结论不依赖EUR列。

### 6. 论文的主要结论与发现

- **核心发现**：基于欧洲发现队列校准的个体级可靠性标签在跨祖先迁移时并非普遍适用，但**失败模式在可诊断、可预测**。
- **三组性状行为**：
  1. **成功迁移（5个性状）**：阿尔茨海默病、乳腺癌、BMI、LDL胆固醇、收缩压。在百分位等级重缩放下，非欧洲人群的富集因子>1，分布形状可比，仅位置偏移。
  2. **完全失败（3个性状）**：冠心病、身高、精神分裂症。两个轴在SGDP上的分布与欧洲在形状上显著不同，任何重缩放均无法修复（包括队列内重新校准）。作者将失败归因于欧洲发现队列偏差在顶部区块方向上的体现。
  3. **中间行为（2个性状）**：
     - 2型糖尿病：出现情景A但无实际准确度增益（EF<1）。
     - 受教育程度：严格迁移下出现55个情景A（看似成功），但百分位重缩放后归零，揭示严格迁移下的成功是伪影（阈值偶然交叉），框架正确检测到了这个假阳性。
- **关键诊断工具**：比较两个队列的`cv_ratio`和`agreement_frac`的经验CDF形状即可在做出个体级预测前判断某个性状的可迁移性（形状相似→可迁移；形状不同→不可迁移）。
- **实践意义**：框架提供了“可证伪的、分性状的”决策基础，而不是一个单一的、沉默地失败的可移植性承诺。

### 7. 优点：方法或实验设计上的亮点

- **个体级决策规则**：首次将后验不确定性转化为二元可信标签，直接面向临床应用。
- **双轴设计**：共识轴和一致性轴互补，覆盖了预测稳定性和解释一致性两个维度，避免了单一轴在高多基因性下的不足。
- **跨祖先可诊断性**：通过CDF形状比较即可确定哪些性状的标签可以迁移，为使用者在没有实测表型的情况下提供先验指导。
- **诚实的失败报告**：明确展示了哪些性状失败、如何失败以及为什么失败，避免了虚假的可移植性声称。
- **开放代码**：提供GitHub仓库（https://github.com/MujeebOnawole/TrustPGS），促进复现和扩展。
- **简单的校准机制**：阈值基于百分位数（30th和70th），逻辑直观，无需复杂优化。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **样本量限制**：SGDP每个超级群体样本量很小（n<100），导致情景A个体数经常低于5，富集因子估计不稳定。作者标记了这些单元格，但小样本限制了对AFR等群体的可靠结论。
- **后验样本构建的近似**：仅从边际后验标准误独立采样（K=20），忽略了SNP间的相关性。作者承认这使共识轴更宽松（低估不确定性），对结果保守，但未使用联合后验（需要完整重跑MCMC）。
- **单方法依赖**：仅使用SBayesRC一种权重方法，未来应扩展到LDpred2、PRS-CS等，以捕捉跨方法不确定性。
- **模拟表型的简化**：由于SGDP没有真实表型，作者使用PGS加噪声（固定h²=0.4）模拟表型。真实遗传力和噪声分布可能不同，影响富集因子绝对值。
- **校准泄漏**：发现队列上的阈值由全EUR样本确定，未进行交叉验证或独立验证集分离，存在轻微过拟合风险（虽然作者声明不影响跨祖先结论）。
- **未在更大独立非欧洲队列上验证**：作者承认需要在All of Us、H3Africa、GenomeAsia 100K等队列上进一步验证。
- **阈值选择的主观性**：30%和70%分位数是经验选择，虽然作者声称标签预测跨祖先迁移的行为不依赖具体数字（只要情景A在发现队列非空），但未进行敏感性分析。
- **临床应用距离**：目前仅在两个队列上展示，且需要SBayesRC权重的预计算和后验样本抽取，计算流程对临床集成尚有一定门槛。

（完）
