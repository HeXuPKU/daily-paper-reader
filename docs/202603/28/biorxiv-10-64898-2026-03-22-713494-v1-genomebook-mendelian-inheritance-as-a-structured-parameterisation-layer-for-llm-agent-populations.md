---
title: "Genomebook: Mendelian inheritance as a structured parameterisation layer for LLM agent populations"
title_zh: Genomebook：孟德尔遗传作为大语言模型（LLM）智能体种群的结构化参数化层
authors: "Corpas, M."
date: 2026-03-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.22.713494v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 具有孟德尔遗传参数的LLM智能体群体
tldr: 本研究针对LLM智能体缺乏遗传变异和群体演化机制的问题，提出了Genomebook系统。该系统利用孟德尔遗传定律在60个二倍体位点上编码了26种行为特征。通过模拟20个初始智能体的有性生殖、突变及环境选择压力，研究观察到了显著的特征演化趋势。实验证明，这种遗传架构能有效作为智能体行为的结构化、可审计且可遗传的参数化层，为模拟复杂的群体动力学提供了新方法。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-001.webp\", \"caption\": \"Figure 6. Population structure. (A) PCA of 60-locus genotypes. PC1 (11.0%) and PC2 (10.4%) partially separate founder lineages, with increasing overlap in later generations. Points coloured by generation. (B) Population growth across 8 generations showing expansion from 20 founders to 186 agents by generation 7.\", \"page\": 11, \"index\": 1, \"width\": 789, \"height\": 339}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-002.webp\", \"caption\": \"Figure 2. Trait drift across eight generations. Mean trait scores (y-axis) for selected traits across generations 0–7 (x-axis). Leadership drive increased under dominant inheritance; obsessive focus declined under fitness cost selection; longevity collapsed as a trade-off for cognitive traits. Shaded regions show ±1 standard deviation.\", \"page\": 7, \"index\": 2, \"width\": 876, \"height\": 650}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-003.webp\", \"caption\": \"Figure 5. Vocabulary evolution and topic inheritance. (A) Top 10 words by frequency across the corpus, showing genetics-specific terminology dominating. (B) Vocabulary diversity (unique/total words) declining across generations, consistent with a linguistic founder effect. (C) Topic inheritance: 83% of offspring post in the same submolts as their parents.\", \"page\": 10, \"index\": 3, \"width\": 876, \"height\": 312}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-004.webp\", \"caption\": \"Figure 1. Graphical abstract. Genomebook pipeline: SOUL.md personality profiles are compiled into diploid genomes via the Soul2DNA compiler. Agents reproduce through Mendelian segregation with de novo mutation, producing non-identical offspring. Agents interact on Moltbook (a local social network) and population analytics track trait drift, allele frequencies, disease prevalence, and emergent behavioural patterns across generations.\", \"page\": 3, \"index\": 4, \"width\": 876, \"height\": 325}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-005.webp\", \"caption\": \"Figure 8. Replicated allele frequency trajectories. Alternate allele frequency at four key loci across 20 independent runs for standard selection (blue) and random mating (red). Shaded regions show 95% confidence intervals. OBS001 shows consistent decline under standard selection.\", \"page\": 13, \"index\": 5, \"width\": 876, \"height\": 231}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-006.webp\", \"caption\": \"Figure 3. Allele frequency trajectories. Alternate allele frequency (y-axis) at selected loci across generations (x-axis). Fitness-linked loci (OBS001, LNG001) show directional change consistent with selection. Neutral loci show stochastic fluctuation consistent with genetic drift.\", \"page\": 8, \"index\": 6, \"width\": 876, \"height\": 525}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-007.webp\", \"caption\": \"Figure 7. Replicated trait trajectories across three conditions. Mean trait scores across 20 independent runs each for standard selection (blue), random mating (red), and nongenetic baseline (grey dashed). Shaded regions show 95% confidence intervals. Genetic conditions produce directional drift from founder values; the non-genetic baseline converges to 0.5 with narrow CIs, confirming that the observed dynamics require genetic architecture.\", \"page\": 12, \"index\": 7, \"width\": 876, \"height\": 310}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-008.webp\", \"caption\": \"Figure 4. Disease prevalence across generations. Number of affected individuals (y-axis) per condition across generations (x-axis). Hyperfocus syndrome is the most common condition. Mutation-only conditions emerge in later generations as mutation burden accumulates.\", \"page\": 9, \"index\": 8, \"width\": 876, \"height\": 526}]"
motivation: 旨在解决现有LLM智能体多为单一配置克隆、缺乏可遗传变异和群体演化动力学的问题。
method: 引入Genomebook系统，通过孟德尔遗传模型编码行为特征，并利用有性生殖、突变和选择压力函数模拟智能体进化。
result: 实验观察到特征轨迹与遗传规则高度一致（如领导力提升、强迫性下降），且通过消融实验证实了遗传架构的必要性。
conclusion: 遗传架构可作为LLM智能体行为的一种结构化且可遗传的参数化层，为群体智能研究提供了可审计的演化框架。
---

