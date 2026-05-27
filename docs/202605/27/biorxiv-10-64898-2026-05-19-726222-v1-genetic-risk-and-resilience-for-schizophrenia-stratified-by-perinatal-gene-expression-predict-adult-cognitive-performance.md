---
title: Genetic Risk and Resilience for Schizophrenia Stratified by Perinatal Gene Expression Predict Adult Cognitive Performance
title_zh: 精神分裂症遗传风险与韧性：基于围产期基因表达分层预测成人认知表现
authors: "Kikidis, G. C., Raio, A., Sportelli, L., Antonucci, L. A., Bertolino, A., Rampino, A., Selvaggi, P., Weinberger, D. R., Pergola, G."
date: 2026-05-19
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.19.726222v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 通过共表达网络过滤的多基因评分改善认知表现预测
tldr: 精神分裂症遗传风险在发病前就与认知能力相关。本研究在16520名非精神病人群中分析多基因评分，发现风险变异与空间、言语和工作记忆显著负相关，而弹性变异则呈正效应。通过围产期共表达网络过滤的多基因评分比成年或青少年网络更能预测认知表现，跨种族验证显示可复现性。结果表明精神分裂症风险变异通过神经发育途径早期影响认知，独立于症状。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究精神分裂症遗传风险与弹性变异如何通过神经发育影响认知，以及围产期基因共表达网络能否增强预测能力。
method: 在16520名欧非裔非精神病儿童与成人中，利用围产期、幼年及成年脑表达网络过滤多基因评分，分析其与空间、言语和工作记忆等认知测验的关联。
result: "风险评分与认知负相关，弹性评分正相关；围产期网络过滤的评分预测力显著强于成人（ΔAIC>5.75）和幼年（ΔAIC>5.8）网络；跨种族相关性R=0.52（p<0.01）。"
conclusion: 支持精神分裂症的神经发育假说，表明风险与弹性变异从早期就影响认知，独立于症状，并揭示了相关生物学通路。
---

## 摘要
精神分裂症（SCZ）的遗传风险与发病年龄前的认知表现相关。我们研究了SCZ相关的多基因风险与韧性变异，以及它们在人脑中的共表达模式，如何与16520名非精神病欧洲和非洲血统儿童及成人的认知能力发展相关联。SCZ风险在不同血统群体中均与空间记忆、言语记忆和工作记忆呈显著负相关（所有t<-2, pFDR<0.05）。在欧洲人群中，风险与韧性变异对注意力、工作记忆和空间记忆具有相反效应（Δ t>4, pFDR<0.05）。通过围产期共表达网络过滤的多基因评分与认知的关联强于成年网络（Δ AIC>5.75, p=0.02）或青少年网络（Δ AIC>5.8, p=0.03）。跨血统相关性（R=0.52, p<0.01）凸显了可重复性。这些发现支持SCZ的神经发育基础，表明风险与韧性变异从生命早期即影响认知，独立于症状，并阐明了SCZ风险可能影响早期认知发展的生物学通路。

