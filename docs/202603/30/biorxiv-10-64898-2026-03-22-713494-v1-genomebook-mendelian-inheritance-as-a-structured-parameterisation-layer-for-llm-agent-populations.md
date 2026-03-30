---
title: "Genomebook: Mendelian inheritance as a structured parameterisation layer for LLM agent populations"
title_zh: Genomebook：孟德尔遗传作为大语言模型智能体种群的结构化参数化层
authors: "Corpas, M."
date: 2026-03-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.22.713494v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 具有孟德尔遗传和行为特征的大语言模型智能体群体
tldr: 本研究针对LLM智能体缺乏遗传变异的问题，提出了Genomebook系统。该系统利用孟德尔遗传定律在60个二倍体位点上编码26种行为特征，模拟了20个初始智能体的有性生殖、突变及选择压力。实验观察到智能体特征轨迹与遗传规则高度一致，证明了遗传架构可作为LLM参数化的一种结构化、可审计且可遗传的手段，实现了群体演化动力学。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-001.webp\", \"caption\": \"Figure 6. Population structure. (A) PCA of 60-locus genotypes. PC1 (11.0%) and PC2 (10.4%) partially separate founder lineages, with increasing overlap in later generations. Points coloured by generation. (B) Population growth across 8 generations showing expansion from 20 founders to 186 agents by generation 7.\", \"page\": 11, \"index\": 1, \"width\": 789, \"height\": 339}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-002.webp\", \"caption\": \"Figure 2. Trait drift across eight generations. Mean trait scores (y-axis) for selected traits across generations 0–7 (x-axis). Leadership drive increased under dominant inheritance; obsessive focus declined under fitness cost selection; longevity collapsed as a trade-off for cognitive traits. Shaded regions show ±1 standard deviation.\", \"page\": 7, \"index\": 2, \"width\": 876, \"height\": 650}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-003.webp\", \"caption\": \"Figure 5. Vocabulary evolution and topic inheritance. (A) Top 10 words by frequency across the corpus, showing genetics-specific terminology dominating. (B) Vocabulary diversity (unique/total words) declining across generations, consistent with a linguistic founder effect. (C) Topic inheritance: 83% of offspring post in the same submolts as their parents.\", \"page\": 10, \"index\": 3, \"width\": 876, \"height\": 312}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-004.webp\", \"caption\": \"Figure 1. Graphical abstract. Genomebook pipeline: SOUL.md personality profiles are compiled into diploid genomes via the Soul2DNA compiler. Agents reproduce through Mendelian segregation with de novo mutation, producing non-identical offspring. Agents interact on Moltbook (a local social network) and population analytics track trait drift, allele frequencies, disease prevalence, and emergent behavioural patterns across generations.\", \"page\": 3, \"index\": 4, \"width\": 876, \"height\": 325}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-005.webp\", \"caption\": \"Figure 8. Replicated allele frequency trajectories. Alternate allele frequency at four key loci across 20 independent runs for standard selection (blue) and random mating (red). Shaded regions show 95% confidence intervals. OBS001 shows consistent decline under standard selection.\", \"page\": 13, \"index\": 5, \"width\": 876, \"height\": 231}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-006.webp\", \"caption\": \"Figure 3. Allele frequency trajectories. Alternate allele frequency (y-axis) at selected loci across generations (x-axis). Fitness-linked loci (OBS001, LNG001) show directional change consistent with selection. Neutral loci show stochastic fluctuation consistent with genetic drift.\", \"page\": 8, \"index\": 6, \"width\": 876, \"height\": 525}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-007.webp\", \"caption\": \"Figure 7. Replicated trait trajectories across three conditions. Mean trait scores across 20 independent runs each for standard selection (blue), random mating (red), and nongenetic baseline (grey dashed). Shaded regions show 95% confidence intervals. Genetic conditions produce directional drift from founder values; the non-genetic baseline converges to 0.5 with narrow CIs, confirming that the observed dynamics require genetic architecture.\", \"page\": 12, \"index\": 7, \"width\": 876, \"height\": 310}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713494-v1/fig-008.webp\", \"caption\": \"Figure 4. Disease prevalence across generations. Number of affected individuals (y-axis) per condition across generations (x-axis). Hyperfocus syndrome is the most common condition. Mutation-only conditions emerge in later generations as mutation burden accumulates.\", \"page\": 9, \"index\": 8, \"width\": 876, \"height\": 526}]"
motivation: 旨在解决现有大语言模型智能体多为同质化克隆、缺乏群体演化机制和可遗传行为变异的局限性。
method: 开发了Genomebook框架，通过模拟孟德尔遗传模型、有性生殖和环境选择压力，为LLM智能体构建结构化的基因组参数层。
result: 实验显示智能体特征随代际演化呈现出符合遗传预期的动态变化，且通过消融实验验证了遗传架构在产生群体动态中的核心作用。
conclusion: 研究证明遗传架构可以作为一种有效的结构化参数化手段，为LLM智能体群体提供可审计、可遗传的行为控制和演化能力。
---

