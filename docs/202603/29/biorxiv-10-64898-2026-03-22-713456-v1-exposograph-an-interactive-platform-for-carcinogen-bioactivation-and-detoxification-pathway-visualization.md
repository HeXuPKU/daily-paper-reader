---
title: "ExposoGraph: An Interactive Platform for Carcinogen Bioactivation and Detoxification Pathway Visualization"
title_zh: ExposoGraph：致癌物生物活化与解毒通路可视化的交互式平台
authors: "Pienta, K., Kazi, J. U."
date: 2026-03-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.22.713456v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 癌症风险中基因-环境相互作用的评估
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

结果：第一代参考图谱涵盖了 9 类致癌物的代谢活化和解毒通路，涉及 15 种索引致癌物。它代表了 36 种酶，包括 I 相活化 (n=14)、II 相结合与解毒 (n=14)、III 相转运 (n=3) 和 DNA 修复 (n=5)。交互式探索支持致癌物类别过滤、节点和边类型过滤、基于元数据的搜索，以及带有出处和药物基因组注释的详细悬停/详情视图。雄激素分支通过 CYP19A1 介导的芳香化作用和下游儿茶酚雌激素化学过程，将雄激素代谢与雌激素醌形成及 DNA 加合物生成联系起来，突显了跨通路连通性。在可选的以雄激素为重点的扩展中，额外的受体、组织和变异背景进一步将该分支与雄激素受体信号传导和基因型特异性注释联系起来。

结论：ExposoGraph 提供了一个第一代集成交互式框架，将致癌暴露与代谢归宿及遗传调节因子联系起来。该平台支持基因-环境相互作用研究的假设生成，并可能为未来的个体化风险建模提供信息，同时它仍是一个研究用途的框架，而非经过临床验证的风险评估工具。

## Abstract
BackgroundDespite extensive cataloging of carcinogenic exposures by the International Agency for Research on Cancer (IARC) and pharmacogenomic variation by resources such as PharmVar and CPIC, few platforms unify exposure, metabolic activation and detoxification, DNA damage, and genetic annotation within a single interactive visualization framework. This gap limits systematic evaluation of gene-environment interactions in cancer risk assessment.

MethodsWe developed the Carcino-Genomic Knowledge Graph, ExposoGraph, an interactive knowledge-graph platform for carcinogen metabolism and DNA damage pathways. The reference graph integrates curated data and annotations from IARC, KEGG, PharmVar, CPIC, CTD, and supporting literature/resources. The current reference graph contains 96 nodes across 5 entity types (Carcinogens, Enzymes, Metabolites, DNA Adducts, and Pathways) and 102 edges across 6 relationship types (activates, detoxifies, transports, forms adduct, repairs, and pathway).

ResultsThe first-generation reference graph captures metabolic activation and detoxification pathways for 9 carcinogen classes spanning 15 index carcinogens. It represents 36 enzymes across Phase I activation (n=14), Phase II conjugation and detoxification (n=14), Phase III transport (n=3), and DNA repair (n=5). Interactive exploration supports carcinogen-class filtering, node- and edge-type filtering, metadata-based search, and detailed hover/detail views with provenance and pharmacogenomic annotations. The androgen branch highlights cross-pathway connectivity by linking androgen metabolism to estrogen quinone formation and DNA adduct generation through CYP19A1-mediated aromatization and downstream catechol estrogen chemistry. In the optional androgen-focused extension, additional receptor, tissue, and variant context further connects this branch to androgen receptor signaling and genotype-specific annotations.

ConclusionsExposoGraph provides a first-generation integrated, interactive framework linking carcinogenic exposures to metabolic fates and genetic modulators. The platform supports hypothesis generation for gene-environment interaction studies and may inform future individualized risk modeling, while remaining a research-use framework rather than a clinically validated risk-assessment tool.

---

## 论文详细总结（自动生成）

### ExposoGraph：致癌物生物活化与解毒通路可视化交互平台论文总结

#### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何系统性地整合并可视化环境致癌物暴露、个体代谢差异（生物活化与解毒）以及最终的遗传损伤（DNA加合物），以评估“基因-环境相互作用”（GxE）对癌症风险的影响。
*   **研究背景**：
    *   环境因素对死亡率变异的影响（约17%）远超多基因风险评分（不足2%）。
    *   虽然 IARC 编目了致癌物，PharmVar/CPIC 记录了遗传变异，但这些数据处于碎片化状态。
    *   现有的生物信息学工具（如 KEGG、CTD、Cytoscape）缺乏专门针对致癌物代谢路径与药物基因组学注释深度融合的交互式平台。

