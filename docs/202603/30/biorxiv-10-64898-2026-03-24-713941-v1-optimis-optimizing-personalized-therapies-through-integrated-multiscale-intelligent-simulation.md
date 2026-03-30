---
title: "OPTIMIS: Optimizing Personalized Therapies through Integrated Multiscale Intelligent Simulation"
title_zh: OPTIMIS：通过集成多尺度智能模拟优化个性化治疗
authors: "Su, Z., Wu, Y."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.713941v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 深度强化学习用于个性化治疗优化
tldr: "该研究提出OPTIMIS框架，通过结合微观随机算法与宏观微分方程，并利用Neural ODE构建高效数字孪生模型，解决了跨尺度生物系统模拟慢、难以训练AI的难题。在细胞疗法应用中，强化学习智能体能预判并调节药量，防止免疫反应失控，将不稳定表型的控制成功率提升至70%以上，为个性化治疗提供了通用方案。"
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-713941-v1/fig-001.webp\", \"caption\": \"Table 2: Comparative performance of the AI-driven reinforcement learning policy against standard constant and adaptive heuristic dosing strategies in managing tumor burden and cytokine toxicity across distinct patient phenotypes.\", \"page\": 30, \"index\": 1, \"width\": 926, \"height\": 454}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-713941-v1/fig-002.webp\", \"caption\": \"Table 1: Ablation analysis demonstrating the critical contribution of individual neural network state features to the overall success rate and dosing efficacy of the reinforcement learning agent.\", \"page\": 29, \"index\": 2, \"width\": 926, \"height\": 434}]"
motivation: 传统的确定性模型忽略了分子变异性，而全随机模拟速度太慢，无法满足AI训练所需的高通量交互需求。
method: 开发了一种混合多尺度框架，将微观受体动力学与宏观系统行为结合，并采用可微Neural ODE代理模型作为快速数字孪生环境。
result: "强化学习智能体通过监测微观细胞信号实现了闭环动态给药，在高度不稳定的模拟表型中将治疗控制成功率提高到70%以上。"
conclusion: 该框架为多尺度生物系统的自适应干预提供了一种实用且通用的方法，展示了AI在优化个性化治疗方案中的巨大潜力。
---

## 摘要
在计算医学中，跨多个尺度控制复杂的生物系统仍然是一个重大挑战，因为全身疾病行为受到更小尺度上噪声细胞事件的密切影响。标准的确定性模型通常会忽略这种分子变异性，而完全随机模拟对于训练人工智能所需的重复、高吞吐量交互来说速度太慢。为了解决这个问题，我们开发了一种新的基于人工智能的框架，该框架将用于微观受体动力学的离散随机 Gillespie 算法与用于系统宏观行为的连续非线性常微分方程（ODE）相结合。为了达到深度强化学习（RL）所需的速度，我们将这种混合系统压缩为一个可微的神经常微分方程（Neural ODE）代理模型，作为快速数字孪生。作为概念验证，我们将该框架应用于工程化细胞疗法，并使用强化学习智能体在代理环境中学习动态闭环治疗策略。通过追踪微观、不可预测的细胞活动作为预警信号，人工智能学会了持续调整药物剂量——在危险的免疫反应失控之前对其进行预测并加以阻止。这一计算进展在高度不稳定的模拟表型中将成功控制率提高到 70% 以上，并为多尺度生物系统中的自适应干预提供了一个实用且通用的框架。

## Abstract
Controlling complex biological systems across multiple scales remains a major challenge in computational medicine, because whole-body disease behavior is closely shaped by noisy cellular events at much smaller scales. Standard deterministic models often miss this molecular variability, while fully stochastic simulations are too slow for the repeated, high-throughput interactions needed to train artificial intelligence. To address this problem, we developed a new AI-based framework that combines a discrete stochastic Gillespie algorithm for microscale receptor dynamics with continuous, nonlinear ordinary differential equations for systemic macroscale behavior. To reach the speed needed for deep reinforcement learning (RL), we compress this hybrid system into a differentiable Neural ODE surrogate that acts as a fast digital twin. As a proof of concept, we applied this framework to engineered cellular therapy and used RL agents to learn dynamic, closed-loop treatment policies inside the surrogate environment. By tracking microscopic, unpredictable cellular activity as an early-warning signal, the AI learned to continuously adjust the drug dose--anticipating and stopping dangerous immune reactions before they could spiral out of control. This computational advance improved successful control rates to more than 70% in highly unstable simulated phenotypes and provides a practical, general framework for adaptive intervention in multiscale biological systems.

---

## 论文详细总结（自动生成）

### 论文总结：OPTIMIS —— 集成多尺度智能模拟优化个性化治疗

#### 1. 核心问题与整体含义（研究动机和背景）
在计算医学领域，如何跨越生物系统的多尺度（从微观分子到宏观全身）进行有效控制是一个重大挑战。以 **CAR-T 细胞疗法** 为例，治疗效果高度依赖于微观层面的受体结合动力学，而这些微观事件具有极强的随机性和噪声。
*   **研究动机**：传统的确定性模型（如常微分方程 ODE）无法捕捉分子层面的随机波动；而完全随机的模拟算法（如 Gillespie 算法）计算开销巨大，无法满足人工智能（尤其是强化学习）训练所需的高通量交互需求。
*   **核心目标**：开发一个既能保留微观生物物理精度，又能实现毫秒级运行速度的计算框架，用于训练 AI 智能体发现个性化的动态给药策略，平衡疗效与毒性（如细胞因子风暴）。

