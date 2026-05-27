---
title: "Parallel Contributions of Externalizing Polygenic Liability and Brain Imaging Phenotypes to Adolescent Substance Use Initiation Timing: A Multistage Analysis in the ABCD Study"
title_zh: 外化多基因倾向与脑影像表型对青少年物质使用开始时间的平行贡献：ABCD研究的多阶段分析
authors: "Wei, M., Peng, Q."
date: 2026-05-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.08.717299v2.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 使用多基因风险评分预测物质使用起始，直接对应PRS预测建模
tldr: "青少年物质使用起始受遗传和神经生物学因素共同影响。本研究基于ABCD研究10,608名参与者，通过多阶段框架分析外部化多基因风险评分（extPRS）与基线脑成像表型对物质起始时间的预测作用。发现extPRS与更早的起始显著相关，数千脑表型与之关联，且众多脑表型独立预测起始风险。但中介分析显示基线脑表型仅解释extPRS效应的很小部分（<2%），表明遗传与脑影像主要呈平行加性贡献。研究揭示了非遗传维度神经生物学脆弱性，并指出纵向脑测量可能更重要。"
source: biorxiv
selection_source: fresh_fetch
motivation: 解析外部化多基因风险如何通过脑结构功能影响青少年物质使用起始，探究基线脑影像是否介导或平行加性贡献。
method: 多阶段分析：线性模型筛选extPRS-脑表型关联，Cox模型估计遗传效应，联合模型识别独立脑预测因子，Bootstrap中介分析量化间接效应。
result: "extPRS显著预测早期起始（HR=1.13-1.67）；数千脑表型关联；独立预测因子数量因物质而异（酒精31，尼古丁459）；中介效应极小（ACME~1e-4，<2%）。"
conclusion: 遗传与基线脑影像对青少年物质起始主要呈平行加性贡献，而非遗传→脑→行为路径；基线脑表型反映未被遗传捕获的神经生物学脆弱性。
---

## 摘要
背景青少年物质使用的开始受到多种遗传和神经生物学因素的影响。外化倾向是一种跨诊断的遗传维度，捕捉了冲动性、去抑制及相关特质的共同易感性，是早期物质开始的最强多基因预测因子之一。然而，这种遗传风险如何与大脑结构和功能相关联，以及基线脑表型是否在统计上解释了遗传倾向的作用，还是与之并行作用，仍不清楚。

方法利用ABCD研究，我们分析了一个包含10,608名参与者的分析队列，这些参与者拥有基因型数据、基线多模态神经影像衍生表型（IDPs）以及纵向物质开始评估。针对生存变量和协变量的完全病例筛选后，各结局特异模型包含多达10,599名参与者。我们实施了一个多阶段框架，将外化多基因风险评分（extPRS）与基线IDPs及纵向物质开始结局（包括酒精、尼古丁、大麻和任何物质）联系起来。第一阶段使用协变量调整的线性模型，并采用错误发现率（FDR）控制，筛选extPRS-IDP关联。第二阶段使用Cox比例风险模型估计extPRS对开始时间的影响。第三阶段拟合联合的extPRS + IDP Cox模型，以识别在extPRS之外预测开始的IDPs。第四阶段进行基于自助法的中介分析，以量化平均因果中介效应（ACME）、平均直接效应（ADE）以及单个IDPs在统计上解释extPRS-开始关联的比例。

结果较高的extPRS与所有物质的更早开始强烈相关：酒精，风险比（HR）= 1.13；尼古丁，HR = 1.63；大麻，HR = 1.67；任何物质，HR = 1.15。在基线识别出数千个与extPRS相关的IDPs，其效应轮廓在稳健性规格上高度一致。在联合模型中，许多IDPs独立于extPRS预测开始时间：酒精31个，任何物质32个，大麻137个，尼古丁459个，并在各规格中有一组重复的核心IDPs。大麻和尼古丁的开始由感觉运动皮层浅层白质（SWM）微结构完整性（保护因素）和右半球区域的不规则活动（风险因素）共同预测。酒精的开始由一个显著不同的、强烈左偏侧的额叶边缘SWM强度轴预测。尼古丁的开始还额外且独特地涉及前扣带皮层和胼胝体下皮层的受限灰质扩散。尽管有这些稳健的独立IDP关联，中介分析显示通过单个基线IDPs的间接效应非常小（ACME约10^-4），占extPRS总效应的不到2%，仅酒精和任何物质开始的中介具有FDR显著性。

结论在外化多基因风险和基线神经影像的范围内，主要模式是对青少年物质开始大致平行、加性的贡献，而非主导的遗传->脑->行为通路。基线脑特征，特别是前额叶功能变异性和额叶边缘及感觉运动白质完整性，在extPRS之外预测开始风险，表明该遗传维度未捕捉到的神经生物学脆弱性。然而，这些基线IDPs仅解释了extPRS-开始关联的一小部分，提示外化遗传倾向可能通过未完全由横断面基线成像代表的其他通路发挥作用。其他遗传风险维度（如物质特异性PRS）或动态纵向脑测量是否显示出更强的中介模式，仍是一个重要的未解问题。