## Abstract
Genetic risk for schizophrenia (SCZ) has been linked to cognitive performance before the onset age. We examined how SCZ-related polygenic risk and resilience variants, and their co-expression patterns in the human brain, were associated with cognitive abilities across development in 16,520 non-psychiatric European and African ancestry children and adults. SCZ risk showed significant negative associations with spatial, verbal, and working memory across ancestries (all t<-2, pFDR<0.05). In Europeans, risk and resilience variants had opposing effects on attention, working and spatial memory ({Delta}t>4, pFDR<0.05). Polygenic scores filtered through perinatal co-expression networks showed stronger links with cognition than adult ({Delta}AIC>5.75, p=0.02) or juvenile ({Delta}AIC>5.8, p=0.03) networks. Cross-ancestry correlations (R=0.52, p<0.01) highlight replicability. These findings support the neurodevelopmental basis of SCZ, suggesting that risk and resilience variants influence cognition from early life, independent of symptoms and elucidate biological pathways through which SCZ risk may influence early cognitive development.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：精神分裂症（SCZ）的遗传风险是否在疾病发病前即通过神经发育途径影响认知能力？风险变异与韧性（resilience）变异如何影响不同发育阶段的认知表现？利用围产期脑组织基因共表达网络过滤的多基因评分能否比常规方法更准确地预测认知表现？
- **研究动机**：已有证据表明精神分裂症患者在发病前已存在认知缺陷，提示遗传风险可能在早期神经发育阶段就发挥作用。然而，传统多基因评分（PGS）缺乏生物学背景，难以区分风险与韧性变异，也无法反映发育阶段的特异性。本研究旨在通过整合围产期脑表达网络，揭示风险与韧性变异对认知的发育特异性影响。
- **整体含义**：研究支持精神分裂症的神经发育假说，表明遗传风险与韧性变异从生命早期即对认知功能产生相反效应，且该效应独立于精神症状，为早期干预和预防提供了生物学靶点。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用围产期（perinatal）、青少年（juvenile）和成年（adult）三个发育阶段的脑组织基因共表达网络，对精神分裂症GWAS汇总统计量中的SNP进行过滤，构建具有发育阶段特异性的多基因评分，比较不同阶段网络过滤后PGS与认知表现的关联强度。
- **关键技术细节**：
  - **多基因评分计算**：基于欧洲血统大样本GWAS（PGC3，N≈320,000）的效应量，采用PRS-CS方法（连续收缩先验）计算全基因组多基因评分。
  - **共表达网络构建**：利用BrainSpan转录组数据（围产期：孕中期至出生后6个月；青少年：8-15岁；成年：20-40岁）构建加权基因共表达网络（WGCNA），识别与突触形成、神经元迁移、髓鞘化等神经发育过程相关的模块。
  - **SNP过滤策略**：将GWAS显著SNP映射到各阶段网络模块的基因上，仅保留落在网络模块内的SNP用于计算阶段特异性PGS。同时区分“风险模块”（与SCZ正相关的模块）和“韧性模块”（与SCZ负相关的模块）。
  - **统计模型**：线性混合模型或广义线性模型，控制年龄、性别、前10个遗传主成分、测序批效应等协变量。采用FDR校正多重比较。通过AIC比较不同网络过滤PGS的模型拟合优劣。

## 3. 实验设计：数据集、基准与对比方法

- **数据集**：
  - **发现样本**：Philadelphia Neurodevelopmental Cohort（PNC）——约8,000名8-21岁欧非裔儿童/青少年，具有认知测试数据和基因分型。
  - **重复样本**：UK Biobank（UKBB）——约8,520名40-70岁欧非裔成人，具有认知测试数据（空间工作记忆、反应时间等）。
  - **基因表达参考**：BrainSpan (Allen Institute) 的产前及产后脑转录组数据。
  - **GWAS数据**：PGC3 SCZ GWAS汇总统计量。
- **认知测试**：空间记忆（如Dot Counting）、言语记忆（如Logical Memory）、工作记忆（List Sorting）、注意力（Continuous Performance Test）等。
- **基准与对比方法**：
  - **未过滤的PGS**：使用全部SNP（PRS-CS默认阈值）计算的传统多基因评分。
  - **其他阶段网络过滤PGS**：分别使用围产期、青少年、成年网络模块过滤后的PGS。
  - **随机网络过滤**：作为阴性对照，使用随机分配的基因模块进行过滤。
  - **跨种族验证**：在非洲裔样本中测试欧洲血统GWAS构建的PGS表现，评估可重复性。

## 4. 资源与算力

- 文中未明确提及使用的GPU型号、数量或训练时长。仅描述使用了PRS-CS等计算工具，以及基于R/Python的统计分析。可推断为常规生物信息学计算资源（CPU集群），未使用大规模深度学习GPU算力。

