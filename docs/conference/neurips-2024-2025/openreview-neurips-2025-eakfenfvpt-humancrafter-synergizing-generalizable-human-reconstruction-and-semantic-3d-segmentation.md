---
title: "HumanCrafter: Synergizing Generalizable Human Reconstruction and Semantic 3D Segmentation"
title_zh: HumanCrafter：协同泛化人体重建与语义三维分割
authors: "Panwang Pan, Tingting Shen, Chenxin Li, Yunlong Lin, Kairun Wen, Jingjing Zhao, Yixuan Yuan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=EakfENFVPT"
tags: ["query:part-aware"]
score: 9.0
evidence: 从单张图像联合建模外观与人体部位语义
tldr: 现有三维人体重建方法虽能实现高保真，但难以同时获得部件语义。HumanCrafter提出统一框架，从单张图像前馈式联合建模外观与人体部位语义，集成几何先验与自监督语义先验，解决了标注数据稀缺问题。实验表明，该方法在重建与分割任务上均取得优异效果，为人体部件感知三维生成提供了新途径。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1393, \"height\": 812, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1277, \"height\": 754, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1286, \"height\": 918, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1199, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1195, \"height\": 697, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1220, \"height\": 889, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-eakfenfvpt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1417, \"height\": 582, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-eakfenfvpt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1371, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eakfenfvpt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1421, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eakfenfvpt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 711, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eakfenfvpt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 710, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eakfenfvpt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 835, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-eakfenfvpt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 958, \"height\": 163, \"label\": \"Table\"}]"
motivation: 现有三维人体重建缺乏部件语义，限制了特定任务应用。
method: 提出统一框架，集成几何与语义先验，从单图像联合重建和分割人体部位。
result: 在人体重建和语义分割上取得高精度，实现部件感知建模。
conclusion: 为人体部件感知三维生成提供了有效方案，可扩展至其他对象。
---

## Abstract
Recent advances in generative models have achieved high-fidelity in 3D human reconstruction, yet their utility for specific tasks (e.g., human 3D segmentation) remains constrained. We propose HumanCrafter, a unified framework that enables the joint modeling of appearance and human-part semantics from a single image in a feed-forward manner. Specifically, we integrate human geometric priors in the reconstruction stage and self-supervised semantic priors in the segmentation stage. To address labeled 3D human datasets scarcity, we further develop an interactive annotation procedure for generating high-quality data-label pairs. Our pixel-aligned aggregation enables cross-task synergy, while the multi-task objective simultaneously optimizes texture modeling fidelity and semantic consistency. Extensive experiments demonstrate that HumanCrafter surpasses existing state-of-the-art methods in both 3D human-part segmentation and 3D human reconstruction **from a single image**.

---

## 论文详细总结（自动生成）

# HumanCrafter 论文详细中文总结

## 1. 论文的核心问题与整体含义
- **核心问题**：当前高保真三维人体重建方法（如基于 NeRF、3DGS 的模型）虽然生成质量高，但大多仅关注外观建模，缺乏对**人体部件语义（如四肢、衣物类别）的三维理解**，难以直接支撑语义编辑、行为理解等下游任务。
- **整体含义**：提出 **HumanCrafter**，一个统一的前馈式框架，**从单张 RGB 图像出发，同时完成三维人体重建和人体部件三维语义分割**，实现“生成”与“理解”的协同增效，为部件感知的三维人体内容创建提供新范式。

## 2. 论文提出的方法论
- **核心思想**：将外观重建与语义分割整合进一个共享的三维高斯泼溅（3DGS）表征中，并扩展高斯点云携带语义特征，形成**可同时渲染彩色图和特征图的“VersatileSplats”**。通过引入人体几何先验和自监督语义先验，实现跨任务增益。
- **关键技术细节与流程**：
  - **多视角特征聚合**：
    - 利用预训练 2D 扩散模型 **SV3D** 从输入图像生成多视角潜在特征，提供外观先验。
    - 引入人体参数化模型 **SMPL** 渲染侧面法线图作为几何引导，与输入图像和相机 **Plücker 嵌入** 拼接后送入 **Transformer**（分组查询注意力）进行跨视角特征交互。
    - 预测深度图与偏移量，将像素特征反投影为**像素对齐的三维高斯点**初始几何。
  - **自监督语义先验与像素对齐聚合**：
    - 冻结预训练的 **DINOv2** 编码器提取 2D 语义特征。
    - 从上一个 Transformer 提取注意力权重，对 DINOv2 特征进行**加权组合**，实现特征维度无关的跨任务**像素对齐聚合**。
    - 从聚合后的语义特征解码出每个像素对应高斯的属性（含语义嵌入）。
  - **渲染与训练目标**：
    - **渲染**：经典 3DGS 阿尔法混合，分别计算颜色和语义特征图。
    - **损失函数** (\mathcal{L}\_) = 多视角重建损失（MSE + 感知 LPIPS + 掩码损失）+ **特征蒸馏损失**（\mathcal{L}_{dist} 用余弦相似度对齐渲染特征与 DINOv2 真值特征）+ **语义分割交叉熵损失**（\mathcal{L}_{CE} 监督生成的分割图）。通过端到端联合训练，使外观重建与语义分割相互促进。
  - **数据标注**：由于缺乏带 3D 语义标签的人体数据，采用**交互式标注流程**（结合 SAM 分割大模型加速），为训练数据生成高质量人体部件语义标签（28 个身体部件类）。

