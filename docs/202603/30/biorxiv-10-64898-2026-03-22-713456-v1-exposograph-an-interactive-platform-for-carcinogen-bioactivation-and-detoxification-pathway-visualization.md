---
title: "ExposoGraph: An Interactive Platform for Carcinogen Bioactivation and Detoxification Pathway Visualization"
title_zh: ExposoGraph：致癌物生物活化与解毒途径可视化的交互式平台
authors: "Pienta, K., Kazi, J. U."
date: 2026-03-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.22.713456v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 用于评估癌症风险评估中基因-环境相互作用的平台
tldr: ExposoGraph是一个交互式致癌物代谢知识图谱平台，旨在填补致癌暴露、代谢激活/解毒、DNA损伤与遗传注释之间缺乏统一可视化框架的空白。该研究整合了IARC、KEGG等多个权威数据库，构建了包含96个节点和102条关系的知识图谱，涵盖15种主要致癌物及其代谢路径。该平台支持多维度过滤与搜索，为研究基因-环境相互作用及个体化癌症风险评估提供了重要的科研工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713456-v1/fig-001.webp\", \"caption\": \"Figure 4. Example Androgen pathway visualization using ExposoGraph Viewer (D3). Only Androgen carcinogen class is visualized.\", \"page\": 8, \"index\": 1, \"width\": 1126, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713456-v1/fig-002.webp\", \"caption\": \"Figure 2. Example pathway visualization using ExposoGraph Viewer (D3). All carcinogen classes are visualized in this example graph.\", \"page\": 6, \"index\": 2, \"width\": 1126, \"height\": 598}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713456-v1/fig-003.webp\", \"caption\": \"Figure 5. Pharmacogenomic risk-scoring foundation in ExposoGraph. In the current reference graph (96 nodes, 102 edges), 13 scored enzymes span 8 carcinogen classes. Left, horizontal bars summarize the current class-level reservoir of scored activation and detoxification support within each graph-defined carcinogen class. Positive red bars indicate summed representative activity scores for activation enzymes, whereas negative green bars indicate summed representative activity scores for detoxification enzymes; mixed-function (M) and repair (R) contributions are shown as text annotations where present. Right, each point represents a scored enzyme positioned by representative activity score on the x-axis and topologyaware gene impact score on the y-axis, where the impact score reflects downstream adduct-forming and repair reachability in the graph. Point color denotes role bucket (activation, detoxification, mixed, or repair), and bubble size reflects how many carcinogen classes each scored gene touches. This figure summarizes current structural support for pharmacogenomic interpretation in ExposoGraph and should be interpreted as a foundation for future composite risk modeling rather than a patient-level automated risk classifier.\", \"page\": 9, \"index\": 3, \"width\": 1126, \"height\": 642}]"
motivation: 现有的致癌暴露与药理基因组资源缺乏统一的交互式可视化框架，限制了对基因-环境相互作用的系统性评估。
method: 开发了名为ExposoGraph的知识图谱平台，整合了来自IARC、KEGG、PharmVar等数据库的致癌物代谢、DNA损伤及遗传注释数据。
result: 第一代参考图谱涵盖了9类致癌物、36种关键酶及其代谢路径，并实现了支持多维度过滤和详细元数据查看的交互式功能。
conclusion: ExposoGraph为连接致癌暴露、代谢归宿与遗传调节因子提供了集成框架，有助于基因-环境相互作用的研究和假设生成。
---

