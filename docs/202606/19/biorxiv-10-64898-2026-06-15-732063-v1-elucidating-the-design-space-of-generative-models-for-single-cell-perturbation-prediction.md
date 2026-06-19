---
title: Elucidating the Design Space of Generative Models for Single-Cell Perturbation Prediction
title_zh: 阐明单细胞扰动预测生成模型的设计空间
authors: "Bhattacharya, S., Gensbigler, C., Karim, S., Lees, J."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732063v1.full.pdf"
tags: ["query:med-ai"]
score: 8.0
evidence: 面向单细胞扰动预测的生成模型（虚拟细胞）
tldr: 单细胞RNA-seq数据缺乏自然基因顺序，直接应用next-token预测效果不佳。为此提出ExpressionVAE，通过有限标量量化将细胞压缩为离散编码序列，并训练扰动条件先验。在多个数据集上，eVAE在分布指标和扰动预测指标上均达到最优，显著优于连续潜变量模型。该工作揭示了离散潜变量的关键作用，并发现了影响指标权衡的设计轴。
source: biorxiv
selection_source: fresh_fetch
motivation: 单细胞RNA-seq无自然基因序，直接使用语言模型预测失败，需探索适合无顺序数据的潜变量生成模型。
method: 提出eVAE，通过FSQ离散瓶颈将细胞压缩为短编码序列，并训练扰动条件离散先验。
result: 在Replogle和Parse 1M上，Fréchet距离和MMD^2比连续基线低3-20倍，所有分布指标达SOTA。
conclusion: 离散潜变量是性能提升关键；解码器消融显示预测分布丰富度是影响方差与均值指标反向变化的设计轴。
---

## 摘要
下一个词元预测已在语言领域产生了可预测的缩放行为，但这一方法假设词元序列具有有意义的顺序。单细胞RNA-seq计数没有天然的基因顺序，因此直接将这一方法应用于原始表达数据会在不合适的从左到右偏置下失败。我们转而探究能否通过学习得到的潜在变量来提供该方法所需的结构。我们提出了\texttt{ExpressionVAE}（eVAE），一种离散潜在变量扰动模型，通过有限标量量化（FSQ）瓶颈将每个细胞压缩为短序列的离散编码，并在这些编码上训练一个扰动条件化的离散先验。在Replogle和Parse~1M数据集上，eVAE在所有分布度量上均达到了新的最优水平，并在大多数细胞评估扰动度量上领先，其Fréchet距离和$\mathrm{MMD}^2$比最强的连续潜在基线低约3到20倍。将先验在自回归和掩蔽离散扩散之间切换，性能几乎相同，从而将收益归因于离散潜在变量本身而非先验家族。随后，解码器头部的消融实验揭示了一个单一的设计轴，即推理时预测分布的丰富度，该轴将标准度量分为两组——方差敏感和均值敏感，它们沿该轴朝相反方向移动。最后，在一个包含1,732个扰动且处于炎症细胞因子胁迫下、留出的CRISPRi回复基准测试中，冻结的eVAE编码器在扰动排序上优于UMAP和差异表达分析，并且仅使用少量数据就与scGPT性能相当。

## Abstract
Next-token prediction has produced predictable scaling in language, but the recipe presumes a sequence of tokens with a meaningful order. Single-cell RNA-seq counts have no natural gene ordering, so applying the recipe directly to raw expression fails under an ill-suited left-to-right bias. We instead ask whether a learned latent can supply the structure the recipe needs. We introduce \texttt{ExpressionVAE} (eVAE), a discrete-latent perturbation model that compresses each cell into a short sequence of discrete codes through a finite-scalar-quantization (FSQ) bottleneck and trains a perturbation-conditioned discrete prior over those codes. On Replogle and Parse~1M, eVAE sets a new state of the art on every distributional metric and leads on most cell-eval perturbation metrics, with Fr\'echet distance and $\mathrm{MMD}^2$ roughly $3$ to $20\times$ lower than the strongest continuous-latent baseline. Swapping the prior between autoregressive and masked discrete diffusion leaves performance near-identical, isolating the gain to the discrete latent itself rather than the prior family. A decoder-head ablation then exposes a single design axis, the richness of the predictive distribution at inference, that splits the standard metrics into two groups, variance-sensitive and mean-sensitive, which move in opposite directions along the axis. Finally, on a held-out CRISPRi reversion benchmark of $1{,}732$ perturbations under inflammatory cytokine stress, the frozen eVAE encoder outperforms UMAP and differential expression and matches scGPT on perturbation ranking at a fraction of the data.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **核心问题**：单细胞 RNA-seq 数据缺乏自然的基因顺序，直接套用语言模型中的 next-token 预测（自回归）会因不合适的左到右偏置而失败。因此需要设计一种适合无顺序、高维、稀疏计数数据的生成模型，用于预测细胞在遗传或化学扰动后的转录组变化（即“虚拟细胞”）。
- **整体含义**：论文通过引入离散潜在变量（离散编码序列）来为无顺序数据提供结构，显著提升了分布保真度和扰动预测性能，揭示了离散潜变量和推理时采样丰富度是影响指标权衡的关键设计轴。这项工作为构建有效的虚拟细胞模型提供了新的范式，有望推动 in-silico 药物发现。

