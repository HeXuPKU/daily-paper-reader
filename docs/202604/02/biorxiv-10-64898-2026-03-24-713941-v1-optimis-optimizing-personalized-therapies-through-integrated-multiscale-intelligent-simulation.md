---
title: "OPTIMIS: Optimizing Personalized Therapies through Integrated Multiscale Intelligent Simulation"
authors: "Su, Z., Wu, Y."
date: 2026-03-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.24.713941v1.full.pdf"
tags: ["query:med-ai"]
score: 9.0
evidence: 用于个性化治疗的深度强化学习
tldr: OPTIMIS 将多尺度模拟与强化学习相结合，以优化个性化医疗方案。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-713941-v1/fig-001.webp\", \"caption\": \"Table 2: Comparative performance of the AI-driven reinforcement learning policy against standard constant and adaptive heuristic dosing strategies in managing tumor burden and cytokine toxicity across distinct patient phenotypes.\", \"page\": 30, \"index\": 1, \"width\": 926, \"height\": 454}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-24-713941-v1/fig-002.webp\", \"caption\": \"Table 1: Ablation analysis demonstrating the critical contribution of individual neural network state features to the overall success rate and dosing efficacy of the reinforcement learning agent.\", \"page\": 29, \"index\": 2, \"width\": 926, \"height\": 434}]"
motivation: 用于个性化治疗的深度强化学习。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## Abstract
Controlling complex biological systems across multiple scales remains a major challenge in computational medicine, because whole-body disease behavior is closely shaped by noisy cellular events at much smaller scales. Standard deterministic models often miss this molecular variability, while fully stochastic simulations are too slow for the repeated, high-throughput interactions needed to train artificial intelligence. To address this problem, we developed a new AI-based framework that combines a discrete stochastic Gillespie algorithm for microscale receptor dynamics with continuous, nonlinear ordinary differential equations for systemic macroscale behavior. To reach the speed needed for deep reinforcement learning (RL), we compress this hybrid system into a differentiable Neural ODE surrogate that acts as a fast digital twin. As a proof of concept, we applied this framework to engineered cellular therapy and used RL agents to learn dynamic, closed-loop treatment policies inside the surrogate environment. By tracking microscopic, unpredictable cellular activity as an early-warning signal, the AI learned to continuously adjust the drug dose--anticipating and stopping dangerous immune reactions before they could spiral out of control. This computational advance improved successful control rates to more than 70% in highly unstable simulated phenotypes and provides a practical, general framework for adaptive intervention in multiscale biological systems.