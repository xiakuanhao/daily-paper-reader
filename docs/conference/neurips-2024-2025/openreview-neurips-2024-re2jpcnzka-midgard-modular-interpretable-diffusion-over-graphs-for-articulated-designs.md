---
title: "MIDGArD: Modular Interpretable Diffusion over Graphs for Articulated Designs"
title_zh: MIDGArD：面向铰接设计的图扩散模块化可解释模型
authors: "Quentin Leboutet, Nina Wiedemann, zhipeng cai, Michael Paulitsch, Kai Yuan"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=re2jPCnzkA"
tags: ["query:part-aware"]
score: 10.0
evidence: 用于生成铰接三维资产的扩散框架，采用模块化结构生成
tldr: MIDGArD通过将铰接三维资产生成拆分为结构生成和形状生成两个模块，在扩散过程中分别处理运动学属性和几何形状，从而生成高质量、一致且可控的铰接对象。该方法显著提升了生成结果的真实感和实用性，为交互式三维内容创建提供了有力工具。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-re2jpcnzka/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-re2jpcnzka/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1458, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-re2jpcnzka/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1429, \"height\": 876, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-re2jpcnzka/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1430, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-re2jpcnzka/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1432, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-re2jpcnzka/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1109, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-re2jpcnzka/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1457, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-re2jpcnzka/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1463, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-re2jpcnzka/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1145, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-re2jpcnzka/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1446, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-re2jpcnzka/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1421, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-re2jpcnzka/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1448, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-re2jpcnzka/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1420, \"height\": 1706, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-re2jpcnzka/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 981, \"height\": 257, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-re2jpcnzka/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 865, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-re2jpcnzka/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1292, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-re2jpcnzka/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1435, \"height\": 364, \"label\": \"Table\"}]"
motivation: 现有方法在生成铰接三维资产时面临质量、一致性和可控性不足的挑战。
method: 提出模块化可解释图扩散模型（MIDGArD），分离结构生成与形状生成，在图上扩散结构属性。
result: 在铰接对象生成任务上，MIDGArD在生成质量和一致性方面显著优于基线方法。
conclusion: 该工作为可交互三维资产的自动化生成开辟了新方向，提升了生成的灵活性和实用性。
---

## Abstract
Providing functionality through articulation and interaction with objects is a key objective in 3D generation. We introduce MIDGArD (Modular Interpretable Diffusion over Graphs for Articulated Designs), a novel diffusion-based framework for articulated 3D asset generation. MIDGArD improves over foundational work in the field by enhancing quality, consistency, and controllability in the generation process. This is achieved through MIDGArD's modular approach that separates the problem into two primary components: structure generation and shape generation. The structure generation module of MIDGArD aims at producing coherent articulation features from noisy or incomplete inputs. It acts on the object's structural and kinematic attributes, represented as features of a graph that are being progressively denoised to issue coherent and interpretable articulation solutions. This denoised graph then serves as an advanced conditioning mechanism for the shape generation module, a 3D generative model that populates each link of the articulated structure with consistent 3D meshes. Experiments show the superiority of MIDGArD on the quality, consistency, and interpretability of the generated assets. Importantly, the generated models are fully simulatable, i.e., can be seamlessly integrated into standard physics engines such as MuJoCo, broadening MIDGArD's applicability to fields such as digital content creation, meta realities, and robotics.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **研究动机**：在3D生成领域，使物体具有可交互的关节结构至关重要。然而，现有铰接3D资产（articulated 3D asset）的创建仍主要依赖人工，且现有生成方法（如NAP）存在运动不自然、可控性差、缺乏可解释性、生成几何形状不一致等问题。
*   **整体含义**：本文提出了 **MIDGArD**（面向铰接设计的图扩散模块化可解释模型），这是一个基于扩散模型的框架，旨在以高质量、高一致性、强可控性的方式生成可模拟的铰接3D对象。其核心思想是将复杂的铰接对象生成问题解耦为“结构生成”和“形状生成”两个顺序执行的模块。

### 2. 论文提出的方法论
*   **核心思想**：采用模块化顺序管道。首先，一个**结构生成器**在图上进行扩散去噪，生成对象的运动学结构（关节类型、连接关系、部件包围盒等），并以人类可读的图像和文本形式输出中间表示；然后，一个**形状生成器**利用这些条件，为每个部件生成一致的高质量3D网格。
*   **结构生成器关键技术细节**：
    *   **表示形式**：将铰接资产编码为全连接图 $G_N$，节点特征包含部件存在性、资产/部件类别、包围盒尺寸/朝向/位置、图像潜在码 $g_i$；边特征包含连接存在性、关节类型、Plücker坐标、关节限位。
    *   **图像潜在码**：不直接编码网格，而是训练一个VQ-VAE学习部件多视图图像的潜在表示，使得中间结果具有可解释性（可解码为图像和文本）。
    *   **Plücker流形扩散**：提出一种新的 $k_{ij} = [m_{ij}, n_{ij}] \in \mathbb{R}^5$ 参数化，直接在Plücker流形上扩散，天然保证轴的单位长度和正交性，避免了每步重投影。
    *   **定向包围盒（OBB）**：通过PCA初始化并结合梯度下降最小化体积，将数据集物体调整到规范姿态，显著提升了包围盒的紧密度和生成一致性。
