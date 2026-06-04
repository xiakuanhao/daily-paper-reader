---
title: "Articulate your NeRF: Unsupervised articulated object modeling via conditional view synthesis"
title_zh: 铰接你的NeRF：通过条件视角合成无监督铰接物体建模
authors: "Jianning Deng, Kartic Subr, Hakan Bilen"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=9B6J64eTp4"
tags: ["query:part-aware"]
score: 10.0
evidence: 无监督学习铰接物体的姿态与部件分割
tldr: 现有无监督方法难以同时学习铰接物体的部件分割与关节运动。本文提出新颖的无监督方法，基于两次不同关节状态的观察，利用条件视图合成隐式建模物体部件的几何与外观，并提炼部件分割与关节信息。通过体素网格初始化和解耦优化策略，解决了联合优化的复杂性。实验表明，该方法在性能上显著优于先前工作，并具有良好的泛化能力，为零件感知生成提供了坚实技术基础。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1443, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 690, \"height\": 348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1343, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 724, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1447, \"height\": 962, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1419, \"height\": 206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1235, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1083, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1159, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1302, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1447, \"height\": 1497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1411, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1428, \"height\": 1427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 974, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-9b6j64etp4/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1323, \"height\": 792, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-9b6j64etp4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1413, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-9b6j64etp4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 844, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-9b6j64etp4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 541, \"height\": 374, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-9b6j64etp4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 775, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-9b6j64etp4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 385, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-9b6j64etp4/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 957, \"height\": 793, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-9b6j64etp4/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1439, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-9b6j64etp4/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1139, \"height\": 172, \"label\": \"Table\"}]"
motivation: 无监督学习铰接物体的部件分割与关节运动具有挑战，现有方法性能有限。
method: 从两次观察中，利用条件视图合成和隐式模型，无监督学习部件分割与关节。
result: 性能显著优于先前无监督工作，且泛化能力更强。
conclusion: 提出有效无监督方法，推动了铰接物体建模与零件感知进展。
---

## Abstract
We propose a novel unsupervised method to learn pose and part-segmentation of articulated objects with rigid parts.
    Given two observations of an object in different articulation states, our method learns the geometry and appearance of object parts by using an implicit model from the first observation, distills the part segmentation and articulation from the second observation while rendering the latter observation.
    Additionally, to tackle the complexities in the joint optimization of part segmentation and articulation, we propose a voxel grid based initialization strategy and a decoupled optimization procedure.
    Compared to the prior unsupervised work, our model obtains significantly better performance, generalizes to objects with multiple parts while it can be efficiently from few views for the latter observation.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的结构化、深入、客观总结。

### 1. 论文的核心问题与整体含义

*   **研究问题**：从两帧不同关节状态的多视角图像中，无监督地学习关节物体的**部件分割**与**关节运动参数**（如旋转/平移轴方向、角度、距离），同时实现新关节状态下的视图合成。
*   **研究动机**：关节物体在日常生活中广泛存在，自动理解其结构（部件）和运动（关节）对机器人操控、动画等至关重要。现有方法多依赖昂贵的3D真值或人工标注，而无监督方法性能有限、不稳定，且通常只能处理单运动部件。
*   **整体含义**：提出一种基于“分析-合成”范式的条件视图合成方法，将关节建模任务分解为先学习静态几何外观，再从目标观察中提纯部件与运动，显著提高了准确性、稳定性，并扩展至多运动部件及少视图场景。

### 2. 论文提出的方法论

*   **核心思想**：关节运动仅改变部件姿态，不改变几何纹理。因此，可先在源观察上训练一个“静态NeRF”来捕获物体几何与外观；然后冻结其参数，利用目标观察，通过渲染差异监督一个**部件分割头**和**关节变换**。
*   **技术流程**：
    1.  **阶段一：静态建模**  
        利用源观察（视图集 I）训练标准NeRF，获得静态几何、外观和密度场。
    2.  **阶段二：部件感知渲染与关节学习**  
        *   在冻结的静态NeRF上追加一个部件分割头（2层MLP），输出每个点属于各部件的概率 \( s_\ell(\mathbf{z}(\mathbf{x})) \)。
        *   为每个部件学习一个SE(3)变换矩阵 \( M_\ell \)，将射线反向变形为 \( \mathbf{r}_\ell = M_\ell^{-1} \mathbf{r} \)。
        *   部件感知渲染：颜色 \( C^P(\mathbf{r}) = \sum_i \hat{T}_i \sum_\ell (1 - \exp(-s_\ell \sigma_\ell \delta)) \mathbf{c}_\ell \)，其中密度被部件概率加权。
        *   使用目标观察的光度损失作为监督。
