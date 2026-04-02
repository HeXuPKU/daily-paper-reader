---
title: "Cirrina: LLM-driven pharmacological reasoning agent enables preclinical CNS drug evaluation"
title_zh: Cirrina：大语言模型驱动的药理学推理智能体赋能临床前中枢神经系统药物评估
authors: "Rajbanshi, B., Iqbal, K., Guruacharya, A."
date: 2026-03-31
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.29.713781v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 用于药理推理和药物评估的LLM智能体
tldr: "本研究针对中枢神经系统（CNS）药物临床前评估的复杂推理难题，开发了集成八种药理学工具的 LLM 智能体 Cirrina。该智能体能跨越从分子结构到动物实验的多维数据进行逻辑推理，并根据靶点动态调整评估阈值。实验表明，Cirrina 在 181 种化合物评估中的准确率（68%）显著优于传统规则方法（31%），为降低临床开发失败率提供了可扩展且透明的决策支持。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-29-713781-v1/fig-001.webp\", \"caption\": \"Fig 4. The Agentic framework performs reasoning traces and adaptive pharmacological interpretation within Tier 2 for failed CNS compounds. Based on these reasoning pathways, the agent recommended (a) CAUTION for Atabecestat. (b) NO-GO for Semagacestat. These traces reveal the underlying logic used to navigate complex pharmacological data that fixed rules might overlook.\", \"page\": 7, \"index\": 1, \"width\": 979, \"height\": 577}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-29-713781-v1/fig-002.webp\", \"caption\": \"Fig 1. Architectural Schematic of Agentic vs. Deterministic Frameworks. Both architectures process data through a five-tier input structure. The Agentic framework utilizes an LLM orchestrator to manage eight specialized tools, while the Deterministic framework relies on a singular baseline tool. Both systems generate decision outputs categorized as GO, CAUTION, or NO-GO. Notably, the Agentic framework provides granular reasoning traces to justify its decision-making, a feature absent in the deterministic pipeline.\", \"page\": 3, \"index\": 2, \"width\": 979, \"height\": 447}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-29-713781-v1/fig-003.webp\", \"caption\": \"Fig 5. Superiority of pharmacological reasoning over fixed rules in discordant cases. Analysis of cases where the two architectures disagreed (discordant cases) highlights the robustness of the agentic approach.(a) In divergence analysis for the cases of conflicting recommendations, the Agentic framework was correct 75% of the time, compared to 10% for the deterministic pipeline.(b) A case study of Atabecestat serves as a representative example where the agent’s reasoning successfully outperformed the fixed-rule deterministic model.\", \"page\": 8, \"index\": 3, \"width\": 852, \"height\": 712}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-29-713781-v1/fig-004.webp\", \"caption\": \"Fig 2. Computational engine validation. (a) Allometric scaling validation for PK parameters (n = 20). Predictions within 3-fold error: CL 75%, Vd 95%, t1/2 100%, F 100%. (b) Predicted vs. observed logBB correlation (R = 0.781); 69.9% within 0.5 log units. (c) Kp,brain fold-error analysis (GMFE = 2.21); 80% within 3-fold. Outliers (risperidone, fluoxetine, duloxetine) likely reflect transporter interactions. (d) Receptor occupancy validation across 73 comparisons and 14 targets (R = 0.385); 35.6% within 20% absolute error. (e) Safety and transporter prediction balanced accuracy: hERG 0.86, P-gp 0.56, BCRP 0.69, LAT1 0.63. (f) Conformal PK coverage of 92.2% at 90% nominal confidence, with interval widths ranging 1.0–4.4x. (g) End-to-end uncertainty propagation coverage of 33.6%, well below the 90% target, reflecting compounding uncertainty across multi-tool reasoning. (h) Parameter sensitivity ranking: Kp,brain (0.684) and fu,plasma (0.660) are the dominant drivers, followed by Ki and Vd (0.577), F (0.542), and t1/2 (0.51).\", \"page\": 4, \"index\": 4, \"width\": 1004, \"height\": 797}]"
motivation: 中枢神经系统药物开发面临复杂的药理约束，传统的基于规则的确定性方法难以应对需要灵活推理的临床前评估。
method: 开发了名为 Cirrina 的 LLM 智能体，通过集成八种机械药理学工具，实现从分子 SMILES 到动物 PK/PD 数据的跨层级逻辑推理。
result: "在 181 种 CNS 化合物的测试中，Cirrina 达到了 68% 的评估准确率，在处理复杂分歧案例时的表现远超传统确定性流水线。"
conclusion: Cirrina 为临床前药物评价提供了一个可扩展且有据可查的推理框架，能有效识别潜在失败风险，优化药物研发决策。
---

