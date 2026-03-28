---
title: "OPTIMIS: Optimizing Personalized Therapies through Integrated Multiscale Intelligent Simulation"
title_zh: OPTIMIS：通过集成多尺度智能模拟优化个性化治疗
authors: "Su, Z., Wu, Y."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.713941v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 深度强化学习用于计算医学中的个性化治疗优化
tldr: 针对多尺度生物系统控制中确定性模型精度不足与随机模拟速度过慢的矛盾，本研究提出了OPTIMIS框架。该框架融合了微观随机动力学与宏观非线性微分方程，并通过神经常微分方程（Neural ODE）构建快速代理模型。利用强化学习，该系统在工程化细胞疗法中实现了闭环动态给药策略，能提前识别微观预警信号并调整剂量，显著提升了复杂免疫反应的控制成功率。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-713941-v1/fig-001.webp\", \"caption\": \"Table 2: Comparative performance of the AI-driven reinforcement learning policy against standard constant and adaptive heuristic dosing strategies in managing tumor burden and cytokine toxicity across distinct patient phenotypes.\", \"page\": 30, \"index\": 1, \"width\": 926, \"height\": 454}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-713941-v1/fig-002.webp\", \"caption\": \"Table 1: Ablation analysis demonstrating the critical contribution of individual neural network state features to the overall success rate and dosing efficacy of the reinforcement learning agent.\", \"page\": 29, \"index\": 2, \"width\": 926, \"height\": 434}]"
motivation: 传统模型难以兼顾分子层面的随机变异性与AI训练所需的大规模模拟速度。
method: 结合Gillespie随机算法与宏观ODE构建混合系统，并利用Neural ODE代理模型加速强化学习训练。
result: "在高度不稳定的模拟表型中，AI驱动的动态治疗策略将成功控制率提高到了70%以上。"
conclusion: OPTIMIS为多尺度生物系统的个性化、自适应干预提供了一个高效且通用的数字孪生计算框架。
---

## 摘要
在计算医学中，跨多个尺度控制复杂的生物系统仍然是一项重大挑战，因为全身性的疾病行为受到更小尺度上带有噪声的细胞事件的密切影响。标准的确定性模型通常会忽略这种分子变异性，而完全随机模拟的速度又太慢，无法满足训练人工智能所需的重复、高吞吐量交互。为了解决这一问题，我们开发了一种新的基于人工智能的框架，该框架将用于微观受体动力学的离散随机 Gillespie 算法与用于系统宏观行为的连续非线性常微分方程相结合。为了达到深度强化学习（RL）所需的速度，我们将该混合系统压缩为一个可微的神经常微分方程（Neural ODE）代理模型，作为快速数字孪生。作为概念验证，我们将该框架应用于工程化细胞疗法，并利用强化学习智能体在代理环境中学习动态闭环治疗策略。通过追踪微观的、不可预测的细胞活动作为预警信号，人工智能学会了持续调整药物剂量，从而在危险的免疫反应失控之前对其进行预测并加以阻止。这一计算领域的进展将高度不稳定模拟表型中的成功控制率提高到了 70% 以上，并为多尺度生物系统中的自适应干预提供了一个实用且通用的框架。

## Abstract
Controlling complex biological systems across multiple scales remains a major challenge in computational medicine, because whole-body disease behavior is closely shaped by noisy cellular events at much smaller scales. Standard deterministic models often miss this molecular variability, while fully stochastic simulations are too slow for the repeated, high-throughput interactions needed to train artificial intelligence. To address this problem, we developed a new AI-based framework that combines a discrete stochastic Gillespie algorithm for microscale receptor dynamics with continuous, nonlinear ordinary differential equations for systemic macroscale behavior. To reach the speed needed for deep reinforcement learning (RL), we compress this hybrid system into a differentiable Neural ODE surrogate that acts as a fast digital twin. As a proof of concept, we applied this framework to engineered cellular therapy and used RL agents to learn dynamic, closed-loop treatment policies inside the surrogate environment. By tracking microscopic, unpredictable cellular activity as an early-warning signal, the AI learned to continuously adjust the drug dose-anticipating and stopping dangerous immune reactions before they could spiral out of control. This computational advance improved successful control rates to more than 70% in highly unstable simulated phenotypes and provides a practical, general framework for adaptive intervention in multiscale biological systems.

---

## 论文详细总结（自动生成）

这篇论文介绍了一个名为 **OPTIMIS** 的 AI 驱动框架，旨在通过集成多尺度模拟和强化学习，优化 CAR-T 细胞疗法等复杂生物系统的个性化给药方案。以下是对该论文的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
*   **核心挑战**：在计算医学中，生物系统具有高度的**多尺度性**。宏观的疾病进展（如肿瘤负担）深受微观随机事件（如受体结合的“分子抖动”）影响。
*   **现有模型局限**：
    *   **确定性模型（如 QSP/PK-PD）**：忽略了分子层面的随机变异性，难以捕捉极端免疫反应。
    *   **离散随机模型（如 Gillespie 算法）**：计算极其缓慢，无法支持强化学习（RL）所需的大规模重复交互训练。
