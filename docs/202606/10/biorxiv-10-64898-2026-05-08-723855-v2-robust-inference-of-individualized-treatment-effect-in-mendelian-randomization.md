---
title: Robust Inference of Individualized Treatment Effect in Mendelian Randomization
title_zh: 孟德尔随机化中个体化治疗效应的稳健推断
authors: "Wu, R., Li, X., Xiao, F., Liang, M."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.08.723855v2.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 孟德尔随机化中个体化治疗效应的稳健推断方法
tldr: 现有孟德尔随机化方法通常关注平均因果效应，难以直接推断个体化治疗效应（ITE）且依赖于强假设。本文提出一种稳健的部分识别推断框架，在最小因果假设下，采用乘子自助法结合数据自适应自助分布偏移和异质方差调整，允许多个工具变量和部分无效工具变量（基于最小比例规则），推导出ITE可识别边界的尖锐推断程序。理论上证明该方法达到名义覆盖率和渐近尖锐性，模拟结果显示区间长度显著短于现有方法。应用于阿尔茨海默病神经影像学数据，揭示了TREM2基因表达对不同教育水平患者风险的异质性因果效应。该工作拓展了孟德尔随机化的应用范围，为精准医学中基于遗传变异的个性化因果推断提供了有效工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有MR方法无法直接推断个体化治疗效应（ITE），且识别依赖于强假设，难以支持精准医学中的异质性因果分析。
method: 提出稳健部分识别框架，采用乘子自助法结合数据自适应分布偏移和异质方差调整，在允许无效工具变量时给出ITE边界的尖锐推断。
result: 理论证明该方法达到名义覆盖和渐近尖锐性，模拟显示区间长度显著缩短，应用发现TREM2对教育亚组风险具有异质性效应。
conclusion: 该框架为孟德尔随机化在精准医学中的个性化因果推断提供了可靠工具，拓展了MR在异质性效应分析中的适用性。
---

## 摘要
孟德尔随机化（MR）利用遗传变异作为工具变量（IVs），广泛用于存在未测量混杂因素时得出因果结论，但大多数MR分析关注平均处理效应并依赖强假设。对于精准医学，主要目标是个体化治疗效应（ITE）；然而在MR中，在核心IV假设下这些效应无法点识别，并且对ITE可识别边界的有效推断尤其具有挑战性。在这项工作中，我们提出了一个针对MR下ITE可识别边界的稳健部分识别推断框架，允许使用多个IV。在最小因果假设下，我们采用乘子自助法程序，结合自适应自助法分布转移和异质性方差调整，推导了ITE边界的锐利推断程序。理论上，我们证明了所提方法实现了名义覆盖率和渐近锐利性。此外，我们将程序扩展以容忍可能无效的IV，在最小比例规则假设下，通过对可行的IV子集进行聚合同时保持覆盖率。模拟研究表明，所提方法达到了名义覆盖率，并且区间比现有程序大幅缩短。我们使用阿尔茨海默病神经影像学倡议的数据来评估TREM2表达在不同教育定义亚组中对阿尔茨海默病风险的异质性因果效应，从而说明该框架。

## Abstract
Mendelian randomization (MR), leveraging genetic variants as instrumental variables (IVs), is widely used to draw causal conclusions in the presence of unmeasured confounding, but most MR analyses focus on average treatment effects and rely on strong assumptions. For precision medicine, the primary target is instead the individualized treatment effect (ITE); yet in MR, such effects are not point-identified under core IV assumptions, and valid inference for identifiable bounds of the ITEs is particularly challenging. In this work, we propose a robust partial identification inference framework for the identifiable bounds of the ITEs under MR allowing multiple IVs. Under minimal causal assumptions, we derive a sharp inference procedure for the bounds of ITE by adopting a multiplier bootstrap procedure with data-adaptive bootstrap distribution shifting and heterogeneous variance adjustment. In theory, we prove that the proposed method achieves nominal coverage and asymptotic sharpness. Further, we extend the procedure to tolerate possible invalid IVs under a minimal proportion rule assumption by aggregating over plausible IV subsets while preserving coverage. Simulation studies demonstrate that the proposed methods attain nominal coverage and substantially shorter intervals than existing procedures. We illustrate the framework using data from the Alzheimer's Disease Neuroimaging Initiative to assess heterogeneous causal effects of TREM2 expression on Alzheimer's disease risk across education-defined subgroups.