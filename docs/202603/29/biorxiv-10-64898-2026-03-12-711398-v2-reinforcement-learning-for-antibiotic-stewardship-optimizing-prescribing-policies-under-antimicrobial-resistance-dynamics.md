---
title: "Reinforcement Learning for Antibiotic Stewardship: Optimizing Prescribing Policies Under Antimicrobial Resistance Dynamics"
title_zh: 强化学习用于抗生素管理：在抗菌药物耐药性动态下优化处方策略
authors: "Lee, J., Blumberg, S."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.12.711398v2.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 强化学习用于优化医疗中的抗生素处方策略
tldr: 针对抗生素耐药性（AMR）带来的挑战，本研究开发了名为 abx_amr_simulator 的仿真框架，用于评估不同强化学习（RL）策略在抗生素管理中的表现。研究发现，在处理具有延迟反馈和部分可观测性的复杂医疗场景时，分层强化学习（Hierarchical PPO）优于传统策略和固定规则，能有效平衡临床疗效与耐药性控制，为制定科学的抗生素处方策略提供了有力工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-001.webp\", \"caption\": \"Figure 4: AMR levels evolution and cumulative count of sensitive vs. resistant infections treated per antibiotic, when tuned Flat PPO agent is trained in perfectly observed environment and then has evaluative rollouts performed. Left: single-antibiotic scenario. Middle: two-antibiotic scenario without cross-resistance. Right: two-antibiotic scenario with cross-resistance. Each column shows evolution of true AMR levels (top) and cumulative infected/treated counts per antibiotic over time (bottom rows).\", \"page\": 11, \"index\": 1, \"width\": 976, \"height\": 629}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-002.webp\", \"caption\": \"Figure 7: Comparison of cumulative performance metrics of Fixed Prescribing Rule (Expected Reward - Greedy) vs. Flat PPO vs. Flat Recurrent PPO vs. Hierarchical PPO vs. Hierarchical Recurrent PPO, in environment with degraded AMR level information. AMR levels affected by update delay = 90 timesteps, noise = 0.2, bias = -0.2.\", \"page\": 15, \"index\": 2, \"width\": 958, \"height\": 1183}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-003.webp\", \"caption\": \"Figure 2: The experimental pipeline consists of three phases. Phase 1 (Tuning): An Optuna hyperparameter search evaluates candidate configurations via truncated training across 5 random seeds, selecting the configuration that maximizes a stability-adjusted objective (mean reward minus a modest variance penalty across seeds). Phase 2 (Training): Twenty agent copies are initialized with the tuned hyperparameters and undergo prolonged training, each using a distinct random seed. Phase 3 (Evaluation): Each trained agent executes three evaluative rollouts in the environment across unseen random seeds; clinical outcome, patient status, and antibiotic response metrics are logged and aggregated for analysis.\", \"page\": 7, \"index\": 3, \"width\": 979, \"height\": 409}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-004.webp\", \"caption\": \"Figure 3: AMR levels evolution and cumulative count of sensitive vs. resistant infections treated per antibiotic, when ’Expected reward - greedy’ policy is followed (where policy is computed using perfectly observed environments). Left: single-antibiotic scenario. Middle: two-antibiotic scenario without cross-resistance. Right: two-antibiotic scenario with cross-resistance. Each column shows evolution of true AMR levels (top) and cumulative infected/treated counts per antibiotic over time (bottom rows).\", \"page\": 10, \"index\": 4, \"width\": 976, \"height\": 631}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-005.webp\", \"caption\": \"Figure 6: Comparison of cumulative performance metrics of Fixed Prescribing Rule (Expected Reward - Greedy) vs. Flat PPO vs. Hierarchical PPO in perfectly observed environment.\", \"page\": 13, \"index\": 5, \"width\": 958, \"height\": 859}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-006.webp\", \"caption\": \"Table 1: Overview of experimental conditions across four experiment sets. Observability, agent architectures, and comparators were systematically varied. All sets evaluated three antibiotic scenarios: single-antibiotic, two-antibiotic without cross-resistance, and two-antibiotic with cross-resistance.\", \"page\": 8, \"index\": 6, \"width\": 975, \"height\": 298}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-007.webp\", \"caption\": \"Figure 1: Schematic overview of the environment and its subcomponents (patient generator, antibiotic leaky balloons, and reward calculator), and the interaction loop between the agent and environment. 1) The environment uses the PatientGenerator to create a patient and present that patient to the agent. 2) The agent decides to prescribe Antibiotic B for the patient. 3) The agent informs the environment that it decided to prescribe Antibiotic B for the current patient. 4) The environment uses the RewardCalculator to compute the reward for the current action, updates each antibiotic’s AMR LeakyBalloon, and advances to the next timestep and next patient.\", \"page\": 4, \"index\": 7, \"width\": 979, \"height\": 1089}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-008.webp\", \"caption\": \"Figure 9: AMR levels evolution and cumulative count of sensitive vs. resistant infections treated per antibiotic, when ’Expected reward - greedy’ policy is followed under experiment set 4 conditions (heterogeneous noisy risk-stratified mixed visibility patients, noisy and delayed AMR levels, 10 patients per timestep). Left: single-antibiotic scenario. Middle: two-antibiotic scenario without cross-resistance. Right: two-antibiotic scenario with cross-resistance. Each column shows evolution of true AMR levels (top) and cumulative infected/treated counts per antibiotic over time (bottom rows).\", \"page\": 19, \"index\": 8, \"width\": 976, \"height\": 632}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-009.webp\", \"caption\": \"Figure 8: Comparison of cumulative performance metrics of Expected Reward - Greedy (Accurate Risk Stratification) vs. Hierarchical PPO (Accurate Risk Stratification Environment) vs. Hierarchical PPO (Exaggerated Risk Stratification Environment) vs. Hierarchical PPO (Compressed Risk Stratification Environment), in environments with heterogeneous risk-stratified patient population with varying levels of bias.\", \"page\": 17, \"index\": 9, \"width\": 958, \"height\": 859}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-010.webp\", \"caption\": \"Figure 5: AMR levels evolution and cumulative count of sensitive vs. resistant infections treated per antibiotic, when tuned Hierarchical PPO agent is trained in perfectly observed environment and then has evaluative rollouts performed. Left: single-antibiotic scenario. Middle: two-antibiotic scenario without cross-resistance. Right: two-antibiotic scenario with cross-resistance. Each column shows evolution of true AMR levels (top) and cumulative infected/treated counts per antibiotic over time (bottom rows).\", \"page\": 12, \"index\": 10, \"width\": 976, \"height\": 632}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-011.webp\", \"caption\": \"Figure 10: Comparison of cumulative performance metrics of Fixed Prescribing Rule (Expected Reward - Greedy) vs. Hierarchical PPO vs. Hierarchical Recurrent PPO, in environments with heterogeneous noisy risk-stratified mixed visibility patient populations (noise=0.1), noisy and delayed AMR Levels (delay = 90 timesteps, noise=0.2)\", \"page\": 20, \"index\": 11, \"width\": 686, \"height\": 202}]"
motivation: 旨在解决在部分可观测和延迟反馈的现实环境下，难以定量评估抗生素管理策略对减缓耐药性影响的问题。
method: 开发了兼容 Gymnasium 的仿真框架，并对比评估了平坦 PPO、分层 PPO、循环神经网络及固定处方规则在多种复杂场景下的表现。
result: 实验表明分层强化学习在复杂设置中表现最佳，且患者风险分层信号是决定策略质量的关键因素。
conclusion: 分层强化学习是处理不确定性下抗生素管理策略分析的有效工具，能够实现低耐药性与高临床收益的平衡。
---