*   **研究动机**：开发一个既能保留微观生物物理精度，又能提供足够计算速度的“数字孪生”环境，以训练能够实时调整剂量的 AI 智能体，平衡疗效与毒性（如细胞因子风暴 CRS）。

### 2. 方法论
OPTIMIS 采用了一种**“慢-快耦合”的混合架构**，包含四个关键层：
*   **微观随机层**：使用 **Gillespie 随机模拟算法 (SSA)** 模拟免疫突触处的受体动态。它捕捉受体在激活和失活状态之间的随机切换，并受药物（达沙替尼）和细胞因子反馈的调节。
*   **宏观动力学层**：使用非线性**常微分方程 (ODE)** 描述肿瘤细胞、CAR-T 细胞和细胞因子的整体演变。
*   **Neural ODE 代理模型（数字孪生）**：为了提速，研究者将上述混合系统“蒸馏”为一个可微的 **Neural ODE**。该模型学习宏观状态的导数，同时保持与微观受体状态的耦合，充当 RL 训练的高速仿真环境。
*   **强化学习控制器**：采用 **PPO (Proximal Policy Optimization)** 算法。智能体观察包括肿瘤负担、细胞因子水平、受体激活比例及患者表型在内的多维向量，输出连续的药物剂量。

### 3. 实验设计
*   **数据集/场景**：构建了一个包含 240 名虚拟患者的合成队列（120 名标准型，120 名激进型）。激进型患者若不干预，会发生严重的细胞因子风暴。
*   **Benchmark（基准）**：
    *   **无药方案 (No Drug)**：观察自然进展。
    *   **固定剂量方案 (Constant Low/Medium)**：模拟临床常见的静态给药。
    *   **启发式自适应方案 (Heuristic Adaptive)**：基于宏观症状（如细胞因子升高）触发的反应性给药规则。
*   **对比目标**：评估不同策略在肿瘤清除率、毒性控制（细胞因子是否超过安全阈值）和给药效率方面的表现。

### 4. 资源与算力
*   **算力支持**：论文提到计算支持由阿尔伯特·爱因斯坦医学院的高性能计算中心提供。
*   **具体细节**：文中**未明确说明**具体的 GPU 型号、数量或训练总时长。但提到 Neural ODE 的引入是为了实现“毫秒级”的执行速度，以支持高吞吐量的 RL 训练。

### 5. 实验数量与充分性
*   **实验规模**：生成了 12,000 个纵向数据点，涵盖 240 名患者 50 天的治疗轨迹。
*   **消融实验**：设计了 5 组消融实验，分别移除“表型提示”、“受体通道”、“趋势特征”和“历史剂量”，验证了各输入特征对决策的重要性。
*   **充分性评价**：实验设计较为充分，涵盖了从模型拟合精度验证到控制策略有效性对比的全过程。通过区分“标准”和“激进”表型，体现了对患者异质性的关注，实验对比具有较好的客观性。

### 6. 主要结论与发现
*   **微观信号是关键**：微观受体活动是系统性毒性的“早期预警指标”。AI 发现，在宏观细胞因子飙升之前，微观受体状态已发生改变。
*   **“冲浪”策略 (Surfing Policy)**：成熟的 AI 智能体自主学习到了一种三阶段策略：
    1.  **预警制动**：早期高剂量抑制过度激活。
    2.  **受控减量**：逐步减药以允许 CAR-T 杀伤肿瘤。
    3.  **软着陆脉冲**：后期微调剂量防止炎症反弹。
*   **性能提升**：在激进型患者中，传统反应性策略成功率为 0%，而 OPTIMIS 驱动的 RL 策略成功率达到了 **74.2%**。

### 7. 优点
*   **跨尺度融合**：成功解决了微观随机性与宏观确定性模型在 AI 训练中的兼容性问题。
*   **前瞻性控制**：相比于临床上“见招拆招”的反应性给药，该方法具有预测性，能提前拦截危险的免疫级联反应。
*   **可解释性**：通过 Neural ODE 保持了生物学结构的完整性，使得 AI 的决策过程具有一定的生物学解释基础。

### 8. 不足与局限
*   **长期预测漂移**：Neural ODE 在单步预测上精度极高，但在长达 50 天的自由滚动预测（Rollout）中存在累积误差（漂移）。
*   **合成数据依赖**：目前模型完全基于合成数据训练，尚未在真实临床数据集或动物实验数据上进行回溯验证。
*   **表型已知假设**：实验中假设患者表型（标准 vs 激进）是已知的或有提示的，但在临床初期准确识别患者表型本身就是一个难题。
*   **药物单一性**：目前仅模拟了达沙替尼一种调节药物，未考虑多种药物联合作用的复杂性。

（完）
