---
title: "ExposoGraph: An Interactive Platform for Carcinogen Bioactivation and Detoxification Pathway Visualization"
title_zh: ExposoGraph：致癌物生物活化与解毒通路可视化的交互式平台
authors: "Pienta, K., Kazi, J. U."
date: 2026-03-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.22.713456v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 统一暴露、代谢激活和遗传注释以评估基因-环境相互作用
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
背景：尽管国际癌症研究机构 (IARC) 对致癌暴露进行了广泛编目，PharmVar 和 CPIC 等资源也记录了药物基因组变异，但很少有平台能将暴露、代谢活化与解毒、DNA 损伤以及遗传注释统一在一个交互式可视化框架内。这一空白限制了癌症风险评估中对基因-环境相互作用的系统性评价。

方法：我们开发了致癌基因组知识图谱 ExposoGraph，这是一个针对致癌物代谢和 DNA 损伤通路的交互式知识图谱平台。该参考图谱整合了来自 IARC、KEGG、PharmVar、CPIC、CTD 以及相关文献/资源的精选数据和注释。目前的参考图谱包含跨越 5 种实体类型（致癌物、酶、代谢物、DNA 加合物和通路）的 96 个节点，以及跨越 6 种关系类型（活化、解毒、转运、形成加合物、修复和通路）的 102 条边。

结果：第一代参考图谱涵盖了 9 类致癌物的代谢活化和解毒通路，涉及 15 种索引致癌物。它代表了 36 种酶，包括 I 相活化 (n=14)、II 相结合与解毒 (n=14)、III 相转运 (n=3) 和 DNA 修复 (n=5)。交互式探索支持致癌物类别过滤、节点和边类型过滤、基于元数据的搜索，以及带有来源和药物基因组注释的详细悬停/细节视图。雄激素分支通过 CYP19A1 介导的芳香化作用和下游儿茶酚雌激素化学过程，将雄激素代谢与雌激素醌形成及 DNA 加合物生成联系起来，突显了跨通路连通性。在可选的以雄激素为重点的扩展中，额外的受体、组织和变异背景进一步将该分支与雄激素受体信号传导和基因型特异性注释联系起来。

结论：ExposoGraph 提供了一个第一代集成式交互框架，将致癌暴露与代谢归宿及遗传调节因子联系起来。该平台支持基因-环境相互作用研究的假设生成，并可能为未来的个体化风险建模提供信息，同时它仍是一个研究用途的框架，而非经过临床验证的风险评估工具。

## Abstract
BackgroundDespite extensive cataloging of carcinogenic exposures by the International Agency for Research on Cancer (IARC) and pharmacogenomic variation by resources such as PharmVar and CPIC, few platforms unify exposure, metabolic activation and detoxification, DNA damage, and genetic annotation within a single interactive visualization framework. This gap limits systematic evaluation of gene-environment interactions in cancer risk assessment.

MethodsWe developed the Carcino-Genomic Knowledge Graph, ExposoGraph, an interactive knowledge-graph platform for carcinogen metabolism and DNA damage pathways. The reference graph integrates curated data and annotations from IARC, KEGG, PharmVar, CPIC, CTD, and supporting literature/resources. The current reference graph contains 96 nodes across 5 entity types (Carcinogens, Enzymes, Metabolites, DNA Adducts, and Pathways) and 102 edges across 6 relationship types (activates, detoxifies, transports, forms adduct, repairs, and pathway).

ResultsThe first-generation reference graph captures metabolic activation and detoxification pathways for 9 carcinogen classes spanning 15 index carcinogens. It represents 36 enzymes across Phase I activation (n=14), Phase II conjugation and detoxification (n=14), Phase III transport (n=3), and DNA repair (n=5). Interactive exploration supports carcinogen-class filtering, node- and edge-type filtering, metadata-based search, and detailed hover/detail views with provenance and pharmacogenomic annotations. The androgen branch highlights cross-pathway connectivity by linking androgen metabolism to estrogen quinone formation and DNA adduct generation through CYP19A1-mediated aromatization and downstream catechol estrogen chemistry. In the optional androgen-focused extension, additional receptor, tissue, and variant context further connects this branch to androgen receptor signaling and genotype-specific annotations.

ConclusionsExposoGraph provides a first-generation integrated, interactive framework linking carcinogenic exposures to metabolic fates and genetic modulators. The platform supports hypothesis generation for gene-environment interaction studies and may inform future individualized risk modeling, while remaining a research-use framework rather than a clinically validated risk-assessment tool.

---

## 论文详细总结（自动生成）

### ExposoGraph：致癌物生物活化与解毒通路可视化的交互式平台

#### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：尽管国际上已有大量关于致癌物分类（如 IARC）和药物基因组变异（如 PharmVar）的数据，但目前缺乏一个统一的、交互式的平台，能够将**环境暴露、代谢激活/解毒过程、DNA 损伤（加合物形成）以及个体遗传注释**整合在一起。
*   **研究背景**：环境因素对死亡率的影响远超多基因风险评分。化学致癌物通常是前致癌物，需经酶代谢活化。个体的遗传差异（如 CYP、GST 基因多态性）决定了其对特定暴露的易感性。研究者需要一个工具来系统性地评估“基因-环境相互作用”（GxE），以实现个体化的癌症风险评估。

