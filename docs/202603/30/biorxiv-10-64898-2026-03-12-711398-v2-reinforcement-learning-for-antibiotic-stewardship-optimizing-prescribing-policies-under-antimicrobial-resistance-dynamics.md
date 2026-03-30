---
title: "Reinforcement Learning for Antibiotic Stewardship: Optimizing Prescribing Policies Under Antimicrobial Resistance Dynamics"
title_zh: 强化学习在抗生素管理中的应用：在抗菌药物耐药性动态下优化处方策略
authors: "Lee, J., Blumberg, S."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.12.711398v2.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 强化学习用于抗生素处方策略优化
tldr: 针对抗生素耐药性（AMR）带来的挑战，本研究开发了abx_amr_simulator仿真框架，并利用强化学习（RL）优化处方策略。研究发现，在处理延迟反馈和部分可观测性时，分层强化学习（Hierarchical PPO）表现优于固定规则和扁平化算法。通过风险分层和时间抽象，RL智能体能有效平衡临床疗效与耐药性控制，为制定抗生素管理政策提供了有力的分析工具。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-001.webp\", \"caption\": \"Figure 4: AMR levels evolution and cumulative count of sensitive vs. resistant infections treated per antibiotic, when tuned Flat PPO agent is trained in perfectly observed environment and then has evaluative rollouts performed. Left: single-antibiotic scenario. Middle: two-antibiotic scenario without cross-resistance. Right: two-antibiotic scenario with cross-resistance. Each column shows evolution of true AMR levels (top) and cumulative infected/treated counts per antibiotic over time (bottom rows).\", \"page\": 11, \"index\": 1, \"width\": 976, \"height\": 629}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-002.webp\", \"caption\": \"Figure 7: Comparison of cumulative performance metrics of Fixed Prescribing Rule (Expected Reward - Greedy) vs. Flat PPO vs. Flat Recurrent PPO vs. Hierarchical PPO vs. Hierarchical Recurrent PPO, in environment with degraded AMR level information. AMR levels affected by update delay = 90 timesteps, noise = 0.2, bias = -0.2.\", \"page\": 15, \"index\": 2, \"width\": 958, \"height\": 1183}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-003.webp\", \"caption\": \"Figure 2: The experimental pipeline consists of three phases. Phase 1 (Tuning): An Optuna hyperparameter search evaluates candidate configurations via truncated training across 5 random seeds, selecting the configuration that maximizes a stability-adjusted objective (mean reward minus a modest variance penalty across seeds). Phase 2 (Training): Twenty agent copies are initialized with the tuned hyperparameters and undergo prolonged training, each using a distinct random seed. Phase 3 (Evaluation): Each trained agent executes three evaluative rollouts in the environment across unseen random seeds; clinical outcome, patient status, and antibiotic response metrics are logged and aggregated for analysis.\", \"page\": 7, \"index\": 3, \"width\": 979, \"height\": 409}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-004.webp\", \"caption\": \"Figure 3: AMR levels evolution and cumulative count of sensitive vs. resistant infections treated per antibiotic, when ’Expected reward - greedy’ policy is followed (where policy is computed using perfectly observed environments). Left: single-antibiotic scenario. Middle: two-antibiotic scenario without cross-resistance. Right: two-antibiotic scenario with cross-resistance. Each column shows evolution of true AMR levels (top) and cumulative infected/treated counts per antibiotic over time (bottom rows).\", \"page\": 10, \"index\": 4, \"width\": 976, \"height\": 631}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-005.webp\", \"caption\": \"Figure 6: Comparison of cumulative performance metrics of Fixed Prescribing Rule (Expected Reward - Greedy) vs. Flat PPO vs. Hierarchical PPO in perfectly observed environment.\", \"page\": 13, \"index\": 5, \"width\": 958, \"height\": 859}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-006.webp\", \"caption\": \"Table 1: Overview of experimental conditions across four experiment sets. Observability, agent architectures, and comparators were systematically varied. All sets evaluated three antibiotic scenarios: single-antibiotic, two-antibiotic without cross-resistance, and two-antibiotic with cross-resistance.\", \"page\": 8, \"index\": 6, \"width\": 975, \"height\": 298}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-007.webp\", \"caption\": \"Figure 1: Schematic overview of the environment and its subcomponents (patient generator, antibiotic leaky balloons, and reward calculator), and the interaction loop between the agent and environment. 1) The environment uses the PatientGenerator to create a patient and present that patient to the agent. 2) The agent decides to prescribe Antibiotic B for the patient. 3) The agent informs the environment that it decided to prescribe Antibiotic B for the current patient. 4) The environment uses the RewardCalculator to compute the reward for the current action, updates each antibiotic’s AMR LeakyBalloon, and advances to the next timestep and next patient.\", \"page\": 4, \"index\": 7, \"width\": 979, \"height\": 1089}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-008.webp\", \"caption\": \"Figure 9: AMR levels evolution and cumulative count of sensitive vs. resistant infections treated per antibiotic, when ’Expected reward - greedy’ policy is followed under experiment set 4 conditions (heterogeneous noisy risk-stratified mixed visibility patients, noisy and delayed AMR levels, 10 patients per timestep). Left: single-antibiotic scenario. Middle: two-antibiotic scenario without cross-resistance. Right: two-antibiotic scenario with cross-resistance. Each column shows evolution of true AMR levels (top) and cumulative infected/treated counts per antibiotic over time (bottom rows).\", \"page\": 19, \"index\": 8, \"width\": 976, \"height\": 632}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-009.webp\", \"caption\": \"Figure 8: Comparison of cumulative performance metrics of Expected Reward - Greedy (Accurate Risk Stratification) vs. Hierarchical PPO (Accurate Risk Stratification Environment) vs. Hierarchical PPO (Exaggerated Risk Stratification Environment) vs. Hierarchical PPO (Compressed Risk Stratification Environment), in environments with heterogeneous risk-stratified patient population with varying levels of bias.\", \"page\": 17, \"index\": 9, \"width\": 958, \"height\": 859}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-010.webp\", \"caption\": \"Figure 5: AMR levels evolution and cumulative count of sensitive vs. resistant infections treated per antibiotic, when tuned Hierarchical PPO agent is trained in perfectly observed environment and then has evaluative rollouts performed. Left: single-antibiotic scenario. Middle: two-antibiotic scenario without cross-resistance. Right: two-antibiotic scenario with cross-resistance. Each column shows evolution of true AMR levels (top) and cumulative infected/treated counts per antibiotic over time (bottom rows).\", \"page\": 12, \"index\": 10, \"width\": 976, \"height\": 632}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-12-711398-v2/fig-011.webp\", \"caption\": \"Figure 10: Comparison of cumulative performance metrics of Fixed Prescribing Rule (Expected Reward - Greedy) vs. Hierarchical PPO vs. Hierarchical Recurrent PPO, in environments with heterogeneous noisy risk-stratified mixed visibility patient populations (noise=0.1), noisy and delayed AMR Levels (delay = 90 timesteps, noise=0.2)\", \"page\": 20, \"index\": 11, \"width\": 686, \"height\": 202}]"
motivation: 针对抗生素耐药性动态变化中存在的观测不完全和反馈延迟问题，寻求最优的抗生素管理处方策略。
method: 开发了兼容Gymnasium的仿真框架，并对比评估了分层强化学习、循环神经网络及固定处方规则在不同复杂场景下的表现。
result: 分层强化学习在复杂且具有延迟效应的场景中表现最佳，且患者风险分层信号是提升策略质量的关键因素。
conclusion: 分层强化学习是处理不确定性下抗生素管理政策分析的有效工具，为临床策略的压力测试提供了受控环境。
---