#### 2. 方法论
*   **核心思想**：构建一个名为 **ExposoGraph** 的“致癌基因组知识图谱”（Carcino-Genomic Knowledge Graph），通过结构化节点和有向边描述致癌物从进入人体到产生 DNA 损伤的全过程。
*   **关键技术细节**：
    *   **数据集成**：整合了 IARC（致癌性分类）、KEGG（代谢通路）、PharmVar/CPIC（药物基因组变异与表型）、CTD（化学品-基因相互作用）、GTEx（组织特异性表达）及 PubMed 文献。
    *   **图谱架构**：包含 96 个节点（5 类：致癌物、酶、代谢物、DNA 加合物、通路）和 102 条边（6 类关系：活化、解毒、转运、形成加合物、修复、通路成员）。
    *   **可视化实现**：采用 D3.js、Plotly 和 Dash Cytoscape 开发，支持力导向布局（Force-directed layout），提供 Web 端交互界面。
    *   **风险评分基础**：建立了一套基于图拓扑结构的评分框架，结合酶的活性得分（Activity Score）和其在路径中的位置（Impact Score）来初步评估遗传变异对致癌风险的影响。

#### 3. 实验设计
*   **应用场景**：该论文主要通过功能展示和案例研究（Case Studies）来验证平台的有效性。
*   **覆盖范围**：涵盖 9 类致癌物（如多环芳烃、芳香胺、霉菌毒素、内源性激素等），涉及 15 种代表性致癌物和 36 种关键代谢/修复酶。
*   **Benchmark 与对比方法**：
    *   **对比对象**：CTD（侧重通用相互作用）、KEGG（侧重标准通路图）、PharmCAT（侧重临床用药指导）、Cytoscape（通用网络分析工具）。
    *   **对比维度**：是否具备预精选的致癌代谢路径、是否集成药物基因组活性注释、是否支持致癌物类别过滤、是否具备交互式 Web 界面。

#### 4. 资源与算力
*   **算力说明**：论文中**未明确提及**具体的 GPU 型号、数量或训练时长。
*   **原因分析**：ExposoGraph 属于基于规则和专家精选数据的知识图谱平台，其核心工作在于数据清洗、本体构建和前端可视化开发，而非深度学习模型的训练，因此对高性能计算资源（如大规模 GPU 集群）的需求较低。

#### 5. 实验数量与充分性
*   **实验规模**：展示了 4 个典型的代谢路径案例（苯并[a]芘、4-氨基联苯、雄激素桥接路径、黄曲霉毒素 B1）。
*   **充分性评估**：
    *   对于一个“第一代”工具类平台，其提供的 9 类致癌物覆盖了主要的已知化学致癌机制，具有较好的代表性。
    *   **客观性**：数据来源于公认的权威数据库（IARC, KEGG 等），逻辑构建符合生物化学常识。
    *   **局限性**：目前仅包含 15 种索引致癌物，对于 IARC 列出的 120 多种 1 类致癌物来说，覆盖面仍有待扩大。

#### 6. 主要结论与发现
*   **平台价值**：ExposoGraph 成功填补了致癌暴露与遗传易感性之间可视化工具的空白。
*   **科学发现**：通过图谱发现，CYP19A1（芳香化酶）是连接雄激素代谢与雌激素介导的 DNA 损伤的关键桥梁，解释了雄激素可能通过非受体途径（即转化为雌激素醌）导致前列腺癌的潜在机制。
*   **应用前景**：该平台可用于 GxE 研究的假设生成、个体化风险建模的结构框架以及化学致癌机制的教学。

#### 7. 优点
*   **高度集成**：首次将暴露科学、代谢组学和药物基因组学数据统一在单一图谱中。
*   **交互性强**：支持多维度过滤（按致癌物类别、节点类型等）和实时元数据查询，用户体验优于静态通路图。
*   **拓扑感知评分**：提出的风险评分框架考虑了酶在代谢网络中的上下游位置，比单纯的变异计数更具生物学意义。

#### 8. 不足与局限
*   **数据覆盖有限**：目前仅为“第一代”，尚需纳入更多致癌物（如重金属、病毒、放射性物质）。
*   **模型静态化**：未能模拟酶的诱导或抑制（如协同暴露导致的代谢改变）等动态过程。
*   **缺乏临床验证**：目前的风险评分模型基于文献和体外数据，尚未在大型前瞻性队列（如 UK Biobank 或 All of Us）中进行人群水平的验证。
*   **应用限制**：目前仅限科研用途，不能直接作为临床风险评估工具。

（完）