#### 2. 方法论
*   **核心思想**：构建一个名为 **ExposoGraph** 的致癌基因组知识图谱（Carcino-Genomic Knowledge Graph），通过结构化的节点和边来模拟致癌物在体内的生物转化路径。
*   **关键技术细节**：
    *   **数据集成**：整合了 IARC（致癌性）、KEGG（代谢通路）、PharmVar/CPIC（药理基因组变异与临床指南）、CTD（化学品-基因相互作用）和 GTEx（组织表达）等权威数据库。
    *   **图谱架构**：包含 5 种节点类型（致癌物、酶、代谢物、DNA 加合物、通路）和 6 种关系边（激活、解毒、转运、形成加合物、修复、通路归属）。
    *   **可视化实现**：采用 D3.js、Plotly 和 Dash Cytoscape 构建交互式前端，支持力导向布局、层次布局等多种视图。
    *   **风险评分基础**：建立了一个拓扑感知的评分框架，根据酶在路径中的位置（激活 vs 解毒）和已知的变异活性数据，为未来的复合风险建模提供结构支持。

#### 3. 实验设计
*   **数据集与场景**：
    *   图谱涵盖了 **9 类致癌物**（如多环芳烃、芳香胺、亚硝胺、霉菌毒素、内源性激素等），涉及 15 种代表性致癌物。
    *   包含 **36 种关键酶**，涵盖 I 相活化、II 相结合、III 相转运及 DNA 修复。
*   **Benchmark 与对比对象**：
    *   论文对比了 **CTD**（侧重通用相互作用而非代谢路径）、**KEGG**（侧重标准通路而非遗传变异）、**PharmCAT**（侧重临床药物而非致癌物）以及 **Cytoscape**（通用工具，缺乏预构建的致癌物知识库）。
*   **案例分析**：重点展示了苯并[a]芘（BaP）、4-氨基联苯（4-ABP）、黄曲霉毒素 B1（AFB1）以及雄激素代谢桥接（连接雄激素与雌激素致癌路径）的特定通路。

#### 4. 资源与算力
*   **算力说明**：论文中**未明确提及**具体的 GPU 型号、数量或训练时长。
*   **原因分析**：ExposoGraph 主要是一个基于规则、精选数据和前端可视化技术的知识图谱平台，而非需要大规模算力训练的深度学习模型。其核心工作在于数据清洗、本体构建和交互逻辑开发。

#### 5. 实验数量与充分性
*   **实验规模**：
    *   构建了包含 96 个节点和 102 条边的参考图谱。
    *   展示了 4 组典型的致癌物路径分析（图 3A-D）。
    *   提供了一个包含 13 种已评分酶的药理基因组风险评分原型（图 5）。
*   **充分性评价**：作为“第一代”工具展示，实验涵盖了主要的致癌物类别，路径展示清晰。但由于目前仅包含 15 种致癌物，对于 IARC 目录中上百种致癌物的覆盖尚显不足。实验侧重于功能验证和案例展示，而非大规模人群数据的统计验证。

#### 6. 主要结论与发现
*   **平台有效性**：ExposoGraph 成功统一了多源异构数据，使用户能够直观地追踪致癌物从暴露到 DNA 损伤的完整代谢链条。
*   **跨通路发现**：通过雄激素分支的建模，揭示了 CYP19A1（芳香化酶）如何将雄激素代谢与雌激素醌诱导的 DNA 损伤联系起来，为前列腺癌等激素依赖性癌症提供了新的 GxE 假设。
*   **科研价值**：该平台为 GxE 研究提供了假设生成工具，有助于识别高风险遗传背景与特定环境暴露的组合。

#### 7. 优点
*   **多源整合**：首次将药理基因组学（变异/活性）与致癌物代谢路径深度融合。
*   **交互性强**：支持多维度过滤（按致癌物类别、节点类型等）、搜索和详细元数据查看，用户体验良好。
*   **填补空白**：解决了研究者需要手动跨多个数据库合成致癌代谢信息的痛点。
*   **开源属性**：提供了 Web 版、PyPI 包和 GitHub 源码，易于学术界使用和扩展。

#### 8. 不足与局限
*   **覆盖范围有限**：目前仅包含 15 种致癌物，需进一步扩展以涵盖更多 IARC 1 类和 2A 类致癌物。
*   **静态模型**：目前的图谱无法模拟动态的酶诱导或抑制效应（如共同暴露导致的代谢改变）。
*   **评分标准化不足**：部分酶的活性评分基于文献估算，而非完全标准化的临床评分，可能存在主观偏差。
*   **缺乏临床验证**：该工具目前仅用于科研假设生成，尚未在具有暴露数据和基因型数据的大规模前瞻性队列中进行风险预测准确性的验证。

（完）
