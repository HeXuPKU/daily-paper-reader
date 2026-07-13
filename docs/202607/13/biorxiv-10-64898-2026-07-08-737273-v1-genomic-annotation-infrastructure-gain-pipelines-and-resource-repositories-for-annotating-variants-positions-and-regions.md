---
title: "Genomic Annotation Infrastructure (GAIn): Pipelines and Resource Repositories for Annotating Variants, Positions, and Regions"
title_zh: 基因组注释基础设施（GAIn）：用于注释变异、位置和区域的流程与资源库
authors: "Cokol, M., Chorbadjiev, L., Lee, Y.-h., Jamsandekar, M., Gergova, I., Todorov, I., Iossifov, I."
date: 2026-07-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.08.737273v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 用于GWAS功能整合的基因组注释框架
tldr: 基因组注释依赖多种异构资源，但资源版本和组装差异导致注释可重现性差。GAIn平台通过声明式管道定义注释任务，并利用公共资源库（含250+资源及ENCODE实验库）提供透明、可复现的注释。用户可通过Web界面或命令行接口执行注释，命令行支持自定义扩展和大规模并行处理。GAIn的重注释功能简化了持续维护，为跨参考基因组的注释提供了可审计、高效的基础设施。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737273-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1687, \"height\": 912, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737273-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 1298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737273-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1685, \"height\": 803, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737273-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1242, \"height\": 706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-08-737273-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 2441, \"height\": 1354, \"label\": \"Figure\"}]"
motivation: 解决基因组注释中资源版本和组装差异导致的可重现性差问题。
method: 采用声明式管道和插件架构，整合资源库与自定义注释器，支持Web和命令行接口。
result: 构建了含250+资源的主库和ENCODE派生库，实现高效并行注释与重注释功能。
conclusion: GAIn为多参考基因组注释提供了可审计、可维护、高效的解决方案。
---

## 摘要
基因组变异、位置和区域的解读依赖于可靠的注释——添加预测效应、保守性、群体频率和基因水平背景等证据，然而底层资源数量众多、版本各异且具有组装特异性。我们提出了基因组注释基础设施（GAIn），这是一个通过声明式流程生成透明、可重复注释的平台，该流程将注释任务定义为有序的组件列表（称为注释器），这些注释器利用来自基因组资源库（GRR）的基因组资源产生注释属性。我们提供两个公共GRR：一个包含250多种异质基因组资源的主资源库，以及一个独立的GRR-ENCODE资源库，其中包含来自数千个ENCODE（DNA元素百科全书）项目实验的资源。用户可以使用我们提供的注释流程、自定义注释流程，并通过GAIn的Web界面和命令行界面执行注释任务。Web界面无需任何设置即可使用，但它依赖于共享的计算基础设施，并对注释任务的大小有限制。命令行界面需要设置，但通过易于使用的并行化支持任意大的注释任务，并提供更广泛的功能。例如，命令行GAIn可以通过使用自定义GRR或通过其插件架构创建自定义注释器进行扩展。此外，GAIn的重新注释功能可以在注释更新时进行更新，从而大大简化了大型基因组学分析项目中注释的维护。GAIn的资源管理、显式版本控制和流程抽象为跨参考组装和用例的现代基因组注释提供了可审计、可维护且高效的基础。

## Abstract
Interpretation of genomic variants, positions, and regions depends on reliable annotation - adding evidence such as predicted effect, conservation, population frequency, and gene-level context - yet the underlying resources are numerous, versioned, and assembly-specific. We present the Genomic Annotation Infrastructure (GAIn), a platform that generates transparent, reproducible annotations via declarative pipelines that define annotation tasks as ordered lists of components, called annotators, that produce annotation attributes using genomic resources from Genomic Resource Repositories (GRRs). We provide two public GRRs: a main repository containing more than 250 heterogeneous genomic resources, and a separate GRR-ENCODE repository containing resources derived from thousands of ENCODE (Encyclopedia of DNA Elements) project experiments. Users can use the annotation pipelines we made available, author custom annotation pipelines, and execute annotation tasks with these pipelines via GAIn's web and command-line interfaces. The web interface can be used without any setup, but it relies on shared computational infrastructure and imposes limits on the size of annotation tasks. The command-line interface requires setup but supports arbitrarily large annotation tasks through simple-to-use parallelization and offers a broader set of features. For example, command-line GAIn can be extended by using custom GRRs or creating custom annotators via its plugin architecture. In addition, GAIn's re-annotation feature, which updates annotations as they evolve, substantially simplifies maintaining annotations in a large genomics analysis project. GAIn's resource management, explicit versioning, and pipeline abstraction provide an auditable, maintainable, and efficient foundation for modern genomic annotation across reference assemblies and use cases.