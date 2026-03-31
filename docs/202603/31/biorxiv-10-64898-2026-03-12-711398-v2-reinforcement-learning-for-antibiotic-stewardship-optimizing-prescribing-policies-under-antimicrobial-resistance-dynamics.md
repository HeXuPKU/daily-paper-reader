---
title: "Reinforcement Learning for Antibiotic Stewardship: Optimizing Prescribing Policies Under Antimicrobial Resistance Dynamics"
title_zh: 强化学习在抗生素管理中的应用：在抗菌药物耐药性动态下优化处方策略
authors: "Lee, J., Blumberg, S."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.12.711398v2.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 用于抗生素管理和优化医疗处方策略的强化学习
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
抗菌药物耐药性（AMR）威胁着抗生素的有效性，但在部分可观测性和延迟反馈的情况下，利用现实世界数据定量评估管理策略仍然具有挑战性。我们开发了 abx_amr_simulator，这是一个兼容 Gymnasium 的仿真框架，并利用它在四个复杂度递增且具有不同程度信息退化的实验集中，将强化学习（RL）处方策略与价值迭代（VI）基准及固定处方规则进行了对比评估。在各种场景中，时间抽象（temporal abstraction）始终非常重要：扁平化 PPO（flat PPO）仅在较简单的设置中具有竞争力，而当处方决策对未来耐药性具有延迟且耦合的影响时，通常需要分层 PPO（hierarchical PPO）。我们发现，添加循环记忆（recurrent memory）并不能一致地提高性能；其价值取决于具体语境。在某些信息退化的设置中，无记忆策略通过采取保守的更新响应行为表现得更好，而在更复杂、多信号的部分可观测设置中，循环记忆提供了适度的优势。患者异质性和风险分层信号是策略质量的主要决定因素。当智能体能够区分高风险和低风险患者时，它们能更可靠地学习选择性治疗行为，稳定 AMR 并改善临床结果。夸大的风险分层表现略优于准确的分层，而压缩的分层则导致了中度性能下降。在结合了噪声患者观察、延迟 AMR 监测和多患者决策的更现实设置中，分层智能体在管理和临床指标上均优于固定处方规则，并收敛至具有较低跨种子方差的保守低 AMR 平衡状态。各项实验结果支持分层 RL 作为不确定性下管理策略分析的最佳工具的效用，同时也强调了性能评估对观察结构和训练时域设计的敏感性。该框架为假设生成以及在转化为政策相关设置之前对处方策略进行压力测试提供了一个受控环境。

## Abstract
Antimicrobial resistance (AMR) threatens antibiotic effectiveness, but quantitatively evaluating stewardship strategies under partial observability and delayed feedback remains difficult in real-world data. We developed abx_amr_simulator, a Gymnasium-compatible simulation framework, and used it to benchmark reinforcement learning (RL) prescribing policies against value-iteration (VI) benchmarks and fixed prescribing rules across four experiment sets of increasing complexity, with varying levels of information degradation.

Across scenarios, temporal abstraction was consistently important: flat PPO was competitive only in simpler settings, whereas hierarchical PPO was generally needed when prescribing decisions had delayed, coupled effects on future resistance. We found that adding recurrent memory did not uniformly improve performance; its value was context-dependent. In some degraded-information settings, memoryless policies performed better by adopting conservative update-responsive behavior, while in more complex, multi-signal partially observable settings, recurrent memory provided modest advantages.

Patient heterogeneity and risk-stratification signals were major determinants of policy quality. When agents could differentiate higher-from lower-risk patients, they more reliably learned selective treatment behavior, stabilized AMR, and improved clinical outcomes. Exaggerated risk stratification modestly outperformed accurate stratification, while compressed stratification produced moderate degradation. In more realistic settings combining noisy patient observations, delayed AMR surveillance, and multi-patient decisions, hierarchical agents outperformed fixed prescribing rules across both stewardship and clinical metrics, converging to conservative low-AMR equilibria with reduced cross-seed variance.

Across experiments, results support the utility of hierarchical RL as a best-case policy-analysis tool for stewardship under uncertainty, while also highlighting that performance estimates are sensitive to observation structure and training horizon design. The framework provides a controlled environment for hypothesis generation and for stress-testing prescribing strategies before translation to policy-relevant settings.

---

## 论文详细总结（自动生成）

### 论文总结：abx_amr_simulator —— 抗菌药物耐药性下的抗生素处方策略优化仿真环境

#### 1. 核心问题与整体含义（研究动机和背景）
抗菌药物耐药性（AMR）是全球公共卫生面临的重大威胁。在现实临床环境中，评估抗生素管理程序（ASP）的长期影响极具挑战，原因在于：
*   **部分可观测性**：真实的耐药水平和病原体选择压力难以实时、准确测量。
*   **反馈延迟**：药敏实验（如抗生素谱）通常存在显著的时间滞后（如年度更新）。
*   **决策复杂性**：处方决策需要在即时临床获益（治愈患者）与长期群体成本（诱导耐药）之间进行权衡。
本研究旨在开发一个受控的仿真环境 `abx_amr_simulator`，利用强化学习（RL）探索在信息不完全和延迟反馈条件下的最优处方策略。