## 摘要
抗菌药物耐药性 (AMR) 威胁着抗生素的有效性，但在部分可观测性和延迟反馈的情况下，利用现实世界数据定量评估管理策略仍然具有挑战性。我们开发了“abx_amr_simulator”，这是一个兼容 Gymnasium 的模拟框架，并利用它在四个复杂度递增且具有不同程度信息退化的实验集中，将强化学习 (RL) 处方策略与价值迭代 (VI) 基准及固定处方规则进行了对比评估。在各种场景中，时间抽象始终非常重要：扁平化 PPO 仅在较简单的设置中具有竞争力，而当处方决策对未来耐药性具有延迟且耦合的影响时，通常需要分层 PPO。我们发现添加循环记忆并不能一致地提高性能；其价值取决于具体语境。在某些信息退化的设置中，无记忆策略通过采取保守的更新响应行为表现得更好，而在更复杂的、具有多信号部分可观测性的设置中，循环记忆提供了适度的优势。患者异质性和风险分层信号是策略质量的主要决定因素。当智能体能够区分高风险和低风险患者时，它们能更可靠地学习选择性治疗行为，稳定 AMR 并改善临床结果。夸大的风险分层略优于准确的分层，而压缩的分层则导致了中度性能下降。在结合了噪声患者观测、延迟 AMR 监测和多患者决策的更现实设置中，分层智能体在管理和临床指标上均优于固定处方规则，并收敛至具有较低跨种子方差的保守低 AMR 平衡状态。跨实验结果支持分层 RL 作为不确定性下管理策略分析的最佳工具的效用，同时也强调了性能评估对观测结构和训练时界设计的敏感性。该框架为假设生成以及在转化为政策相关设置之前对处方策略进行压力测试提供了一个受控环境。

