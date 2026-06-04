---
title: Improved Convex Decomposition with Ensembling and Boolean Primitives
title_zh: 改进的凸分解：结合集成与布尔原语
authors: "Vaibhav Vavilala, Florian Kluger, Seemandhar Jain, Bodo Rosenhahn, David Forsyth"
date: 2025-01-22
pdf: "https://openreview.net/pdf?id=nHaaNf5cOM"
tags: ["query:part-aware"]
score: 9.0
evidence: 改进的凸分解将场景描述为图元，实现部件的分割
tldr: 针对场景解析中图元拟合问题，现有方法评估困难且图元数量固定。本文提出改进的凸分解方法，通过集成学习和布尔操作（如集合差）增强CSG表示。方法先用学习回归预测初始图元，再进行下降优化和去冗余。实验在深度、法线和分割预测上均优于现有技术，为紧凑且可解释的3D形状分解提供了新途径。该工作表明，布尔操作能显著提升基于原语的场景描述能力，对于三维视觉理解与生成中的部件级表示具有重要意义。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1593, \"height\": 1103, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1767, \"height\": 953, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1807, \"height\": 1182, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1760, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 825, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 813, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 864, \"height\": 1140, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1768, \"height\": 940, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 866, \"height\": 1098, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 862, \"height\": 1090, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1770, \"height\": 1153, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1881, \"height\": 2013, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1770, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-nhaanf5com/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1418, \"height\": 570, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-nhaanf5com/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1777, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nhaanf5com/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1426, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nhaanf5com/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 758, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nhaanf5com/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1776, \"height\": 1095, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nhaanf5com/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1776, \"height\": 882, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nhaanf5com/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1775, \"height\": 881, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-nhaanf5com/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1881, \"height\": 1276, \"label\": \"Table\"}]"
motivation: 现有场景解析中图元拟合困难，不同场景需不同数量图元且图元间强交互。
method: 提出集成学习方法与布尔操作增强的凸分解，从学习回归起点开始，经下降法优化并移除冗余。
result: 预测深度、法线和分割精度优于现有方法，图元表示更精确。
conclusion: 布尔操作显著提升CSG表示能力，为可解释的紧凑场景描述提供了新途径。
---

## Abstract
Describing a scene in terms of primitives -- geometrically simple shapes that offer a parsimonious but accurate abstraction of structure -- is an established and difficult fitting problem. Different scenes require different numbers of primitives, and these primitives interact strongly. Existing methods are evaluated by predicting depth, normals and segmentation from the primitives, then evaluating the accuracy of those predictions. The state of the art method involves a learned regression procedure to predict a start point consisting of a fixed number of primitives, followed by a descent method to refine the geometry and remove redundant primitives. CSG representations are significantly enhanced by a set-differencing operation. Our representation incorporates $\textit{negative}$ primitives, which are differenced from the positive primitives. These notably enrich the geometry that the model can encode, while complicating the fitting problem. This paper  demonstrates a method that can (a) incorporate these negative primitives and (b) choose the overall number of positive and negative primitives by ensembling. Extensive experiments on the standard NYUv2 dataset confirm that (a) this approach results in substantial improvements in depth representation and segmentation over SOTA and (b) negative primitives make a notable contribution to accuracy. Our method is robustly applicable across datasets: in a first, we evaluate primitive prediction for LAION images. Code will be released upon acceptance of the paper.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **研究问题**：如何将复杂的室内外场景自动、紧凑地表示为几何基元（如凸多面体）的集合，以便于高层推理与交互（如场景编辑、机器人规划）。该问题长期存在，困难在于不同场景需要不同数量的基元，且基元之间强耦合，极易陷入拟合的局部极小值。
*   **核心动机**：现有方法多采用固定数量的正基元，表达能力受限。引入**构造实体几何（CSG）中的布尔差运算（即“负基元”）** 能极大丰富可编码的几何形状，但会显著增加拟合难度。本工作旨在同时解决“负基元拟合”与“自动确定基元数量”两个关键挑战。
*   **整体含义**：通过集成学习与布尔基元，本文在场景基元分解任务上取得了显著的性能突破，证明负基元对精度有实质性贡献，并且能够自适应地为每张图像选择最优基元组合，从而推动可解释、可编辑的紧凑场景表示向前发展。

### 2. 论文提出的方法论
*   **核心思想**：提出一种两阶段框架——先由神经网络预测多组不同数量（含正/负）的基元作为起点，再通过测试时优化进行精修，最后利用深度图评估选出最佳基元集合。
*   **负基元与CSG表示**：
    *   基元为平滑多面体（参数包括中心、法线、偏移、混合系数），可拟合曲面。
    *   通过集合差运算构造最终物体指示函数：\( O(\mathbf{x}) = \text{relu}(O^{+}(\mathbf{x}) - O^{-}(\mathbf{x})) \)，其中 \(O^{+}, O^{-}\) 分别为正、负基元的并集指示函数。这使得少数基元即可表达“挖洞”等复杂结构。
*   **集成与基元数量选择**：
    *   针对18种不同的 \((K_{\text{total}}, K_{-})\) 组合（\(K_{\text{total}}\) 为总基元数 12/24/36，\(K_{-}\) 为负基元数 0~32）分别训练独立的预测网络（ResNet-18编码器+MLP解码器，接受 RGB-D 输入）。
    *   提出两种集成策略：**S→R**（先基于样本分类误差选择最佳网络预测，再精修）和 **R→S**（对所有网络的预测都进行精修，再根据绝对相对深度误差选出最优者）。