## Abstract
BackgroundAdolescent substance use initiation is shaped by multiple genetic and neurobiological factors. Externalizing liability, a transdiagnostic genetic dimension capturing shared predisposition to impulsivity, disinhibition, and related traits, is among the strongest polygenic predictors of early substance initiation. Yet how this genetic risk relates to brain structure and function, and whether baseline brain phenotypes statistically account for or instead act in parallel with genetic liability, remains unresolved.

MethodsUsing the ABCD Study, we analyzed an analytic cohort of 10,608 participants with genotype data, baseline multimodal neuroimaging-derived phenotypes (IDPs), and longitudinal substance initiation assessments. Outcome-specific models included up to 10,599 participants after complete-case filtering for survival variables and covariates. We implemented a multistage framework linking an externalizing polygenic risk score (extPRS) to baseline IDPs and longitudinal substance initiation outcomes, including alcohol, nicotine, cannabis, and any substance. Stage 1 screened extPRS-IDP associations using covariate-adjusted linear models with false discovery rate (FDR) control. Stage 2 estimated extPRS effects on time-to-initiation using Cox proportional hazards models. Stage 3 fit joint extPRS + IDP Cox models to identify IDPs that predicted initiation beyond extPRS. Stage 4 conducted bootstrap-based mediation analyses to quantify average causal mediation effects (ACME), average direct effects (ADE), and the proportion of the extPRS-initiation association statistically accounted for by individual IDPs.

ResultsHigher extPRS was robustly associated with earlier initiation across all substances: alcohol, hazard ratio (HR) = 1.13; nicotine, HR = 1.63; cannabis, HR = 1.67; and any substance, HR = 1.15. Thousands of extPRS-associated IDPs were identified at baseline, with highly concordant effect profiles across robustness specifications. In joint models, numerous IDPs independently predicted initiation timing above and beyond extPRS: 31 for alcohol, 32 for any substance, 137 for cannabis, and 459 for nicotine, with a replicated core set across specifications. Cannabis and nicotine initiation were jointly predicted by superficial white matter (SWM) microstructural integrity in sensorimotor cortex as a protective factor, and by irregular activity in a right-hemisphere region as a risk factor. Alcohol initiation was predicted by a largely distinct, strongly left-lateralized frontolimbic SWM intensity axis. Nicotine initiation additionally and uniquely involved restricted gray matter diffusion in the anterior cingulate cortex and subcallosal cortex. Despite these robust independent IDP associations, mediation analyses showed that indirect effects through individual baseline IDPs were very small in magnitude (ACME {approx} 10-4), accounting for less than 2% of the total extPRS effect, with FDR-significant mediation surviving only for alcohol and any-substance initiation.

ConclusionsWithin the scope of externalizing polygenic risk and baseline neuroimaging, the predominant pattern is one of largely parallel, additive contributions to adolescent substance initiation rather than a dominant genetic [-&gt;] brain [-&gt;] behavior pathway. Baseline brain features, particularly prefrontal functional variability and frontolimbic and sensorimotor white matter integrity, predict initiation risk beyond extPRS, indicating neurobiological vulnerabilities not captured by this genetic dimension. However, these baseline IDPs explain only a small fraction of the extPRS-initiation association, suggesting that externalizing genetic liability may operate through pathways not fully represented by cross-sectional baseline imaging. Whether other genetic risk dimensions, such as substance-specific PRS, or dynamic longitudinal brain measures show stronger mediation patterns remains an important open question.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：青少年物质使用（酒精、尼古丁、大麻等）的起始时间受遗传和神经生物学因素共同影响。外化倾向（externalizing liability）作为一种跨诊断的遗传维度，能捕捉冲动性、去抑制等共同易感性，是多基因预测早期物质使用的最强因子之一。然而，这种遗传风险如何通过大脑结构和功能发挥作用，以及基线脑影像表型是**统计上中介了遗传倾向的效应，还是与其平行独立地贡献**，尚不清楚。
- **整体含义**：旨在解析“遗传→脑→行为”这一潜在因果路径是否成立，还是遗传和脑影像分别提供加性信息。这对于理解物质使用障碍的神经生物学基础、识别早期生物标志物具有重要意义。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：采用“多阶段分析框架”，将外化多基因风险评分（extPRS）、基线多模态神经影像衍生表型（IDPs）和纵向物质起始时间（生存数据）串联起来，通过逐步筛选和中介分析量化各因素的作用路径。
- **关键技术细节**：
  - **第一阶段**：协变量调整的线性模型，对每个IDP与extPRS的关联进行筛查，采用错误发现率（FDR）控制，筛选出与extPRS显著关联的IDPs。
  - **第二阶段**：Cox比例风险模型，单独估计extPRS对各类物质起始时间（生存变量）的效应，计算风险比（HR）。
  - **第三阶段**：联合Cox模型（extPRS + 显著IDPs），识别在extPRS之外仍能独立预测起始时间的IDPs。
  - **第四阶段**：基于自助法（bootstrap）的中介分析，量化单个IDPs的平均因果中介效应（ACME）、平均直接效应（ADE）以及中介效应占总效应的比例。
