---
title: "Reinforcement Learning for Antibiotic Stewardship: Optimizing Prescribing Policies Under Antimicrobial Resistance Dynamics"
title_zh: 强化学习用于抗生素管理：在抗生素耐药性动态下优化处方策略
authors: "Lee, J., Blumberg, S."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.12.711398v2.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 用于优化抗生素处方策略的强化学习
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
抗生素耐药性 (AMR) 威胁着抗生素的有效性，但在部分可观测性和延迟反馈的情况下，利用现实世界数据定量评估管理策略仍然具有挑战性。我们开发了“abx_amr_simulator”，这是一个兼容 Gymnasium 的仿真框架，并利用它在四个复杂度递增且具有不同程度信息退化的实验集中，将强化学习 (RL) 处方策略与价值迭代 (VI) 基准及固定处方规则进行了对比评估。在各种场景中，时间抽象始终非常重要：扁平化 PPO 仅在较简单的设置中具有竞争力，而当处方决策对未来耐药性具有延迟且耦合的影响时，通常需要分层 PPO。我们发现，添加循环记忆并不能一致地提高性能；其价值取决于具体语境。在某些信息退化的设置中，无记忆策略通过采取保守的更新响应行为表现得更好，而在更复杂、多信号的部分可观测设置中，循环记忆提供了适度的优势。患者异质性和风险分层信号是策略质量的主要决定因素。当智能体能够区分高风险和低风险患者时，它们能更可靠地学习选择性治疗行为，稳定 AMR 并改善临床结果。夸大的风险分层表现略优于准确的分层，而压缩的分层则导致了中度性能下降。在结合了噪声患者观测、延迟 AMR 监测和多患者决策的更现实设置中，分层智能体在管理和临床指标上均优于固定处方规则，并收敛到具有较低跨种子方差的保守低 AMR 平衡状态。实验结果支持分层 RL 作为不确定性下管理策略分析的最佳工具，同时也强调了性能评估对观测结构和训练时界设计的敏感性。该框架为假设生成以及在转化为政策相关设置之前对抗生素处方策略进行压力测试提供了一个受控环境。

## Abstract
Antimicrobial resistance (AMR) threatens antibiotic effectiveness, but quantitatively evaluating stewardship strategies under partial observability and delayed feedback remains difficult in real-world data. We developed 'abx_amr_simulator', a Gymnasium-compatible simulation framework, and used it to benchmark reinforcement learning (RL) prescribing policies against value-iteration (VI) benchmarks and fixed prescribing rules across four experiment sets of increasing complexity, with varying levels of information degradation. Across scenarios, temporal abstraction was consistently important: flat PPO was competitive only in simpler settings, whereas hierarchical PPO was generally needed when prescribing decisions had delayed, coupled effects on future resistance. We found that adding recurrent memory did not uniformly improve performance; its value was context-dependent. In some degraded-information settings, memoryless policies performed better by adopting conservative update-responsive behavior, while in more complex, multi-signal partially observable settings, recurrent memory provided modest advantages. Patient heterogeneity and risk-stratification signals were major determinants of policy quality. When agents could differentiate higher- from lower-risk patients, they more reliably learned selective treatment behavior, stabilized AMR, and improved clinical outcomes. Exaggerated risk stratification modestly outperformed accurate stratification, while compressed stratification produced moderate degradation. In more realistic settings combining noisy patient observations, delayed AMR surveillance, and multi-patient decisions, hierarchical agents outperformed fixed prescribing rules across both stewardship and clinical metrics, converging to conservative low-AMR equilibria with reduced cross-seed variance. Across experiments, results support the utility of hierarchical RL as a best-case policy-analysis tool for stewardship under uncertainty, while also highlighting that performance estimates are sensitive to observation structure and training horizon design. The framework provides a controlled environment for hypothesis generation and for stress-testing prescribing strategies before translation to policy-relevant settings.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 `abx_amr_simulator` 的仿真框架，旨在利用强化学习（RL）优化抗生素处方策略，以应对全球性的抗生素耐药性（AMR）挑战。以下是对该论文的深度结构化总结：

### 1. 核心问题与研究动机
*   **核心问题**：如何在保证患者即时临床疗效的同时，通过优化处方决策来减缓长期的抗生素耐药性演变？
*   **研究背景**：
    *   **现实挑战**：抗生素管理程序（ASP）的评估受限于数据的“部分可观测性”（如无法直接观测病原体演变）和“延迟反馈”（药敏实验报告通常滞后且不频繁）。
    *   **现有研究不足**：以往的仿真多集中在病原体进化层面，缺乏患者临床动态与群体耐药性之间的闭环反馈模型；而机器学习研究多侧重于静态预测而非动态策略优化。