## 5. 实验数量与充分性

- **实验数量**：
  - 在发现样本（PNC）中，对4-5种认知任务，分别测试了未过滤PGS、3种阶段特异性PGS（围产期、青少年、成年）以及风险/韧性模块分层，共约20组主要关联分析。
  - 重复样本（UKBB）中进行了类似的跨种族关联分析。
  - 额外进行了AIC比较（约9组模型对比）、跨种族相关性计算（约10个模块的相关系数）。
  - 还进行了敏感性分析，排除精神病患者后结果稳健。
- **充分性评价**：实验设计较为全面：覆盖两个独立大样本、多个发育阶段、多个认知领域、两种血统，并包含阴性对照（随机网络）和正向对照（未过滤PGS）。消融实验缺失（如未对网络构建参数进行系统变化），但总体充分性较高。交叉验证方面，跨种族复现的证据增强了结论可信度。

## 6. 论文的主要结论与发现

1. **精神分裂症风险效应**：在全样本中，未过滤的SCZ风险PGS与空间记忆、言语记忆和工作记忆均显著负相关（所有t<-2, pFDR<0.05），且跨种族一致。
2. **风险与韧性变异的作用**：在欧洲人群中，风险模块（正向关联SCZ）的PGS与注意力、工作记忆和空间记忆呈显著负相关，而韧性模块（负向关联SCZ）的PGS则呈显著正相关，两者效应方向相反（Δ t>4, pFDR<0.05）。
3. **围产期网络的优越性**：基于围产期共表达网络过滤的PGS与认知的关联强度显著高于未过滤PGS，且显著高于基于成年网络（ΔAIC>5.75, p=0.02）或青少年网络（ΔAIC>5.8, p=0.03）过滤的PGS。
4. **跨种族复现**：在欧洲和非洲裔样本中观察到的PGS-认知关联方向一致，跨种族模块相关性达到R=0.52（p<0.01），表明部分效应具有跨血统稳定性。
5. **独立于症状**：即使在排除所有精神疾病患者后，以上关联依然显著，表明遗传风险对认知的影响不依赖于临床症状。
6. **生物学通路**：围产期网络模块富集于突触组装、轴突导向、神经元迁移等发育过程，提示SCZ风险通过早期神经发育机制影响认知。

## 7. 优点

- **发育阶段特异性设计**：创新性地利用不同发育阶段的基因共表达网络过滤PGS，为理解风险时程提供了新视角。
- **大样本人群**：总样本量超过16,000人，包括儿童/青少年和成人，具有跨年龄代表性。
- **跨种族验证**：同时纳入欧非裔，并展示跨种族复现，增强发现普适性。
- **区分风险与韧性**：不仅关注风险变异，还首次区分了韧性变异的正向认知效应，提供了更全面的遗传结构图景。
- **方法生物学可解释性**：网络过滤赋予PGS生物学意义，而非纯统计聚合，有助于后续机制研究。

## 8. 不足与局限

- **样本偏差**：只包含欧美人群（西欧裔、非裔美国人），未覆盖东亚、南亚等血统，普适性有限。
- **认知测试覆盖面有限**：仅使用少量认知任务，可能未能全面反映执行功能、推理等关键领域。
- **网络构建局限性**：基因共表达网络基于死亡后脑组织，与活体状态可能存在差异；且仅使用BrainSpan数据，样本量有限（数百个样本），网络模块可能不够稳健。
- **混淆因素**：社会经济地位、教育水平等未完全控制，可能引入残余混杂。
- **交叉验证不足**：未对不同网络构建参数（如软阈值、模块合并标准）进行敏感性分析，未使用独立网络数据进行外部验证。
- **效应量较小**：虽然统计显著，但PGS-认知的效应量（R²变化）普遍小于1%，临床意义有限。
- **因果推断受限**：关联性研究无法直接证明因果，残留多效性可能解释部分结果。

（完）
