---
title: "ExposoGraph: An Interactive Platform for Carcinogen Bioactivation and Detoxification Pathway Visualization"
title_zh: ExposoGraph：致癌物生物活化与解毒途径可视化的交互式平台
authors: "Pienta, K., Kazi, J. U."
date: 2026-03-24
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.22.713456v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 统一暴露和遗传注释以研究基因-环境相互作用
tldr: ExposoGraph是一个交互式致癌物代谢知识图谱平台，旨在填补致癌暴露、代谢激活/解毒、DNA损伤与遗传注释之间缺乏统一可视化框架的空白。该研究整合了IARC、KEGG等多个权威数据库，构建了包含96个节点和102条关系的知识图谱，涵盖15种主要致癌物及其代谢路径。该平台支持多维度过滤与搜索，为研究基因-环境相互作用及个体化癌症风险评估提供了重要的科研工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713456-v1/fig-001.webp\", \"caption\": \"Figure 4. Example Androgen pathway visualization using ExposoGraph Viewer (D3). Only Androgen carcinogen class is visualized.\", \"page\": 8, \"index\": 1, \"width\": 1126, \"height\": 602}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713456-v1/fig-002.webp\", \"caption\": \"Figure 2. Example pathway visualization using ExposoGraph Viewer (D3). All carcinogen classes are visualized in this example graph.\", \"page\": 6, \"index\": 2, \"width\": 1126, \"height\": 598}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-22-713456-v1/fig-003.webp\", \"caption\": \"Figure 5. Pharmacogenomic risk-scoring foundation in ExposoGraph. In the current reference graph (96 nodes, 102 edges), 13 scored enzymes span 8 carcinogen classes. Left, horizontal bars summarize the current class-level reservoir of scored activation and detoxification support within each graph-defined carcinogen class. Positive red bars indicate summed representative activity scores for activation enzymes, whereas negative green bars indicate summed representative activity scores for detoxification enzymes; mixed-function (M) and repair (R) contributions are shown as text annotations where present. Right, each point represents a scored enzyme positioned by representative activity score on the x-axis and topologyaware gene impact score on the y-axis, where the impact score reflects downstream adduct-forming and repair reachability in the graph. Point color denotes role bucket (activation, detoxification, mixed, or repair), and bubble size reflects how many carcinogen classes each scored gene touches. This figure summarizes current structural support for pharmacogenomic interpretation in ExposoGraph and should be interpreted as a foundation for future composite risk modeling rather than a patient-level automated risk classifier.\", \"page\": 9, \"index\": 3, \"width\": 1126, \"height\": 642}]"
motivation: 现有的致癌暴露与药理基因组资源缺乏统一的交互式可视化框架，限制了对基因-环境相互作用的系统性评估。
method: 开发了名为ExposoGraph的知识图谱平台，整合了来自IARC、KEGG、PharmVar等数据库的致癌物代谢、DNA损伤及遗传注释数据。
result: 平台涵盖了9类致癌物、36种关键酶及其代谢路径，支持交互式过滤、元数据搜索以及详细的药理基因组注释查看。
conclusion: ExposoGraph为连接致癌暴露、代谢归宿与遗传调节因子提供了集成框架，有助于基因-环境相互作用的研究和假设生成。
---

## 摘要
背景：尽管国际癌症研究机构 (IARC) 对致癌暴露进行了广泛编目，且 PharmVar 和 CPIC 等资源对药物基因组变异进行了记录，但很少有平台能在单一交互式可视化框架内统一暴露、代谢活化与解毒、DNA 损伤及遗传注释。这一空白限制了癌症风险评估中对基因-环境相互作用的系统性评价。

方法：我们开发了致癌基因组知识图谱 (Carcino-Genomic Knowledge Graph) —— ExposoGraph，这是一个用于致癌物代谢和 DNA 损伤途径的交互式知识图谱平台。参考图谱整合了来自 IARC、KEGG、PharmVar、CPIC、CTD 以及支持性文献/资源的精选数据和注释。目前的参考图谱包含跨越 5 种实体类型（致癌物、酶、代谢物、DNA 加合物和途径）的 96 个节点，以及跨越 6 种关系类型（活化、解毒、转运、形成加合物、修复和途径）的 102 条边。