## 3. 实验设计
- **数据集**：
  - **THuman2.1**（2449 例，2300 训练/剩余评估）
  - **2K2K**（2000 例，1500 训练/剩余评估）
  - **Human MVImageNet**（4000+ 身份，用于丰富的多视角渲染）
  - **自建语义分割数据集**：从训练集随机选 500 个扫描，每个扫描人工标注 8 个语义分割图。
  - **真实泛化测试集**：从互联网收集的包含多样姿态、身份和视角的野外图像。
- **Benchmark 与对比方法**：
  - **三维人体分割**：与 **LSM**（多视角输入）、**Sapiens**（2D 分割 SOTA）、**Human3Diffusion+Sapiens**（单图重建后分割）对比。指标：mIoU、mAcc。
  - **三维人体重建**：与 **LGM**、**GRM**、**InstantMesh**、**LaRa**、**PSHuman**、**Human3Diffusion** 等单图前馈式方法对比。指标：PSNR、SSIM、LPIPS、COLMAP 恢复点数（衡量多视角一致性）。
- **效率对比**：单图推理总时间约 **6.24 秒**（扩散多视角约 6 秒，重建约 0.2 秒），显著快于二阶段管线（如 Human3Diffusion+Sapiens 需 23 秒以上）。

## 4. 资源与算力
- **GPU**：8 块 NVIDIA A800 GPU。
- **训练时长**：总计训练约 7 天。
- **训练策略**：两阶段——前 80k 次迭代在 256×256 分辨率下训练，再在 512×512 分辨率下微调 20k 次迭代。使用 Flash-Attention-v2、梯度检查点、BFloat16 混合精度加速，并采用 AdamW 优化器及余弦学习率衰减。

## 5. 实验数量与充分性
- 论文设计了**多层面的实验验证**，包括：
  - **主实验**：在两个标准数据集（THuman2.1，2K2K）上分别对比**三维重建**与**三维分割**性能，涵盖定量指标、定性结果及运行时间。
  - **消融研究**：考察人体几何先验（SMPL 的有无、法线图等输入模态）、像素对齐聚合模块、模型组件（Plücker 嵌入、DINOv2 替换为 MAE、双 Transformer 结构）、各损失项（LPIPS、蒸馏损失、语义分割损失）的贡献，以及图像编码器冻结/微调的影响。合计至少 **7 组独立消融**。
  - **泛化性测试**：展示在野外图像、复杂姿态和宽松衣物上的重建效果，并演示 3D 一致性编辑与 VR 应用。
  - **实验充分性**：对比方法覆盖全面，消融针对性强，定量与定性结果相互印证，实验规模与对比基准设置公允。

## 6. 论文的主要结论与发现
- 首次实现**从单张图像前馈式联合生成高质量三维人体外观与人体部件语义分割**。
- 通过将几何先验、自监督视觉特征与可微分三维高斯表征深度融合，**重建质量与分割精度均达到或超越现有 SOTA**（如 PSNR 23.489 vs. Human3Diffusion 22.323，mIoU 0.840 vs. Sapiens 0.823）。
- **像素对齐聚合机制**有效实现了跨任务信息复用，使重建和分割任务协同提升。
- 所提框架具备**强泛化能力**，可处理野外图像并支持实时渲染与即时的三维编辑、VR 沉浸体验等下游应用。

## 7. 优点
- **统一的框架设计**：首次将单图人体重建与部件语义分割融为一体，避免了二阶段管线的 3D 不一致和高计算成本。
- **巧妙的先验融合**：仅用 2D 监督（SMPL 法线图、DINOv2 特征蒸馏）和极少量人工标注的 3D 分割图，就实现了高质量的三维语义场。
- **像素对齐的跨任务聚合**：利用重建任务的注意力权重来指引语义特征聚合，设计新颖且效果显著。
- **高效与实用**：单图推理仅需约 6.2 秒，渲染可实时进行，且显式高斯表征可直接接入 VR 设备。
- **实验扎实**：在多个数据集、多个指标上对比了大量 SOTA 方法，消融充分，并展示了丰富的应用案例。

## 8. 不足与局限
- **仅限于静态人体**：目前不支持动态 4D 场景生成，未来可向动态高斯表征扩展。
- **未见极限位姿与重度遮挡验证**：虽展示了复杂姿态和宽松衣物，但缺乏对极重度遮挡或非常罕见位姿的系统性评估。
- **标注视角稀疏**：语义分割标签仅标注了 8 个视角，在部分不可见区域可能产生分割谬误，三维一致性仍有提升空间。
- **伦理与安全风险**：框架可能被滥用于生成虚假数字资产，且存在隐私侵犯和种族偏见等隐忧，文中仅提出需嵌入水印等粗略对策。
- **计算依赖**：依赖一个 2D 扩散模型生成多视角特征，增加了推理耗时和显存开销，实时交互性仍有优化空间。

（完）