*   **形状生成器关键技术细节**：
    *   基于多模态3D生成模型 **SDFusion** 改造。输入条件包括：由结构生成器解码的单视图图像、由类别信息构建的文本描述、以及图特征。
    *   **包围盒约束生成**：提出在潜在空间中学习形状与包围盒TSDF的差值 $z_\Delta = z_o - z_b$。推理时，将 $z_b$ 与加噪的 $z_\Delta$ 拼接，强制生成的形状与目标包围盒匹配，保证部件尺寸准确。

### 3. 实验设计
*   **数据集与场景**：全部实验基于 **PartNet Mobility** 数据集进行。所有网格均经过了流形化预处理和定向包围盒姿态估计。
*   **基准与指标**：与现有基线 **NAP** 进行对比。评估指标沿用NAP的 **Instantiation Distance (ID)**，并配合无条件生成的标准指标：最小匹配距离（MMD）、覆盖率（COV）和1-最近邻准确率（1-NNA）。
*   **对比方法**：
    *   主要与 **NAP** 在无条件生成任务上对比。
    *   形状生成部分，与原始 **SDFusion** 及其变体（仅增加包围盒MLP条件、但使用原始AABB数据集）进行了消融比较。

### 4. 资源与算力
*   结构生成器和图像VQ-VAE在单块 **NVIDIA RTX 3090** GPU上训练。
*   形状生成器在单块 **NVIDIA RTX 6000** GPU上训练。
*   评估在单块 **NVIDIA RTX 3090** GPU上进行。
*   论文未明确给出具体的训练总时长。

### 5. 实验数量与充分性
*   **实验数量**：开展了多组实验，包括：
    *   与NAP在无条件生成上的量化对比（Table 1）。
    *   关节类型分布的统计分析（Table 2），验证物理合理性。
    *   针对形状生成中包围盒约束的消融研究（Table 3），比较了有无“bb prior”、是否使用“定向数据集”以及后处理的影响。
    *   对图编码方式的消融（MLP vs. GAT，Appendix Table 4）。
    *   丰富的定性结果展示（Figure 3），包括与NAP的并排对比、条件生成（Part-To-Motion, 图像引导）和典型失败案例。
*   **充分性与公平性**：实验设计较全面，覆盖了系统主要创新点的验证。对比对象NAP被重训练于相同预处理数据集，确保了公平性。多种消融实验清晰展示了各组件的贡献。

### 6. 论文的主要结论与发现
*   MIDGArD在铰接物体生成的质量、一致性和可解释性上全面超越现有方法NAP。
*   通过类别嵌入和Plücker流形扩散，MIDGArD生成的关节类型分布与训练数据高度一致（$\chi^2=12.7$），解决了NAP几乎只生成螺旋关节的失配问题。
*   提出的定向包围盒预处理和约束形状生成方法大幅改善了部件尺寸准确性，将错误溢出体积显著降低，并提升了重建的Chamfer Distance。
*   框架的模块化设计天然支持多层次（资产级、部件级、图像/文本级）的人机交互控制，且生成的模型可直接导入MuJoCo等物理引擎中进行模拟。

### 7. 优点
*   **模块化与可扩展性**：将结构和形状生成解耦，便于各模块独立升级（如替换更先进的形状生成器）。
*   **强可解释性与可控性**：图结构中的图像潜在码和类别变量可解码为人可理解的图像和文本，为非技术用户提供了细粒度的控制接口。
*   **物理合理性增强**：Plücker流形上的扩散和OBB姿态估计分别从运动学和几何尺寸上保证了生成结果的合理性。
*   **实用性**：端到端生成可无缝接入物理引擎的模拟就绪资产，直击数字内容创作、具身AI和机器人学的应用痛点。

### 8. 不足与局限
*   **评估指标有限**：现有指标（如ID）可能无法准确反映所有失败模式，例如对小部件发生不真实大位移运动的检测能力不足。
*   **图结构可扩展性**：固定最大节点数（$N=8$）的方式限制了处理包含大量部件复杂物体的能力。
*   **混合数据类型处理**：未采用像MiDi这类能同时处理连续和离散变量的扩散方法，可能在表示能力上存在提升空间。
*   **条件生成限制**：未探索用自然语言或图像直接条件化结构生成过程，而仅将其用于形状生成。
*   **形状生成编码**：实验显示训练GAT来编码图信息的效果不如简单MLP，可能是由于训练同步收敛慢，未来可探索预训练GAT编码器。

（完）