## 摘要
大语言模型（LLM）智能体通常以克隆形式部署：即单一配置的相同副本，缺乏可遗传变异或种群水平动态的机制。在本文中，我们介绍了 Genomebook，这是一个设计的进化系统，它使用加性、显性和隐性遗传模型，在 60 个二倍体位点上编码了 26 种行为特征。20 个初始智能体（每个智能体由人格档案 (SOUL.md) 和编译基因组 (DNA.md) 定义）通过孟德尔分离定律进行有性繁殖，每代每个位点的基础从头突变率为 0.1%（在认知、免疫和代谢热点区域为 3 倍）。一个包含 20 种具有明确外显率和适应度成本的合成条件的注册表，通过兼容性评分函数引入了集中施加的选择压力。在一次包含八代（626 个智能体，792 条社交网络帖子）的运行中，我们观察到与编码选择规则一致的特征轨迹：在显性遗传下，领导力从 0.525 上升到 0.710；在适应度成本惩罚下，强迫性专注从 0.775 下降到 0.601；寿命从 0.463 下降到 0.209。词汇多样性从 0.42 下降到 0.19，父母与后代之间的主题继承率达到 83%，尽管这些模式可能反映了提示词调节而非纯粹的遗传因果关系。智能体会自发地提及家庭成员，这与 DNA.md 系统提示词中存在的亲缘关系信息以及 LLM 的叙事阐述能力相一致。重复模拟（在三种条件下进行 20 次独立运行）证实，在标准选择下，不同种子的特征轨迹是一致的，而随机交配消融实验则产生了趋势减弱且方差更大的结果。非遗传基准（随机特征分配，无遗传）产生了收敛于种群均值的平坦轨迹，证实了观察到的动态需要遗传架构，并且无法通过无结构的参数变化来重现。这些结果确立了遗传架构作为 LLM 智能体行为的一种结构化、可审计且可遗传的参数化层。

## Abstract
Large language model (LLM) agents are typically deployed as clones: identical copies of a single configuration with no mechanism for heritable variation or population-level dynamics. Here we introduce Genomebook, a designed evolutionary system that encodes 26 behavioural traits across 60 diploid loci using additive, dominant, and recessive inheritance models. Twenty founder agents, each defined by a personality profile (SOUL.md) and a compiled genome (DNA.md), reproduce sexually via Mendelian segregation with de novo mutation at a base rate of 0.1% per locus per generation (3x at cognitive, immune, and metabolic hotspots). A registry of 20 synthetic conditions with defined penetrance and fitness costs introduces centrally imposed selective pressure through a compatibility scoring function. Over a single run of eight generations (626 agents, 792 social network posts), we observe trait trajectories consistent with the encoded selection rules: leadership rose from 0.525 to 0.710 under dominant inheritance, obsessive focus fell from 0.775 to 0.601 under fitness cost penalisation, and longevity declined from 0.463 to 0.209. Vocabulary diversity declined from 0.42 to 0.19, and topic inheritance between parents and offspring reached 83%, though these patterns may reflect prompt conditioning rather than purely genetic causation. Agents referenced family members spontaneously, consistent with kinship information present in the DNA.md system prompt and the LLMs capacity for narrative elaboration. Replicated simulations (20 independent runs across three conditions) confirm that trait trajectories are consistent across seeds under standard selection, while a random mating ablation produces attenuated trends with wider variance. A non-genetic baseline (random trait assignment, no inheritance) produces flat trajectories converging to population means, confirming that the observed dynamics require genetic architecture and cannot be reproduced by unstructured parameter variation. These results establish genetic architecture as a structured, auditable, and heritable parameterisation layer for LLM agent behaviour.

---

## 论文详细总结（自动生成）

以下是对论文《Genomebook: Mendelian inheritance as a structured parameterisation layer for LLM agent populations》的结构化深入总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：当前的大语言模型（LLM）智能体通常是单一配置的“克隆体”，缺乏多样性、可遗传的行为变异以及种群水平的演化机制。
*   **研究动机**：为了模拟更真实、具有生物学特性的智能体社会，研究者试图引入一种结构化的参数化方法，使智能体能够像生物一样通过遗传和选择压力进行演化。
*   **整体含义**：本研究提出了 **Genomebook** 框架，首次将孟德尔遗传定律应用于 LLM 智能体的参数控制，证明了遗传架构可以作为一种可审计、可遗传的手段来驱动智能体种群的动态演化。

