---
title: "GWAS Summary Statistic Tool: A Meta-Analysis and Parsing Tool for Polygenic Risk Score Calculation"
title_zh: GWAS 汇总统计量工具：一种用于多基因风险评分计算的荟萃分析与解析工具
authors: "Muneeb, M. -, Ascher, D."
date: 2026-03-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.04.709666v1.full.pdf"
tags: ["query:gwas"]
score: 9.0
evidence: 用于解析GWAS摘要统计数据以进行PRS计算的工具
tldr: 多基因风险评分（PRS）计算依赖GWAS汇总统计数据，但从海量目录中筛选合适文件既耗时又耗存储。本文推出GWASPoker工具，专门针对GWAS Catalog设计，通过部分下载和表头检测技术，在无需下载全文件的情况下预筛选符合PRS要求的候选文件。该工具支持20种文件格式，能自动识别724种表头特征，显著提升了数据获取效率，为大规模基因组研究提供了便捷的元分析与解析方案。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-04-709666-v1/fig-001.webp\", \"caption\": \"Table 1. Frequency count of file extensions of downloaded files. Files in .yaml and.RData formats were discarded from further analysis.\", \"page\": 4, \"index\": 1, \"width\": 331, \"height\": 464}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-03-04-709666-v1/fig-002.webp\", \"caption\": \"Table 2. The first column shows the column name, and the second column shows the number of unique mappings extracted from the downloaded GWAS files.\", \"page\": 4, \"index\": 2, \"width\": 411, \"height\": 334}]"
motivation: 解决从海量GWAS Catalog条目中手动筛选和下载大文件以检查PRS所需列结构导致的效率低下和存储浪费问题。
method: 开发了GWASPoker工具，通过部分下载文件并自动检测表头签名，实现对候选GWAS文件的快速分选和列可用性验证。
result: "在对6万余条记录的测试中，成功解析了89.6%的文件，涵盖20种格式，且表头验证准确率与全量下载高度一致。"
conclusion: GWASPoker是一个高效、自动化的GWAS数据预处理工具，极大地简化了PRS计算前的数据筛选与解析流程。
---

## 摘要
动机：GWAS（全基因组关联研究）汇总统计文件是多基因风险评分（PRS）计算的关键输入。然而，在成千上万的目录条目中识别合适的文件需要下载大文件并手动检查其列结构，这一过程既耗时又耗费存储空间。结果：我们推出了 GWASPoker，这是一款针对 GWAS Catalog 的表型驱动型预下载分选工具。它通过部分下载和表头检测来扫描候选 GWAS 文件的 PRS 列可用性，而无需进行全文件传输。在对来自 GWAS Catalog 的 60,499 条记录进行分析时，60,281 条（99.6%）包含可访问的下载链接，其中 54,026 条（89.6%）在 20 种文件格式中成功实现了部分下载和解析，生成了 724 个唯一的表头特征。在 13 种表型中，85 个手动策划的 GWAS 文件中有 84 个（98.8%）被自动检索和处理。针对完整下载文件的表头验证显示，28 个案例中有 23 个（82.1%）完全一致。可用性与实现：GWASPoker 使用 Python 3 实现，可在 https://github.com/MuhammadMuneeb007/GWASPokerforPRS 根据 MIT 许可证免费获取。仓库中提供了示例输出和文档。该工具已在 Linux（HPC 集群）上使用 Python 3.8+ 进行了测试。基于大语言模型（LLM）的代码生成步骤完全是可选的；为完全离线使用提供了一个基于规则的列映射模板。

## Abstract
MotivationGWAS (genome-wide association study) summary statistic files are essential inputs for polygenic risk score (PRS) calculation, yet identifying suitable files across thousands of catalog entries requires downloading large files and manually inspecting their column structures--a process that is time-consuming and storage-intensive.

ResultsWe present GWASPoker, a phenotype-driven, GWAS-Catalog-specific pre-download triage tool that scans candidate GWAS files for PRS column availability by partial download and header detection, without requiring full-file transfer. Analysing 60,499 records from the GWAS Catalog, 60,281 (99.6%) contained accessible download links, of which 54,026 (89.6%) were successfully partially downloaded and parsed across 20 file formats, yielding 724 unique header signatures. Across 13 phenotypes, 84 of 85 manually curated GWAS files (98.8%) were automatically retrieved and processed. Header validation against fully downloaded files showed exact agreement in 23 of 28 cases (82.1%).

Availability and implementationGWASPoker is implemented in Python 3 and freely available at https://github.com/MuhammadMuneeb007/GWASPokerforPRS under the MIT licence. Example outputs and documentation are provided in the repository. The tool was tested on Linux (HPC cluster) with Python 3.8+. The LLM-based code-generation step is entirely optional; a rules-based column-mapping template is provided for fully offline use.