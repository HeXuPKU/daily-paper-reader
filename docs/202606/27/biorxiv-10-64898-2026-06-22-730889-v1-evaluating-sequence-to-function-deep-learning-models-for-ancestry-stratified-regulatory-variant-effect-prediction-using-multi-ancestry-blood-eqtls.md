---
title: Evaluating sequence-to-function deep learning models for ancestry-stratified regulatory variant effect prediction using multi-ancestry blood eQTLs
title_zh: 利用多种族血液eQTL评估序列-功能深度学习模型在祖先分层调控变异效应预测中的表现
authors: "Sun, X., Mews, M., Wheeler, N. R., Benchek, P., Gu, T., Gomez, L., Mustafa, Y., Wang, L.-S., Leung, Y. Y., Schellenberg, G. D., Pericak-Vance, M. A., Haines, J. L., Griswold, A. J., Bush, W. S."
date: 2026-06-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.22.730889v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 跨血统调控变异效应预测的深度学习模型评估
tldr: "多祖先血液eQTL数据评估显示，Borzoi和AlphaGenome对名义eQTL效应预测能力弱，但能较好区分高置信度精细定位变异，非裔美国人高PIP变异集AUROC最高(>0.82)。结果支持S2F分数作为精细定位调控变异优先级证据，但非效应大小直接预测器，且表现受精细定位分辨率、LD和注释组成影响。"
source: biorxiv
selection_source: fresh_fetch
motivation: 序列-功能深度学习模型在多样化祖先人群中的调控变异预测一致性未经验证，需多祖先基准测试。
method: 利用MAGENTA队列全血eQTL数据（非裔、加勒比西班牙裔、非西班牙裔白人），比较Borzoi和AlphaGenome预测与名义及精细定位eQTL的关联。
result: 模型对名义eQTL相关性弱（rho≤0.138），对高PIP精细定位变异AUROC达0.82-0.84，非裔美国人集最高，但受比较集和MAF影响。
conclusion: S2F分数适合优先考虑精细定位调控变异，而非预测效应量，非裔高PIP变异区分度最佳归因于精细定位分辨率和LD特征。
---

## 摘要
背景：序列-功能（S2F）深度学习模型越来越多地被用于优先排序非编码调控变异，但它们在祖先多样性群体中的行为尚不清楚。由于训练数据和参考资源高度集中在欧洲人群，需要进行多种族基准测试，以确定S2F评分是否能在等位基因频率和LD模式不同的群体中一致地捕获调控效应。方法：我们使用来自MAGENTA队列的全血eQTL数据评估了Borzoi和AlphaGenome，其中包括非裔美国人（AA；N=224）、加勒比西班牙裔（CH；N=209）和非西班牙裔白人（NHW；N=235）参与者。模型预测与抽样的名义eQTL和祖先分层的SuSiE精细映射变异进行了基准比较，使用了Spearman相关性、方向一致性、模型间收敛性和距离匹配的AUROC，同时对次要等位基因频率和比较集定义进行了敏感性分析。我们还比较了不同祖先中高后验包含概率（PIP）变异的FILER功能注释重叠。结果：两个模型在不同祖先和TSS距离区间内与名义eQTL效应大小的弱一致性（ρ≤0.138），方向一致性仅略高于偶然水平。对于高置信度精细映射变异，一致性和区分度有所提高，并且Borzoi和AlphaGenome在精细映射变异上的模型间收敛性强于名义eQTL，这与富含序列模型效应更明显的调控变异一致。在PIP≥0.9的距离匹配AUROC分析中，使用PIP<0.01的变异作为低PIP比较变异，AA高PIP变异集在Borzoi（0.837 [95% CI: 0.790-0.870]）和AlphaGenome（0.820 [0.793-0.845]）中均产生最高的区分度。CH与NHW的排序因模型而异：Borzoi在NHW中的AUROC高于CH，而AlphaGenome产生的CH和NHW估计值几乎相同。当使用中等PIP变异作为比较变异时，AUROC值较低，但AA集仍保持最高的区分度。MAF分层的敏感性分析减弱了一些祖先对比，但没有消除AA更高的区分模式。功能注释分析显示，AA高PIP变异比NHW变异更常重叠染色质可及性和染色质接触注释，尽管与先前的eQTL和sQTL注释目录的重叠较低。结论：Borzoi和AlphaGenome与名义eQTL效应大小的一致性有限，但能更好地区分高置信度精细映射eQTL与低PIP变异。这些结果支持将S2F评分作为精细映射调控变异（尤其是启动子近端高PIP变异）的优先排序证据，而不是作为eQTL效应大小的独立预测因子。最强的区分度在AA高PIP变异集中观察到。总体而言，AA结果最好解释为高PIP变异与较低PIP比较变异之间的更强分离，这受到精细映射分辨率、LD、比较变异的选择和注释组成的影响。