*   **测试时精修**：利用输入深度图作为监督，采用 AdamW 优化器直接对基元参数进行梯度下降，并采用大规模点云采样和子采样策略以提升梯度丰富度和效率。
*   **损失函数**：复用常用的样本损失、唯一参数化损失、重叠损失、引导损失和定位损失，同时作用于正、负基元，但移除了曼哈顿世界损失、体积损失和分割损失。

### 3. 实验设计
*   **数据集与场景**：
    *   **NYUv2**：标准室内场景RGB-D数据集，使用官方795/654划分。评估深度图、法线图以及基于基元面标签的预测类别语义分割（Oracle分割）。
    *   **LAION**：从LAION-Aesthetic收集约180万张开放场景自然图像，利用预训练深度估计网络（Depth Anything V2）生成伪深度图和点云进行训练与评估，验证方法的跨域泛化性。
*   **基准与对比方法**：
    *   主要对比 SOTA 方法：**Vavilala & Forsyth (ICCV 2023)** 和 **Kluger et al. (CVPR 2021)**。
    *   消融对比：纯正基元集成 vs 正负基元集成；仅精修不集成 vs 集成选择；网络起点 vs 纯随机起点优化。
    *   基元面数影响：分析了6面与12面多面体的性能差异。
*   **评估指标**：深度指标（AbsRel, AUC@50/20/10/5, 平均/中位距离误差）、法线指标（平均/中位角度误差）、Oracle分割准确率。

### 4. 资源与算力
*   **硬件**：所有网络训练均在 **单张 A40 GPU** 上完成。
*   **训练时长**：在 NYUv2 上，训练一个12基元模型约 **39 分钟**，训练一个32基元模型约 **62 分钟**。LAION 数据集上训练步数增加至 30000 步。
*   **推理效率**：单张图像编码约0.0006秒，200步精修耗时占主导（12基元约0.68秒，36基元约1.79秒）。通过 TorchScript、BFloat16混合精度和批处理大幅加速推理。

### 5. 实验数量与充分性
*   **实验规模**：两组数据集（NYUv2, LAION），两种面数设置（6面、12面），18组单模型结果，多组集成策略消融，以及随机起点对比、模型频率分布统计、推理时间分析等。
*   **充分性与公平性**：实验设计较为全面，覆盖了多个维度（基元数、负基元数、集成方式、面数、数据集）。对比的基准方法均为近期SOTA，且使用了标准数据集和划分，多指标评估，结果具有说服力。消融实验清晰展示了负基元和集成各自的贡献。

### 6. 论文的主要结论与发现
*   **负基元至关重要**：引入负基元极大地提升了深度与分割精度，使模型可以表达更丰富、更精确的几何细节。模型频率直方图显示，集成算法在许多场景下主动选择了带负基元的模型。
*   **集成显著提升性能**：通过集成不同基元数量的模型，实现了自适应选择，整体性能远超任何固定基元数的单模型，也比先前 SOTA 有大幅提升（AbsRel 相对误差降低超50%）。
*   **网络起点远优于纯优化**：即使纯随机起点加梯度下降也能得到可用基元，但神经网络提供的起点能让后续优化收敛更快、最终效果更好。
*   **方法跨数据集鲁棒**：在开放场景 LAION 上同样有效，且增加基元面数可进一步改善拟合质量，证实了方法的通用性。
*   **实际应用潜力**：初步展示了如何利用本方法提取的基元进行场景编辑、视角变化和可控图像生成，具有实际应用价值。

### 7. 优点
*   **创新性强**：首次成功地将布尔负基元融入基于学习的场景级基元分解，并配合集成策略解决数量选择难题，实验证明改进巨大。
*   **框架有效且紧凑**：延续并优化了预测+精修的范式，损失函数复用现有组件，实现相对简洁但效果斐然。
*   **实验扎实全面**：在两个差异性较大的数据集上进行了大量定量、定性和消融实验，充分验证了各模块的贡献。
*   **推理效率高**：通过工程优化（混合精度、JIT编译），在实现集成带来的精度增益的同时，控制了总体推理耗时。

### 8. 不足与局限
*   **对深度图的依赖**：训练和测试时精修均需深度图，在仅有RGB图像的场景下依赖预训练深度估计网络，其误差可能会传递并限制基元质量。
*   **拟合问题的本质局限**：测试时精修虽强，但文中提到好的起点未必导向最好的终点（S→R不如R→S），说明拟合问题仍存在局部极小值风险。
*   **基元类型相对简单**：目前仅支持凸多面体，虽然通过负基元提升了表达能力，但处理高度非凸、细长或复杂拓扑结构可能仍需大量基元或存在局限。
*   **评估的间接性**：没有真实基元标注，评估都是通过深度、法线、分割等中间任务间接进行，无法直接度量基元分解的几何正确性和语义合理性。
*   **应用验证尚浅**：虽然展示了编辑潜力，但未在更复杂的实际下游任务（如机器人抓取、高保真场景重建）中系统评估。

（完）
