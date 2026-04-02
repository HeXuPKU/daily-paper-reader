---
title: "Reinforcement Learning for Antibiotic Stewardship: Optimizing Prescribing Policies Under Antimicrobial Resistance Dynamics"
title_zh: 强化学习在抗生素管理中的应用：在抗菌药物耐药性动态下优化处方策略
authors: "Lee, J., Blumberg, S."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.12.711398v2.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 强化学习用于抗生素处方策略
tldr: 针对抗生素耐药性（AMR）带来的挑战，本研究开发了abx_amr_simulator仿真框架，利用强化学习（RL）优化处方策略。研究发现，在处理具有延迟反馈和部分可观测性的复杂医疗场景时，分层强化学习（Hierarchical RL）表现优于固定规则和扁平化算法。通过风险分层和时间抽象，RL智能体能有效平衡临床疗效与耐药性控制，为制定抗生素管理政策提供了有力的分析工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-001.webp\", \"caption\": \"Figure 4: AMR levels evolution and cumulative count of sensitive vs. resistant infections treated per antibiotic, when tuned Flat PPO agent is trained in perfectly observed environment and then has evaluative rollouts performed. Left: single-antibiotic scenario. Middle: two-antibiotic scenario without cross-resistance. Right: two-antibiotic scenario with cross-resistance. Each column shows evolution of true AMR levels (top) and cumulative infected/treated counts per antibiotic over time (bottom rows).\", \"page\": 11, \"index\": 1, \"width\": 976, \"height\": 629}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-002.webp\", \"caption\": \"Figure 7: Comparison of cumulative performance metrics of Fixed Prescribing Rule (Expected Reward - Greedy) vs. Flat PPO vs. Flat Recurrent PPO vs. Hierarchical PPO vs. Hierarchical Recurrent PPO, in environment with degraded AMR level information. AMR levels affected by update delay = 90 timesteps, noise = 0.2, bias = -0.2.\", \"page\": 15, \"index\": 2, \"width\": 958, \"height\": 1183}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-003.webp\", \"caption\": \"Figure 2: The experimental pipeline consists of three phases. Phase 1 (Tuning): An Optuna hyperparameter search evaluates candidate configurations via truncated training across 5 random seeds, selecting the configuration that maximizes a stability-adjusted objective (mean reward minus a modest variance penalty across seeds). Phase 2 (Training): Twenty agent copies are initialized with the tuned hyperparameters and undergo prolonged training, each using a distinct random seed. Phase 3 (Evaluation): Each trained agent executes three evaluative rollouts in the environment across unseen random seeds; clinical outcome, patient status, and antibiotic response metrics are logged and aggregated for analysis.\", \"page\": 7, \"index\": 3, \"width\": 979, \"height\": 409}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-004.webp\", \"caption\": \"Figure 3: AMR levels evolution and cumulative count of sensitive vs. resistant infections treated per antibiotic, when ’Expected reward - greedy’ policy is followed (where policy is computed using perfectly observed environments). Left: single-antibiotic scenario. Middle: two-antibiotic scenario without cross-resistance. Right: two-antibiotic scenario with cross-resistance. Each column shows evolution of true AMR levels (top) and cumulative infected/treated counts per antibiotic over time (bottom rows).\", \"page\": 10, \"index\": 4, \"width\": 976, \"height\": 631}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-005.webp\", \"caption\": \"Figure 6: Comparison of cumulative performance metrics of Fixed Prescribing Rule (Expected Reward - Greedy) vs. Flat PPO vs. Hierarchical PPO in perfectly observed environment.\", \"page\": 13, \"index\": 5, \"width\": 958, \"height\": 859}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-006.webp\", \"caption\": \"Table 1: Overview of experimental conditions across four experiment sets. Observability, agent architectures, and comparators were systematically varied. All sets evaluated three antibiotic scenarios: single-antibiotic, two-antibiotic without cross-resistance, and two-antibiotic with cross-resistance.\", \"page\": 8, \"index\": 6, \"width\": 975, \"height\": 298}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-007.webp\", \"caption\": \"Figure 1: Schematic overview of the environment and its subcomponents (patient generator, antibiotic leaky balloons, and reward calculator), and the interaction loop between the agent and environment. 1) The environment uses the PatientGenerator to create a patient and present that patient to the agent. 2) The agent decides to prescribe Antibiotic B for the patient. 3) The agent informs the environment that it decided to prescribe Antibiotic B for the current patient. 4) The environment uses the RewardCalculator to compute the reward for the current action, updates each antibiotic’s AMR LeakyBalloon, and advances to the next timestep and next patient.\", \"page\": 4, \"index\": 7, \"width\": 979, \"height\": 1089}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-008.webp\", \"caption\": \"Figure 9: AMR levels evolution and cumulative count of sensitive vs. resistant infections treated per antibiotic, when ’Expected reward - greedy’ policy is followed under experiment set 4 conditions (heterogeneous noisy risk-stratified mixed visibility patients, noisy and delayed AMR levels, 10 patients per timestep). Left: single-antibiotic scenario. Middle: two-antibiotic scenario without cross-resistance. Right: two-antibiotic scenario with cross-resistance. Each column shows evolution of true AMR levels (top) and cumulative infected/treated counts per antibiotic over time (bottom rows).\", \"page\": 19, \"index\": 8, \"width\": 976, \"height\": 632}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-009.webp\", \"caption\": \"Figure 8: Comparison of cumulative performance metrics of Expected Reward - Greedy (Accurate Risk Stratification) vs. Hierarchical PPO (Accurate Risk Stratification Environment) vs. Hierarchical PPO (Exaggerated Risk Stratification Environment) vs. Hierarchical PPO (Compressed Risk Stratification Environment), in environments with heterogeneous risk-stratified patient population with varying levels of bias.\", \"page\": 17, \"index\": 9, \"width\": 958, \"height\": 859}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-010.webp\", \"caption\": \"Figure 5: AMR levels evolution and cumulative count of sensitive vs. resistant infections treated per antibiotic, when tuned Hierarchical PPO agent is trained in perfectly observed environment and then has evaluative rollouts performed. Left: single-antibiotic scenario. Middle: two-antibiotic scenario without cross-resistance. Right: two-antibiotic scenario with cross-resistance. Each column shows evolution of true AMR levels (top) and cumulative infected/treated counts per antibiotic over time (bottom rows).\", \"page\": 12, \"index\": 10, \"width\": 976, \"height\": 632}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-011.webp\", \"caption\": \"Figure 10: Comparison of cumulative performance metrics of Fixed Prescribing Rule (Expected Reward - Greedy) vs. Hierarchical PPO vs. Hierarchical Recurrent PPO, in environments with heterogeneous noisy risk-stratified mixed visibility patient populations (noise=0.1), noisy and delayed AMR Levels (delay = 90 timesteps, noise=0.2)\", \"page\": 20, \"index\": 11, \"width\": 686, \"height\": 202}]"
motivation: 针对抗生素耐药性动态演化中存在的观测不完全和反馈延迟问题，探索量化评估和优化抗生素管理策略的方法。
method: 开发了兼容Gymnasium的仿真框架，并对比评估了分层PPO、循环PPO等强化学习算法在不同复杂度和信息降级场景下的表现。
result: 分层强化学习在复杂场景中显著优于固定规则，且患者风险分层信号是提升策略质量的关键因素。
conclusion: 分层强化学习是处理不确定性下抗生素管理政策分析的有效工具，但其性能受观测结构和训练设计的影响。
---

