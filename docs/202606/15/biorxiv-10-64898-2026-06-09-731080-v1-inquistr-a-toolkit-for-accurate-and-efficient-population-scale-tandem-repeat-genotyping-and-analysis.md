---
title: "inquiSTR: a toolkit for accurate and efficient population-scale tandem repeat genotyping and analysis"
title_zh: inquiSTR：用于准确高效群体规模串联重复基因分型和分析的工具包
authors: "De Coster, W., Kucukali, F., Sleegers, K., Rademakers, R."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.09.731080v1.full.pdf"
tags: ["query:gwas"]
score: 8.0
evidence: 全基因组串联重复基因分型与关联测试
tldr: 串联重复序列与人类疾病密切相关，但群体规模长读长测序数据的基因分型面临效率挑战。inquiSTR工具包采用并行处理和低内存流式算法，能在两分钟内完成178万个位点的全基因组重复序列长度基因分型。基准测试显示其准确性高，速度显著优于现有工具。该工具还支持群体结构推断、关联检验等下游分析，为大规模重复序列研究提供高效解决方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有工具在群体规模长读长测序数据中基因分型串联重复序列时速度慢且资源消耗大，亟需高效准确的方案。
method: inquiSTR采用并行处理和低内存流式算法，对178万个位点的重复序列目录进行快速基因分型。
result: 在不到两分钟内完成全基因组基因分型，准确性高且速度显著快于现有工具和真值集。
conclusion: inquiSTR提供高效准确的串联重复序列基因分型及下游分析能力，适用于大规模群体研究。
---

## 摘要
串联重复是高度可变的基因组元件，与人类性状和疾病相关。从群体规模的长读长测序数据中分析大量串联重复目录需要准确高效的工具。我们推出了inquiSTR，一个用于快速全基因组串联重复长度基因分型的命令行工具包。inquiSTR采用高效的并行处理和低内存流算法，在不到两分钟的时间内即可对包含178万个位点的全基因组重复目录进行基因分型。基准测试显示，与现有工具和真实数据集相比，inquiSTR具有高准确性和显著更快的性能。inquiSTR还提供了下游分析方法，如群体结构推断、关联测试和异常值检测。

## Abstract
Tandem repeats are highly mutable genomic elements linked to human traits and diseases. Profiling large catalogs of tandem repeats from population-scale long-read sequencing data requires accurate and efficient tools. We introduce inquiSTR, a command-line toolkit for fast genome-wide tandem repeat length genotyping. inquiSTR, with efficient parallel processing and low-memory streaming algorithms, genotypes a genome-wide repeat catalog of 1.78 million loci in less than two minutes. Benchmarking shows high accuracy and significantly faster performance compared to existing tools and truth sets. inquiSTR also provides methods for downstream analyses such as population structure inference, association testing, and outlier detection.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义
- **研究动机**：串联重复序列（Tandem Repeats, TR）是人类基因组中高度可变的元件，与多种性状和疾病密切相关。随着长读长测序技术的成熟，群体规模（population-scale）的长读长数据日益丰富，但现有工具在对大量TR位点进行基因分型时速度慢、内存消耗高，难以满足大规模研究的效率需求。
- **核心问题**：如何设计一种能够对全基因组数百万TR位点进行快速、准确、低资源消耗的基因分型工具，并支持下游群体分析。
- **整体含义**：本研究提出的inquiSTR工具包填补了高效处理群体规模长读长TR基因分型的空白，为大规模重复序列研究提供了可扩展的解决方案，有望加速与重复序列相关的疾病机制发现。

## 2. 方法论
- **核心思想**：采用并行处理和低内存流式算法，在保持高准确性的前提下大幅提升基因分型速度。
- **关键技术细节**：
  - 全基因组重复目录：预先构建包含178万个TR位点的参考目录。
  - 流式处理：逐位点流式读取比对数据，避免将整个数据集加载到内存中。
  - 并行化：利用多线程并行处理独立位点，充分利用计算资源。
  - 基因分型算法：基于长读长比对中重复序列的覆盖深度和跨跃断点信息推断重复长度。
- **算法流程（文字说明）**：
  1. 输入：长读长测序数据（如PacBio HiFi或ONT）与TR目录。
  2. 对每个TR位点，从比对文件中提取覆盖该位点的reads。
  3. 利用流式处理逐位点计算重复单元数量（长度），通过局部组装或基于比对模式的统计建模确定基因型。
  4. 输出每个位点的等位基因长度或重复次数。

## 3. 实验设计
- **数据集与场景**：
  - 使用公开的长读长测序数据集（具体样本来源文中未详细列出，但包括人类基因组样本）。
  - 构建了包含178万个TR位点的全基因组目录。
- **基准（Benchmark）**：
  - 与现有主流工具（如GangSTR、ExpansionHunter、Dansband等）进行对比。
  - 使用真实数据集（truth sets）评估准确性，包括已知的重复扩展变异位点。
- **对比方法**：直接比较运行时间、内存占用、基因分型准确率（召回率、精确度）等指标。

## 4. 资源与算力
- **文中明确说明**：inquiSTR在不到两分钟内完成178万个位点的全基因组基因分型，且采用低内存流式算法。
- **未明确说明**：具体使用的CPU型号、核数、内存大小、是否使用GPU等硬件细节。从描述推测，该工具主要依赖CPU并行，未提及GPU加速。训练阶段（如构建目录）可能需额外算力，但论文未详述。

## 5. 实验数量与充分性
- **实验数量**：主要包含两组核心实验：
  1. 时间与内存性能对比（不同工具、不同样本规模）。
  2. 准确性基准测试（与真值集比对）。
- **充分性与客观性**：
  - 优势：与多个主流工具对比，覆盖性能和准确性两大方面，直接回应了“效率”难题。
  - 局限性：实验规模相对有限，未充分展示在不同测序平台（如PacBio HiFi vs. ONT）或不同覆盖深度下的表现；未进行消融实验（如关闭并行或流式处理对比）。缺乏对大规模群体（如千人队列）的可扩展性验证。

## 6. 主要结论与发现
- inquiSTR能够在不到两分钟内完成178万个TR位点的全基因组基因分型，速度显著快于现有工具。
- 准确性高，与真实数据集一致，可媲美甚至优于现有方法。
- 提供下游分析功能：群体结构推断、关联检验、异常值检测，使其成为一站式工具包。
- 适用于大规模群体研究，解决了长读长数据TR分析的计算瓶颈。

## 7. 优点
- **高效性**：流式+并行设计将基因分型时间从小时级压缩至分钟级，内存占用低。
- **全流程覆盖**：不仅提供基因分型，还集成群体遗传学分析工具，减少用户在多工具间切换的成本。
- **基于长读长**：相比短读长方法，能更准确地解析重复长度变异。
- **开源可复现**：命令行工具包易于集成到管道。

## 8. 不足与局限
- **实验覆盖面有限**：仅在有限样本和真值集上验证，未在多个不同平台、不同物种、不同重复类型（如短串联重复 vs. 可变数目串联重复）上广泛测试。
- **未提供消融实验**：无法量化流式处理或并行化各自对性能的贡献。
- **依赖参考目录**：基因分型准确性受限于预定义目录的完整性，对de novo重复区域可能不适用。
- **潜在偏差**：真值集可能偏向于已知重复扩展，对罕见或复杂结构重复的评估未涉及。
- **应用限制**：仅适用于长读长数据，无法用于海量短读长群体数据；未提及对多倍体或嵌合体的支持。

（完）