结果：第一代参考图谱涵盖了涉及 15 种索引致癌物的 9 类致癌物的代谢活化和解毒途径。它代表了 36 种酶，包括 I 相活化 (n=14)、II 相结合与解毒 (n=14)、III 相转运 (n=3) 和 DNA 修复 (n=5)。交互式探索支持致癌物类别过滤、节点和边类型过滤、基于元数据的搜索，以及带有出处和药物基因组注释的详细悬停/细节视图。雄激素分支通过 CYP19A1 介导的芳香化作用和下游儿茶酚雌激素化学过程，将雄激素代谢与雌激素醌形成及 DNA 加合物生成联系起来，突显了跨途径的连通性。在可选的以雄激素为重点的扩展中，额外的受体、组织和变异背景进一步将该分支与雄激素受体信号传导和基因型特异性注释联系起来。

结论：ExposoGraph 提供了一个将致癌暴露与代谢归宿及遗传调节因子联系起来的第一代集成交互式框架。该平台支持基因-环境相互作用研究的假设生成，并可能为未来的个体化风险建模提供信息，同时它仍是一个研究用途的框架，而非经过临床验证的风险评估工具。

## Abstract
BackgroundDespite extensive cataloging of carcinogenic exposures by the International Agency for Research on Cancer (IARC) and pharmacogenomic variation by resources such as PharmVar and CPIC, few platforms unify exposure, metabolic activation and detoxification, DNA damage, and genetic annotation within a single interactive visualization framework. This gap limits systematic evaluation of gene-environment interactions in cancer risk assessment.

MethodsWe developed the Carcino-Genomic Knowledge Graph, ExposoGraph, an interactive knowledge-graph platform for carcinogen metabolism and DNA damage pathways. The reference graph integrates curated data and annotations from IARC, KEGG, PharmVar, CPIC, CTD, and supporting literature/resources. The current reference graph contains 96 nodes across 5 entity types (Carcinogens, Enzymes, Metabolites, DNA Adducts, and Pathways) and 102 edges across 6 relationship types (activates, detoxifies, transports, forms adduct, repairs, and pathway).

ResultsThe first-generation reference graph captures metabolic activation and detoxification pathways for 9 carcinogen classes spanning 15 index carcinogens. It represents 36 enzymes across Phase I activation (n=14), Phase II conjugation and detoxification (n=14), Phase III transport (n=3), and DNA repair (n=5). Interactive exploration supports carcinogen-class filtering, node- and edge-type filtering, metadata-based search, and detailed hover/detail views with provenance and pharmacogenomic annotations. The androgen branch highlights cross-pathway connectivity by linking androgen metabolism to estrogen quinone formation and DNA adduct generation through CYP19A1-mediated aromatization and downstream catechol estrogen chemistry. In the optional androgen-focused extension, additional receptor, tissue, and variant context further connects this branch to androgen receptor signaling and genotype-specific annotations.

ConclusionsExposoGraph provides a first-generation integrated, interactive framework linking carcinogenic exposures to metabolic fates and genetic modulators. The platform supports hypothesis generation for gene-environment interaction studies and may inform future individualized risk modeling, while remaining a research-use framework rather than a clinically validated risk-assessment tool.

---

## 论文详细总结（自动生成）

### 论文总结：ExposoGraph——致癌物生物活化与解毒途径可视化的交互式平台

#### 1. 核心问题与整体含义（研究动机和背景）
癌症的发生通常是环境暴露与个体遗传易感性共同作用的结果。虽然国际癌症研究机构（IARC）对致癌物进行了广泛分类，且 PharmVar 等数据库记录了大量的药物基因组变异，但目前缺乏一个统一的、交互式的框架来整合**致癌物暴露、代谢活化/解毒过程、DNA 损伤以及相关的遗传注释**。这种数据的孤立性限制了研究人员系统性评估“基因-环境相互作用（GxE）”对癌症风险影响的能力。ExposoGraph 的开发旨在填补这一空白，提供一个可视化的知识图谱，连接化学暴露与生物学后果。