## Abstract
Background: Sequence-to-function (S2F) deep learning models are increasingly used to prioritize non-coding regulatory variants, but their behavior across ancestrally diverse populations remains unclear. Because both training data and reference resources are heavily European-centered, multi-ancestry benchmarks are needed to determine whether S2F scores capture regulatory effects consistently across populations with different allele-frequency and LD patterns. Methods: We evaluated Borzoi and AlphaGenome using whole blood eQTL data from the MAGENTA cohort, including African American (AA; N=224), Caribbean Hispanic (CH; N=209), and Non-Hispanic White (NHW; N=235) participants. Model predictions were benchmarked against sampled nominal eQTLs and ancestry-stratified SuSiE fine-mapped variants using Spearman correlation, direction concordance, inter-model convergence, and distance-matched AUROC, with sensitivity analyses for minor allele frequency and comparison-set definition. We also compared FILER functional annotation overlap among high-Posterior Inclusion Probability (PIP) variants across ancestries. Results: Both models showed weak agreement with nominal eQTL effect sizes across ancestries and TSS-distance bins ({rho}[&le;]0.138), with direction concordance only marginally above chance. Agreement and discrimination improved for high-confidence fine-mapped variants, and Borzoi and AlphaGenome showed stronger inter-model convergence on fine-mapped variants than on nominal eQTLs, consistent with enrichment for regulatory variants whose effects are more apparent to sequence-based models. In distance-matched AUROC analyses at PIP [&ge;]0.9 using PIP <0.01 variants as low-PIP comparison variants, the AA high-PIP variant set yielded the highest discrimination for both Borzoi (0.837 [95% CI: 0.790-0.870]) and AlphaGenome (0.820 [0.793-0.845]). The CH-versus-NHW ordering was model-dependent: Borzoi yielded higher AUROC in NHW than CH, whereas AlphaGenome produced nearly identical CH and NHW estimates. AUROC values were lower when intermediate-PIP variants were used as comparison variants, but the AA set retained the highest discrimination. MAF-stratified sensitivity analyses attenuated some ancestry contrasts but did not eliminate the higher AA discrimination pattern. Functional annotation analysis showed that AA high-PIP variants more often overlapped chromatin accessibility and chromatin-contact annotations than NHW variants, despite lower overlap with prior eQTL and sQTL annotation catalogs. Conclusions: Borzoi and AlphaGenome showed limited agreement with nominal eQTL effect sizes, but better distinguished high-confidence fine-mapped eQTLs from low-PIP variants. These results support using S2F scores as prioritization evidence for fine-mapped regulatory variants, especially promoter-proximal high-PIP variants, rather than as standalone predictors of eQTL effect size. The strongest discrimination was observed for the AA high-PIP variant set. Overall, the AA result is best interpreted as stronger separation of high-PIP variants from lower-PIP comparison variants, shaped by fine-mapping resolution, LD, the choice of comparison variants, and annotation composition.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **研究动机**：序列-功能（S2F）深度学习模型（如 Borzoi、AlphaGenome）被广泛用于非编码调控变异的优先排序，但它们的训练数据和参考资源高度集中于欧洲人群，导致在祖先多样性群体中的预测行为尚不明确。
- **核心问题**：评估 S2F 模型在多祖先人群（非裔美国人、加勒比西班牙裔、非西班牙裔白人）中调控变异效应的预测一致性，验证其分数能否在不同等位基因频率和 LD 模式下可靠地捕获调控效应。

## 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：利用多种族全血 eQTL 数据作为真实基准，将两个 S2F 模型（Borzoi、AlphaGenome）的预测分数与 eQTL 关联统计量（名义效应大小、精细定位后验包含概率 PIP）进行系统比较。
- **关键技术细节**：
  - 对名义 eQTL 使用 Spearman 相关性、方向一致性（预测效应方向与观测效应方向的一致程度）以及模型间收敛性（两个模型预测之间的相关性）进行评估。
  - 对 SuSiE 精细映射变异，按 PIP 分层（高 PIP ≥ 0.9、低 PIP < 0.01、中等 PIP），采用**距离匹配的 AUROC**（匹配变异与 TSS 距离，消除距离偏差）衡量模型区分高置信度调控变异与低概率变异的能力。
  - 敏感性分析：按次要等位基因频率（MAF）分层，更换比较集（如使用中等 PIP 变异作为比较基准）。
  - 功能注释分析：比较不同祖先高 PIP 变异的 FILER 功能注释重叠情况（如染色质可及性、染色质接触、已知 eQTL/sQTL）。
- **流程**：数据获取 → 模型预测 → 统计检验（相关性、AUROC） → 敏感性分析 → 注释分析。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法
- **数据集**：MAGENTA 队列的全血 eQTL 数据，包含三个祖先群体：
  - 非裔美国人（AA，N=224）、加勒比西班牙裔（CH，N=209）、非西班牙裔白人（NHW，N=235）。
