---
title: "REArtGS: Reconstructing and Generating Articulated Objects via 3D Gaussian Splatting with Geometric and Motion Constraints"
title_zh: REArtGS：通过几何与运动约束的3D高斯泼溅重建与生成铰接物体
authors: "Di Wu, Liu Liu, Zhou Linli, Anran Huang, Liangtu Song, Qiaojun Yu, Qi Wu, Cewu Lu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=6LGyChG6Ep"
tags: ["query:part-aware"]
score: 9.0
evidence: 利用3D高斯的几何与运动约束生成铰接物体
tldr: REArtGS提出一种新框架，将几何和运动约束引入3D高斯泼溅，从两状态多视角RGB图像重建并生成铰接物体。通过无偏SDF引导高斯不透明度场，保证高保真表面重建；同时利用运动约束实现动态生成，解决了现有方法在铰接物体高质量重建与生成上的不足，为机器人、AR/VR等应用提供关键技术支持。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-6lgychg6ep/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 724, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6lgychg6ep/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1308, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6lgychg6ep/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 724, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6lgychg6ep/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1266, \"height\": 803, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6lgychg6ep/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1304, \"height\": 869, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6lgychg6ep/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1308, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6lgychg6ep/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 727, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6lgychg6ep/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1015, \"height\": 1053, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6lgychg6ep/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1131, \"height\": 274, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-6lgychg6ep/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1453, \"height\": 821, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-6lgychg6ep/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1386, \"height\": 695, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6lgychg6ep/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1380, \"height\": 587, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6lgychg6ep/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 662, \"height\": 135, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6lgychg6ep/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 666, \"height\": 118, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6lgychg6ep/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 805, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6lgychg6ep/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6lgychg6ep/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6lgychg6ep/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 442, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-6lgychg6ep/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 740, \"height\": 244, \"label\": \"Table\"}]"
motivation: 现有方法难以同时实现铰接物体的高保真表面重建与动态生成。
method: 提出REArtGS，将几何与运动约束融入3D高斯泼溅，从多视图图像重建铰接物体。
result: 实现了铰接物体的逼真表面重建与动态生成，优于现有方法。
conclusion: REArtGS为铰接物体的3D表示与生成提供了有效解决方案，推动相关应用。
---

## Abstract
Articulated objects, as prevalent entities in human life, their 3D representations play crucial roles across various applications. However, achieving both high-fidelity textured surface reconstruction and dynamic generation for articulated objects remains challenging for existing methods. In this paper, we present REArtGS, a novel framework that introduces additional geometric and motion constraints to 3D Gaussian primitives, enabling realistic surface reconstruction and generation for articulated objects. Specifically, given multi-view RGB images of arbitrary two states of articulated objects,  we first introduce an unbiased Signed Distance Field (SDF) guidance to regularize Gaussian opacity fields, enhancing geometry constraints and improving surface reconstruction quality. Then we establish deformable fields for 3D Gaussians constrained by the kinematic structures of articulated objects, achieving unsupervised generation of surface meshes in unseen states. Extensive experiments on both synthetic and real datasets demonstrate our approach achieves high-quality textured surface reconstruction for given states, and enables high-fidelity surface generation for unseen states. Project site: https://sites.google.com/view/reartgs/home.

---

## 论文详细总结（自动生成）

# REArtGS 论文详细总结

## 1. 论文的核心问题与整体含义
- **研究动机**：铰接物体（如剪刀、冰箱、折叠椅等）在日常生活中广泛存在，其高质量三维表示对虚拟现实、机器人操作、人机交互等应用至关重要。然而，现有方法难以同时实现**高保真纹理表面重建**和**动态生成**（即生成未观察状态下的形状）。
- **核心问题**：
    - 基于3D高斯泼溅（3DGS）的表面重建方法缺乏足够的几何约束，导致表面提取噪声大。
    - 现有的动态重建方法需要完整运动过程的连续监督，无法仅从两个离散状态生成未见状态下的网格。
- **整体含义**：论文提出 **REArtGS** 框架，**仅利用铰接物体两个任意状态的多视角RGB图像**，通过引入**几何约束**（无偏SDF引导）和**运动约束**（基于运动学的可变形场），实现高质量的纹理表面重建与时间连续的动态生成，填补了现有方法的空白。

## 2. 论文提出的方法论
### 核心思想
- **两阶段框架**：先进行高质量静态表面重建，再基于运动学约束生成动态网格。
- **阶段一：带无偏SDF引导的重建**
    - 使用GOF中的射线追踪方式计算3D高斯的渲染贡献，建立不透明度场。
    - 引入**符号距离函数（SDF）网络**（MLP，8层），将空间点的SDF值通过一种钟形激活函数 \( \Phi_k \) 转换为**局部不透明度** \( \hat{\sigma} \)，并与高斯自身的渲染贡献 \( \varepsilon \) 相乘得到最终的高斯不透明度。
    - 提出**无偏SDF正则化** \( \mathcal{L}_{\text{unbias}} = \|f(o + t^* r)\|^2 \)：迫使SDF值在高斯渲染贡献最大的深度 \( t^* \) 处趋近于零，消除不透明度峰值的空间偏差，使高斯不透明度场严格对齐物体表面。
    - 额外引入**法线正则化**（使高斯的法线与SDF梯度平行）和**Eikonal损失**，增强几何一致性。
    - 优化完成后，使用**TSDF融合**从正则化后的高斯场中提取带纹理的三角网格。
