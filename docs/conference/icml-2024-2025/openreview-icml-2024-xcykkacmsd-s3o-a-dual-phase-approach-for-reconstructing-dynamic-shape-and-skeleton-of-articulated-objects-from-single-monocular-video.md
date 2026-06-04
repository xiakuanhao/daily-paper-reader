---
title: "S3O: A Dual-Phase Approach for Reconstructing Dynamic Shape and Skeleton of Articulated Objects from Single Monocular Video"
title_zh: S3O：从单目视频重建铰接物体动态形状与骨架的双阶段方法
authors: "Hao Zhang, Fang Li, Samyak Rawlekar, Narendra Ahuja"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=xcyKKACmSd"
tags: ["query:part-aware"]
score: 9.0
evidence: 从单目视频重建动态铰接物体的形状与骨架
tldr: 针对单目视频中动态铰接物体重建需大量计算和人工标注的局限，S3O提出两阶段协同优化方法。第一阶段粗略估计相机位姿和初始形状，第二阶段联合细化形状与骨架，避免参数耦合。无需预定义模型或关键点，直接从视频学习。实验证明该方法高效且泛化性强，为无先验条件下铰接物体的快速重建提供了实用框架。其无需人工标注的特点使其在非结构化环境中具有广泛应用前景，且两阶段设计显著降低了计算开销，适合实时应用。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1591, \"height\": 273, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1601, \"height\": 250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1585, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1779, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 723, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 702, \"height\": 178, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1760, \"height\": 792, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1747, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1769, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1758, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 895, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1764, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1760, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1770, \"height\": 326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-xcykkacmsd/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 890, \"height\": 622, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-xcykkacmsd/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 384, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xcykkacmsd/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1692, \"height\": 211, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-xcykkacmsd/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1178, \"height\": 1356, \"label\": \"Table\"}]"
motivation: 现有方法依赖大量计算和人工标注，泛化性受限。
method: 提出S3O两阶段优化，分步学习相机、形状和骨架参数，避免同时优化干扰。
result: 实验显示高效重建，无需预定义模型，泛化能力强。
conclusion: 为无先验的铰接物体重建提供了简洁有效的方案。
---

## Abstract
Reconstructing dynamic articulated objects from a singular monocular video is challenging, requiring joint estimation of shape, motion, and camera parameters from limited views. Current methods typically demand extensive computational resources and training time, and require additional human annotations such as predefined parametric models, camera poses, and key points, limiting their generalizability. We propose Synergistic Shape and Skeleton Optimization (S3O), a novel two-phase method that forgoes these prerequisites and efficiently learns parametric models including visible shapes and underlying skeletons. Conventional strategies typically learn all parameters simultaneously, leading to interdependencies where a single incorrect prediction can result in significant errors. In contrast, S3O adopts a phased approach: it first focuses on learning coarse parametric models, then progresses to motion learning and detail addition. This method substantially lowers computational complexity and enhances robustness in reconstruction from limited viewpoints, all without requiring additional annotations. To address the current inadequacies in 3D reconstruction from monocular video benchmarks, we collected the PlanetZoo dataset. Our experimental evaluations on standard benchmarks and the PlanetZoo dataset affirm that S3O provides more accurate 3D reconstruction, and plausible skeletons, and reduces the training time by approximately 60% compared to the state-of-the-art, thus advancing the state of the art in dynamic object reconstruction.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

*   **任务定义**：从**单个单目视频**中重建动态铰接物体的**可见 3D 形状**和**不可见底层物理骨架**。这需要从有限视角中同时估计形状、运动及相机参数。
*   **核心挑战**：
    *   **参数耦合严重**：若同时学习所有参数（形状、运动、相机、骨架），任何一个参数的微小误差都可能导致全局重建失败。
    *   **高度依赖先验**：现有许多方法需要预定义参数模型（如 SMAL）、手动标注关键点或精确的相机位姿，这严重限制了在开放环境中的泛化能力。
    *   **计算资源消耗大**：当前最优方法（SOTA）通常需要在 A100 GPU 上训练 8 到 30 小时，实用性较差。
*   **整体含义**：论文提出了一种计算高效且泛化能力强的方案，旨在不依赖任何人工标注或 3D 模板的情况下，直接从单目视频中重建出物理上合理的形状与骨架。

### 2. 论文提出的方法论

S3O 的核心是一种**双阶段协同优化**策略，将高度耦合的参数分离，分阶段进行学习，类似于期望最大化（EM）过程。

*   **第一阶段：粗略参数模型学习**
    *   **标准帧选取与 2D 骨架提取**：自动选取姿态最舒展（水平/垂直距离比最大）的一帧作为标准帧。使用中轴变换提取其 2D 骨架，并将其简化为端点和连接点。
    *   **粗略 3D 模型生成**：利用物体的对称性假设，将 2D 骨架提升为粗略的 3D 骨架，并生成一个对应的粗略 3D 网格形状作为后续阶段的初始化。