## 摘要
抗菌药物耐药性（AMR）威胁着抗生素的有效性，但在部分可观测性和延迟反馈的情况下，利用现实世界数据定量评估管理策略仍然具有挑战性。我们开发了 abx_amr_simulator，这是一个兼容 Gymnasium 的仿真框架，并利用它在四个复杂度递增且信息退化程度不同的实验集中，将强化学习（RL）处方策略与价值迭代（VI）基准及固定处方规则进行了对比评估。在各种场景中，时间抽象（temporal abstraction）始终至关重要：扁平化 PPO 仅在较简单的设置中具有竞争力，而当处方决策对未来耐药性具有延迟且耦合的影响时，通常需要分层 PPO（hierarchical PPO）。我们发现，添加循环记忆（recurrent memory）并不能一致地提高性能；其价值取决于具体语境。在某些信息退化的设置中，无记忆策略通过采取保守的更新响应行为表现得更好，而在更复杂、多信号的部分可观测设置中，循环记忆提供了适度的优势。患者异质性和风险分层信号是策略质量的主要决定因素。当智能体能够区分高风险和低风险患者时，它们能更可靠地学习选择性治疗行为，稳定 AMR 并改善临床结果。夸大的风险分层表现略优于准确的分层，而压缩的分层则导致了中度性能下降。在结合了噪声患者观察、延迟 AMR 监测和多患者决策的更现实设置中，分层智能体在管理指标和临床指标上均优于固定处方规则，并收敛至具有较低跨种子方差的保守低 AMR 平衡状态。各项实验结果支持分层 RL 作为不确定性下管理策略分析的最佳工具，同时也强调了性能评估对观察结构和训练时界（training horizon）设计的敏感性。该框架为假设生成以及在转化为政策相关设置之前对处方策略进行压力测试提供了一个受控环境。

