---
title: "SpatialJEPA: JEPA-inspired graph-context distillation for spatially aware multiomics integration"
title_zh: SpatialJEPA：受JEPA启发的图上下文蒸馏实现空间感知多组学整合
authors: "Mann-Krzisnik, D., Li, Y."
date: 2026-07-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.21.739810v1.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: SpatialJEPA将空间上下文从空间多组学迁移至非空间数据，与功能基因组整合相关。
tldr: 针对多数配对RNA-ATAC数据缺乏空间坐标的问题，提出SpatialJEPA框架，通过教师-学生结构将空间多组学数据的图上下文蒸馏到非空间数据。训练时遮蔽教师的空间邻域图，迫使学生从解离视角学习匹配嵌入。在鼠脑多组学中实现了源-目标对齐、恢复空间转录组和染色质可及性程序，并展示配体-受体通路一致性。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-21-739810-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1649, \"height\": 835, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-21-739810-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1659, \"height\": 1621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-21-739810-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1640, \"height\": 1257, \"label\": \"Figure\"}]"
motivation: 现有空间多组学整合方法依赖配对空间坐标，但大量RNA-ATAC数据为解离态，需迁移空间上下文。
method: 设计JEPA启发教师-学生框架，训练时将教师空间邻域图替换为自同构图，使学生学习解离视角下的嵌入匹配。
result: 在鼠脑多组学中，SpatialJEPA实现源-目标空间对齐，恢复空间转录组与染色质程序，且与配体-受体通路结构一致。
conclusion: SpatialJEPA成功将空间上下文从空间数据蒸馏至解离数据，拓展多组学整合应用场景。
---

## 摘要
用于整合空间基因组学模式的计算框架跨分子层扩展了基于细胞的表示学习，但许多配对的RNA-ATAC数据集是解离的，缺乏空间坐标。我们提出了SpatialJEPA，这是一种受JEPA启发的教师-学生框架，用于将空间多组学数据的空间上下文转移到非空间多组学数据中。与补丁或特征掩蔽目标不同，SpatialJEPA通过在学生训练期间用仅自身的恒等图替换教师的空间邻域图来掩蔽空间上下文，使得空间样本对学生而言表现为解离状态。学生从这种图上下文受限的视图中学习匹配教师嵌入，从而可以在推理时应用于解离的RNA-ATAC数据。在小鼠脑多组学中，所得的表示支持源-目标对齐，恢复空间组织的转录组和染色质可及性程序，并且与非空间参考相比，显示出与配体-受体通路结构的一致性。已被CIBB 2026会议（https://cibb2026.teralab.ai/）接收。

## Abstract
Computational frameworks for integrating spatial genomics modalities extend cell-based representation learning across molecular layers, but many paired RNA-ATAC datasets are dissociated and lack spatial coordinates. We introduce SpatialJEPA, a JEPA-inspired teacher-student framework for transferring spatial context from spatial multiomics data to non-spatial multiome data. In contrast to patch- or feature-masking objectives, SpatialJEPA masks spatial context by replacing the teacher's spatial neighborhood graph with a self-only identity graph during student training, making the spatial sample appear dissociated to the student. The student learns to match teacher embeddings from this graph-context-restricted view and can therefore be applied to dissociated RNA-ATAC data at inference time. In mouse brain multiomics, the resulting representation supports source-target alignment, recovers spatially organized transcriptomic and chromatin-accessibility programs, and shows concordance with ligand-receptor pathway structure compared with non-spatial references. Accepted at the CIBB 2026 conference (https://cibb2026.teralab.ai/)