#### 2. 方法论：核心思想与关键技术
OPTIMIS 框架采用了一种“慢-快耦合”的混合架构，主要包含三个层次：
*   **微观随机模拟（Gillespie SSA）**：利用 Gillespie 随机模拟算法模拟免疫突触处的受体状态切换（激活/失活）。它捕捉了分子层面的“抖动”，并受药物（达沙替尼）浓度和系统细胞因子水平的动态调节。
*   **宏观系统动力学（Neural ODE 代理模型）**：
    *   研究者首先建立了一套描述肿瘤负担（T）、CAR-T 细胞数量（C）和细胞因子浓度（I）的非线性 ODE 系统。
    *   为了提速，将上述混合系统压缩为一个**可微的神经常微分方程（Neural ODE）**。该模型作为“数字孪生”，学习微观受体状态与宏观疾病进展之间的映射关系，极大地提高了计算效率。
*   **强化学习控制器（RL Controller）**：
    *   采用 **PPO（近端策略优化）算法**。
    *   **输入（状态）**：肿瘤负担、CAR-T 计数、细胞因子水平、微观受体激活比例、表型提示（标准/激进）等。
    *   **输出（动作）**：连续的药物剂量（0 到 1 之间的标量）。
    *   **奖励函数**：鼓励减少肿瘤，惩罚系统毒性（细胞因子超标）、过度用药和剂量剧烈波动。

#### 3. 实验设计
*   **数据集/场景**：构建了一个包含 240 名虚拟患者的合成队列（120 名标准表型，120 名激进表型）。激进表型模拟了极易引发致命细胞因子风暴的高风险患者。
*   **对比基准（Benchmarks）**：
    1.  **无药治疗（No Drug）**：观察自然进展。
    2.  **恒定剂量（Constant Low/Medium）**：固定给药 0.2 或 0.5。
    3.  **启发式自适应策略（Heuristic Adaptive）**：基于宏观症状（如细胞因子升高后）再进行反应性调药的规则。
*   **消融实验**：分别移除“表型提示”、“受体状态输入”、“增量特征”和“前序剂量记忆”，以验证各组件的必要性。

#### 4. 资源与算力
*   论文提到计算支持由 **Albert Einstein College of Medicine 的高性能计算中心（HPC）** 提供。
*   **具体参数**：文中**未明确说明**具体的 GPU 型号、数量以及训练智能体所需的总时长。但提到 Neural ODE 的引入是为了实现“毫秒级执行速度”，以支持高吞吐量的 RL 训练。

#### 5. 实验数量与充分性
*   **实验规模**：生成了 12,000 个纵向数据点用于训练 Neural ODE；在 240 名患者的队列上进行了验证。
*   **充分性评价**：实验设计较为全面，包含了不同病理表型的对比、与临床常见启发式规则的对比以及深入的消融实验。
*   **客观性**：通过引入随机采样和多种给药模式（脉冲、斜坡、随机游走）来增强训练数据的多样性，确保了模型在面对异质性患者时的鲁棒性。

#### 6. 主要结论与发现
*   **“冲浪”策略的发现**：成熟的 RL 智能体自主学习到了一种三阶段策略：**前期预判性重刹**（抑制初始过度激活）、**中期受控减量**（允许 CAR-T 杀伤肿瘤）、**后期精准脉冲**（防止细胞因子反弹）。
*   **性能提升**：在激进表型患者中，传统反应性给药策略的成功率为 0%（全部死于毒性），而 OPTIMIS 智能体实现了 **70% 以上的治愈成功率**。
*   **微观信号的重要性**：消融实验证明，微观受体激活状态是极其重要的“早期预警指标”，仅靠宏观症状（细胞因子水平）调药往往为时已晚。

#### 7. 优点（亮点）
*   **跨尺度集成**：成功将离散随机过程（微观）与连续确定性动力学（宏观）整合进同一个 AI 训练循环。
*   **计算效率高**：通过 Neural ODE 蒸馏复杂生物模型，解决了 RL 训练中的计算瓶颈。
*   **闭环控制**：实现了从“静态给药表”向“动态反馈控制”的范式转变，更符合精准医疗的需求。

#### 8. 不足与局限
*   **依赖合成数据**：目前所有结论均基于数学模拟产生的合成数据集，尚未在真实临床数据或动物实验数据上进行回溯性验证。
*   **模型漂移风险**：实验显示 Neural ODE 在长期预测（Rollout）中存在一定的累积误差（漂移），这可能影响长期治疗方案的稳定性。
*   **应用范围限制**：目前仅在 CAR-T 疗法这一特定场景下验证，对于其他更复杂的多药联合治疗场景，状态空间和动作空间的维度灾难尚待解决。

（完）
