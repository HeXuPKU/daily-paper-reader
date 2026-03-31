---
title: "OPTIMIS: Optimizing Personalized Therapies through Integrated Multiscale Intelligent Simulation"
title_zh: OPTIMIS：通过集成多尺度智能模拟优化个性化治疗
authors: "Su, Z., Wu, Y."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.713941v1.full.pdf"
tags: ["query:med-ai"]
score: 10.0
evidence: 用于个性化治疗优化的深度强化学习
tldr: "该研究提出了OPTIMIS框架，旨在解决计算医学中跨尺度生物系统控制的难题。通过结合微观随机Gillespie算法与宏观非线性常微分方程，并利用Neural ODE将其压缩为高效的数字孪生模型，该框架实现了深度强化学习的快速训练。在工程化细胞疗法应用中，AI智能体能根据微观细胞活动预判并调节药量，有效防止免疫反应失控，将不稳定表型的控制成功率提升至70%以上。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-713941-v1/fig-001.webp\", \"caption\": \"Table 2: Comparative performance of the AI-driven reinforcement learning policy against standard constant and adaptive heuristic dosing strategies in managing tumor burden and cytokine toxicity across distinct patient phenotypes.\", \"page\": 30, \"index\": 1, \"width\": 926, \"height\": 454}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-713941-v1/fig-002.webp\", \"caption\": \"Table 1: Ablation analysis demonstrating the critical contribution of individual neural network state features to the overall success rate and dosing efficacy of the reinforcement learning agent.\", \"page\": 29, \"index\": 2, \"width\": 926, \"height\": 434}]"
motivation: 传统的确定性模型忽略了分子变异性，而全随机模拟速度太慢，无法满足AI训练所需的高通量交互需求。
method: 开发了一种混合模拟框架，将微观受体动力学与宏观系统行为结合，并采用可微Neural ODE代理模型作为快速数字孪生环境。
result: "强化学习智能体通过监测微观细胞信号实现了闭环动态给药，在高度不稳定的模拟表型中将治疗控制成功率提高到70%以上。"
conclusion: 该框架为多尺度生物系统的自适应干预提供了一种实用且通用的计算方案，展示了AI在个性化精准医疗中的潜力。
---

## 摘要
在计算医学中，跨多个尺度控制复杂的生物系统仍然是一项重大挑战，因为全身疾病行为受到更小尺度上带有噪声的细胞事件的密切影响。标准的确定性模型通常会忽略这种分子变异性，而完全随机模拟对于训练人工智能所需的重复、高吞吐量交互来说速度太慢。为了解决这个问题，我们开发了一种新的基于人工智能的框架，该框架将用于微观受体动力学的离散随机 Gillespie 算法与用于系统宏观行为的连续非线性常微分方程相结合。为了达到深度强化学习（RL）所需的速度，我们将这种混合系统压缩为一个可微的神经常微分方程（Neural ODE）代理模型，作为快速数字孪生。作为概念验证，我们将该框架应用于工程化细胞疗法，并使用强化学习智能体在代理环境中学习动态闭环治疗策略。通过追踪微观、不可预测的细胞活动作为预警信号，人工智能学会了持续调整药物剂量——在危险的免疫反应失控之前对其进行预测并加以阻止。这一计算进展在高度不稳定的模拟表型中将成功控制率提高到 70% 以上，并为多尺度生物系统中的自适应干预提供了一个实用且通用的框架。

## Abstract
Controlling complex biological systems across multiple scales remains a major challenge in computational medicine, because whole-body disease behavior is closely shaped by noisy cellular events at much smaller scales. Standard deterministic models often miss this molecular variability, while fully stochastic simulations are too slow for the repeated, high-throughput interactions needed to train artificial intelligence. To address this problem, we developed a new AI-based framework that combines a discrete stochastic Gillespie algorithm for microscale receptor dynamics with continuous, nonlinear ordinary differential equations for systemic macroscale behavior. To reach the speed needed for deep reinforcement learning (RL), we compress this hybrid system into a differentiable Neural ODE surrogate that acts as a fast digital twin. As a proof of concept, we applied this framework to engineered cellular therapy and used RL agents to learn dynamic, closed-loop treatment policies inside the surrogate environment. By tracking microscopic, unpredictable cellular activity as an early-warning signal, the AI learned to continuously adjust the drug dose--anticipating and stopping dangerous immune reactions before they could spiral out of control. This computational advance improved successful control rates to more than 70% in highly unstable simulated phenotypes and provides a practical, general framework for adaptive intervention in multiscale biological systems.

---

## 论文详细总结（自动生成）

这是一份关于论文 **《OPTIMIS: Optimizing Personalized Therapies through Integrated Multiscale Intelligent Simulation》** 的深度结构化总结：

### 1. 核心问题与整体含义（研究动机与背景）
在计算医学领域，控制复杂的生物系统（如 CAR-T 细胞疗法）面临巨大的**跨尺度挑战**。
*   **研究动机**：全身性的疾病行为（宏观）是由微观尺度上具有随机噪声的细胞事件（如受体结合）决定的。
*   **现有瓶颈**：传统的确定性模型（如 ODE）无法捕捉分子层面的变异性；而完全随机的模拟（如 Gillespie 算法）计算开销极大，无法支持人工智能（AI）训练所需的数百万次高通量交互。
*   **核心目标**：开发一个名为 **OPTIMIS** 的 AI 框架，通过集成微观随机模拟与宏观连续动力学，并利用代理模型加速，实现个性化、闭环的给药策略优化。

