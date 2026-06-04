---
title: Compositional Scene Understanding through Inverse Generative Modeling
title_zh: 通过逆生成式建模实现组合场景理解
authors: "Yanbo Wang, Justin Dauwels, Yilun Du"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=JmOCquEAqW"
tags: ["query:part-aware"]
score: 7.0
evidence: 通过组合场景小块模型实现逆生成式建模，推断物体级别结构
tldr: 现有的生成模型多用于合成，本文探索将其用于场景理解，将之视为逆问题——寻找能最佳拟合输入图像的条件参数。为使模型能从异域图像推断，构建组合式生成模型，由场景各部分的子模型构成。实验展示该方法能够推断物体集合、位姿与形状，无需监督信号。这不仅扩展了生成模型的应用，也为场景的语义、部件级解析提供了统一框架。该工作为通过生成先验实现无监督的部件发现与结构化理解铺平了道路，对于自动驾驶、机器人抓取等任务中从单一图像理解场景具有潜在价值。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jmocqueaqw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 832, \"height\": 848, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmocqueaqw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1765, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmocqueaqw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 839, \"height\": 627, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmocqueaqw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmocqueaqw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1770, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmocqueaqw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1768, \"height\": 533, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmocqueaqw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 865, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmocqueaqw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 846, \"height\": 1352, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmocqueaqw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 854, \"height\": 1366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmocqueaqw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 849, \"height\": 1226, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmocqueaqw/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 846, \"height\": 1249, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmocqueaqw/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1779, \"height\": 1074, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jmocqueaqw/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 849, \"height\": 1362, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jmocqueaqw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 779, \"height\": 420, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmocqueaqw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1691, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmocqueaqw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 835, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmocqueaqw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 802, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmocqueaqw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1542, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmocqueaqw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 638, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmocqueaqw/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1734, \"height\": 328, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmocqueaqw/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1115, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmocqueaqw/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1179, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jmocqueaqw/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 849, \"height\": 1362, \"label\": \"Table\"}]"
motivation: 生成模型不仅可用于合成，还可用于理解单张图像中的场景属性。
method: 将场景理解转为拟合条件生成模型参数，组合各部件模型来结构发现。
result: 能推断物体集合与属性，即使测试图与训练分布不同也有效。
conclusion: 提供了一种无监督的、基于部件的场景理解新范式。
---

## Abstract
Generative models have demonstrated remarkable abilities in generating high-fidelity visual content. In this work, we explore how generative models can further be used not only to synthesize visual content but also to understand the properties of a scene given a natural image. We formulate scene understanding as an inverse generative modeling problem, where we seek to find conditional parameters of a visual generative model to best fit a given natural image. To enable this procedure to infer scene structure from images substantially different than those seen during training, we further propose to build this visual generative model compositionally from smaller models over pieces of a scene. We illustrate how this procedure enables us to infer the set of objects in a scene, enabling robust generalization to new test scenes with an increased number of objects of new shapes. We further illustrate how this enables us to infer global scene factors, likewise enabling robust generalization to new scenes. Finally, we illustrate how this approach can be directly applied to existing pretrained text-to-image generative models for zero-shot multi-object perception. Code and visualizations are at https://energy-based-model.github.io/compositional-inference.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：如何利用生成模型实现更通用、更具泛化性的场景理解，特别是当测试场景显著比训练场景复杂时（如物体更多、类别分布不同、背景完全变化）。
- **整体含义**：传统判别式模型在场景理解中泛化能力有限，而生成模型天然具有建模数据分布的潜力。这篇论文将“场景理解”重新定义为**逆生成式建模问题**——即寻找一组条件参数，使得一个生成模型能够最好地“解释”或“重建”给定的输入图像。通过**组合式生成建模**，模型能够将场景分解为多个独立视觉概念，并分别由小型子生成模型表示，从而实现对训练分布之外场景的鲁棒推断。最终目标是让机器像人类一样，用可组合的抽象概念无监督地解析新场景。

### 2. 论文提出的方法论

