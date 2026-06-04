---
title: "PartCrafter: Structured 3D Mesh Generation via Compositional Latent Diffusion Transformers"
title_zh: PartCrafter：通过组合潜在扩散Transformer进行结构化三维网格生成
authors: "Yuchen Lin, Chenguo Lin, Panwang Pan, Honglei Yan, Feng Yiqiang, Yadong MU, Katerina Fragkiadaki"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=0e1KaHtgvU"
tags: ["query:part-aware"]
score: 10.0
evidence: 从单张图像端到端地生成多个语义三维网格部件
tldr: PartCrafter首次提出结构化三维生成模型，可直接从单张RGB图像联合去噪生成多个语义上有意义、几何上分离的三维网格部件，无需预先分割。该端到端框架基于预测练的网格扩散Transformer，能同时生成单个物体和复杂多物体场景，为零件感知的三维内容创建提供了高效解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-0e1kahtgvu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1263, \"height\": 707, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0e1kahtgvu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1390, \"height\": 625, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0e1kahtgvu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1407, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0e1kahtgvu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1433, \"height\": 825, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0e1kahtgvu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0e1kahtgvu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1445, \"height\": 1265, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0e1kahtgvu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1414, \"height\": 1479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0e1kahtgvu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1440, \"height\": 522, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0e1kahtgvu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1567, \"height\": 2097, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0e1kahtgvu/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1565, \"height\": 2090, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0e1kahtgvu/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1493, \"height\": 2093, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0e1kahtgvu/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1567, \"height\": 2072, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0e1kahtgvu/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1535, \"height\": 2023, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-0e1kahtgvu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 424, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0e1kahtgvu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1439, \"height\": 300, \"label\": \"Table\"}]"
motivation: 现有方法或生成整体形状，或依赖预分割的两阶段流程，无法端到端生成结构化多部件模型。
method: 采用统一组合式潜在扩散Transformer，从单图同时去噪生成多个三维网格部件。
result: 在多种物体和场景上，PartCrafter成功生成结构清晰的多部件三维模型。
conclusion: 该工作首次实现无需分割线索的端到端零件感知生成，推动结构化三维建模发展。
---

## Abstract
We introduce PartCrafter, the first structured 3D generative model that jointly synthesizes multiple semantically meaningful and geometrically distinct 3D meshes from a single RGB image. Unlike existing methods that either produce monolithic 3D shapes or follow two-stage pipelines, i.e. first segmenting an image and then reconstructing each segment, PartCrafter adopts a unified, compositional generation architecture that does not rely on pre-segmented inputs. Conditioned on a single image, it simultaneously denoises multiple 3D parts, enabling end-to-end part-aware generation of both individual objects and complex multi-object scenes. PartCrafter builds upon a pretrained 3D mesh diffusion transformer (DiT) trained on whole objects, inheriting the pretrained weights, encoder, and decoder, and introduces two key innovations: (1) A compositional latent space, where each 3D part is represented by a set of disentangled latent tokens; (2) A hierarchical attention mechanism that enables structured information flow both within individual parts and across all parts, ensuring global coherence while preserving part-level detail during generation. To support part-level supervision, we curate a new dataset by mining part-level annotations from large-scale 3D object datasets. Experiments show that PartCrafter outperforms existing approaches in generating decomposable 3D meshes, including parts that are not directly visible in input images, demonstrating the strength of part-aware generative priors for 3D understanding and synthesis. Code and training data are released.

---

## 论文详细总结（自动生成）

# PartCrafter 论文总结

## 1. 论文的核心问题与整体含义

- **核心问题**：现有的3D生成模型大多只能生成整体的、不可分解的单体网格，缺乏对零件（part）级别的结构化理解。少数方法采用“先分割图像，再逐部件重建”的两阶段流水线，但这严重依赖分割质量，且计算开销大、难以扩展。
- **整体含义**：本工作首次提出端到端的结构化3D生成模型 PartCrafter，能够直接从单张RGB图像一次性生成多个语义明确、几何独立的3D网格部件，无需任何预先分割输入，实现对物体和场景的“零件感知”生成，从而更好地支持纹理映射、动画、物理模拟、场景编辑等下游任务。

## 2. 论文提出的方法论

- **核心思想**：在预训练的单体3D网格扩散Transformer（DiT）基础上，通过组合式潜在空间和层次化注意力机制，将整体生成扩展为多部件的结构化生成。
- **关键技术细节**：
  - **组合式潜在空间**：每个3D部件由一个独立的隐变量集合 \(\mathbf{z}_i = \{\mathbf{z}_{ij}\}_{j=1}^K \in \mathbb{R}^{K \times C}\) 表示，整个物体的隐变量由所有部件的隐变量拼接而成 \(\mathbf{Z} = \{\mathbf{z}_i\}_{i=1}^N\)。为区分部件，对每个部件的隐变量添加可学习的部件身份嵌入 \(\mathbf{e}_i\)。
  - **局部-全局注意力机制**：在DiT的每个Transformer块中交替使用局部注意力（仅在单个部件内部计算）和全局注意力（在所有部件的隐变量之间计算）。局部注意力捕捉部件内部结构，全局注意力建模跨部件交互，同时通过交叉注意力注入输入图像的DINOv2特征，使生成既保持部件独立性又具备整体一致性。
  - **训练目标**：采用 rectified flow matching 进行训练，噪声水平 \(t\) 在所有部件间共享，优化速度预测与真实速度的均方误差。
  - **数据集构建**：从Objaverse、ShapeNet、ABO等数据集中挖掘已有的部件标注（源自艺术家创作时的模块化设计），并基于纹理质量、部件数量、部件间交并比等进行过滤，构建了约5万个带有部件标签的3D物体数据集。对于场景，使用3D-Front数据集。