## 摘要
评估临床前候选药物是否有效并非一个预测问题，而是一个推理问题。同样的数值输出，根据靶点和治疗背景的不同，需要不同的解释。中枢神经系统（CNS）药物开发是这一推理问题中要求最高的情况。例如，化合物必须穿过血脑屏障，抵抗外排转运，并在满足安全边际的剂量下实现充足的受体占有率。这些约束条件相互交织成网，需要仔细解读。在这里，我们展示了 Cirrina，一个与八种机制药理学工具耦合的大语言模型（LLM）智能体，能够对输入数据进行跨维度推理，从而提供更好的决策和记录详尽的推理轨迹。该 LLM 智能体在从 SMILES 到动物 PK/PD 测量的多个数据层级上进行推理，并根据特定靶点的要求调整阈值。在 181 种 CNS 化合物的验证中，它达到了 68% 的准确率，而基于规则的确定性流程准确率仅为 31%。在 103 个不一致的案例中，该智能体的推理在 75% 的情况下是正确的，而确定性流程仅为 10%。Cirrina 为临床前决策提供了一个可扩展且有据可查的框架，能够有效识别通用阈值容易忽略的易失败候选药物，从而降低临床开发周期中的失败几率。

## Abstract
Assessing whether a preclinical drug candidate will work is not a prediction problem but a reasoning problem. The same numerical output warrants different interpretations depending on the target and therapeutic context. CNS drug development presents the most demanding instance of this reasoning problem. For example, a compound must cross the blood-brain barrier, resist efflux transport, and achieve adequate receptor occupancy at a dose that clears safety margins. The constraints interact with each other in a web that needs careful interpretation. Here, we show that Cirrina, an LLM agent coupled to eight mechanistic pharmacology tools, can reason across the input data to provide better decisions and a well documented reasoning trace. The LLM agent reasons across multiple data tiers from SMILES to animal PK/PD measurements adjusting thresholds based on target-specific requirements. Validated against 181 CNS compounds, it achieved a 68% accuracy compared to a rule-based deterministic pipeline of 31% accuracy. In 103 discordant cases, the agent's reasoning was correct in 75% of instances compared to only 10% for deterministic pipelines. Cirrina provides a scalable, documented framework for preclinical decision-making, effectively identifying failure-prone candidates that generic thresholds overlook, and thereby reducing the chances of failure along the clinical development cycle.

---

## 论文详细总结（自动生成）

以下是对论文《Cirrina: LLM-driven pharmacological reasoning agent enables preclinical CNS drug evaluation》的深度总结：

### 1. 核心问题与研究动机
*   **核心问题**：中枢神经系统（CNS）药物研发的失败率极高（>90%），主要原因在于临床前评估不仅是“预测”问题，更是复杂的“推理”问题。
*   **研究动机**：
    *   **多因素交织**：药物需同时满足血脑屏障（BBB）渗透、抗外排转运、受体占有率（RO）及安全边际等互相关联的指标。
    *   **现有工具局限**：传统的 ADMET 预测工具（如 SwissADME）仅提供孤立的二元分类，缺乏机制关联；而复杂的 PBPK 模型在研发早期又因缺乏实验参数而难以应用。
    *   **集成缺口**：药理学家通常手动整合这些数据，过程缺乏标准化、难以记录且因人而异。