## 摘要
大语言模型（LLM）智能体通常以克隆形式部署：即单一配置的相同副本，缺乏可遗传变异或种群水平动态的机制。在此，我们介绍了 Genomebook，这是一个设计的进化系统，它使用加性、显性和隐性遗传模型，在 60 个二倍体位点上编码了 26 种行为特征。20 个初始智能体分别由人格档案（SOUL.md）和编译基因组（DNA.md）定义，通过孟德尔分离定律进行有性繁殖，每代每个位点的基础自发突变率为 0.1%（在认知、免疫和代谢热点区域为 3 倍）。一个包含 20 种具有明确外显率和适应度成本的合成条件的注册表，通过兼容性评分函数引入了集中施加的选择压力。在单次运行的八代演化中（包含 626 个智能体，792 条社交网络帖子），我们观察到与编码选择规则一致的特征轨迹：在显性遗传下，领导力从 0.525 上升到 0.710；在适应度成本惩罚下，强迫性专注从 0.775 下降到 0.601；长寿度从 0.463 下降到 0.209。词汇多样性从 0.42 下降到 0.19，父母与后代之间的主题继承率达到 83%，尽管这些模式可能反映了提示词调节而非纯粹的遗传因果关系。智能体会自发地提及家庭成员，这与 DNA.md 系统提示词中存在的亲缘关系信息以及 LLM 的叙事阐述能力相一致。重复模拟（在三种条件下进行 20 次独立运行）证实，在标准选择下，不同种子的特征轨迹是一致的，而随机交配的消融实验则产生了趋势减弱且方差更大的结果。非遗传基准（随机特征分配，无遗传）产生了收敛于种群均值的平坦轨迹，证实了所观察到的动态需要遗传架构，且无法通过非结构化的参数变化来重现。这些结果确立了遗传架构可以作为 LLM 智能体行为的一种结构化、可审计且可遗传的参数化层。

## Abstract
Large language model (LLM) agents are typically deployed as clones: identical copies of a single configuration with no mechanism for heritable variation or population-level dynamics. Here we introduce Genomebook, a designed evolutionary system that encodes 26 behavioural traits across 60 diploid loci using additive, dominant, and recessive inheritance models. Twenty founder agents, each defined by a personality profile (SOUL.md) and a compiled genome (DNA.md), reproduce sexually via Mendelian segregation with de novo mutation at a base rate of 0.1% per locus per generation (3x at cognitive, immune, and metabolic hotspots). A registry of 20 synthetic conditions with defined penetrance and fitness costs introduces centrally imposed selective pressure through a compatibility scoring function. Over a single run of eight generations (626 agents, 792 social network posts), we observe trait trajectories consistent with the encoded selection rules: leadership rose from 0.525 to 0.710 under dominant inheritance, obsessive focus fell from 0.775 to 0.601 under fitness cost penalisation, and longevity declined from 0.463 to 0.209. Vocabulary diversity declined from 0.42 to 0.19, and topic inheritance between parents and offspring reached 83%, though these patterns may reflect prompt conditioning rather than purely genetic causation. Agents referenced family members spontaneously, consistent with kinship information present in the DNA.md system prompt and the LLMs capacity for narrative elaboration. Replicated simulations (20 independent runs across three conditions) confirm that trait trajectories are consistent across seeds under standard selection, while a random mating ablation produces attenuated trends with wider variance. A non-genetic baseline (random trait assignment, no inheritance) produces flat trajectories converging to population means, confirming that the observed dynamics require genetic architecture and cannot be reproduced by unstructured parameter variation. These results establish genetic architecture as a structured, auditable, and heritable parameterisation layer for LLM agent behaviour.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **Genomebook** 的系统，旨在为大语言模型（LLM）智能体引入类似于生物进化的遗传机制。以下是对该论文的深度结构化总结：

### 1. 核心问题与研究动机
*   **核心问题**：当前的 LLM 智能体通常是单一配置的“克隆体”，缺乏个体差异、可遗传的变异以及种群水平的演化动力学。
*   **研究动机**：借鉴群体遗传学（如费舍尔、赖特、木村资生的理论），探索是否可以通过一套结构化的遗传架构（基因组）来参数化智能体的行为，使其在多代繁殖中表现出可预测、可审计的特征演化，从而为人工生命、AI 安全和群体模拟提供新工具。