- **核心思想**：
  - **组合式生成建模**：将一个复杂场景的生成过程分解为多个独立视觉概念（如单个物体的位置、人脸属性）生成过程的乘积。假设图像的条件概率可近似为  
    \( p(x | c_1, \dots, c_K) \propto \prod_{k=1}^K p(x | c_k) \)。
  - **能量模型与扩散模型结合**：每个 \( p(x|c_k) \) 用能量模型（EBM）表示 \( e^{-E_\theta(x|c_k)} \)，并通过扩散模型中的去噪函数 \( \epsilon_\theta(x_t, t|c_k) \) 来参数化其分数函数 \( \nabla_x E_\theta \)。
  - **组合去噪函数**：对于多个概念，总去噪函数为各子模型的求和：  
    \( \epsilon_\theta^\text{comb}(x_t, t) = \sum_{k=1}^K \epsilon_\theta(x_t, t | c_k) \)。
  - **端到端训练**：直接优化组合后的去噪目标 \( \mathcal{L} = \mathbb{E}_{x,\epsilon,t} \|\epsilon - \sum_k \epsilon_\theta(x_t, t|c_k)\|^2 \)，使子模型能够协同工作。

- **场景理解作为逆问题**：
  - 给定图像 \( x \)，通过优化找到概念参数 \( \hat{c}_1,\dots,\hat{c}_K \) 使下式最小化：  
    \( \mathbb{E}_{\epsilon,t} \big\| \epsilon - \sum_{k=1}^K \epsilon_\theta(x_t, t|c_k) \big\|^2 \)。
  - **离散概念推理**（如人脸属性）：直接枚举所有可能的离散概念组合，计算平均去噪误差，选误差最小的组合（第 4 章 Algorithm 2）。为了加速，还设计了基于梯度的连续松弛优化（Algorithm 5）。
  - **连续概念推理**（如物体坐标）：采用随机梯度下降（SGD），并引入**多次随机初始化策略**：同时维护 \( R \) 组初始值分别优化，最终选取使去噪误差最小的那组，以减轻非凸优化易陷入局部极小的问题（Algorithm 3）。
  - **概念数量推断**：当场景中概念数量 \( K \) 未知时，对每个可能的 \( K \) 值进行概念推断，然后选择使平均去噪误差最小的 \( K \)（Algorithm 4）。

- **算法流程**：
  1. 训练阶段：用包含 \( K \) 个概念的图像数据，训练组合去噪网络 \( \epsilon_\theta \)（Algorithm 1）。
  2. 推理阶段：输入单张图像，用上述逆优化方法推断出概念参数（连续或离散）以及概念数量。

### 3. 实验设计

- **任务与数据集**：

  | 任务 | 训练集 | 测试集（分布内） | 测试集（分布外） | 对比方法 |
  |------|--------|------------------|------------------|----------|
  | **局部因子感知（物体发现）** | CLEVR（3～5个物体） | CLEVR（3～5个物体） | CLEVR（6～8个物体）、CLEVRTex（6～8个物体，不同纹理、形状） | ResNet-50、Slot Attention、DINOSAUR、Generative Classifier |
  | **全局因子感知（人脸属性）** | CelebA **女性**人脸（黑发、眼镜、微笑三项属性） | CelebA 女性人脸 | CelebA **男性**人脸 | ResNet-50、Generative Classifier、GC 变体 |
  | **零样本多物体感知** | **无需训练**，直接使用预训练 Stable Diffusion | — | 71 张真实网络图像，包含 {狗, 猫, 兔} 中的两两组合 | Diffusion Classifier、DC 变体 |

- **评价指标**：
  - 物体发现：**感知率**（正确匹配的物体比例，MSE < 0.002）和**坐标估计误差**（平均 MSE）。
  - 人脸属性：**分类准确率**（三项属性同时预测正确才算对）。
  - 零样本感知：**分类准确率**。

### 4. 资源与算力