*   **第二阶段：运动与精细形状学习**
    *   **参数解耦**：固定骨架，仅更新形状、运动和相机参数；然后固定这些参数，根据物理约束优化骨架。
    *   **骨架适应与生长**：在网格变形后，通过移动骨骼中心点（骨移）和自动延伸末端骨骼（骨生长）来适应新的网格结构。
    *   **物理约束优化**：
        1.  **骨骼合并**：根据骨骼在视频中的运动相似度，合并运动一致的骨骼。
        2.  **关节连接**：根据骨骼间距离的显著变化来建立关节连接。
        3.  **骨运动估计**：通过将 2D 光流反投影加权到骨上，估算骨骼的 2D 运动轨迹。
    *   **动态刚性损失**：与传统的 ARAP 约束不同，S3O 引入动态刚性损失，它允许关节附近的顶点拥有更多形变自由度，而骨骼上的顶点则保持更刚性，使形变更符合物理规律。

### 3. 实验设计

*   **数据集与评测基准**：
    *   **DAVIS**：包含清晰分割掩膜的常规视频数据集，评测其上的骆驼、牛、狗等动物。
    *   **PlanetZoo（论文新提出）**：一个专门收集的数据集，特点在于包含**大幅度、长距离的相机运动**，用于更严格地评估算法在相机参数需要动态估计时的鲁棒性。评估了长颈鹿、老虎、大象等动物。
    *   **AMA-Human**：包含多视角视频并提供 3D 真值网格的人体数据集，用于进行 3D 定量评估。
*   **对比方法**：
    *   **形状重建**：与模板无关的方法（LASR, ViSER），基于 NeRF 的方法（BANMo, MagicPony）以及最新的 Hi-LASSIE 进行定性、定量对比。
    *   **骨架重建**：与有监督方法 RigNet 和无监督方法 Skeletor 进行定性对比。
*   **评估指标**：
    *   2D 关键点转移准确率、3D Chamfer 距离、F-score 和 mIoU。

### 4. 资源与算力

*   **硬件配置**：实验主要在 **1 块 40GB 显存的 Nvidia A100 GPU** 上完成。
*   **训练效率**：S3O 仅需约 **4 到 6 个 GPU 小时**，相比 ViSER、LASR 等方法（约 10 到 24 小时）**减少了约 60% 的训练时间**。

### 5. 实验数量与充分性

*   **实验数量**：论文进行了多组实验，包括在 2 个动物视频数据集上的多物体定量评估、在人体数据集上的 3D 定量评估，以及骨架生成的可视化对比。此外，还进行了消融实验来验证“动态刚性损失”的有效性和不同骨骼粒度阈值的影响。
*   **充分性与公平性**：实验设计较为充分。通过在多个数据集上进行多次实验，并汇报平均值与标准差，证明了方法的稳定性。与 LASR、ViSER 等方法的对比是公平的，因为它们所需的输入条件完全一致。同时，论文也指出了 S3O 运行在降配条件下与 BANMo 的对比，并解释了原因，体现了公平性。

### 6. 论文的主要结论与发现

*   S3O 在**形状重建精度**和**骨架物理合理性**上均优于当前最优方法。
*   S3O 学习到的**物理骨架比传统虚拟骨头在物体形变操控上更有效**，因为其骨骼分布符合运动逻辑（运动多的部位骨骼多），避免了虚拟骨头方法在躯干分配过多骨骼，在四肢分配过少的问题。
*   两阶段方法能显著**减少训练时间约 60%**，同时提高训练的稳定性。

### 7. 优点

*   **无需人工标注和 3D 模板**：直接从视频中学习一切，通用性强。
*   **方法简洁高效**：两阶段分离式优化策略有效降低了计算复杂度，提升了训练速度和稳定性。
*   **物理合理性**：所学骨架更符合物体的内在运动结构，通过动态刚性损失使得形变更自然。
*   **新数据集**：提出的 PlanetZoo 数据集弥补了现有基准中缺乏大幅相机运动的不足，有助于评估算法的鲁棒性。

### 8. 不足与局限

*   **计算成本依然偏高**：尽管训练时间大幅缩短，但数小时的训练时间仍不适合实时或日常场景的应用。
*   **依赖场景分割和质量**：方法依赖于高精度的物体掩膜和光流估计，当自动分割模型（如 SAM）效果不佳时，方法性能可能会退化。
*   **缺乏真实世界复杂场景验证**：实验主要基于 DAVIS、PlanetZoo 和 AMA 数据集，对于背景杂乱、严重遮挡或非朗伯表面的真实长视频，其鲁棒性尚待验证。

（完）