## Abstract
Antimicrobial resistance (AMR) threatens antibiotic effectiveness, but quantitatively evaluating stewardship strategies under partial observability and delayed feedback remains difficult in real-world data. We developed 'abx_amr_simulator', a Gymnasium-compatible simulation framework, and used it to benchmark reinforcement learning (RL) prescribing policies against value-iteration (VI) benchmarks and fixed prescribing rules across four experiment sets of increasing complexity, with varying levels of information degradation. Across scenarios, temporal abstraction was consistently important: flat PPO was competitive only in simpler settings, whereas hierarchical PPO was generally needed when prescribing decisions had delayed, coupled effects on future resistance. We found that adding recurrent memory did not uniformly improve performance; its value was context-dependent. In some degraded-information settings, memoryless policies performed better by adopting conservative update-responsive behavior, while in more complex, multi-signal partially observable settings, recurrent memory provided modest advantages. Patient heterogeneity and risk-stratification signals were major determinants of policy quality. When agents could differentiate higher- from lower-risk patients, they more reliably learned selective treatment behavior, stabilized AMR, and improved clinical outcomes. Exaggerated risk stratification modestly outperformed accurate stratification, while compressed stratification produced moderate degradation. In more realistic settings combining noisy patient observations, delayed AMR surveillance, and multi-patient decisions, hierarchical agents outperformed fixed prescribing rules across both stewardship and clinical metrics, converging to conservative low-AMR equilibria with reduced cross-seed variance. Across experiments, results support the utility of hierarchical RL as a best-case policy-analysis tool for stewardship under uncertainty, while also highlighting that performance estimates are sensitive to observation structure and training horizon design. The framework provides a controlled environment for hypothesis generation and for stress-testing prescribing strategies before translation to policy-relevant settings.

---

## 论文详细总结（自动生成）

这是一份关于论文《Reinforcement Learning for Antibiotic Stewardship: Optimizing Prescribing Policies Under Antimicrobial Resistance Dynamics》的结构化深入分析报告：

### 1. 核心问题与整体含义
*   **研究动机**：抗菌药物耐药性（AMR）已成为全球公共卫生危机，但定量评估抗生素管理程序（ASP）的长期影响极具挑战。
*   **核心挑战**：现实世界中，系统状态具有**部分可观测性**（如耐药性监测数据滞后、不全）和**延迟反馈**（当前的处方行为对未来耐药性的影响是长期的）。
*   **研究目标**：开发一个可控的仿真环境，利用强化学习（RL）探索在不确定性和信息退化条件下，如何优化处方策略以平衡“即时临床疗效”与“长期耐药性控制”。

### 2. 方法论
*   **核心框架**：开发了 **`abx_amr_simulator`**，这是一个兼容 Gymnasium 的 Python 仿真环境。
*   **环境建模**：
    *   **患者生成器**：模拟具有不同感染概率和治疗反应的患者群体。
    *   **AMR 漏气球模型 (AMR_LeakyBalloon)**：将耐药性模拟为“压力累积”过程——处方增加压力（气球膨胀），停药则压力随时间衰减（气球漏气）。
    *   **奖励函数**：由个体临床奖励（成功治疗、失败、副作用）组成。值得注意的是，实验中将社区耐药性惩罚权重设为 0，旨在测试智能体是否能仅通过环境动力学自发学到保护抗生素的行为。
