---
title: "Dissecting Alzheimer's disease heterogeneity by cross-trait polygenic prediction"
title_zh: 通过跨性状多基因预测剖析阿尔茨海默病的异质性
authors: "Li, W. F., Mohammed, N., Bennett, D. A., Kellis, M., Tanigawa, Y."
date: 2026-05-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.15.725551v1.full.pdf"
tags: ["query:gwas"]
score: 10.0
evidence: 用于疾病异质性的跨性状多基因评分分析
tldr: 本研究针对阿尔茨海默病（AD）的临床与病理异质性，提出了一种跨性状多基因评分（PGS）分析策略。通过整合英国生物样本库的713个PGS与ROSMAP队列的深度表型数据，识别出12个与AD认知及病理显著相关的遗传特征（如血脂和炎症）。研究不仅提升了对淀粉样蛋白和认知的预测能力，还定义了六种独特的AD多基因亚型，为异质性疾病的精准分层提供了新模型。
source: biorxiv
selection_source: fresh_fetch
motivation: 旨在利用复杂性状的遗传多效性，克服深度表型AD队列样本量不足的限制，揭示AD异质性的遗传基础。
method: 将713个预训练的PGS应用于1678名具有36种深度AD表型的参与者，进行跨队列、跨性状的关联分析与预测建模。
result: 识别出12个关键PGS与AD表型间的268个显著关联，且多PGS模型在预测淀粉样蛋白和认知方面优于单一的AD PGS或APOE基因。
conclusion: 该方法成功揭示了驱动AD异质性的遗传特征，并证明了利用大规模生物库资源对异质性疾病队列进行基因组分层的有效性。
---

## 摘要
绘制多因素疾病个体间异质性的遗传基础，为深入了解其机制和针对性干预提供了契机。在阿尔茨海默病（AD）中，临床和病理异质性已得到广泛认可，但由于缺乏具有深度表型特征的高效力队列，遗传剖析受到了限制。在此，我们引入了一种多基因评分（PGS）分析策略，通过利用复杂性状遗传学中固有的多效性来解决这些局限性。我们进行了预训练 PGS 的跨队列、跨性状应用，将 713 个源自英国生物样本库（UK Biobank）的 PGS 与 1678 名 ROSMAP 参与者的 36 个深度 AD 表型相结合。我们在 12 个优先排序的 PGS 与 36 个 AD 表型之间识别出 268 个具有统计学显著性（FDR < 0.1）的关联。优先排序的 PGS 包括血脂测量、炎症生物标志物和癌症性状；观察到的 AD 表型包括认知、淀粉样蛋白和神经原纤维缠结。在 268 个关联中，有 49 个在排除 APOE 基因的 PGS 中依然存在。在预测淀粉样蛋白和认知方面，基于多个优先排序 PGS 训练的预测模型优于单独的 AD PGS 或 APOE。最后，我们的方法识别出六种个体层面的 AD 多基因亚型，并得到了不同病理模式的支持。总体而言，我们利用 PGS 结合了大规模生物样本库资源和深度表型队列，揭示了 AD 异质性背后的遗传特征，并为利用基因组学对异质性疾病队列进行分层提供了一个通用模型。

## Abstract
Mapping the genetic basis of inter-individual heterogeneity in multifactorial diseases opens the door to mechanistic insights and opportunities for targeted intervention. In Alzheimer's disease (AD), clinical and pathological heterogeneity is well recognized, but genetic dissection is limited by a lack of well-powered cohorts with deep phenotypic characterization. Here, we introduce a polygenic score (PGS) analysis strategy to address these limitations by leveraging the inherent pleiotropy in complex trait genetics. We perform a cross-cohort, cross-trait application of pre-trained PGS, integrating 713 UK Biobank-derived PGS with 36 deep AD phenotypes across 1678 ROSMAP participants. We identify 268 statistically significant (FDR<0.1) associations between 12 prioritized PGS and 36 AD phenotypes. Prioritized PGS include blood lipid measurements, inflammatory biomarkers, and cancer traits; observed AD phenotypes include cognition, amyloid, and tangles. Of the 268 associations, 49 persist with APOE-excluded PGS. Predictive models trained on multiple prioritized PGS outperform the AD PGS or APOE alone for predicting amyloid and cognition. Lastly, our approach identifies six individual-level AD polygenic subtypes supported by distinct pathological patterns. Overall, we combine large-scale biobank resources and deeply-phenotyped cohorts using PGS, reveal genetic features underlying AD heterogeneity, and provide a general model for stratifying heterogeneous disease-focused cohorts using genomics.

---

## 论文详细总结（自动生成）

这是一份关于论文《通过跨性状多基因预测剖析阿尔茨海默病的异质性》（Dissecting Alzheimer's disease heterogeneity by cross-trait polygenic prediction）的深度结构化总结：