## 摘要
背景：尽管国际癌症研究机构 (IARC) 对致癌暴露进行了广泛编目，且 PharmVar 和 CPIC 等资源对药物基因组变异进行了记录，但很少有平台能在单一交互式可视化框架内统一暴露、代谢活化与解毒、DNA 损伤以及遗传注释。这一空白限制了癌症风险评估中对基因-环境相互作用的系统评价。方法：我们开发了致癌基因组知识图谱 ExposoGraph，这是一个用于致癌物代谢和 DNA 损伤途径的交互式知识图谱平台。参考图谱整合了来自 IARC、KEGG、PharmVar、CPIC、CTD 以及支持性文献/资源的精选数据和注释。目前的参考图谱包含跨越 5 种实体类型（致癌物、酶、代谢物、DNA 加合物和途径）的 96 个节点，以及跨越 6 种关系类型（活化、解毒、转运、形成加合物、修复和途径）的 102 条边。结果：第一代参考图谱涵盖了 9 类致癌物的代谢活化和解毒途径，涉及 15 种索引致癌物。它代表了 36 种酶，包括 I 相活化 (n=14)、II 相结合与解毒 (n=14)、III 相转运 (n=3) 和 DNA 修复 (n=5)。交互式探索支持致癌物类别过滤、节点和边类型过滤、基于元数据的搜索，以及带有来源和药物基因组注释的详细悬停/详情视图。雄激素分支通过 CYP19A1 介导的芳香化作用和下游儿茶酚雌激素化学过程，将雄激素代谢与雌激素醌形成及 DNA 加合物生成联系起来，突显了跨途径的连通性。在可选的以雄激素为重点的扩展中，额外的受体、组织和变异背景进一步将该分支与雄激素受体信号传导和基因型特异性注释联系起来。结论：ExposoGraph 提供了一个将致癌暴露与代谢归宿及遗传调节因子联系起来的第一代集成交互式框架。该平台支持基因-环境相互作用研究的假设生成，并可能为未来的个体化风险建模提供信息，同时它仍是一个研究用途的框架，而非经过临床验证的风险评估工具。

## Abstract
BackgroundDespite extensive cataloging of carcinogenic exposures by the International Agency for Research on Cancer (IARC) and pharmacogenomic variation by resources such as PharmVar and CPIC, few platforms unify exposure, metabolic activation and detoxification, DNA damage, and genetic annotation within a single interactive visualization framework. This gap limits systematic evaluation of gene-environment interactions in cancer risk assessment.

MethodsWe developed the Carcino-Genomic Knowledge Graph, ExposoGraph, an interactive knowledge-graph platform for carcinogen metabolism and DNA damage pathways. The reference graph integrates curated data and annotations from IARC, KEGG, PharmVar, CPIC, CTD, and supporting literature/resources. The current reference graph contains 96 nodes across 5 entity types (Carcinogens, Enzymes, Metabolites, DNA Adducts, and Pathways) and 102 edges across 6 relationship types (activates, detoxifies, transports, forms adduct, repairs, and pathway).

ResultsThe first-generation reference graph captures metabolic activation and detoxification pathways for 9 carcinogen classes spanning 15 index carcinogens. It represents 36 enzymes across Phase I activation (n=14), Phase II conjugation and detoxification (n=14), Phase III transport (n=3), and DNA repair (n=5). Interactive exploration supports carcinogen-class filtering, node- and edge-type filtering, metadata-based search, and detailed hover/detail views with provenance and pharmacogenomic annotations. The androgen branch highlights cross-pathway connectivity by linking androgen metabolism to estrogen quinone formation and DNA adduct generation through CYP19A1-mediated aromatization and downstream catechol estrogen chemistry. In the optional androgen-focused extension, additional receptor, tissue, and variant context further connects this branch to androgen receptor signaling and genotype-specific annotations.

ConclusionsExposoGraph provides a first-generation integrated, interactive framework linking carcinogenic exposures to metabolic fates and genetic modulators. The platform supports hypothesis generation for gene-environment interaction studies and may inform future individualized risk modeling, while remaining a research-use framework rather than a clinically validated risk-assessment tool.

---

## 论文详细总结（自动生成）

### ExposoGraph：致癌物生物活化与解毒途径可视化的交互式平台

#### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：尽管国际癌症研究机构（IARC）对致癌物有详尽分类，且 PharmVar 和 CPIC 等数据库记录了丰富的药物基因组变异，但目前缺乏一个统一的、交互式的可视化框架，能够将**环境暴露、代谢活化/解毒过程、DNA 损伤以及遗传注释**整合在一起。
*   **研究背景**：这种信息的碎片化限制了研究人员系统评估“基因-环境相互作用”（GxE）对癌症风险影响的能力。ExposoGraph 的开发旨在填补这一空白，为致癌物的代谢归宿提供一个结构化的知识图谱。