## 摘要
抗菌药物耐药性（AMR）威胁着抗生素的有效性，但在部分可观测性和延迟反馈的情况下，利用现实世界数据定量评估管理策略仍然具有挑战性。我们开发了 abx_amr_simulator，这是一个兼容 Gymnasium 的仿真框架，并利用它在四个复杂度递增且具有不同程度信息退化的实验集中，将强化学习（RL）处方策略与价值迭代（VI）基准及固定处方规则进行了对比评估。在各种场景中，时间抽象（temporal abstraction）始终非常重要：扁平化 PPO（flat PPO）仅在较简单的设置中具有竞争力，而当处方决策对未来耐药性具有延迟且耦合的影响时，通常需要分层 PPO（hierarchical PPO）。我们发现，添加循环记忆（recurrent memory）并不能一致地提高性能；其价值取决于具体语境。在某些信息退化的设置中，无记忆策略通过采取保守的更新响应行为表现得更好，而在更复杂、多信号的部分可观测设置中，循环记忆提供了适度的优势。患者异质性和风险分层信号是策略质量的主要决定因素。当智能体能够区分高风险和低风险患者时，它们能更可靠地学习选择性治疗行为，稳定 AMR 并改善临床结果。夸大的风险分层表现略优于准确的分层，而压缩的分层则导致了中度性能下降。在结合了噪声患者观察、延迟 AMR 监测和多患者决策的更现实设置中，分层智能体在管理和临床指标上均优于固定处方规则，并收敛至具有较低跨种子方差的保守低 AMR 平衡状态。各项实验结果支持分层 RL 作为不确定性下管理策略分析的最佳工具的效用，同时也强调了性能评估对观察结构和训练时域设计的敏感性。该框架为假设生成以及在转化为政策相关设置之前对处方策略进行压力测试提供了一个受控环境。

