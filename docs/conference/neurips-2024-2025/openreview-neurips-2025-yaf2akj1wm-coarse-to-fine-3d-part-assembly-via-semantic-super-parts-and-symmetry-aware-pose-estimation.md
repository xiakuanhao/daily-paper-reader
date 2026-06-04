---
title: Coarse-to-Fine 3D Part Assembly via Semantic Super-Parts and Symmetry-Aware Pose Estimation
title_zh: 基于语义超部件与对称性感知姿态估计的由粗到细三维零件装配
authors: "Xinyi Zhang, Bingyang Wei, Ruixuan Yu, Jian Sun"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=yAf2Akj1Wm"
tags: ["query:part-aware"]
score: 10.0
evidence: 由粗到细的三维零件装配方法，将基本零件组装成完整形状
tldr: 该论文针对三维零件装配中的局部几何推理与全局结构理解挑战，提出由粗到细的装配框架（CFPA）。方法首先通过最优传输构建语义超部件来捕获对象高层结构，然后借助跨阶段特征传播细化零件姿态。实验结果表明，该方法在装配精度和语义一致性方面优于现有技术，为复杂零件装配提供了有效途径。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaf2akj1wm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaf2akj1wm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 497, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaf2akj1wm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1450, \"height\": 736, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaf2akj1wm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1433, \"height\": 716, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaf2akj1wm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 723, \"height\": 498, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaf2akj1wm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1121, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaf2akj1wm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1432, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaf2akj1wm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1412, \"height\": 822, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaf2akj1wm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1416, \"height\": 784, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yaf2akj1wm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1407, \"height\": 818, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaf2akj1wm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 521, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaf2akj1wm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 500, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaf2akj1wm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaf2akj1wm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 734, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaf2akj1wm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 742, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaf2akj1wm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 751, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaf2akj1wm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1451, \"height\": 520, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaf2akj1wm/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1448, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaf2akj1wm/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1446, \"height\": 493, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaf2akj1wm/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1444, \"height\": 492, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaf2akj1wm/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 764, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaf2akj1wm/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1365, \"height\": 771, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yaf2akj1wm/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 772, \"height\": 224, \"label\": \"Table\"}]"
motivation: 三维零件装配需要精确的局部几何推理和全局结构理解，以生成语义连贯的完整形状。
method: 提出由粗到细的两阶段框架：先用最优传输构建语义超部件，再通过对称性感知细化姿态。
result: 在多个基准上实现了高精度装配，验证了语义抽象和对称性推理在零件装配中的有效性。
conclusion: 该方法为复杂三维形状的零件装配提供了统一的解决方案，推动了自动化装配领域的发展。
---

## Abstract
We propose a novel two-stage framework, Coarse-to-Fine Part Assembly (CFPA), for 3D shape assembly from basic parts. Effective part assembly demands precise local geometric reasoning for accurate component assembly, as well as global structural understanding to ensure semantic coherence and plausible configurations. CFPA addresses this challenge by integrating semantic abstraction and symmetry-aware reasoning into a unified pose prediction process. In the first stage, semantic super-parts are constructed via an optimal transport formulation to capture high-level object structure, which is then propagated to individual parts through a dual-range feature propagation mechanism. The second stage refines part poses via cross-stage feature interaction and instance-level geometric encoding, improving spatial precision and coherence. To enable diverse yet valid assemblies, we introduce a symmetry-aware loss that jointly models both self-symmetry and inter-part geometric similarity, allowing for diverse but structurally consistent assemblies. Extensive experiments on the PartNet benchmark demonstrate that CFPA achieves state-of-the-art performance in assembly accuracy, structural consistency, and diversity across multiple categories.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
这篇论文旨在解决**三维零件装配**任务——即从一组独立的、零散的三维零件（如椅子的腿、座面、靠背），精确预测每个零件的6自由度位姿（旋转和位移），将它们组装成一个完整、语义连贯的三维形状。该任务的核心挑战在于：
*   **局部与全局的双重需求**：既需要精确的局部几何推理来保证零件间的准确拼接，又需要强大的全局结构理解能力来确保装配结果在语义上合理、形态上正确。
*   **对称性带来的歧义性**：现实物体中广泛存在零件自身的对称性（如方形座面）和零件间的几何相似性（如四条相同的椅腿），这导致了多种同样有效的装配方案，给标准的监督学习带来了困难。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
论文提出了一个名为**CFPA (Coarse-to-Fine Part Assembly)** 的两阶段框架，其核心思想是通过引入语义抽象和对称性感知推理，统一解决上述挑战。

*   **第一阶段：基于语义超部件的粗粒度姿态估计**
    *   **语义超部件构建**：利用最优传输理论，将所有零件特征 `{f_i}` 软分配到一组数量更少的“语义超部件” `{h_j}` 上。这些超部件作为高层结构先验，捕获了物体的全局语义信息。
    *   **双范围特征传播**：
        1.  **短范围传播**：每个零件特征与它最近的超部件特征融合，注入局部结构上下文。
        2.  **长范围传播**：通过注意力机制，让每个零件从所有超部件中聚合全局语义信息，并在几何相似的零件子图内进行消息传递，以增强空间一致性。
    *   **粗姿态预测**：将增强后的特征通过多头注意力模块和多层感知机，预测出每个零件的初始位姿。

