---
title: "OPTIMIS: Optimizing Personalized Therapies through Integrated Multiscale Intelligent Simulation"
title_zh: OPTIMIS：通过集成多尺度智能模拟优化个性化治疗
authors: "Su, Z., Wu, Y."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.713941v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 深度强化学习用于优化计算医学中的个性化治疗
tldr: "针对复杂生物系统跨尺度控制难题，本研究提出OPTIMIS框架。该框架结合了处理微观受体动力学的随机算法与描述宏观系统行为的非线性微分方程，并通过神经微分方程（Neural ODE）代理模型实现加速。利用强化学习，该系统能根据微观细胞信号动态调整给药策略。在细胞疗法模拟中，该方法成功将不稳定表型的控制率提升至70%以上，为个性化精准医疗提供了高效的计算工具。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-713941-v1/fig-001.webp\", \"caption\": \"Table 2: Comparative performance of the AI-driven reinforcement learning policy against standard constant and adaptive heuristic dosing strategies in managing tumor burden and cytokine toxicity across distinct patient phenotypes.\", \"page\": 30, \"index\": 1, \"width\": 926, \"height\": 454}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-713941-v1/fig-002.webp\", \"caption\": \"Table 1: Ablation analysis demonstrating the critical contribution of individual neural network state features to the overall success rate and dosing efficacy of the reinforcement learning agent.\", \"page\": 29, \"index\": 2, \"width\": 926, \"height\": 434}]"
motivation: 解决传统确定性模型忽略分子变异性且随机模拟速度过慢，导致难以训练人工智能进行复杂生物系统控制的问题。
method: 开发了结合微观随机算法与宏观微分方程的混合框架，并将其压缩为可微分的神经微分方程代理模型以加速强化学习训练。
result: "在工程化细胞疗法模拟中，AI代理通过监测微观细胞活动实现了动态闭环给药，将高度不稳定表型的控制成功率提升至70%以上。"
conclusion: 该框架为多尺度生物系统的自适应干预提供了一种实用且通用的计算方案，能够有效预测并控制危险的免疫反应。
---

## 摘要
在计算医学中，跨多个尺度控制复杂的生物系统仍然是一项重大挑战，因为全身性的疾病行为受到更小尺度上带有噪声的细胞事件的密切影响。标准的确定性模型通常会忽略这种分子变异性，而完全随机的模拟对于训练人工智能所需的重复、高吞吐量交互来说速度太慢。为了解决这一问题，我们开发了一种新的基于人工智能的框架，该框架将用于微观受体动力学的离散随机 Gillespie 算法与用于系统宏观行为的连续非线性常微分方程相结合。为了达到深度强化学习（RL）所需的速度，我们将该混合系统压缩为一个可微的神经常微分方程（Neural ODE）代理模型，作为快速数字孪生。作为概念验证，我们将该框架应用于工程化细胞疗法，并利用强化学习智能体在代理环境中学习动态闭环治疗策略。通过追踪微观的、不可预测的细胞活动作为预警信号，人工智能学会了持续调整药物剂量，从而在危险的免疫反应失控之前对其进行预测并加以阻止。这一计算领域的进展将高度不稳定模拟表型中的成功控制率提高到了 70% 以上，并为多尺度生物系统中的自适应干预提供了一个实用且通用的框架。

## Abstract
Controlling complex biological systems across multiple scales remains a major challenge in computational medicine, because whole-body disease behavior is closely shaped by noisy cellular events at much smaller scales. Standard deterministic models often miss this molecular variability, while fully stochastic simulations are too slow for the repeated, high-throughput interactions needed to train artificial intelligence. To address this problem, we developed a new AI-based framework that combines a discrete stochastic Gillespie algorithm for microscale receptor dynamics with continuous, nonlinear ordinary differential equations for systemic macroscale behavior. To reach the speed needed for deep reinforcement learning (RL), we compress this hybrid system into a differentiable Neural ODE surrogate that acts as a fast digital twin. As a proof of concept, we applied this framework to engineered cellular therapy and used RL agents to learn dynamic, closed-loop treatment policies inside the surrogate environment. By tracking microscopic, unpredictable cellular activity as an early-warning signal, the AI learned to continuously adjust the drug dose-anticipating and stopping dangerous immune reactions before they could spiral out of control. This computational advance improved successful control rates to more than 70% in highly unstable simulated phenotypes and provides a practical, general framework for adaptive intervention in multiscale biological systems.

---

## 论文详细总结（自动生成）

### 论文总结：OPTIMIS —— 集成多尺度智能模拟优化个性化治疗

#### 1. 核心问题与整体含义（研究动机和背景）
在计算医学领域，控制复杂的生物系统（如 CAR-T 细胞疗法）面临巨大的**跨尺度挑战**。全身性的疾病进展（宏观）是由微观尺度上具有随机噪声的细胞事件（如受体结合）驱动的。
*   **研究动机**：传统的确定性模型（如 ODE）无法捕捉分子层面的变异性；而完全随机的模拟（如 Gillespie 算法）计算开销巨大，无法满足强化学习（RL）训练所需的高频交互需求。
*   **核心问题**：如何构建一个既能保留微观生物物理保真度，又能提供足够计算速度以支持 AI 学习闭环控制策略的计算框架，从而解决 CAR-T 治疗中疗效与毒性（细胞因子风暴）的平衡难题。