### 2. 方法论
Cirrina 是一个将大语言模型（LLM）作为“推理核心”，并耦合了 8 个“药理学工具箱”的智能体框架。
*   **核心思想**：利用 LLM 的逻辑推理能力，根据特定靶点的药理背景动态调整评估阈值，而非使用僵化的固定规则。
*   **关键技术细节**：
    *   **8 种机制工具**：包括 BBB 分类、P-gp/BCRP 外排评分、主动转运检测、PK 参数异速生长缩放、四室 CNS PBPK 模拟、Hill 方程受体占有率计算、定量安全边际分析及逆向 PK/PD 剂量估算。
    *   **五级数据分层（Tier 1-5）**：系统根据数据丰富度自动适配。从仅有 SMILES 结构（Tier 1）到包含实测毒性数据（Tier 5），逐步用实验值替换预测值。
    *   **推理环路**：LLM 决定调用哪些工具、检查中间输出、根据上游发现重新解释下游预测，并生成自然语言形式的推理轨迹（Reasoning Trace）。

### 3. 实验设计
*   **数据集**：共 181 种 CNS 化合物，涵盖 14 个分子靶点。
    *   包括 103 种已验证药物、25 种外部验证药物、32 种 BBB 阴性对照和 21 种 NO-GO 化合物（临床失败或撤市药物）。
*   **Benchmark（基准）**：
    *   **确定性流水线（Deterministic Pipeline）**：使用完全相同的 8 种药理工具，但采用固定的硬性阈值（Fixed Rules）进行决策。
*   **对比维度**：评估准确率、马修斯相关系数（MCC）、AUC-ROC 以及在两者决策分歧案例中的表现。

### 4. 资源与算力
*   **模型选择**：使用了 **Claude 3 Haiku**。作者选择该模型是基于速度、成本和迭代开发的平衡考虑。
*   **算力细节**：文中未明确提及具体的 GPU 硬件型号或训练时长。由于 Cirrina 是一个基于推理的智能体框架（Agentic Framework），其核心在于 Prompt Engineering 和工具调用，而非从头训练大模型。实验中将 Temperature 设为 0 以保证输出的稳定性。

### 5. 实验数量与充分性
*   **实验规模**：对 181 种化合物进行了全量评估，并针对 16 种临床失败药物进行了专门的追溯分析。
*   **消融实验**：通过“智能体 vs. 确定性流水线”的对比，有效地隔离了“药理推理”本身带来的增量价值。
*   **充分性评价**：实验设计较为客观，涵盖了成功与失败的多种案例。通过敏感性分析（图 2h）验证了底层计算引擎的可靠性。但在“CAUTION”类别的样本量（17个）相对较小，可能影响该类别的统计显著性。

### 6. 主要结论与发现
*   **性能飞跃**：Cirrina 的整体评估准确率为 **68%**，远高于确定性流水线的 **31%**。
*   **分歧案例表现**：在两者意见不一致的 103 个案例中，Cirrina 的正确率高达 **75%**，而固定规则仅为 **10%**。
*   **特定靶点优势**：在需要特定药理知识（如 GABA-A 调节剂仅需低占有率即可生效）的领域，智能体的推理优势最为明显。
*   **失败检测**：在 Tier 1（仅结构）阶段即可识别 87.5% 的临床失败药物，随着数据层级提升，识别率可达 100%。

### 7. 优点
*   **透明度与可解释性**：提供详细的推理轨迹，使药理学家能够审查决策逻辑，而非面对“黑箱”预测。
*   **动态适配**：能够根据上游预测的确定性（如 BBB 渗透极低时跳过 RO 计算）自动调整工作流。
*   **弥补人才缺口**：将资深药理学家的集成推理经验自动化，有助于在药物发现早期快速筛选化合物。

### 8. 不足与局限
*   **数据泄露风险**：LLM 的训练数据可能包含这些已知药物的信息，虽然作者通过交叉验证进行了缓解，但仍需在完全未公开的专有化合物上进行前瞻性验证。
*   **底层工具依赖**：智能体的推理质量受限于底层 8 个工具的准确性（如 RO 预测的绝对误差仍较大）。
*   **覆盖范围限制**：目前主要关注 PK/PD 和靶点参与，对于胃肠道毒性或孤立的疗效失败（非药理机制引起）的检测能力有限。
*   **样本不平衡**：评估集中 GO 类化合物占比过高，可能对某些分类指标产生偏差。

（完）