- **基准（benchmark）**：
  - 名义 eQTL 效应大小（通过抽样获取）。
  - 祖先层级的 SuSiE 精细定位变异（按 PIP 分档，其中高 PIP ≥ 0.9，低 PIP < 0.01）。
- **对比方法**：Borzoi 和 AlphaGenome 两个深度学习模型，比较它们的预测分数与真实 eQTL 关联的一致性。
- **场景**：
  - 不同祖先群体间比较。
  - 不同 TSS 距离区间的名义 eQTL。
  - 不同 MAF 分层。
  - 不同比较集定义（低 PIP vs 中等 PIP）。

## 4. 资源与算力
- 文中未提及所使用的 GPU 型号、数量、训练时长等算力信息。摘要内容主要聚焦于模型评估而非训练阶段，因此无法总结具体算力开销。

## 5. 实验数量与充分性
- **实验数量**：涵盖多个维度的比较，包括：
  - 名义 eQTL 的 Spearman 相关、方向一致性、模型间收敛性（跨祖先、跨 TSS 距离）。
  - 精细定位变异的多组 AUROC（不同祖先、不同 PIP 阈值、不同比较集、不同 MAF 分层）。
  - 功能注释重叠分析。
- **充分性**：实验设计较为系统，考虑了多种可能影响预测表现的因子（祖先、PIP、MAF、比较集定义），并进行了敏感性分析以验证结果的稳健性。但仅使用了全血 eQTL 单一组织类型，且样本量中等（每组约 200 人），可能影响统计功效和泛化性。整体而言，实验在给定条件下是充分且客观的，但未对比更多 S2F 模型（如 Enformer、DeepSEA）或多种组织。

## 6. 论文的主要结论与发现
- 两个模型与名义 eQTL 效应大小的相关性很弱（ρ ≤ 0.138），方向一致性仅略高于随机水平。
- 对于高置信度精细定位变异（PIP ≥ 0.9），模型的一致性和区分能力显著提高；Borzoi 和 AlphaGenome 在精细定位变异上的收敛性远强于名义 eQTL，符合序列模型更擅长捕获强调控信号的预期。
- 在距离匹配的 AUROC 分析中（高 PIP vs 低 PIP），AA 高 PIP 变异集获得最高区分度（Borzoi 0.837，AlphaGenome 0.820）；CH 与 NHW 的排名因模型而异（Borzoi NHW > CH，AlphaGenome 两者接近）。
- 当使用中等 PIP 变异作为比较集时，AUROC 下降，但 AA 依然最高。
- MAF 分层削弱了部分祖先对比，但 AA 更高的区分模式未完全消失。
- 功能注释显示：AA 高 PIP 变异更常重叠染色质可及性和染色质接触注释，但重叠已知 eQTL/sQTL 注释的比例低于 NHW。

## 7. 优点
- **种族多样性覆盖**：首次在多祖先群体（非裔、西班牙裔、白人）中系统评估 S2F 模型的调控变异预测能力，弥补了以往基准测试的欧洲中心缺陷。
- **精细定位的使用**：采用 SuSiE 精细映射变异而非仅名义 eQTL，更接近因果调控变异，提升了评估的可靠性。
- **多重敏感性分析**：考虑了 MAF、比较集定义、TSS 距离等因素，增强了结论的稳健性。
- **模型间收敛性对比**：同时比较两个模型，并分析其一致性程度，提供了模型机理的额外见解。
- **结论实用**：明确建议 S2F 分数适用于优先排序精细定位调控变异，而非预测效应量，为实际应用提供了清晰指导。

## 8. 不足与局限
- **组织类型单一**：仅基于全血 eQTL，无法推广至其他组织或细胞类型（如肝脏、大脑等）。
- **样本量中等**：每组约 200 人，可能限制精细定位分辨率，尤其对低频变异。
- **名义 eQTL 分析依赖抽样**：未使用全基因组所有显著 eQTL，可能引入采样偏差。
- **模型训练偏差**：Borzoi 和 AlphaGenome 的训练数据仍以欧洲人群为主，可能影响跨祖先预测公平性，但论文正是评估此问题，未试图纠正。
- **模型覆盖不全**：未纳入其他流行的 S2F 模型（如 Enformer、Sei、DeepSEA），对比不够全面。
- **缺乏独立验证队列**：所有分析均基于 MAGENTA 队列，未在外部独立数据集中验证。
- **算力信息缺失**：无法评估计算资源需求，对各实验室复现造成不便。
- **精细定位比较集的选择**：低 PIP 变异（<0.01）可能包含非调控变异，而中等 PIP 作为比较时 AUROC 下降，说明区分能力高度依赖于比较集定义，限制了结论的普适性。

（完）