*   **关键技术细节**：
    *   **算法选择**：使用近端策略优化（PPO）算法。
    *   **架构对比**：对比了**平坦架构 (Flat PPO)** 和 **分层架构 (Hierarchical PPO)**。分层架构中，上层“管理者”选择下层“工人”（启发式规则），通过时间抽象解决长时程信用分配问题。
    *   **记忆机制**：引入循环神经网络（LSTM）构建 Recurrent PPO，以处理耐药性信息的观测延迟。

### 3. 实验设计
*   **实验场景**：
    1.  单抗生素场景。
    2.  双抗生素（无交叉耐药）场景。
    3.  双抗生素（具有非对称交叉耐药）场景。
*   **实验集 (Experiment Sets)**：
    *   **Set 1 (完美观测)**：基准测试，验证 RL 学习上限。
    *   **Set 2 (延迟/噪声/偏差 AMR)**：模拟现实中监测数据的滞后（如 90 天更新一次）和误差。
    *   **Set 3 (患者异质性)**：测试不同风险分层（准确、夸大、压缩）对策略的影响。
    *   **Set 4 (综合复杂环境)**：结合噪声、延迟、高患者流量和多维度异质性。
*   **Benchmark (基准方法)**：
    *   **固定处方规则 (Expected Reward - Greedy)**：模仿现实中医生根据当前已知信息采取的最优贪婪策略。
    *   **价值迭代 (VI)**：在简单场景下作为理论最优参考。

### 4. 资源与算力
*   **算力说明**：论文**未明确说明**具体的 GPU 型号、数量或总训练时长。
*   **优化过程**：提到了使用 **Optuna** 库进行自动超参数调优，每个实验配置在 5 个随机种子上进行截断训练以筛选参数。
*   **训练规模**：最终训练阶段为每个实验配置初始化了 20 个独立的智能体副本（对应 20 个随机种子），以确保结果的统计可靠性。

### 5. 实验数量与充分性
*   **实验规模**：共进行了 4 组大类实验，细分为约 33 组具体的 RL 实验配置。
*   **充分性评价**：
    *   **多维度消融**：系统对比了平坦 vs 分层、有记忆 vs 无记忆、不同风险分层偏见等变量，实验设计非常全面。
    *   **统计严谨性**：每组实验均使用 20 个随机种子，并进行了多次评估回放（Rollouts），有效降低了 RL 训练随机性带来的偏差。
    *   **公平性**：所有方法（RL 和固定规则）在相同的观测退化条件下进行评估，对比具有高度客观性。

### 6. 主要结论与发现
*   **分层架构的必要性**：在复杂场景下，平坦 PPO 往往无法学习到有效的长期策略，而**分层 PPO (HRL)** 表现出极强的鲁棒性，能有效处理延迟反馈。
*   **风险分层是关键**：智能体利用患者异质性信号进行“分诊”是成功的核心。有趣的是，**“夸大”的风险分层**（让高危更高危，低危更低危）比准确分层更能引导智能体采取保守且有效的处方策略。
*   **固定规则的局限性**：在患者流量大且信息延迟的场景下，传统的贪婪固定规则会导致耐药性迅速飙升至 100%（灾难性失效），而 HRL 能维持低耐药性的稳定平衡。
*   **记忆的价值具有条件性**：添加 LSTM 记忆并不总是提升性能，在某些简单延迟场景下，无记忆策略通过保守的更新响应反而表现更稳健。

### 7. 优点
*   **仿真环境创新**：填补了病原体进化模型与临床决策模型之间的空白，开源了 `abx_amr_simulator` 供社区使用。
*   **现实针对性强**：深入探讨了信息退化（噪声、偏见、延迟）对决策的影响，这非常符合临床实际。
*   **自发性保护行为**：证明了即使不直接惩罚耐药性，只要环境动力学设计合理，分层 RL 也能学到具有前瞻性的抗生素保护策略。

### 8. 不足与局限
*   **病原体抽象化**：为了提高可解释性，模型忽略了具体病原体种类（如金葡菌 vs 大肠杆菌）的差异，这在现实临床中是核心考量因素。
*   **平稳性假设**：假设患者分布和耐药反应曲线在长期内是静态的，未考虑季节性波动或耐药机制的突发进化。
*   **单智能体限制**：模拟的是单一中心化决策者，而现实中抗生素处方是由无数独立医生在信息不完全共享的情况下做出的（多智能体博弈）。
*   **应用限制**：研究结果属于“假设生成”性质，不能直接作为临床指南，需在更复杂的非平稳模型中进一步验证。

（完）