- **阶段二：带运动约束的网格生成**
    - 利用重建阶段优化的3D高斯作为初始几何。
    - **运动学结构建模**：
        - **启发式关节类型预测**：通过两状态稀疏点云的位移方向方差自动判断旋转关节或棱柱关节。
        - **可变形场参数化**：旋转关节学习轴心点 \( o_r \) 和归一化四元数 \( q \)，采用规范状态 \( s^*=0.5 \) 和角度有界参数化避免奇异性，利用罗德里格斯旋转公式得到变形位置。棱柱关节学习方向 \( d \) 和距离 \( m \)，取规范状态 \( s^*=0 \)，通过线性插值得到位置。
        - **动态部件分割**：通过预热训练后的点位移初步分割，并在训练中根据与学习到的运动参数的吻合度迭代更新分割掩码。
    - 可扩展至多部件物体，采用顺序学习策略逐个处理动态部件。

### 关键技术细节
- 损失函数：图像重建损失（D-SSIM + L1）、无偏正则化、法线正则化、Eikonal损失、深度失真损失。
- 训练过程：重建阶段约31000次迭代（含预热），生成阶段约30000次迭代（含预热）。

## 3. 实验设计
### 数据集与场景
- **合成数据集**：PartNet-Mobility，选取10个类别（订书机、USB、剪刀、冰箱等），每类提供64至100个上半球采样视角。
- **真实数据集**：AKB-48，选取6个类别（盒子、订书机、剪刀、美工刀、抽屉、眼镜），含双部件和多部件物体，每物体具备100个视角。

### Benchmark与评价指标
- **重建/生成质量指标**：Chamfer Distance（CD，分整体采样和射线可见区域采样）、F1-score（距离阈值0.4）、Earth Mover’s Distance（EMD，射线可见区域）。注意：生成实验以端状态作为生成目标进行评估。
- **部件分割与关节参数估计**：动态/静态部件的CD，关节轴角度误差，旋转关节轴心位置误差。

### 对比方法
- **表面重建**：A-SDF、Ditto、PARIS、GOF、ArtGS（为公平比较，去掉深度监督）。
- **动态生成**：A-SDF、PARIS、Deformable-3DGS (D-3DGS)、ArtGS。

## 4. 资源与算力
- **GPU**：所有实验在**单张NVIDIA RTX 4090 GPU**上完成。
- **训练时长**：
    - 重建阶段：约**60分钟**。
    - 生成阶段：约**10分钟**。
    - 从零开始到生成总时长约**70分钟**。
- **推理速度**：单个网格生成约**21秒**，显著优于对比方法（PARIS: 33秒，D-3DGS: 40秒）。

## 5. 实验数量与充分性
- **实验规模**：在两个数据集上跨多个类别进行定量对比；包含4个主表、多个消融实验表和大量定性结果图。
- **消融实验**：
    - 无偏SDF引导的效果（添加SDF vs. 无SDF vs. SDF+无偏正则）。
    - 运动约束的贡献（有/无可变形场）。
    - 规范状态选择的敏感性分析。
- **附加分析**：部件分割定量评估、关节参数估计定量评估、计算效率对比。
- **公平性**：对ArtGS去掉深度监督以保持输入一致；所有方法使用统一输入和评估协议。实验总体设计充分、客观、公平，系统地验证了各组件贡献和整体优势。

## 6. 论文的主要结论与发现
- REArtGS只依靠两状态多视角RGB，就能同时实现**高保真表面重建**和**无监督的未见状态网格生成**。
- 提出的**无偏SDF正则化**有效解决了高斯不透明度场与真实表面的对齐问题，显著提升了重建表面质量。
- **运动学约束的可变形场**无需连续运动先验，即可生成时间连续、物理合理的运动序列。
- 方法在合成与真实场景中均大幅超越现有最先进方法，并具备较强的泛化能力和计算效率。

## 7. 优点
- **创新性强**：首次将无偏SDF引导与运动学约束结合到3DGS框架，同时解决铰接物体重建与生成。
- **几何质量提升显著**：通过理论推导和消融验证，无偏正则化从根本上改善了不透明度场的分布，获得的表面更清晰、噪声更少。
- **运动生成无需连续监督**：仅靠两个状态即可恢复运动参数并生成任意中间状态，降低数据采集要求。
- **高实用性与高效性**：支持真实世界物体，训练和推理速度快，便于应用。
- **可扩展性**：方法可自然扩展至多部件铰接物体。

## 8. 不足与局限
- **依赖相机位姿先验**：需要预先标定的相机位姿，对于非受控场景不友好。
- **材质局限**：对透明、高反光材质难以处理，这是当前隐式/显式神经表示的普遍弱点。
- **关节类型预测的鲁棒性**：启发式阈值方法可能对复杂运动或噪声点云敏感，论文未探讨极端条件下的表现。
- **顺序多部件学习**：多部件依次学习可能累积误差，且部件间交互未被显式建模。
- **生成评估局限**：仅以端状态作为定量评估目标，缺少对任意中间状态的质量评测报告（尽管定性结果展示了中间状态）。

（完）