#### 2. 方法论：核心思想与技术细节
OPTIMIS 框架采用了一种“慢-快耦合”的混合架构，主要包含三个层次：
*   **微观随机模型**：使用 **Gillespie 随机模拟算法 (SSA)** 模拟免疫突触处的受体激活状态。它捕捉了受体在激活（$R_{act}$）和失活（$R_{inact}$）状态之间的随机切换，并考虑了药物（达沙替尼）的抑制作用和细胞因子的反馈调节。
*   **宏观系统模型**：建立非线性常微分方程（ODE）组，描述肿瘤负担（$T$）、CAR-T 细胞数量（$C$）和细胞因子浓度（$I$）的演变。
    *   *公式示例*：肿瘤清除率受活跃受体比例（$\alpha$）调节：$dT/dt = r_T T - k_k C \alpha T$。
*   **Neural ODE 代理模型（数字孪生）**：为了加速计算，研究者将上述混合系统“蒸馏”为一个可微的**神经常微分方程（NeuroODE）**。该代理模型学习宏观状态的导数预测，作为 RL 训练的高速仿真环境。
*   **强化学习控制器**：采用 **近端策略优化（PPO）算法**。智能体观察包括肿瘤、细胞因子、受体状态及患者表型在内的多维向量，输出连续的药物剂量（0-1），实现闭环自适应给药。

#### 3. 实验设计
*   **数据集/场景**：生成了一个包含 240 名虚拟患者（120 名标准型，120 名激进型）的合成队列，涵盖 50 天的临床观察期，共计 12,000 个纵向数据点。
*   **Benchmark（基准）与对比方法**：
    *   **无药治疗（No Drug）**：观察自然进展。
    *   **恒定剂量（Constant Low/Medium）**：固定给药 0.2 或 0.5。
    *   **启发式自适应策略（Heuristic Adaptive）**：基于宏观指标（如细胞因子水平）的简单反应性规则。
*   **消融实验**：通过移除“表型提示”、“受体通道”、“增量特征”和“前序剂量”来验证各输入特征对控制效果的贡献。

#### 4. 资源与算力
*   论文提到计算支持由 **Albert Einstein College of Medicine 的高性能计算中心（HPC）** 提供。
*   **具体参数**：文中**未明确说明**具体的 GPU 型号、数量以及训练总时长。但提到 Neural ODE 的引入是为了将执行速度提升至毫秒级，以支持高吞吐量的 RL 训练。

#### 5. 实验数量与充分性
*   **实验规模**：进行了 240 名患者的完整轨迹模拟，并在 11,760 次状态转移上验证了 Neural ODE 的准确性。
*   **充分性评价**：实验设计较为充分。通过对比多种基线策略和详尽的消融实验，证明了多尺度信息（尤其是微观受体状态）在预防毒性超调中的必要性。实验涵盖了不同风险等级的患者表型，逻辑链条完整，评估指标（成功率、最终肿瘤负担、峰值细胞因子等）较为客观。

#### 6. 主要结论与发现
*   **“冲浪”策略的发现**：成熟的 RL 智能体自主学习到了一种三阶段策略：**预见性重刹**（初期抑制过激反应）、**受控减量**（允许肿瘤清除）和**软着陆脉冲**（防止后期炎症反弹）。
*   **性能提升**：在激进型表型中，传统反应性协议成功率为 0%（均死于细胞因子风暴），而 OPTIMIS 智能体实现了 **74.2% 的治愈成功率**。
*   **早期预警信号**：微观受体活动被证明是比宏观细胞因子更有效的“早期预警指标”，能够让 AI 在毒性爆发前提前介入。

#### 7. 优点（亮点）
*   **跨尺度集成**：成功桥接了随机微观动力学与确定性宏观轨迹，解决了生物物理保真度与计算效率的矛盾。
*   **Neural ODE 的应用**：利用 NeuroODE 作为可微代理模型，不仅加速了训练，还保留了生物系统的连续时间特性。
*   **前瞻性控制**：相比于“见招拆招”的临床启发式方法，RL 展现了预测性干预的能力，显著降低了高危患者的死亡风险。

#### 8. 不足与局限
*   **合成数据依赖**：目前所有结论均基于合成数据集，缺乏真实临床试验数据的验证。
*   **长期预测漂移**：实验显示 Neural ODE 在长程预测（Rollout）中存在一定的累积误差（漂移），虽然对短期控制影响较小，但限制了其作为长期预后工具的可靠性。
*   **模型简化**：仅考虑了达沙替尼这一种调节药物，实际临床环境中的联合用药和复杂的免疫微环境尚未完全建模。
*   **应用限制**：微观受体状态在现实临床中难以实时监测，如何将该“计算生物标志物”转化为临床可测指标仍是挑战。

（完）