- **实现细节**：基于TripoSG的21个DiT块，在偶数索引块应用全局注意力，奇数索引块应用局部注意力，并采用长跳跃连接。先训练最多8个部件的基模型，再微调至最多16个部件（物体）或8个物体（场景）。训练时混入30%的单体物体作为正则化。

## 3. 实验设计

- **数据集与场景**：
  - 3D零件级物体生成：Objaverse、ShapeNet、ABO 的测试集，每个数据集约2千样本。
  - 3D场景生成：3D-Front数据集，包括其中严重遮挡的子集。
- **对比方法**：
  - 物体级：HoloPart（先由TripoSG生成网格，再用3D分割模型获取部件），以及等量隐变量的TripoSG（作为基线骨干）。
  - 场景级：MIDI（使用真实分割掩码的多实例扩散方法）。
- **评测指标**：
  - 重建保真度：L2 Chamfer Distance（CD）和阈值0.1的F-Score。
  - 部件几何独立性：平均部件间交并比（IoU），值越低表示重叠越少。
  - 运行时间。
- **消融实验**：针对局部-全局注意力必要性、部件身份嵌入、交叉注意力位置、局部-全局注意力顺序等分别进行了消融，总计设计了多组对照（如移除局部注意力、移除全局注意力、移除身份嵌入、调整交叉注意力注入方式、改变全局注意力块排列顺序等）。

## 4. 资源与算力

- **训练硬件**：8块H20 GPU。
- **批次大小**：256。
- **训练时长**：整个训练过程约2天。基模型训练5K次迭代，学习率1e-4；针对更高部件数或场景的微调各进行5K次迭代，学习率降至5e-5。
- 推理阶段，单个场景/物体（含4个部件）生成时间约34秒（H20 GPU）。

## 5. 实验数量与充分性

- **主要实验组数**：涵盖3个物体数据集 + 1个场景数据集（含正常和严重遮挡子集），对比2种基线方法，消融实验至少包含5组不同的架构变体（Exp.1-5，每组又可能包含子配置，如交叉注意力的3种设置、全局注意力顺序的3种配置），合计十余组实验。
- **充分性与客观性**：实验覆盖了物体和场景两个层次，验证了从可见部分推理不可见部件的能力，且所有对比方法均使用公开模型或同等设定，评测指标多样（保真度+独立性+速度），消融实验系统性地分析了各模块贡献，结论较为可靠且客观。

## 6. 论文的主要结论与发现

- PartCrafter 在 3D 零件级物体生成和场景生成任务上均显著优于基于分割的两阶段方法，即使不使用任何分割输入也能实现更高的重建保真度和部件独立性。
- 通过结构化生成，PartCrafter 能够自动推断并生成输入图像中不可见的部件，验证了零件感知生成先验的强大能力。
- 值得注意的是，PartCrafter 在物体重建保真度上甚至超过了其单体生成骨干网络 TripoSG，表明理解物体的组成结构能反哺生成质量的提升。
- 消融实验证明，局部-全局注意力、部件身份嵌入以及两者中交叉注意力的注入对模型性能至关重要，缺失任一部分都会导致严重性能下降或无法生成可分解的网格。

## 7. 优点

- **端到端一体化**：首次实现无需任何分割线索的结构化多部件3D生成，避免了分割误差和两阶段的复杂流水线。
- **架构创新**：提出的组合式潜在空间与层次化注意力机制，有效实现了部件级别的独立控制与全局场景的一致性，设计优雅且可扩展。
- **数据挖掘策略**：巧妙利用现有3D资源中的原生部件标注，无需昂贵的人工二次标注，快速构建了大规模部件数据集。
- **广泛的适用性**：方法可无缝用于单个物体、复杂多对象场景，并能调节生成部件的颗粒度，显示出灵活的下游应用潜力。
- **性能增益**：实验证明结构化生成不仅带来部件分解能力，还整体提升了3D重建的精度。

## 8. 不足与局限

- **训练数据规模**：所构建的部件级数据集仅约5万物体，远小于单体生成模型常用数百万级别的数据，可能限制模型的泛化能力，尤其对长尾或罕见部件结构。
- **部件数量限制**：目前支持最多16个部件（物体）或8个对象（场景），对于极为复杂的层次化结构仍显不足。
- **真实世界泛化**：虽然在合成渲染图上表现优异，但在真实世界图像上的泛化能力受域差异影响，需要借助风格迁移等后处理手段，尚未实现直接鲁棒的推理。
- **消融实验的全面性**：虽然架构消融较为充分，但对于训练策略（如课程学习、正则化比例）等未做深入对比，可能存在进一步优化空间。
- **评估局限**：仅使用几何度量，缺乏纹理、语义一致性或用户主观评价，难以全面反映生成结果在内容创作等实际应用中的可用性。

（完）