#### 2. 论文提出的方法论
*   **仿真框架**：基于 Python 和 Gymnasium API 开发。包含三个核心组件：
    *   **PatientGenerator**：生成具有不同感染概率、康复概率等属性的合成患者。
    *   **AMR_LeakyBalloon 模型**：将耐药性模拟为“漏气气球”，处方压力增加耐药水平，停止处方则耐药性随时间缓慢衰减。
    *   **RewardCalculator**：计算奖励函数，平衡个体临床获益（治愈、失败、副作用）与社区耐药惩罚（本研究中主要关注长时程临床获益驱动的自发管理）。
*   **核心算法**：
    *   **PPO（近端策略优化）**：作为基础 RL 算法。
    *   **分层强化学习（Hierarchical RL）**：引入“启发式工人（Heuristic Workers）”作为宏动作，由上层经理（Manager）决定何时切换策略，以解决长时程信用分配问题。
    *   **循环神经网络（Recurrent PPO）**：集成 LSTM 以处理具有时间依赖性的部分可观测状态。

#### 3. 实验设计
研究设计了四个复杂度递增的实验集，涵盖三种抗生素场景（单药、双药无交叉耐药、双药有交叉耐药）：
*   **实验集 1（完美观测）**：基准测试，验证 RL 是否能达到理论最优。
*   **实验集 2（延迟/噪声 AMR 观测）**：模拟现实中过时的抗生素谱数据。
*   **实验集 3（患者异质性与感知偏差）**：测试智能体在不同风险分层信号下的表现。
*   **实验集 4（综合不确定性）**：结合噪声、延迟、异质性和高患者流量（每步 10 人）的复杂场景。
*   **Benchmark（基准）**：**“期望奖励-贪婪（Expected-reward greedy）”**固定规则，模拟遵循静态指南且不具备学习能力的临床医生。

#### 4. 资源与算力
*   **超参数调优**：使用 **Optuna** 框架进行自动化调优。
*   **训练规模**：每个实验配置初始化 **20 个独立随机种子**进行训练，以评估策略的稳定性和收敛性。
*   **算力说明**：论文**未明确提及**具体的 GPU 型号、数量或具体的训练总时长。但考虑到 PPO 在此类离散动作空间仿真环境中的特性，通常在标准工作站级 CPU/GPU 上即可完成。

#### 5. 实验数量与充分性
*   **实验规模**：共进行了数十组核心实验（4 个实验集 × 3 种抗生素场景 × 多种智能体架构）。
*   **充分性**：实验设计非常系统，通过逐步引入噪声、延迟和异质性，清晰地展示了不同算法组件（如分层架构、记忆模块）的增量价值。
*   **客观性**：通过多种子训练和多次评估 rollout 减少了随机性干扰，并对比了固定规则基准，实验结果具有较强的说服力。

#### 6. 主要结论与发现
*   **分层架构的必要性**：在复杂场景中，扁平化 PPO 往往失效，而分层 RL（HRL）通过时间抽象能更好地处理耐药性的延迟效应。
*   **风险分层是关键**：智能体利用患者异质性（风险高低）进行“分诊”是稳定 AMR 的核心。有趣的是，**夸大的风险分层信号**（感知到的风险差异大于实际）反而能诱导更保守、更有效的管理行为。
*   **记忆模块的局限性**：添加 LSTM 并不总是提升性能。在某些简单延迟场景下，无记忆策略通过采取极度保守的“更新响应”行为反而表现更好。
*   **固定规则的崩溃**：在患者流量大且信息模糊的场景（实验集 4）中，固定规则会导致耐药性迅速饱和（100%），而 HRL 能维持低耐药的平衡状态。

#### 7. 优点
*   **填补空白**：提供了一个专门用于抗生素管理政策压力测试的开源 Gymnasium 环境。
*   **架构创新**：证明了分层强化学习在处理具有长期环境反馈的医疗决策问题上的优越性。
*   **现实意义**：模拟了抗生素谱延迟和患者观察噪声，研究结论对现实中 ASP 的设计具有启发性（如强调风险分层的重要性）。

#### 8. 不足与局限
*   **病原体抽象**：为了简化模型，忽略了具体病原体身份（如金黄色葡萄球菌 vs 大肠杆菌），这在现实药敏分析中是核心要素。
*   **平稳性假设**：假设患者分布和耐药动态在长时程内是平稳的，未考虑季节性波动或耐药机制的进化漂移。
*   **单决策者模型**：模拟的是单一中心化处方者，未考虑多名医生或多机构之间的博弈与协作。
*   **应用限制**：结果属于“假设生成”性质，不能直接作为临床指南，需进一步在更复杂的流行病学模型中验证。

（完）
