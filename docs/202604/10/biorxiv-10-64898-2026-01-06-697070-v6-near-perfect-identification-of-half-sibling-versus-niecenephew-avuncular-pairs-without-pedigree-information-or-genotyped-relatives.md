---
title: Near perfect identification of half sibling versus niece/nephew avuncular pairs without pedigree information or genotyped relatives
title_zh: 在无需系谱信息或已基因分型亲属的情况下，近乎完美地识别半同胞与叔侄/舅甥对
authors: "Sapin, E., Kelly, K., Keller, M. C."
date: 2026-04-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.01.06.697070v6.full.pdf"
tags: ["query:gwas"]
score: 7.0
evidence: 在大规模基因组生物样本库中识别亲属关系的纯基因型方法
tldr: 针对大规模基因库中难以区分半同胞与叔侄等二级亲属的问题，本研究提出一种基于跨染色体相位单倍型共享特征的新型计算框架。该方法利用多元高斯混合模型（GMM）对基因型数据进行建模，无需家系或表型信息即可实现近乎完美的分类精度，为大规模基因组研究中的家系重建和隐性亲缘关系控制提供了高效、可扩展的解决方案。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-06-697070-v6/fig-001.webp\", \"caption\": \"Figure 1: Example pedigree with two half-siblings (half-sib1, half-sib2) sharing a mother and each having a paternal first cousin (FC1, FC2), illustrating a configuration that is incompatible with an avuncular relationship between half-sib1 and half-sib2.\", \"page\": 3, \"index\": 1, \"width\": 1012, \"height\": 206}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-06-697070-v6/fig-002.webp\", \"caption\": \"Figure 2: Example pedigree showing that a first cousin (CA) of an avuncular relative A must also be related to the niece/nephew N .\", \"page\": 3, \"index\": 2, \"width\": 631, \"height\": 227}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-01-06-697070-v6/fig-003.webp\", \"caption\": \"Figure 4: Distribution of the posterior probability P (half − sibling) for ground-truth and unlabeled second-degree relative candidates. The dashed line indicates the threshold for half-sibling identification (P (half − sibling) > 0.5).\", \"page\": 5, \"index\": 3, \"width\": 857, \"height\": 675}]"
motivation: 现有的基于SNP和年龄的二级亲属区分方法因特征分布重叠严重而导致误判率高，亟需一种仅依赖基因型数据的可扩展识别方法。
method: 提出一种利用跨染色体相位衍生的单倍型共享特征，并结合多元高斯混合模型（GMM）进行分类的新型计算框架。
result: "在生物样本库规模的数据验证中，该方法实现了100%的叔侄对识别准确率和98.4%的半同胞识别敏感性。"
conclusion: 该框架为大规模基因组研究中区分复杂二级亲属关系提供了一种鲁棒且高效的工具，有助于完善家系重建。
---

## 摘要
动机：大规模基因组生物样本库包含数千名缺乏系谱数据的二级亲属。准确区分半同胞与叔侄/舅甥对（两者均共享约25%的基因组）仍然是一项重大挑战。目前基于单核苷酸多态性（SNP）的方法依赖于累积同源后裔（IBD）片段计数和年龄差异，但这些分布的显著重叠导致了较高的误分类率。因此，需要一种可扩展的、仅基于基因型的方法，能够在不需要观察系谱或表型信息的情况下解决这些二级亲属的歧义。结果：我们提出了一种新型计算框架，利用源自跨染色体定相（phasing）的单倍型级共享特征，实现了半同胞与叔侄/舅甥对的近乎完全分离。这些特征还允许在叔侄/舅甥对中区分侄（甥）与伯叔姑（舅姨）。通过使用多元高斯混合模型（GMM）对这些特征进行建模，我们在生物样本库规模的数据中展示了卓越的分类性能。用于验证的地面真值标签是通过在基于高置信度一级亲属关系构建的家族图中进行多步推理过程确定的。所有395对地面真值叔侄/舅甥对均被正确分类，61对半同胞对中的60对被正确识别。若以半同胞状态作为正类，这对应于98.4%的灵敏度和100%的特异性。我们的结果表明，该框架在其他类似规模的数据集上可能具有相当的表现。该方法为大规模基因组研究中的系谱重建和隐性亲缘关系控制提供了一种稳健、可扩展的解决方案。

## Abstract
MotivationLarge-scale genomic biobanks contain thousands of second-degree relatives without pedigree data. Accurately distinguishing half-siblings from avuncular pairs-both sharing approximately 25% of the genome-remains a significant challenge. Current SNP-based methods rely on aggregate Identical-By-Descent (IBD) segment counts and age differences, but substantial overlap in these distributions leads to high misclassification rates. There is a need for a scalable, genotype-only method that can resolve these second-degree ambiguities without requiring observed pedigrees or phenotypic information.

ResultsWe present a novel computational framework that achieves near-complete separation of half-siblings and avuncular pairs using haplotype-level sharing features derived from across-chromosome phasing. These features also allow differentiation of nieces/nephews from aunts/uncles within avuncular pairs. By modeling these features with a multivariate Gaussian mixture model (GMM), we demonstrate exceptional classification performance in biobank-scale data. Ground-truth labels for validation were established through a multi-step inference process within a family graph constructed from high-confidence first-degree relationships. All 395 ground-truth avuncular pairs were correctly classified, and 60 of 61 half-sibling pairs were correctly identified. Treating (e.g.) half-sibling status as the positive class, this corresponds to 98.4% sensitivity and 100% specificity. Our results suggest that the framework could perform comparably on other datasets of similar size. This method provides a robust, scalable solution for pedigree reconstruction and the control of cryptic relatedness in large-scale genomic studies.

Contactemmanuel.sapin@colorado.edu, kristen.kelly@colorado.edu, and matthew.c.keller@colorado.edu