## Abstract
Antimicrobial resistance (AMR) threatens antibiotic effectiveness, but quantitatively evaluating stewardship strategies under partial observability and delayed feedback remains difficult in real-world data. We developed abx_amr_simulator, a Gymnasium-compatible simulation framework, and used it to benchmark reinforcement learning (RL) prescribing policies against value-iteration (VI) benchmarks and fixed prescribing rules across four experiment sets of increasing complexity, with varying levels of information degradation.

Across scenarios, temporal abstraction was consistently important: flat PPO was competitive only in simpler settings, whereas hierarchical PPO was generally needed when prescribing decisions had delayed, coupled effects on future resistance. We found that adding recurrent memory did not uniformly improve performance; its value was context-dependent. In some degraded-information settings, memoryless policies performed better by adopting conservative update-responsive behavior, while in more complex, multi-signal partially observable settings, recurrent memory provided modest advantages.

Patient heterogeneity and risk-stratification signals were major determinants of policy quality. When agents could differentiate higher-from lower-risk patients, they more reliably learned selective treatment behavior, stabilized AMR, and improved clinical outcomes. Exaggerated risk stratification modestly outperformed accurate stratification, while compressed stratification produced moderate degradation. In more realistic settings combining noisy patient observations, delayed AMR surveillance, and multi-patient decisions, hierarchical agents outperformed fixed prescribing rules across both stewardship and clinical metrics, converging to conservative low-AMR equilibria with reduced cross-seed variance.

Across experiments, results support the utility of hierarchical RL as a best-case policy-analysis tool for stewardship under uncertainty, while also highlighting that performance estimates are sensitive to observation structure and training horizon design. The framework provides a controlled environment for hypothesis generation and for stress-testing prescribing strategies before translation to policy-relevant settings.

---

## 论文详细总结（自动生成）

### 论文总结：基于强化学习的抗生素处方策略优化研究

#### 1. 核心问题与整体含义（研究动机和背景）
*   **核心问题**：如何在抗菌药物耐药性（AMR）不断上升的背景下，优化抗生素处方策略，以平衡个体临床疗效与长期群体耐药性控制。
*   **研究背景**：
    *   AMR 是全球公共健康威胁，但评估抗生素管理计划（ASP）的效果非常困难。
    *   **现实挑战**：系统具有“部分可观测性”（如耐药性监测数据滞后且有偏）和“延迟反馈”（当前的处方行为对未来耐药性的影响是长期的）。
    *   **研究意义**：通过构建仿真环境 `abx_amr_simulator`，为强化学习（RL）算法提供一个受控的测试平台，探索在信息不完全和不确定性下的最优决策逻辑。

#### 2. 论文提出的方法论
*   **核心思想**：将抗生素处方建模为一个马尔可夫决策过程（MDP），利用分层强化学习（HRL）处理长时界（Long-horizon）的信用分配问题。
*   **关键技术细节**：
    *   **仿真框架**：基于 Gymnasium API 开发。包含 `PatientGenerator`（生成患者属性）、`AMR_LeakyBalloon`（模拟耐药性动态，采用类似气球充放气的累积与衰减模型）和 `RewardCalculator`（计算临床收益）。
    *   **耐药性模型**：通过 Sigmoid 函数将潜在的处方压力映射为可观测的耐药概率。
    *   **智能体架构**：
        *   **扁平化 PPO (Flat PPO)**：直接输出处方动作。
        *   **分层 PPO (Hierarchical PPO)**：管理者（Manager）选择高层策略（Worker），Worker 是基于风险的启发式规则。
        *   **循环神经网络 (Recurrent/LSTM)**：为智能体提供记忆能力，以应对观测延迟。
    *   **奖励函数**：虽然设计了包含个体和社区奖励的标量函数，但实验中主要设定 $\lambda=0$（仅关注个体临床奖励），旨在观察智能体是否能自发学习到保护耐药性的远见行为。

