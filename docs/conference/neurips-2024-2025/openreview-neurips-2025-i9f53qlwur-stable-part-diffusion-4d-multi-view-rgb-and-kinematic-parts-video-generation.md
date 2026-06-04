---
title: "Stable Part Diffusion 4D: Multi-View RGB and Kinematic Parts Video Generation"
title_zh: Stable Part Diffusion 4D：多视角RGB与运动部件视频生成
authors: "Hao Zhang, Chun-Han Yao, Simon Donné, Narendra Ahuja, Varun Jampani"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=I9F53Qlwur"
tags: ["query:part-aware"]
score: 9.0
evidence: 从单目输入生成与物体铰接对齐的运动部件视频
tldr: SP4D提出一种从单目输入生成配对RGB与运动部件视频的框架，采用双分支扩散模型联合合成RGB帧与部件分割图。通过空间颜色编码将部件掩膜映射为连续图像，使分割分支共享潜在空间，实现与物体铰接对齐且跨视角、时间一致的部件生成，为铰接物体的3D部件生成提供新范式。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-i9f53qlwur/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 493, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i9f53qlwur/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 222, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i9f53qlwur/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i9f53qlwur/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1352, \"height\": 1309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i9f53qlwur/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1440, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-i9f53qlwur/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 710, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-i9f53qlwur/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 918, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i9f53qlwur/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 522, \"height\": 205, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i9f53qlwur/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 878, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-i9f53qlwur/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 874, \"height\": 239, \"label\": \"Table\"}]"
motivation: 现有部件分割依赖外观语义，缺乏与物体铰接对齐的部件生成。
method: 提出SP4D，双分支扩散模型联合合成RGB与部件分割图，用空间颜色编码实现柔性部件计数。
result: 生成跨视角、时间一致的运动部件视频，优于基线方法。
conclusion: SP4D为从单目输入生成铰接部件提供了有效框架，推动部件感知生成。
---

## Abstract
We present Stable Part Diffusion 4D (SP4D), a framework for generating paired RGB and kinematic part videos from monocular inputs. Unlike conventional part segmentation methods that rely on appearance-based semantic cues, SP4D learns to produce kinematic parts --- structural components aligned with object articulation and consistent across views and time.

SP4D adopts a dual-branch diffusion model that jointly synthesizes RGB frames and corresponding part segmentation maps. To simplify architecture and flexibly enable different part counts, we introduce a spatial color encoding scheme that maps part masks to continuous RGB-like images. This encoding allows the segmentation branch to share the latents VAE from the RGB branch, while enabling part segmentation to be recovered via straightforward post-processing. A Bidirectional Diffusion Fusion (BiDiFuse) module enhances cross-branch consistency, supported by a contrastive part consistency loss to promote spatial and temporal alignment of part predictions.

We demonstrate that the generated 2D part maps can be lifted to 3D to derive skeletal structures and harmonic skinning weights with few manual adjustments. To train and evaluate SP4D, we construct KinematicParts20K, a curated dataset of over 20K rigged objects selected and processed from Objaverse XL, each paired with multi-view RGB and part video sequences. Experiments show that SP4D generalizes strongly to diverse scenarios, including real-world videos, novel generated objects, and rare articulated poses, producing kinematic-aware outputs suitable for downstream animation and motion-related tasks.

---

## 论文详细总结（自动生成）

# Stable Part Diffusion 4D (SP4D) 论文深度分析报告

## 1. 核心问题与研究背景
- **核心挑战**：从单目输入（单张图片或视频）自动生成具有铰接结构感知且视角、时间一致的部件分解结果，是计算机视觉与图形学的核心难题。
- **现有局限**：
    - 主流视频生成或4D生成方法仅关注表面几何、RGB合成，缺少内在的结构化部件信息。
    - 传统2D/3D部件分割依赖语义标签与外观线索，预测出的部件不等于物理上可运动的“运动部件”（kinematic parts），且视点与时间上不稳定。
    - 自动绑骨/蒙皮方法受限于训练数据规模，泛化能力有限。
- **本工作意义**：提出 SP4D，首次从单目输入同时合成多视图RGB视频和运动部件分割视频，使输出可直接用于动画、运动编辑等下游任务，大幅降低后续手动绑骨工作量。

## 2. 方法论

### 2.1 整体框架
- 建立在 **SV4D 2.0** 多视图视频扩散模型之上，扩展为**双分支UNet**：一个分支生成多视图RGB帧，另一个分支生成运动部件分割图。

### 2.2 关键技术细节
- **空间颜色编码**：将离散部件ID编码为连续的RGB彩色图像。做法：将物体归一化到单位立方体，取第一帧中每个部件的3D中心坐标 $(x, y, z)$ 作为该部件在所有帧和视图中的统一颜色代码。该编码从根本上保证跨帧与跨视角的部件身份一致性，并能共享VAE编解码器。
- **双向扩散融合（BiDiFuse）**：在RGB分支和部件分支的中每一层插入轻量融合模块，实现交叉特征交互：
  - $h_{RGB}^{fused} = h_{RGB} + \mathcal{F}([h_{RGB}, h_{Part}])$
  - $h_{Part}^{fused} = h_{Part} + \mathcal{F}([h_{RGB}, h_{Part}])$
  - $\mathcal{F}$ 为两层1×1卷积+ReLU。
