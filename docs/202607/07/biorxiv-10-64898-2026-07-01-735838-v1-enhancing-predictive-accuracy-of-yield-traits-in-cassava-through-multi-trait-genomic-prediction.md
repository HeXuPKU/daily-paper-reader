---
title: Enhancing predictive accuracy of yield traits in cassava through multi-trait genomic prediction
title_zh: 通过多性状基因组预测提高木薯产量性状的预测准确性
authors: "de Freitas, G. M., Certuche, D. S., Jannink, J.-L., de Oliveira, E. J., Garcia, A. A. F."
date: 2026-07-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.01.735838v1.full.pdf"
tags: ["query:gwas"]
score: 6.0
evidence: 多性状基因组预测方法与多基因风险评分预测模型类似
tldr: "木薯育种中，多性状基因组预测可提升产量等复杂性状的选择效率。本研究基于1078份巴西木薯材料，比较单性状与多性状GBLUP模型，并模拟五种交叉验证方案。多性状模型在辅助性状信息充分时，鲜根产量预测能力提升44%（达0.65），均方根误差降低13.5%。稀疏表型方案下多性状模型仍保持较高预测能力，且与单性状模型选择一致性高。研究表明策略性多性状预测可降低表型负担并提高遗传增益。"
source: biorxiv
selection_source: fresh_fetch
motivation: 木薯中鲜根产量等复杂性状表型成本高，单性状预测精度有限，需探索多性状模型利用辅助信息提升选择效率。
method: "对1078份木薯克隆的25,923个SNP及6个性状，采用GBLUP模型比较单性状与多性状预测，设计五种交叉验证方案模拟育种场景。"
result: "多性状模型在CV3方案下鲜根产量预测能力从0.45升至0.65，干物质含量小幅提升2%；稀疏表型下预测能力稳定在0.62–0.65。"
conclusion: 合理利用操作上相关的辅助性状和稀疏表型，多性状GBLUP可显著提高关键产量性状的预测精度并降低表型工作量。
---

## 摘要
多性状基因组预测为提高克隆繁殖作物（如木薯）中昂贵且复杂性状的选择提供了一条实用途径。在一个包含1,078个木薯无性系、使用25,923个SNP进行基因分型并针对六个农艺性状进行表型鉴定的巴西育种群体中，我们比较了单性状（ST）和多性状（MT）GBLUP模型。阶段性混合模型产生了最佳线性无偏估计值（BLUEs），这些估计值被用于ST和MT-GBLUP。我们测试了五种模拟育种实际情况的交叉验证方案：ST基线（CV1）；针对未表型候选者的朴素全性状MT预测（CV2）；利用测试集中辅助性状表型的MT预测（CV3）；以及两种稀疏表型方案，分别按性状（CV4）或按无性系（CV5）缺失数据，缺失程度为25%、50%和75%。主要结果表明，在ST基线（CV1）下，预测能力范围从DMC的0.50和FRY的0.45降至Le.Dis的0.13。朴素全MT模型（CV2）的表现与ST-GBLUP大致相当。相比之下，包含信息性辅助性状（如地上部产量以及与植物活力和叶片病害严重程度的组合）的MT设计（CV3）使DMC的预测能力略有提高，达到约0.51（+2%），而FRY的预测能力提高至约0.65（+44%），同时FRY的均方根误差（RMSE）降低高达约13.5%（例如RMSE约6.2）。稀疏表型模拟（CV4/CV5）表明，在实际缺失数据情况下（预测能力约0.62-0.65），MT模型能够维持甚至提高预测能力。MT和ST前10%集合的选择一致性普遍较高（>0.80），并且MT配置在几个目标性状的预期选择响应和每周期遗传增益方面产生了可衡量的改进。这些结果表明，策略性地实施MT-GBLUP，利用少量生物学和操作上信息丰富的辅助性状以及优化的稀疏表型，可以显著提高经济上关键木薯性状的预测准确性和选择效率，同时减少表型鉴定负担。

## Abstract
Multi-trait genomic prediction offers a practical route to improve selection for costly, complex traits in clonally propagated crops such as cassava. In a Brazilian breeding panel of 1,078 cassava clones genotyped with 25,923 SNPs and phenotyped for six agronomic traits, we compared single-trait (ST) and multi-trait (MT) GBLUP models. Stage-wise mixed models produced BLUEs that fed into ST and MT-GBLUP. We tested five cross-validation schemes that mimic breeder realities: ST baseline (CV1); naive all-traits MT prediction for unphenotyped candidates (CV2); MT prediction using auxiliary trait phenotypes in the test set (CV3); and two sparse-phenotyping regimes with missingness by trait (CV4) or by clone (CV5) at 25%, 50%, and 75% levels. The main results were that, under the ST baseline (CV1), predictive ability ranged from 0.50 for DMC and 0.45 for FRY down to 0.13 for Le.Dis. A naive full MT model (CV2) performed approximately on par with ST-GBLUP. In contrast, MT designs (CV3) that included informative auxiliary traits, such as shoot yield and combinations with plant vigor and leaf disease severity, yielded small gains for DMC with predictive ability of approximately 0.51 (+2%), while FRY predictive ability increased to approximately 0.65 (+44%), accompanied by RMSE reductions for FRY up to approximately 13.5% (e.g. RMSE approximately 6.2). Sparse-phenotyping simulations (CV4/CV5) demonstrated that MT models sustain or even improve predictive ability under realistic missing-data regimes (PA {approx} 0.62 - 0.65). Selection concordance between MT and ST top-10% sets was generally high (>0.80), and MT configurations produced measurable improvements in expected selection response and genetic gain per cycle for several target traits. These results indicate that strategically implemented MT-GBLUP, using a small set of biologically and operationally informative auxiliary traits and optimized sparse phenotyping, can materially increase predictive accuracy and selection efciency for economically critical cassava traits while reducing phenotyping burden.