#### 3. 实验设计
*   **场景设置**：
    1.  单抗生素场景。
    2.  双抗生素（无交叉耐药）。
    3.  双抗生素（具有非对称交叉耐药）。
*   **实验集 (Experiment Sets)**：
    *   **Set 1**：完全可观测（基准）。
    *   **Set 2**：AMR 信息延迟（90步更新一次）、有噪声和偏差。
    *   **Set 3**：患者异质性（高/低风险）及感知偏差（夸大或压缩风险）。
    *   **Set 4**：综合复杂场景（高患者流量、噪声观测、延迟监测）。
*   **Benchmark 与对比方法**：
    *   **固定规则基准**：期望收益贪婪策略（Expected Reward - Greedy），模拟现实中遵循指南但缺乏学习能力的临床医生。
    *   **算法对比**：Flat PPO vs. Hierarchical PPO，以及它们的记忆增强版本（Recurrent）。

#### 4. 资源与算力
*   **算力说明**：论文未明确提及具体的 GPU 型号或训练总时长。
*   **优化工具**：使用了 **Optuna** 框架进行自动超参数调优。
*   **训练规模**：每个实验配置使用 20 个不同的随机种子进行训练，以确保结果的统计稳定性。

#### 5. 实验数量与充分性
*   **实验规模**：涵盖了 4 大类实验集，每类实验集下包含 3 种抗生素场景，并对比了 4-5 种不同的智能体架构。
*   **充分性评价**：实验设计非常充分且系统。通过引入随机种子方差分析、消融记忆模块、对比分层架构，客观地展示了不同因素对策略性能的影响。尤其是对“感知偏差”的探讨（Set 3），增强了实验的深度。

#### 6. 主要结论与发现
*   **分层架构的必要性**：在复杂场景下，分层 PPO 显著优于扁平化 PPO，证明了时间抽象在处理 AMR 长期耦合效应中的关键作用。
*   **风险分层的重要性**：患者的异质性信号是策略成功的核心。智能体通过识别高风险患者并进行选择性治疗，能有效稳定 AMR 水平。
*   **记忆模块的局限性**：添加 LSTM 记忆并不总是能提升性能。在某些延迟场景下，无记忆策略通过采取保守行为反而表现更稳健。
*   **感知偏差的影响**：适度“夸大”患者风险分层（Over-stratification）反而能带来更好的群体结果，因为它促使智能体在不确定时更加谨慎。
*   **超越固定规则**：在最现实的 Set 4 中，RL 智能体不仅在耐药性控制上优于固定规则，在临床成功率上也更高，避免了固定规则导致的耐药性“饱和”崩溃。

#### 7. 优点
*   **仿真器创新**：开发了一个模块化、可扩展的 AMR 处方仿真环境，填补了该领域缺乏标准化测试平台的空白。
*   **架构洞察**：明确了分层强化学习在处理医疗决策长时界问题上的优势。
*   **鲁棒性验证**：系统地测试了噪声、延迟和偏差对策略的影响，具有很强的政策分析参考价值。

#### 8. 不足与局限
*   **病原体抽象化**：为了简化模型，忽略了具体病原体种类（如金黄色葡萄球菌 vs. 大肠杆菌）的差异，这在现实临床中是核心考量因素。
*   **平稳性假设**：假设患者分布和耐药动态是平稳的，未考虑现实中季节性流行病或耐药机制进化导致的非平稳性。
*   **单决策者模型**：模拟的是单一中心化决策者，未考虑多名医生或多所医院在去中心化环境下的博弈与竞争。
*   **算法局限**：主要集中在 PPO 算法，未探索其他如离线强化学习（Offline RL）或基于模型的强化学习（Model-based RL）的表现。

（完）