- **关键指标**：HR（风险比）、ACME、ADE、中介比例（%）。协变量包括年龄、性别、种族/民族、家庭收入、父母教育、基因主成分等。

## 3. 实验设计：数据集、基准、对比方法
- **数据集**：美国青少年脑认知发展研究（ABCD Study），包含10,608名参与者（完全病例筛选后各结局模型最多10,599人）。数据包括基因型数据、基线（约9-10岁）多模态神经影像IDPs（结构MRI、扩散MRI、静息态功能MRI）以及纵向随访的物质开始评估（生存时间变量）。
- **基准（baseline）**：未明确报告基准模型，但逻辑上以仅有协变量的Cox模型为基准。对比了加入extPRS前后的效应，以及加入IDPs后的额外预测力。
- **对比方法**：未与其他PRS（如物质特异性PRS）或机器学习方法对比。主要比较不同物质（酒精、尼古丁、大麻、任何物质）之间的差异，以及不同稳健性规格（协变量集合、质量控制阈值等）下结果的稳定性。

## 4. 资源与算力
- **文中未明确说明**：未提及GPU型号、数量、训练时长等硬件资源信息。分析主要基于统计和生存分析模型，计算量相对较小，可能使用CPU集群完成。论文未提供代码或计算环境细节。

## 5. 实验数量与充分性
- **实验数量**：
  - 四种物质结局：酒精、尼古丁、大麻、任何物质。
  - 第一阶段：数千个IDP关联测试（FDR校正）。
  - 第三阶段：联合模型识别独立预测因子：酒精31个，任何物质32个，大麻137个，尼古丁459个。
  - 第四阶段：中介分析针对每个显著IDP分别进行，最终报告FDR显著的中介结果（仅酒精和任何物质）。
  - 不同稳健性规格：多种协变量调整方案（如是否包含24小时运动、屏幕时间等）下重复分析，验证结果一致性。
- **充分性与公平性**：
  - **优点**：样本量大（>10,000）、多模态影像、纵向设计、多种物质、稳健性检验充分。
  - **客观性**：采用FDR控制多重比较，统计报告完整。中介分析使用自助法，可靠性较高。
  - **局限**：仅使用基线脑影像，缺乏纵向脑变化；仅采用外化PRS单维度，未对比物质特异性PRS或其他遗传维度；未做外部验证数据集。

## 6. 论文的主要结论与发现
- **遗传效应显著**：较高extPRS与所有物质更早起始强烈相关：酒精HR=1.13，尼古丁HR=1.63，大麻HR=1.67，任何物质HR=1.15。
- **大量脑表型与extPRS关联**：基线识别出数千个与extPRS相关的IDPs，效应轮廓在不同规格中高度一致。
- **独立于遗传的脑预测因子**：许多IDPs在联合模型中独立于extPRS预测起始时间。大麻和尼古丁由感觉运动皮层浅层白质（SWM）微结构完整性（保护因素）和右半球区域不规则活动（风险因素）共同预测；酒精由左偏侧的额叶边缘SWM强度轴预测；尼古丁还涉及前扣带皮层和胼胝体下皮层的受限灰质扩散。
- **中介效应极小**：通过单个基线IDPs的间接效应非常小（ACME约10^-4），占extPRS总效应不到2%。仅酒精和任何物质起始的中介通过FDR显著性检验。
- **核心结论**：遗传（extPRS）与基线脑影像对青少年物质起始主要呈**平行加性贡献**，而非主导的“遗传→脑→行为”路径。基线脑特征反映了未被遗传维度捕获的神经生物学脆弱性。

## 7. 优点
- **多阶段分析框架清晰**：系统地将遗传关联、独立预测、中介路径分开，逻辑严密。
- **大样本高质量数据**：ABCD研究提供全国代表性、多模态、纵向数据，结果推广性较好。
- **多物质对照**：同时分析酒精、尼古丁、大麻及复合指标，揭示不同物质有共享和特异脑基序。
- **稳健性检验丰富**：多种协变量规格下重复分析，增强了结果可信度。
- **统计方法严谨**：FDR校正多重比较，自助法中介分析，避免过拟合。

## 8. 不足与局限
- **仅基线脑影像**：无法捕捉遗传对大脑发育动态轨迹的影响，纵向脑测量可能显示更强中介效应（作者也指出这一点）。
- **单一遗传维度**：仅使用外化PRS，未纳入物质特异性PRS（如尼古丁代谢相关PRS），可能低估遗传通过脑介导的路径。
- **中介分析限于单IDP**：未考虑多IDP联合中介或网络级中介，可能遗漏复合路径。
- **因果推断有限**：观察性设计，无法排除残留混杂（如家庭环境、同伴影响等），中介分析假设顺序可交换性可能不成立。
- **样本年龄限制**：ABCD参与者基线约9-10岁，早期起始定义可能受随访时间短影响，部分物质（如大麻）起始事件较少，统计效力较低。
- **种族/民族多样性**：虽包含多种族，但基因主成分校正后仍可能存在人群分层残余，且PRS在欧洲血统样本中预测力更高（论文未详细说明PRS构建来源）。

（完）