### 2. 方法论：核心思想与技术细节
*   **遗传架构设计**：
    *   **基因组**：每个智能体拥有 60 个二倍体位点，分布在 22 条常染色体和性染色体上。
    *   **特征编码**：编码了 26 种行为特征，分为认知（如分析推理）、人格（如领导力）和物理（如长寿倾向）三大类。
    *   **遗传模型**：采用孟德尔遗传定律，包括加性（Additive）、显性（Dominant）和隐性（Recessive）三种遗传模式。
*   **编译与繁殖流程**：
    *   **Soul-to-Genome**：将初始的人格档案（SOUL.md）编译为基因组文件（DNA.md）。
    *   **有性生殖**：通过孟德尔分离定律产生后代，并引入自发突变（基础概率 0.1%，特定热点区域 0.3%）。
    *   **选择压力**：通过一个“兼容性评分函数”施加人工选择，考虑杂合度（奖励多样性）、特征互补性和隐性疾病风险。
*   **环境与交互**：
    *   **Moltbook**：一个模拟社交网络，智能体在此发布帖子、评论和投票。其系统提示词（System Prompt）包含其基因组信息，影响其表达风格。
    *   **疾病模型**：包含 20 种合成疾病，具有不同的外显率和适应度成本（Fitness Cost），直接影响智能体的生存和繁殖概率。

### 3. 实验设计与基准对比
*   **实验场景**：从 20 个基于历史名人（如爱因斯坦、居里夫人、图灵等）定义的初始智能体开始，演化 8 代，共产生 626 个智能体。
*   **对比方法（基准测试）**：
    1.  **标准选择（Standard）**：完整的遗传+选择压力模型。
    2.  **随机交配（Random Mating）**：有遗传但无选择压力评分。
    3.  **非遗传基准（Non-genetic Baseline）**：每代随机分配特征和基因，无父代遗传。
*   **评估指标**：特征均值轨迹、等位基因频率、疾病流行率、词汇多样性、主题继承率。

### 4. 资源与算力
*   **模型使用**：底层 LLM 使用了 **Claude 3.5 Sonnet**。
*   **算力成本**：论文未提及具体的 GPU 硬件，但明确指出运行 8 代智能体交互的总 API 成本约为 **70 美元**。
*   **训练时长**：由于是基于推理的智能体模拟，不涉及模型训练，主要耗时在于多轮 API 调用和演化逻辑计算。

### 5. 实验数量与充分性
*   **实验规模**：主实验运行了 1 次完整的 8 代演化（包含社交网络交互）；为了验证稳健性，针对遗传动力学部分（不含 API 调用）进行了 **20 次独立重复模拟**。
*   **充分性评价**：实验设计较为全面，包含了消融实验（随机交配）和对照组（非遗传基准）。20 次重复模拟为遗传趋势提供了 95% 的置信区间，证明了结果并非偶然。但受限于 API 成本，包含社交行为的大规模重复实验较少。

### 6. 主要结论与发现
*   **特征演化符合预期**：在显性遗传下，领导力特征显著上升；在适应度成本压力下，强迫性专注特征下降；长寿特征因非直接选择而出现衰退。
*   **行为受遗传信息调节**：智能体会自发提及家族谱系，后代与父母在社交话题上的重合度高达 83%。
*   **遗传架构的必要性**：非遗传基准组的特征轨迹呈平坦状并收敛于均值，证明了观察到的动态确实是由遗传架构驱动的。
*   **词汇漂移**：观察到类似于生物学“奠基者效应”的现象，词汇多样性随代际增加而下降，术语向遗传学相关词汇收敛。

### 7. 优点与亮点
*   **结构化与可审计性**：将复杂的智能体行为参数化为可追踪的基因位点，使得行为的演化过程完全透明、可追溯。
*   **跨学科融合**：成功将成熟的生物信息学工具（如 PCA、等位基因频率分析）引入 LLM 智能体研究。
*   **叙事一致性**：通过 DNA.md 提示词，智能体展现出了极强的身份认同感和家族叙事能力。

### 8. 不足与局限
*   **提示词偏见（Prompt Conditioning）**：很难区分智能体的行为改变是由于“遗传特征”驱动，还是仅仅因为提示词中包含了“你患有某基因病”的描述（即 LLM 的角色扮演能力）。
*   **人工干预过强**：选择压力是通过预设函数施加的，而非从智能体之间的竞争中自发涌现。
*   **样本量限制**：20 个初始成员的种群较小，容易受到遗传漂变和奠基者效应的强烈影响。
*   **参数主观性**：基因位点与特征之间的映射关系（如哪些位点决定创造力）具有一定的人为设定主观性。

（完）