- 论文正文及附录**未明确提及**使用的 GPU 型号、数量、训练时长或总计算量。仅提到推理效率评估在 “NVIDIA H100 GPU” 上进行（用于比较推理时间，见表 VII、VIII），但训练相关算力细节缺失。

### 5. 实验数量与充分性

- 至少完成了以下**主要实验组**：
  - **三个不同维度的场景理解任务**（物体发现、人脸属性、零样本感知）。
  - **每个任务均包含分布内和分布外的对比评估**，与多个基线方法比较（共约 6 组对比表格）。
  - **消融实验**：
    - 多随机初始化策略的效果（1、5、10、15、20 次初始化，表 IV）。
    - 概念数量推断的可视化验证（图 3、图 XII）。
    - 梯度连续近似对离散推理的效率与精度影响（表 VII、VIII）。
    - 提示加权 (prompt weighting) 作为零样本基线的附加实验（表 V）。
    - 额外在 CLEVRTex 上单独评估物体发现（表 VI）。
  - **定性可视化**大量提供。

- **充分性与公平性**：
  - 实验设计比较**充分**：覆盖了合成数据到真实数据、连续参数到离散参数、有监督到零样本等多场景。
  - 对比方法选择合理，包含判别式和生成式基线，且对基线进行了适当改造以适配多概念任务。
  - 尽管缺少训练算力报告，但任务本身和模型规模相对较小，实验对比在相同测试条件下进行，**客观性和公平性较好**。

### 6. 论文的主要结论与发现

- 组合式逆生成建模能够**大幅提升场景理解的泛化能力**，尤其是在训练与测试分布差异极大的情况下（例如物体数量增加或换用全新数据集）。
- 在物体发现任务中，该方法在 CLEVR 上的分布外感知率（85.3%）远优于最好基线 GC（58.7%）；在 CLEVRTex 上也保持了明显优势（72.4% vs 52.9%）。
- 在人脸属性分类中，在男性脸上测试时准确率（65.6%）同样高于 GC（61.7%）和 ResNet（62.2%）。
- 在零样本多物体感知中，直接应用 Stable Diffusion 并用组合去噪误差进行推理，准确率达到 87.3%，显著优于 Diffusion Classifier（70.4%）。
- 多次随机初始化对避免连续概念优化中的局部极小至关重要。

### 7. 优点

- **统一的生成式框架**：将物体定位、多属性分类、零样本感知等任务纳入同一个逆优化范式。
- **强大的组合泛化**：通过子模型的独立性与组合性，模型能自适应从未见过的概念数量和场景类型。
- **利用预训练模型**：可以直接嫁接 Stable Diffusion 实现零样本多物体理解，无需任何微调。
- **灵活的概念类型**：同时支持连续概念（坐标）和离散概念（标签），且能推断概念数量。
- **工程上的实用性**：提供了基于梯度的连续松弛方法，缓解了枚举带来的指数级计算开销，在精度和效率之间取得平衡。

### 8. 不足与局限

- **概念独立性假设过强**：组合模型假设各视觉概念之间条件独立，忽略了物体间的交互（如遮挡、空间关系），可能限制在高度结构化场景中的性能。作者提到可学习交互模型作为补救，但未在本工作中实现。
- **离散概念计算成本高**：直接枚举所有概念组合的复杂度为 \(O(M^K)\)，当可能类别数或概念数较多时难以承受。梯度松弛法虽能加速，但在某些实验中会牺牲一定精度（如零样本准确率从 87% 降至 75%）。
- **连续优化仍可能陷入局部极小**：尽管多初始化能缓解，但并不能完全保证收敛到全局最优解。
- **零样本感知评估规模偏小**：仅使用了 71 张图像且只有三种动物类别，结论的普适性有待更大规模数据集的验证。
- **缺乏复杂真实场景测试**：物体发现实验只在合成数据集（CLEVR 及变体）上进行，未在真实图像中验证物体定位能力。
- **计算资源不透明**：未报告训练所用 GPU 型号、数量、训练时长等，不利于精确复现和成本评估。

（完）