*   **第二阶段：基于跨阶段交互的姿态细化**
    *   **跨阶段注意力**：以细化阶段的零件特征为查询，粗粒度阶段的特征为键和值，进行注意力交互，从而将粗阶段的语义引导信息传递到细化阶段。
    *   **实例级几何编码**：引入可学习的实例编码，进一步显式建模零件间的几何相似性和关系。
    *   **细姿态预测**：融合上述所有特征，再次通过注意力模块和多层感知机，回归出最终的、更精确的零件位姿。

*   **对称性感知的损失函数**
    *   为了解决对称性带来的多解问题，论文设计了一种对称性感知损失，它在训练时不再强制模型输出唯一的规范姿态，而是：
        1.  **自对称性**：针对零件自身的镜像对称性，计算预测姿态与所有（共8种）轴翻转后的真值姿态中的最小误差。
        2.  **零件间几何相似性**：针对可互换的相似零件，计算预测姿态与该零件所在相似组内所有零件的翻转真值姿态的最小误差。
    *   总损失函数由**零件损失**、**形状损失**和**对称性感知损失**加权求和构成。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法
*   **数据集**：实验在**PartNet**数据集上进行，聚焦于三个最大的物体类别：**椅子(Chair)**、**桌子(Table)** 和**台灯(Lamp)**。数据集按照官方设定划分训练/验证/测试集（70%/10%/20%）。
*   **评估指标**：
    *   **装配精度**：形状倒角距离、零件准确率、连接性准确率。
    *   **多样性**：质量-多样性分数、加权质量-多样性分数。
*   **对比方法**：与广泛的现有主流方法进行了比较，包括：
    *   **序列化方法**：B-LSTM。
    *   **图网络方法**：DGL, RGL。
    *   **Transformer方法**：IET, SPAFormer。
    *   **层次化方法**：3DHPA。
    *   **生成式方法**：Score-PA, B-Global。

### 4. 资源与算力
*   **硬件与训练时长**：实验使用了**4块NVIDIA RTX 4090 GPU**，采用批量大小为64的设置下，训练了**500个周期**。
*   **优化器**：采用**AdamW**优化器，配合余弦退火学习率衰减策略。

### 5. 实验数量与充分性
论文进行了丰富且充分的实验，以验证方法的有效性和各模块贡献。具体包括：
*   **基准对比实验**：在3个类别、5项指标上与8种主流方法进行了全面对比，并提供了不同阈值下的性能曲线。这构成了**超过100组**的主要结果对比。
*   **消融研究**：
    *   验证了语义超部件（包括不同构建方式）的有效性。
    *   验证了双范围特征传播和跨阶段注意力等核心模块的必要性。
    *   验证了对称性感知损失中各组成部分（自对称性 vs. 零件间相似性）的作用。
*   **超参数分析**：探讨了超部件数量和损失函数中关键超参数对性能的影响。
*   **泛化性测试**：将提出的对称性感知损失应用到多种不同的基线方法上，证明了其即插即用的有效性和通用性。
*   **可视化分析**：提供了丰富的装配过程可视化和最终结果对比，从定性和定量（计算开销）两个角度提供了充分证据。实验设计客观、公平，对比全面。

### 6. 论文的主要结论与发现
*   **性能领先**：CFPA框架在PartNet基准测试的椅子、桌子和台灯类别上，在装配精度、结构一致性和多样性指标上，全面达到了新的**最优水平**。
*   **有效性验证**：语义超部件作为一种学习到的中层结构抽象，能够有效指导粗粒度的位姿预测；对称性感知损失能很好地处理零件对称性带来的多解问题，生成多样且有效的装配体。
*   **模块通用性**：所提出的对称性感知损失可以作为一个通用组件，提升其他基线方法的性能。

### 7. 优点：方法或实验设计上有哪些亮点
*   **创新的两阶段框架**：“由粗到细”的设计解耦了全局语义学习和局部几何细化，思路清晰有效。
*   **巧妙的语义抽象方法**：首次利用**最优传输**从数据中动态学习语义超部件，避免了预定义或硬性划分零件层级的局限性，为零件分组提供了更灵活、语义更丰富的方案。
*   **对称性问题的系统化解决**：提出的对称性感知损失联合建模了**零件内对称和零件间相似**这两种对称性，是该领域内处理对称性歧义问题的更为完善和系统的方案。
*   **实验扎实充分**：不仅包含全面的性能对比，还通过详尽的消融实验、超参数分析和泛化性测试，深刻揭示了各模块的内在价值，结论具有高可信度。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等
*   **应用场景受限**：方法目前仅适用于**语义级零件装配**，无法直接应用于由不规则、不完整碎片组成的“碎片重组”任务，应用范围存在一定的局限性。
*   **依赖PCA预处理**：输入零件需要经过PCA中心化和归一化等预处理，该过程对噪声和严重遮挡的鲁棒性文中未作深入探讨。
*   **对称性设定简化**：损失函数中对自对称性的建模仅考虑了沿主轴的`Z_3^2`翻转，可能无法完全覆盖所有复杂的对称性（如旋转对称等），是一种近似处理。

（完）