## Abstract
Antimicrobial resistance (AMR) threatens antibiotic effectiveness, but quantitatively evaluating stewardship strategies under partial observability and delayed feedback remains difficult in real-world data. We developed abx_amr_simulator, a Gymnasium-compatible simulation framework, and used it to benchmark reinforcement learning (RL) prescribing policies against value-iteration (VI) benchmarks and fixed prescribing rules across four experiment sets of increasing complexity, with varying levels of information degradation.

Across scenarios, temporal abstraction was consistently important: flat PPO was competitive only in simpler settings, whereas hierarchical PPO was generally needed when prescribing decisions had delayed, coupled effects on future resistance. We found that adding recurrent memory did not uniformly improve performance; its value was context-dependent. In some degraded-information settings, memoryless policies performed better by adopting conservative update-responsive behavior, while in more complex, multi-signal partially observable settings, recurrent memory provided modest advantages.

Patient heterogeneity and risk-stratification signals were major determinants of policy quality. When agents could differentiate higher-from lower-risk patients, they more reliably learned selective treatment behavior, stabilized AMR, and improved clinical outcomes. Exaggerated risk stratification modestly outperformed accurate stratification, while compressed stratification produced moderate degradation. In more realistic settings combining noisy patient observations, delayed AMR surveillance, and multi-patient decisions, hierarchical agents outperformed fixed prescribing rules across both stewardship and clinical metrics, converging to conservative low-AMR equilibria with reduced cross-seed variance.

Across experiments, results support the utility of hierarchical RL as a best-case policy-analysis tool for stewardship under uncertainty, while also highlighting that performance estimates are sensitive to observation structure and training horizon design. The framework provides a controlled environment for hypothesis generation and for stress-testing prescribing strategies before translation to policy-relevant settings.

---

## 论文详细总结（自动生成）

### 论文结构化深入总结：abx_amr_simulator 仿真环境与抗生素处方优化研究

#### 1. 核心问题与研究背景
*   **研究动机**：抗菌药物耐药性（AMR）已成为全球公共卫生危机，导致每年数百万人死亡。虽然各国推行了抗生素管理程序（ASP），但由于现实世界中存在**部分可观测性**（如耐药性监测数据不全、存在延迟）和**反馈滞后**，很难定量评估不同处方策略的长期影响。
*   **核心问题**：如何在信息不透明、决策后果延迟显现的复杂动态系统中，找到平衡“即时临床疗效”与“长期耐药性控制”的最优处方策略？

#### 2. 方法论与核心技术
*   **核心思想**：开发一个名为 `abx_amr_simulator` 的仿真框架（基于 Gymnasium API），将抗生素处方建模为马尔可夫决策过程（MDP），并利用强化学习（RL）寻找最优策略。
*   **关键技术组件**：
    *   **PatientGenerator**：生成具有不同临床特征（感染概率、自愈率等）的合成患者。
    *   **AMR_LeakyBalloon 模型**：将耐药性动态模拟为“漏气气球”。处方增加压力（气球膨胀），停止处方则压力随时间衰减（气球漏气）。通过 Sigmoid 函数将潜在压力映射为可观测的耐药概率。
    *   **分层强化学习（Hierarchical RL）**：引入“经理-工人”架构。经理负责高层策略选择，工人（Heuristic Workers）执行基于风险的固定规则。这种时间抽象（Temporal Abstraction）有助于解决长时程信用分配问题。
    *   **算法实现**：主要采用近端策略优化算法（PPO），并对比了扁平化（Flat）、循环（Recurrent/LSTM）和分层（Hierarchical）三种变体。