*   **关键创新：解耦优化策略**  
    由于分割与变换联合优化困难且对初始化敏感，提出：
    1.  **体素网格初始化**：通过静态NeRF渲染目标视图，找出像素差异（前景掩码不一致）并反投影到3D空间，聚类得到初始运动部件体素 \( X_\ell \)。
    2.  **三步交替优化**：
        *   Step 1：基于当前体素 \( X_\ell \)，通过最小化投射点与目标掩码的2D Chamfer距离优化 \( M_\ell \)。
        *   Step 2：固定 \( M_\ell \)，通过部件感知渲染的光度损失优化分割头 \( s \)。
        *   Step 3：使用更新后的 \( s \) 重新提取并精炼体素网格 \( X_\ell^* \)（分辨率从128提升至256），仅当邻域预测一致时接受。
    3.  以上循环多次，有效稳定训练。

### 3. 实验设计

*   **数据集与基准**：
    *   **合成数据**：PartNet-Mobility数据集。使用与PARIS相同的6个物体（笔记本电脑、烤箱、订书机、冰箱、刀片、储物柜）的单运动部件实验，另选4个多运动部件物体（盒子、眼镜、烤炉、储物柜）进行评估。每个物体提供两个状态的100个视图及前景掩码。
    *   **真实数据**：手持设备拍摄的玩具汽车，用KIRI Engine估计相机位姿。
*   **对比方法**：与当前最先进的无监督方法 **PARIS** （ICCV 2023）全面比较。同时与PARIS已报告结果、复现结果对比。由于PARIS原论文未提供多次运行结果，作者使用其公开代码和默认超参进行了5次随机种子实验。
*   **评估指标**：
    *   *姿态估计*：关节轴方向误差 \( e_d \)、轴位置误差 \( e_p \)、旋转角误差 \( e_g \)、平移距离误差 \( e_t \)。
    *   *部件分割*：mIoU。
    *   *新视图/关节合成*：PSNR。
*   **消融实验**：在“fridge”对象上评估解耦姿态估计（DP）和迭代细化（IR）的作用，还测试了目标视图数量（2,4,8,16,32,100）的影响。

### 4. 资源与算力

*   **硬件**：单块NVIDIA RTX 4090 GPU，约需16 GB显存。
*   **训练时间**：
    *   静态NeRF训练约**10分钟**。
    *   部件分割与关节学习阶段，单个物体约**30分钟**（包含5-6次循环）。
*   **估计总计算量**：整个项目预估GPU时间总计约**2 GPU月**。文中对算力消耗描述清晰。

### 5. 实验数量与充分性

*   **实验组数丰富**：覆盖6个单运动部件物体、4个多运动部件物体的定量对比；对每个物体进行了5次随机初始化运行，报告均值和标准差；展示定性结果如分割图、新关节视图等。
*   **消融与分析**：
    *   验证了解耦优化（DP）和体素网格迭代细化（IR）的关键有效性。
    *   系统研究了目标视图数量对性能的影响，表明仅需8张图即可超越PARIS用100张图的结果。
    *   额外展示了真实世界例子、对称物体失败案例（折叠椅）、细薄部分伪影等分析。
    *   对比了静态NeRF到新关节合成渲染的PSNR损失。
*   **公平性**：使用标准数据集、公开代码复现对比方法，承认PARIS复现结果与报告差异，并分析了原因；多对象多指标评估，实验设计客观、充分。

### 6. 论文的主要结论与发现

*   提出了首个可无监督建模多运动部件关节物体的方法，仅需两帧多视图图像。
*   通过“静态NeRF预训练 + 部件感知解耦优化”策略，**稳定性**显著优于以PARIS为代表的端到端联合优化方法。
*   在合成数据集上，部件姿态估计、分割质量和合成PSNR**全面超越**已有无监督方法PARIS，且标准差更低。
*   方法得益于阶段式训练，**数据效率极高**：仅需8张目标视图即可获得优于PARIS（100视图）的性能。
*   在真实场景（玩具车）上也展示了良好的鲁棒性和泛化能力。

### 7. 优点

*   **方法新颖且实用**：将复杂的关节建模分解为“静态重建→运动提炼”，降低了学习难度，稳定了训练。
*   **高效性**：模型大小不随部件数量增长，从少视图目标观察中即可快速学习，计算开销低（30分钟）。
*   **强大的基准结果**：在多项指标上大幅领先，尤其在不稳定物体（订书机、刀片）上解决了对比方法的崩溃问题。
*   **扩展性**：成功推广到多运动部件物体，而此前的无监督工作只能处理单运动部件。
*   **充分的实验验证**：多对象、多指标、多条件测试，包括真实场景和详尽的消融/分析，结论可信。

### 8. 不足与局限

*   **依赖几何差异初始化**：当运动幅度极小，像素差异不足以识别移动部件时，初始化可能失败。
*   **对称零部件问题**：仅利用几何信息可能导致错误翻转（如折叠椅座位），未能利用外观线索进行区分。
*   **细薄部件**：在非常细或薄的部件（如眼镜腿)上，渲染质量可能下降或出现伪影，提案网络处理能力不足。
*   **静态NeRF的继承缺陷**：受限于隐式模型的固有问题，如无法处理透明物体、对相机位姿噪声敏感。
*   **仅限于刚体部件**：无法建模软组织变形。
*   **多部件稳定性**：相对于两部件对象，在多部件对象上稳定性略低。

（完）