#### 2. 方法论：核心思想与技术细节
*   **核心思想**：构建一个名为 ExposoGraph 的致癌基因组知识图谱（Carcino-Genomic Knowledge Graph），通过整合多源异构数据，实现从致癌物暴露到达标靶 DNA 损伤的全路径可视化。
*   **关键技术细节**：
    *   **数据整合**：从 IARC（致癌物分类）、KEGG（代谢途径）、PharmVar/CPIC（遗传变异与药效）、CTD（化学物质-基因相互作用）及相关文献中提取精选数据。
    *   **图谱结构**：包含 5 种实体类型（致癌物、酶、代谢物、DNA 加合物、途径）和 6 种关系类型（活化、解毒、转运、形成加合物、修复、属于途径）。
    *   **交互功能**：利用 D3.js 开发可视化界面，支持按致癌物类别过滤、节点/边类型过滤、元数据搜索，以及显示来源和药物基因组注释的悬停详情视图。
    *   **风险评分框架**：引入了初步的药理基因组风险评分基础，结合酶的活性分数（Activity Score）和拓扑感知的基因影响分数（Impact Score），评估基因变异对代谢路径的潜在影响。

#### 3. 实验设计：数据集与对比
*   **数据集/场景**：该研究构建了一个“第一代参考图谱”，涵盖了 9 类致癌物（如雄激素、芳香胺、多环芳烃等），涉及 15 种索引致癌物和 36 种关键酶。
*   **Benchmark/对比**：本文并非传统的算法对比论文，其 Benchmark 是现有的碎片化数据库。论文通过**雄激素（Androgen）分支**作为案例研究，展示了 ExposoGraph 如何通过 CYP19A1 介导的芳香化作用，将雄激素代谢与雌激素醌形成及 DNA 加合物生成联系起来，证明了其在揭示跨途径连通性方面的优势。

#### 4. 资源与算力
*   **算力说明**：论文中**未明确提及**具体的 GPU 型号、数量或训练时长。由于该平台主要基于知识图谱的构建与 Web 交互可视化，其核心开销在于数据的精选、清洗与前端渲染，而非大规模深度学习模型的训练。

#### 5. 实验数量与充分性
*   **实验规模**：参考图谱目前包含 96 个节点和 102 条边。
*   **充分性评价**：
    *   **广度**：涵盖了 I 相活化（14 种酶）、II 相结合（14 种酶）、III 相转运（3 种酶）和 DNA 修复（5 种酶），覆盖面较广。
    *   **深度**：通过对雄激素路径的深入分析，验证了图谱在复杂生物学逻辑表达上的准确性。
    *   **局限性**：作为第一代工具，节点数量相对较少，主要集中在已知的经典路径上，尚未实现全基因组规模的自动化覆盖。

#### 6. 主要结论与发现
*   **集成框架的有效性**：ExposoGraph 成功提供了一个将致癌暴露、代谢命运与遗传调节因子联系起来的集成框架。
*   **跨途径发现**：通过图谱可视化，能够清晰观察到不同致癌物代谢路径之间的交叉（如雄激素与雌激素路径的关联），这有助于生成新的基因-环境相互作用假设。
*   **风险建模基础**：初步建立的风险评分逻辑为未来开发个体化癌症风险评估工具奠定了结构化基础。

#### 7. 优点
*   **交互性强**：提供了多维度的过滤和搜索功能，极大地方便了非计算背景的研究人员探索复杂代谢网络。
*   **数据融合度高**：打破了毒理学、药理学和遗传学之间的数据孤岛。
*   **可视化直观**：通过 D3.js 实现的动态图谱能够清晰展示致癌物从“进入人体”到“产生 DNA 加合物”的动态过程。

#### 8. 不足与局限
*   **规模限制**：目前的 96 个节点仅代表了致癌物世界的冰山一角，需进一步扩展以包含更多环境污染物。
*   **临床验证缺失**：该平台目前仅用于科研用途和假设生成，其风险评分模型尚未经过临床队列的验证，不能直接用于临床风险诊断。
*   **自动化程度**：数据主要依靠人工精选和整合，未来需要引入更强大的自然语言处理（NLP）技术来自动更新图谱。

（完）