### 1. 核心问题与整体含义（研究动机和背景）
阿尔茨海默病（AD）在临床表现和病理特征上具有高度的**异质性**（如淀粉样蛋白沉积、神经原纤维缠结和认知下降速度的差异）。然而，传统的全基因组关联研究（GWAS）通常将 AD 视为单一的二元性状（患病 vs. 健康），且具有深度表型记录的队列（如 ROSMAP）样本量较小，难以直接进行高强度的遗传剖析。
本研究旨在利用**遗传多效性**（Pleiotropy），通过大规模生物样本库（英国生物样本库 UKB）预训练的多基因评分（PGS），来解析小规模深度表型队列中的 AD 异质性，从而识别驱动不同病理特征的遗传因素。

### 2. 论文提出的方法论
核心思想是**“跨性状、跨队列的多基因预测”**。
*   **PGS 迁移应用**：从英国生物样本库（UKB）中提取了 713 个预训练的 PGS（涵盖代谢、免疫、人类测量学等性状）。
*   **关联分析**：将这 713 个 PGS 应用于 ROSMAP 队列的 1678 名参与者，并与 36 种深度 AD 表型（包括认知评分、病理负荷等）进行关联分析。
*   **特征筛选与建模**：
    *   使用 FDR < 0.1 筛选显著关联。
    *   构建**多 PGS 预测模型**：利用弹性网络（Elastic Net）回归，整合多个优先排序的 PGS 来预测特定的 AD 表型。
    *   **排除 APOE 效应**：专门测试了移除 APOE 区域后的 PGS，以验证发现是否独立于这一最强遗传风险因子。
*   **亚型识别**：基于优先排序的 PGS 谱系，利用 K-means 聚类算法对个体进行分层，定义多基因亚型。

### 3. 实验设计
*   **数据集**：
    *   **训练集（PGS 来源）**：英国生物样本库（UK Biobank），用于生成 713 个性状的遗传权重。
    *   **目标集（表型分析）**：ROSMAP 队列（1678 人），包含详尽的尸检病理数据和生前认知追踪。
*   **Benchmark（基准对比）**：
    *   单一的 AD 风险 PGS（基于 AD GWAS 结果）。
    *   APOE ε4 等位基因状态（传统的金标准预测因子）。
*   **对比方法**：对比了“单一 AD PGS”、“APOE 状态”以及“本研究提出的多性状 PGS 组合模型”在预测淀粉样蛋白（Amyloid）和认知功能方面的准确性。

### 4. 资源与算力
论文中**未明确说明**具体的算力细节（如 GPU 型号或训练时长）。由于该研究主要涉及统计遗传学计算（如线性回归、弹性网络和 PGS 加权求和），其计算压力通常集中在 CPU 集群和内存上，而非深度学习所需的 GPU 算力。

### 5. 实验数量与充分性
*   **实验规模**：分析了 713 个 PGS 与 36 个表型的配对关联，总计进行了数万次统计检验。
*   **充分性**：
    *   研究识别出 12 个关键 PGS（如高密度脂蛋白、炎症标志物、癌症相关性状）与 AD 表型间的 268 个显著关联。
    *   进行了**敏感性分析**（如排除 APOE 区域），确保了结果的稳健性。
    *   通过聚类分析识别出 6 种亚型，并用实际病理数据进行了验证。
*   **客观性**：实验设计考虑了年龄、性别等协变量，并使用了交叉验证来评估预测模型的性能，具有较高的客观性。

### 6. 主要结论与发现
*   **识别关键驱动因素**：血脂测量（HDL/LDL）、炎症生物标志物和某些癌症相关遗传特征是 AD 异质性的重要遗传驱动力。
*   **预测性能提升**：整合多个非 AD 性状的 PGS 模型在预测淀粉样蛋白负荷和认知衰退方面，显著优于仅使用 AD PGS 或 APOE 基因。
*   **亚型分层**：成功将 AD 患者分为 6 种具有不同遗传和病理特征的亚型（例如，某些亚型表现为高淀粉样蛋白但认知下降较慢，而另一些则相反）。
*   **多效性证据**：证明了许多与 AD 相关的遗传变异通过影响代谢和免疫途径来发挥作用。

### 7. 优点
*   **创新视角**：巧妙利用大规模生物库的“广度”来弥补深度表型队列“深度有余、样本不足”的缺陷。
*   **超越 APOE**：在 APOE 这一强效因子之外，挖掘出了具有生物学意义的微效遗传贡献。
*   **临床潜力**：提出的多基因亚型分层模型为精准医疗和个性化干预提供了理论基础。

### 8. 不足与局限
*   **族群偏差**：研究主要基于欧洲裔人群（UKB 和 ROSMAP），其结论在非欧洲裔人群中的适用性有待验证。
*   **因果性限制**：PGS 关联分析本质上是相关性研究，无法直接证明这些性状（如癌症性状）与 AD 之间的生物学因果链条。
*   **表型覆盖**：虽然包含 36 种表型，但仍可能遗漏了某些环境因素或表观遗传因素对异质性的贡献。

（完）