#### 2. 论文提出的方法论
ExposoGraph 采用**知识图谱（Knowledge Graph, KG）**架构，核心思想是将复杂的生化代谢路径抽象为节点和边：
*   **数据整合**：从 IARC（致癌物分类）、KEGG（代谢途径）、PharmVar/CPIC（遗传变异与药理注释）、CTD（化学-基因相互作用）及相关文献中提取并精选数据。
*   **实体与关系建模**：
    *   **5类节点**：致癌物（Carcinogens）、酶（Enzymes）、代谢物（Metabolites）、DNA 加合物（DNA Adducts）和生物途径（Pathways）。
    *   **6类关系**：活化（activates）、解毒（detoxifies）、转运（transports）、形成加合物（forms adduct）、修复（repairs）和路径归属（pathway）。
*   **交互式可视化**：基于 D3.js 开发了 ExposoGraph Viewer，支持按致癌物类别过滤、节点/边类型过滤、元数据搜索以及详细的药理基因组注释悬停显示。
*   **风险评分基础**：引入了初步的药理基因组风险评分框架，结合酶的活性分数（代表代谢能力）和拓扑感知基因影响分数（代表在图谱中影响下游加合物形成的范围）。

#### 3. 实验设计
该研究属于**工具与平台开发类**，其“实验”主要体现在对参考图谱的构建和特定生物学案例的验证：
*   **数据集/场景**：构建了一个包含 96 个节点和 102 条边的第一代参考图谱，涵盖 9 类致癌物（如黄曲霉毒素、多环芳烃、雄激素等）和 15 种索引致癌物。
*   **案例研究（Benchmark）**：重点展示了**雄激素（Androgen）路径**。通过图谱展示了 CYP19A1 介导的芳香化作用如何将雄激素代谢与雌激素醌形成及 DNA 加合物生成联系起来，证明了平台揭示跨途径连通性的能力。
*   **对比方法**：论文未进行算法性能的横向对比（如准确率、召回率），而是强调其在**集成性、交互性和药理基因组关联性**方面优于现有的单一功能数据库。

#### 4. 资源与算力
*   论文中**未明确说明**具体的算力细节（如 GPU 型号或训练时长）。
*   由于该平台主要基于精选数据的知识图谱构建和 Web 端可视化，其核心计算压力在于数据清洗、结构化存储和前端渲染，而非大规模深度学习模型的训练，因此对高性能算力的需求相对较低。

#### 5. 实验数量与充分性
*   **实验规模**：涵盖了 36 种关键酶（包括 I 相活化酶、II 相结合酶、III 相转运蛋白和 DNA 修复蛋白）。
*   **充分性评价**：作为“第一代”原型，其覆盖的致癌物种类（15种）和节点数量（96个）相对有限。实验主要通过逻辑一致性和已知生物学路径的复现来验证，对于展示平台功能是充分的，但作为通用的风险评估工具，其数据广度仍需扩展。

#### 6. 主要结论与发现
*   **成功构建集成框架**：ExposoGraph 成功将致癌物暴露与代谢归宿、遗传调节因子整合在单一交互界面中。
*   **揭示复杂关联**：通过图谱发现，某些代谢路径（如雄激素与雌激素代谢）在分子水平上是高度交织的，这为理解激素相关癌症提供了新视角。
*   **药理基因组价值**：平台能够识别出具有高度“拓扑影响”的基因（如 CYP1A2, GSTP1 等），这些基因在多种致癌物的活化或解毒中起到关键作用，是个体化风险评估的潜在生物标志物。

#### 7. 优点
*   **多维整合**：打破了环境科学与遗传学之间的数据壁垒。
*   **交互性强**：用户可以动态探索复杂的代谢网络，而非查看静态的通路图。
*   **药理基因组导向**：直接关联了临床相关的遗传变异（如 PharmVar 数据），具有较强的科研转化潜力。
*   **出处透明**：每个节点和边都关联了原始文献或数据库来源，保证了数据的可追溯性。

#### 8. 不足与局限
*   **数据规模有限**：目前仅涵盖 15 种致癌物，尚未覆盖 IARC 清单中的所有已知致癌物。
*   **静态局限性**：目前的图谱主要基于已知文献的精选，缺乏对未知相互作用的预测能力（如基于机器学习的边预测）。
*   **非临床工具**：作者明确指出该平台目前仅用于科研假设生成，未经临床验证，不能直接用于患者的癌症风险分类。
*   **更新维护压力**：生物医学数据更新极快，手动精选（Curated）模式在扩展到数千个节点时将面临巨大的维护挑战。

（完）