---

## 2. 方法论

### 核心思想
采用两阶段流水线：
1. **Stage 1：ExpressionVAE**  
   将每个细胞的基因表达向量压缩为**固定长度的离散编码序列**（L=64 个 token），通过**有限标量量化（FSQ）** 实现无参数离散瓶颈，消除 VQ-VAE 常见的 codebook collapse。  
   解码器将离散编码映射回基因空间，并配合不同的输出似然头。

2. **Stage 2：扰动条件离散先验**  
   冻结 VAE，训练一个扰动条件化（基于 ESM2-3B 蛋白嵌入和细胞类型）的生成先验，用于建模离散编码序列的分布。可选先验家族：
   - **自回归（AR）**：因果掩码 DiT，顺序解码。
   - **掩蔽离散扩散（MDLM）**：双向 DiT 去噪器，单遍并行解码。

### 关键技术细节
- **FSQ 量化**：对每个维度执行 tanh 后取整，形成统一网格；字典大小 K=512，维度水平向量 ℓ 乘积为 K。
- **输出头家族**（反映推理时预测分布的丰富度梯度）：
  - `ce-quant`：20 个分位数桶的分类分布，采样。
  - `nb-sample`：负二项分布，采样（过离散）。
  - `hurdle`：伯努利零门控 + 确定性正值 MSE。
  - `mse`：直接回归 log1p 计数，确定性输出。
  - `nb-deter`：负二项分布，只返回均值 μ（确定性）。
- **先验训练**：DiT 骨干（6 层，8 头，d_model=384），adaLN-Zero 条件化扰动嵌入和细胞类型信号。AR 和 MDLM 共享相同容量，仅解码策略不同。
- **推理**：给定新扰动，先验采样离散编码序列，经解码器和输出头得到预测表达谱。

---

## 3. 实验设计

### 数据集与基准
- **Replogle (HepG2)**：CRISPRi 必需基因敲除，留出 372 个扰动。
- **Parse 1M**：细胞因子扰动（~1M 细胞），留出 27 个细胞因子（CD4 Naive 背景）。
- **TeloHAEC 表型回复基准**：1,732 个 CRISPRi 扰动（IL-1β/TNF-α 炎症应激），用于评估冻结编码器的生物学泛化性。

### 对比方法
六种基线：
- 连续潜变量：scVI、CPA、scLDM（流匹配）。
- 表达空间基础模型：scGPT、STATE。
- 非参数基线：PerturbMean（均值基线）。

### 消融实验
- **先验消融**：AR vs MDLM（共享骨干容量）。
- **解码器头部消融**：5 个头部在同一训练骨干上比较（ce-quant、nb-sample、hurdle、mse、nb-deter）。
- **代码本大小/ token 长度消融**（见附录）。
- **冻结编码器评估**：在表型回复任务上比较不同编码器-解码器组合。

### 评估指标
- **分布指标（方差敏感）**：Wasserstein-2 距离（W2）、最大均值差异（MMD²）、Fréchet 距离（FD）——均在 PCA-30 空间中计算。
- **细胞评估（DE 发现与排序）**：
  - 方差敏感：PR-AUC、Spearman sig、PDS（L1 全向量）、disc_l1。
  - 均值敏感：Spearman LFC、overlap@N、Pearson Δ。

---

## 4. 资源与算力

**论文未明确说明使用的 GPU 型号、数量或总训练时长**。  
仅给出以下可参考信息：
- Stage 1 VAE 训练 75,000 步，批大小 128。
- Stage 2 先验训练 75,000 步，批大小 128。
- 使用了 AdamW 优化器、余弦学习率调度，梯度裁剪 1.0。  
- 附录中提及在 Replogle 上进行了代码本大小消融，但未提供时间/功耗数据。