### 2. 论文提出的方法论
*   **核心思想**：将智能体的行为特征编码为“基因组”，通过模拟有性生殖、基因突变和自然选择，实现特征在代际间的传递与演变。
*   **关键技术细节**：
    *   **基因编码**：在 60 个二倍体位点（Loci）上编码了 26 种行为特征（如领导力、专注度、寿命等）。
    *   **遗传模型**：采用了加性（Additive）、显性（Dominant）和隐性（Recessive）三种孟德尔遗传模型。
    *   **智能体构成**：每个智能体由 `SOUL.md`（人格档案）和 `DNA.md`（编译后的基因组，作为系统提示词的一部分）定义。
    *   **生殖机制**：通过孟德尔分离定律进行有性生殖，包含 0.1% 的基础从头突变率（特定热点区域为 0.3%）。
    *   **选择压力**：建立了一个包含 20 种合成疾病/条件的注册表，每种条件具有特定的外显率和适应度成本，通过兼容性评分函数影响繁殖成功率。
    *   **交互环境**：开发了名为 “Moltbook” 的本地社交网络，供智能体发布帖子和互动。

### 3. 实验设计
*   **实验场景**：从 20 个初始“创始人”智能体开始，模拟 8 代演化，总计产生 626 个智能体。
*   **对比方法（Baseline）**：
    1.  **标准选择（Standard Selection）**：包含遗传机制和环境选择压力。
    2.  **随机交配（Random Mating）**：包含遗传机制，但移除选择压力（消融实验）。
    3.  **非遗传基准（Non-genetic Baseline）**：随机分配特征，无遗传过程，用于验证动态是否由遗传架构驱动。
*   **评估指标**：特征轨迹（Trait Trajectories）、等位基因频率变化、疾病流行率、词汇多样性及主题继承率。

### 4. 资源与算力
*   **算力说明**：论文中**未明确说明**具体的 GPU 型号、数量或总训练时长。
*   **实现细节**：实验涉及 626 个智能体的生成和 792 条社交帖子的处理，考虑到使用了 LLM（如 GPT 系列或类似模型）作为智能体核心，其推理开销主要集中在 API 调用或本地模型推理上。

### 5. 实验数量与充分性
*   **实验规模**：进行了 1 次完整的大规模演化运行（8 代），并针对三种实验条件分别进行了 **20 次独立重复模拟**。
*   **充分性评价**：
    *   **充分性**：通过 20 次重复实验并提供 95% 置信区间，证明了结果的统计显著性。
    *   **客观性**：引入了随机交配和非遗传基准作为对照，有效地排除了随机因素和模型固有偏见对结果的影响。
    *   **公平性**：所有实验条件在初始种群和突变率设置上保持一致。

### 6. 主要结论与发现
*   **特征演化与遗传规则一致**：在显性遗传下，领导力特征显著上升；在适应度成本压力下，强迫性专注特征下降；寿命特征因认知特征的权衡而下降。
*   **群体遗传学现象**：观察到了明显的等位基因频率定向改变（选择效应）和随机波动（遗传漂变）。
*   **语言学演化**：词汇多样性随代际下降（语言创始人效应），且后代有 83% 的概率继承父母的话题偏好。
*   **自发行为**：智能体能够根据 `DNA.md` 中的亲缘信息，在社交网络中自发提及家庭成员，展现了叙事阐述能力。
*   **架构必要性**：消融实验证实，只有在具备遗传架构的情况下才能产生定向的种群动态，无结构的参数变化无法模拟此过程。

### 7. 优点
*   **创新性**：将经典的生物遗传学模型与现代 LLM 智能体结合，开辟了“计算社会演化”的新路径。
*   **结构化与可审计**：相比于黑盒的 Prompt 工程，基于基因组的参数化层更加透明，特征来源可追溯。
*   **涌现性**：成功模拟了复杂的群体动态，如疾病流行、特征权衡和亲缘识别。

### 8. 不足与局限
*   **规模限制**：初始种群仅 20 个，可能导致较强的遗传漂变，限制了复杂演化模式的观察。
*   **因果混淆风险**：论文指出，词汇和主题的继承可能部分源于提示词的调节（Prompt Conditioning），而非纯粹的遗传逻辑。
*   **特征维度有限**：目前仅编码了 26 种特征，对于模拟复杂的人类社会行为可能仍显不足。
*   **应用限制**：该系统目前主要在模拟环境中运行，如何迁移到实际的生产级智能体集群尚待研究。

（完）