### 2. 方法论：核心思想与技术细节
OPTIMIS 采用了一种“慢-快耦合”的混合架构，主要包含三个层次：
*   **微观尺度（随机性）**：使用 **Gillespie 随机模拟算法 (SSA)** 模拟免疫突触处的受体状态切换（激活/失活）。药物（达沙替尼）通过抑制结合速率 $k_{bind}$ 起作用，而细胞因子通过反馈调节增加脱离速率 $k_{unbind}$。
*   **宏观尺度（连续性）**：建立非线性常微分方程（ODE）组，描述肿瘤负担 ($T$)、CAR-T 细胞数量 ($C$) 和系统性细胞因子浓度 ($I$)。其中引入了“风暴惩罚”项 ($S_p$) 来模拟高浓度细胞因子导致的免疫耗竭。
*   **Neural ODE 代理模型（数字孪生）**：为了解决计算速度问题，研究者将上述混合系统压缩为一个可微的 **神经常微分方程 (Neural ODE)**。它学习宏观状态的导数，同时保持与微观受体状态的耦合，充当 RL 训练的高速环境。
*   **强化学习控制器**：采用 **近端策略优化算法 (PPO)**。智能体观察包括肿瘤、细胞因子、受体激活比例及患者表型在内的状态向量，输出连续的药物剂量（0 到 1 之间），以最大化肿瘤清除率并最小化毒性。

### 3. 实验设计
*   **数据集/场景**：生成了一个包含 240 名虚拟患者（120 名标准型，120 名侵略型）的合成队列，涵盖 50 天的临床观察期，共计 12,000 个纵向数据点。
*   **Benchmark（基准对比）**：
    *   **No Drug**：不给药。
    *   **Constant Low/Medium**：固定低剂量 (0.2) 或中剂量 (0.5)。
    *   **Heuristic Adaptive**：基于宏观症状（如细胞因子升高后）才反应的规则化给药策略。
*   **对比维度**：肿瘤清除成功率、峰值细胞因子浓度、累积药量、给药平滑度。

### 4. 资源与算力
*   **算力支持**：论文提到计算支持由 Albert Einstein College of Medicine 的高性能计算中心（HPC）提供。
*   **具体参数**：文中**未明确说明**具体的 GPU 型号、数量或 RL 训练的确切时长。但提到 Neural ODE 的引入将执行速度提升到了毫秒级，从而使深度强化学习的训练变得可行。

### 5. 实验数量与充分性
*   **实验规模**：
    *   **训练集**：240 名患者的合成轨迹。
    *   **消融实验**：设计了 5 组变体（移除表型提示、移除受体通道、移除增量特征、移除前序剂量记忆等），验证了各输入特征的贡献。
    *   **验证集**：在独立的测试队列上进行了多次评估。
*   **充分性评价**：实验设计较为充分，通过对比静态给药和反应式给药，清晰地展示了 RL 的优势。消融实验有力地证明了“微观受体信息”和“表型识别”是实现成功控制的关键。

### 6. 主要结论与发现
*   **“冲浪”策略的发现**：RL 智能体自主学习到了一种三阶段策略：**预判性重刹**（初期抑制过度激活）→ **受控减量**（允许肿瘤清除）→ **软着陆脉冲**（防止后期细胞因子反弹）。
*   **性能提升**：在侵略型（高风险）患者中，传统反应式策略成功率为 0%（均死于细胞因子风暴），而 OPTIMIS 智能体实现了 **74.2%** 的治愈成功率。
*   **早期预警机制**：研究发现，微观受体活动是系统性毒性的“领先指标”，AI 通过监测微观信号，能在宏观症状出现前数日进行干预。

### 7. 优点（亮点）
*   **跨尺度融合**：成功解决了随机微观模型与确定性宏观模型在 AI 训练中的兼容性问题。
*   **Neural ODE 的应用**：利用 Neural ODE 作为代理模型，既保留了物理/生物意义上的耦合，又获得了可微性和极高的计算效率。
*   **前瞻性控制**：相比于临床常见的“见招拆招”（反应式给药），该方法展示了“预判性给药”在处理非线性生物级联反应中的巨大潜力。

### 8. 不足与局限
*   **合成数据依赖**：目前所有结论均基于合成的数学模型，尚未在真实临床数据或动物实验数据上进行回溯性验证。
*   **模型漂移**：实验显示 Neural ODE 在长程预测（Rollout）中存在一定的累积误差（漂移），这可能影响长期治疗方案的稳定性。
*   **表型已知假设**：实验中假设患者的“侵略性/标准型”标签是部分已知的（Class Hint），在实际临床中，准确识别患者表型本身就是一个难题。
*   **应用限制**：目前仅针对 CAR-T 和达沙替尼这一特定场景，推广到其他多尺度生物系统（如组合化疗）仍需重新建模。

（完）