### 2. 方法论
*   **核心思想**：将抗生素处方建模为一个具有长时界（Long-horizon）和部分可观测性的序列决策问题，利用强化学习在模拟环境中探索最优平衡点。
*   **关键技术细节**：
    *   **仿真环境 (`abx_amr_simulator`)**：基于 Gymnasium 接口，包含患者生成器、耐药性模型（AMR_LeakyBalloon）和奖励计算器。
    *   **耐药性模型（漏气气球模型）**：将耐药性建模为“压力累积”过程。处方会增加内部压力，停止处方则压力随时间衰减；通过 Sigmoid 函数将潜在压力映射为可观测的耐药概率。
    *   **智能体架构**：
        *   **平坦 PPO (Flat PPO)**：直接输出处方动作。
        *   **分层 PPO (Hierarchical PPO)**：管理者（Manager）选择高层策略（Worker），Worker 执行具体的临床规则。这种时间抽象有助于解决长时界信用分配问题。
        *   **循环神经网络 (Recurrent/LSTM)**：用于处理时间上的部分可观测性，帮助智能体在信息过时期间维持内部状态。
    *   **奖励函数**：平衡个体临床收益（治愈、失败、副作用）与社区耐药性惩罚。实验中主要测试仅基于临床收益（$\lambda=0$）时，智能体是否能自发学习到保护耐药性的行为。

### 3. 实验设计
*   **场景设置**：涵盖三种抗生素场景（单药、双药无交叉耐药、双药有交叉耐药）。
*   **实验集 (Experiment Sets)**：
    1.  **完全可观测**：基准测试，验证 RL 学习能力。
    2.  **延迟/噪声/偏差 AMR 信息**：模拟现实中滞后的药敏报告。
    3.  **患者异质性与感知偏差**：测试不同风险等级患者对策略的影响。
    4.  **综合复杂场景**：结合噪声、延迟、高患者流量和异质性。
*   **基准方法 (Benchmark)**：
    *   **固定处方规则 (Expected Reward - Greedy)**：模仿现实中医生根据当前可用信息采取的最优临床决策（贪婪策略）。
    *   **对比方法**：Flat PPO vs. Hierarchical PPO，Memoryless vs. Recurrent。

### 4. 资源与算力
*   **算力说明**：论文**未明确说明**具体的 GPU 型号或训练时长。
*   **软件栈**：使用了 `stable-baselines3` 实现 PPO 算法，利用 `Optuna` 进行自动化超参数调优。
*   **训练规模**：每个实验配置运行 20 个不同的随机种子，以评估策略的稳定性和鲁棒性。

### 5. 实验数量与充分性
*   **实验规模**：共进行了 4 组大类实验，每类实验下细分多种抗生素场景和观测条件，总计进行了数十组强化学习训练任务。
*   **充分性评价**：实验设计非常**充分且系统**。通过从简单到复杂的阶梯式设计，隔离了观测噪声、时间延迟和患者异质性等变量。使用 20 个随机种子进行训练和评估，确保了结果的统计客观性，避免了强化学习中常见的随机性偏差。

### 6. 主要结论与发现
*   **架构决定性能**：在复杂场景下，**分层强化学习 (HRL)** 显著优于平坦架构。平坦 PPO 在处理延迟反馈时表现挣扎，而 HRL 能有效捕捉长期的耐药性动态。
*   **风险分层是关键**：当智能体能识别患者风险差异时，会采取“选择性治疗”，仅对高危患者用药，从而在不牺牲临床收益的情况下稳定耐药性。
*   **记忆的局限性**：添加循环记忆（LSTM）并不总是有效。在某些简单延迟场景下，无记忆策略通过采取保守行为反而更稳健。
*   **固定规则的失效**：在患者流量大且信息模糊的场景下，传统的贪婪处方规则会导致耐药性迅速飙升至 100%，而 RL 智能体能收敛到保守的低耐药平衡态。

### 7. 优点与亮点
*   **时间抽象的应用**：成功证明了分层强化学习在解决医疗决策中“即时收益 vs 长期耐药”矛盾上的优越性。
*   **高度可定制的仿真器**：`abx_amr_simulator` 为抗生素管理提供了一个标准化的压力测试平台，支持多种噪声和偏差模拟。
*   **自发性管理行为**：证明了即使不显式惩罚耐药性，只要环境动态设计合理，智能体也能为了长期临床收益而自发保护抗生素效力。

### 8. 不足与局限
*   **病原体抽象化**：为了简化模型，忽略了具体病原体种类（如金黄色葡萄球菌 vs 大肠杆菌）的差异，这在现实临床中是核心考量因素。
*   **平稳性假设**：假设患者分布和耐药演变曲线在长时期内是静态的，未考虑季节性波动或突发的新型耐药机制。
*   **单决策者模型**：模拟的是单一中心化决策者，而现实中处方行为是多名医生在信息不完全共享的情况下独立做出的（多智能体问题）。
*   **应用限制**：结果属于假设生成性质，不能直接作为临床指南，需在更复杂的非平稳模型中进一步验证。

（完）