**结论**：实验可复现，但资源消耗不透明，可能对资源不足的研究者构成复现门槛。

---

## 5. 实验数量与充分性

### 实验规模
- **主结果表**：2 个数据集 × 2 先验 × 2 输出头（NB-sample 和 MSE），对比 6 个基线，报告 9 个指标，4 个随机种子（均值±SE）。
- **解码器头部消融**（图 3）：5 个头部 × 2 先验，在两个数据集上全面展示指标分组趋势。
- **代码本消融**（附录表 4）：L∈{64,128} × K∈{512,1024}，加流基线。
- **表型回复评估**（图 4-5）：冻结编码器，多个编码器/解码器组合，比较了 UMAP、差异表达、scGPT。

### 充分性与公平性
- 控制变量严谨：先验消融中两个先验共享相同骨干容量；NB 采样 vs 确定性 NB 共享完全相同的权重，仅推理规则不同，完美分离采样轴。
- 与基线比较时，使用与 scLDM 相同的训练/测试划分，部分指标（PR-AUC, Sp-sig, P-Δ）直接引用 STATE 论文结果，确保可比性。
- 4 种子平均报告标准误差，统计可靠性高。

**结论**：实验设计系统、充分，消融链条清晰，对比公平。

---

## 6. 主要结论与发现

1. **离散潜变量显著优于连续潜变量**：在分布指标上，eVAE 的 MMD² 和 FD 比最强的连续基线（scLDM）低 3–20 倍；在细胞评估指标上也全面领先。
2. **先验家族不影响性能**：AR 和 MDLM 在所有指标上几乎相同，证明收益来自离散潜变量本身而非先验架构。
3. **解码器头部选择由单一“采样丰富度”轴支配**：
   - 方差敏感指标（分布指标、PR-AUC、Sp-sig）受益于采样头部（ce-quant、nb-sample）。
   - 均值敏感指标（Sp-LFC、overlap@N、Pearson Δ）受益于确定性头部（mse、nb-deter）。
   - NB 采样 vs 确定性 NB 的直接对比排除了其他混淆因素，确认此轴。
4. **冻结的 eVAE 编码器在表型回复任务上表现强**：Hurdle 解码器达到最佳 Enrichment AUC（0.792），与 scGPT（0.79）相当，但训练数据量少一个数量级。

---

## 7. 优点

- **方法创新**：首次将离散潜在变量（FSQ）与扰动条件先验结合用于单细胞生成建模，解决了无顺序数据难题。
- **实验设计精巧**：控制变量（先验、头部、采样轴）分离清晰，NB 内对比完美隔离采样效应；优先前文献中矛盾的指标排名得到统一解释。
- **评估全面**：同时覆盖分布质量、DE 发现、基因排序和生物学泛化，避免单一指标误导。
- **实用性验证**：在留出生物任务（CRISPRi 表型回复）上验证了表示学习能力的泛化性，且仅用 1M 细胞数据达到与 10× 数据量基础模型相当的水平。
- **开源代码**：提供了完整的代码仓库，便于复现与扩展。

---

## 8. 不足与局限

- **数据集覆盖有限**：仅测试了两个扰动数据集（CRISPR 敲除和细胞因子），未涵盖更多细胞类型、化学扰动、剂量梯度或时间序列，泛化性有待进一步验证。
- **表型回复基准的模糊性**：该基准存在多种分布偏移（细胞类型、扰动集、生物背景），难以清晰归因是哪个设计轴导致了泛化；作者也指出这一点。
- **计算资源不透明**：未报告 GPU 型号、数量、训练总时长，对于资源敏感的研究者复现成本未知。
- **可扩展性未测试**：仅使用 2000 个高变基因，对全基因组（~20,000 基因）或更多 token（L>64）的扩展性未实验。
- **与 scGPT 的比较不够严格**：scGPT 使用不同预训练数据集，且并非在完全相同测试集上训练；仅提到“匹配”性能，并非严格公平的 SOTA 超越。
- **多组学限制**：仅基于 scRNA-seq，未整合蛋白、染色质、空间等数据，限制了虚拟细胞的完整态。
- **附录中缺少部分消融细节**：如更广泛的超参数扫描（学习率、深度）未报告，可能影响最优配置的绝对性。

---

（完）