#### 3. 实验设计与基准对比
*   **实验场景**：涵盖三种抗生素配置（单药、双药无交叉耐药、双药有交叉耐药）。
*   **实验集（Experiment Sets）**：
    *   **Set 1**：完美观测（基准）。
    *   **Set 2**：AMR 观测存在延迟（90步更新一次）、噪声和偏差。
    *   **Set 3**：患者属性异质化（高/低风险组），并测试观测偏差（准确、夸大、压缩风险）。
    *   **Set 4**：综合复杂场景（高患者流量、多重噪声、延迟观测、部分可见性）。
*   **Benchmark（基准方法）**：
    *   **Expected Reward - Greedy**：模仿现实中临床医生的固定规则，即根据当前可见信息选择预期收益最高的药物。
    *   **Value Iteration (VI)**：在简单场景下作为理论上限。

#### 4. 资源与算力消耗
*   **算力说明**：论文**未明确列出**具体的 GPU 型号、数量或总训练时长。
*   **计算细节**：提到了使用 **Optuna** 库进行自动超参数调优。在训练阶段，每个实验配置使用了 **20 个不同的随机种子**进行重复训练，以评估策略的稳定性和收敛性。这表明实验过程涉及大量的并行计算任务。

#### 5. 实验数量与充分性
*   **实验规模**：论文设计了 4 个大类实验集，细分为数十种具体配置（如表 1 所示）。
*   **充分性评价**：
    *   **多维度覆盖**：实验从简单的单药场景过渡到复杂的交叉耐药和信息缺失场景，逻辑严密。
    *   **消融与对比**：对比了记忆（Recurrent）与无记忆、扁平与分层架构，实验设计较为充分。
    *   **客观性**：通过多种子训练和独立评估 Rollout，降低了随机性对结论的影响。

#### 6. 主要结论与发现
*   **分层架构的必要性**：在复杂场景下，扁平化 PPO 往往失效，而分层 RL（HRL）通过时间抽象能更好地处理耐药性的延迟反馈。
*   **风险分层的重要性**：当智能体能识别患者风险差异时，性能大幅提升。有趣的是，**“夸大”风险差异**（Over-stratification）比准确分层更能引导智能体采取保守处方，从而更好地稳定 AMR。
*   **固定规则的局限**：在患者流量大且信息延迟的场景下，传统的“贪婪”固定规则会导致 AMR 迅速飙升至 100%，而 RL 智能体能维持低 AMR 的平衡。
*   **记忆的作用**：循环记忆（LSTM）并非万能，在某些简单延迟场景下，无记忆策略反而更稳健。

#### 7. 论文亮点与优点
*   **填补空白**：首次将患者层面的临床决策与群体层面的 AMR 演化动态结合在强化学习框架中。
*   **仿真器设计**：`abx_amr_simulator` 具有高度模块化和可扩展性，兼容标准 Gymnasium 接口，便于后续研究者使用。
*   **策略鲁棒性**：证明了即使不直接在奖励函数中加入 AMR 惩罚（仅优化临床收益），只要环境动态设计合理，RL 也能自发学到保护抗生素效力的长远策略。

#### 8. 不足与局限
*   **病原体抽象**：为了简化模型，论文忽略了具体病原体种类（Pathogen Identity），这与现实中基于特定细菌的药敏试验（Antibiogram）有差距。
*   **平稳性假设**：假设患者分布和耐药动态在长时程内是平稳的，未考虑季节性波动或耐药机制的突发进化。
*   **单决策者模型**：模拟的是单一中心化处方者，未考虑现实中多名医生、多个医疗机构之间缺乏协调的博弈行为。
*   **算法局限**：主要集中在 PPO 算法，未探索其他如离线强化学习（Offline RL）或基于模型的强化学习（Model-based RL）。

（完）