- **对比式部件一致性损失**：提取每个部件区域的特征，同一部件跨视图/跨帧的特征为正值对，不同部件为负值对，采用 InfoNCE 损失强制特征嵌入的一致性：
  - $\mathcal{L}_{contrast} = -\mathbb{E}\left[ \log \frac{\exp(sim(f_i, f_j) / \tau)}{\sum_{k} \exp(sim(f_i, f_k) / \tau)} \right]$
- **后处理恢复离散部件**：先用SAM自动生成候选掩码，每个掩码内统计颜色众数进行填充，最后对所有视图的掩码聚类得到最终部件分割图。

### 2.3 2D到3D的动画资产生成
- 将SP4D生成的多视图RGB和部件分割图送入Hunyuan 3D 2.0重建几何。
- 用部件标签在网格顶点上通过HDBSCAN赋ID，再求解Laplace方程 $\Delta w_p(x)=0$ 并设置边界条件，获得平滑的蒙皮权重（harmonic skinning weights）。

## 3. 实验设计

### 3.1 数据集
- **KinematicParts20K**：从Objaverse XL中精心筛选超过20K个带有骨骼绑定信息的动态物体，渲染为24视角×24帧的多视图视频，并生成基于骨骼蒙皮权重的逐像素部件标签。
- 训练分两阶段：先在ObjaverseDy上仅以RGB监督训练SV4D 2.0主干（绕过BiDiFuse），再在KinematicParts20K上微调完整双分支模型。

### 3.2 评估对象与指标
- **2D部件分割对比**：与 SAM2 （含点提示版本 SAM2*）和 DeepViT （基于DINO聚类）对比。
  - 指标：mIoU, ARI, F1, mAcc。
  - 设置：多视图（静态对象）与多帧（静态相机）两种模式。
- **3D部件分割对比**：与 SAMesh 和 SamPart3D 比较，定性评估。
- **自评消融实验**：去掉 BiDiFuse 模块、去掉对比损失，测试各部分贡献。
- **用户研究**：20名参与者对20个随机样本从“部件清晰度、视角一致性、绑定适用性”三方面打分（1-5分）。

### 3.3 对比方法列表
| 类型 | 方法 |
|------|------|
| 2D分割 | SAM2, SAM2*, DeepViT |
| 3D分割 | SAMesh, SamPart3D |
| 消融 | 无一致性损失、无BiDiFuse |
| 绑骨对比 | Magic Articulate, UniRig |

## 4. 资源与算力
- 训练硬件：**32块NVIDIA H100 GPU**，有效批次大小为32。
- 训练数据规格：每次采样12个视图、4帧。
- 微调阶段训练迭代数：**40,000 iterations**。
- 推断资源：论文未披露单次推断时间，但提及基于扩散模型生成多视图RGB和部件视频的完整流水线。

## 5. 实验数量与充分性
- **定量实验**：
  - 2D部件分割对照实验（4种度量，2种设置）——表1。
  - 用户研究——表2。
  - 3D分割对比——表3。
  - 绑骨精度与动画合理性用户研究——表4。
- **消融研究**：2项核心组件（BiDiFuse、对比一致性损失）对比，覆盖4项定量指标。
- **定性分析**：多种物体（合成、真实视频、零样本生成）的跨视角、跨时间可视化；与SAM2等基线并行展示。
- **评估是否充分**：实验设计覆盖了2D/3D、多视图/多帧、定量指标及人类偏好，且与代表性基线公平比较，消融回答了关键设计作用。但缺少不同部件数量、运动复杂度、背景干扰程度等挑战性场景的系统测试；用户研究样本量偏小；未报告误差棒。

## 6. 主要结论与发现
- SP4D能够生成与物体铰接结构对齐、跨视角与时间高度一致的运动部件分割视频。
- 空间颜色编码与对比损失是稳定学习运动部件表示的关键。
- BiDiFuse双向融合使RGB先验有效传递给部件分支，大幅提升分割质量。
- 生成结果可轻松提升到3D并生成蒙皮权重，用于动画资产，且泛化至真实视频和未见物体类别。
- SP4D在与基于外观的分割方法和现有绑骨方法的对比中表现出显著优势。

## 7. 优点
- **首次将运动部件生成融入多视图扩散模型**，突破语义分割局限。
- **简洁且有效的色彩编码**，实现VAE共享，灵活应对任意部件数量。
- **模块化设计**：BiDiFuse与对比损失易于集成到现有视频扩散架构。
- 提供了大型**KinematicParts20K**基准，有望促进该方向研究。
- **强大的泛化能力**，对真实视频、新生成物体、罕见姿态均有效。
- 完整的2D到3D蒙皮流水线，大幅降低手动绑骨成本。

## 8. 不足与局限
- **相机模型受限**：仅支持方位角与仰角，不能应对复杂相机运动或强透视变形。
- **仅支持单物体场景**：多物体情形未处理。
- **未提供推断速度数据**，实际应用效率未知。
- **部分后处理依赖SAM**，若SAM失效则可能影响最终部件精度。
- **训练数据源自特定3D资产库**，对极端形状或特殊拓扑可能仍有偏差。
- **未能端到端输出完整骨骼拓扑**，骨架连接仍需少量人工。
- **用户研究规模偏小**，可扩大以获得更可靠结论。

（完）
