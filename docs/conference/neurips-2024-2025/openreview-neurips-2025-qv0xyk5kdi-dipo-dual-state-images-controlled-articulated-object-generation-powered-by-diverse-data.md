---
title: "DIPO: Dual-State Images Controlled Articulated Object Generation Powered by Diverse Data"
title_zh: DIPO：双状态图像控制的铰接物体生成，由多样化数据赋能
authors: "Ruiqi Wu, Xinjie wang, Liu.Liu, Chun-Le Guo, Jiaxiong Qiu, Chongyi Li, Lichao Huang, Zhizhong Su, Ming-Ming Cheng"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Qv0XyK5kdI"
tags: ["query:part-aware"]
score: 10.0
evidence: 从双状态图像生成铰接三维物体，预测部件布局、关节和连接关系。
tldr: 现有单图像方法难以捕捉铰接运动信息。本文提出DIPO，从双状态图像（静止与铰接状态）中生成铰接三维物体。通过双图扩散模型预测部件布局与关节参数，并结合思维链图推理器推断部件连接关系。实验表明该方法能生成具有运动学关系的完整部件装配，推动了铰接物体生成。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qv0xyk5kdi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1407, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qv0xyk5kdi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1421, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qv0xyk5kdi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 679, \"height\": 403, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qv0xyk5kdi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 734, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qv0xyk5kdi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1445, \"height\": 1356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qv0xyk5kdi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 678, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qv0xyk5kdi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1324, \"height\": 244, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qv0xyk5kdi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1298, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qv0xyk5kdi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1423, \"height\": 67, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qv0xyk5kdi/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1088, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qv0xyk5kdi/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1429, \"height\": 190, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qv0xyk5kdi/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1421, \"height\": 813, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qv0xyk5kdi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 678, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qv0xyk5kdi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1440, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qv0xyk5kdi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1440, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qv0xyk5kdi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 483, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-qv0xyk5kdi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 604, \"height\": 280, \"label\": \"Table\"}]"
motivation: 单图像方法缺乏运动信息，难以预测铰接物体的运动学关系。
method: 提出双图扩散模型捕捉图像对关系生成部件布局与关节，图推理器推断连接性。
result: 生成具有正确运动学关系的铰接三维物体部件。
conclusion: 利用双状态图像有效控制铰接物体生成，实现部件级装配。
---

## Abstract
We present **DIPO**, a novel framework for the controllable generation of articulated 3D objects from a pair of images: one depicting the object in a resting state and the other in an articulated state.
Compared to the single-image approach, our dual-image input imposes only a modest overhead for data collection, but at the same time provides important motion information, which is a reliable guide for predicting kinematic relationships between parts.
Specifically, we propose a dual-image diffusion model that captures relationships between the image pair to generate part layouts and joint parameters. In addition, we introduce a Chain-of-Thought (CoT) based **graph reasoner** that explicitly infers part connectivity relationships.
To further improve robustness and generalization on complex articulated objects, we develop a fully automated dataset expansion pipeline, name **LEGO-Art**, that enriches the diversity and complexity of PartNet-Mobility dataset. We propose **PM-X**, a large-scale dataset of complex articulated 3D objects, accompanied by rendered images, URDF annotations, and textual descriptions.
Extensive experiments demonstrate that DIPO significantly outperforms existing baselines in both the resting state and the articulated state, while the proposed PM-X dataset further enhances generalization to diverse and structurally complex articulated objects.
Our code and dataset are available at https://github.com/RQ-Wu/DIPO.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **背景**：铰接物体（如带门、抽屉的家具）在机器人、仿真、动画等领域至关重要，但其三维模型手动构建成本高、难以规模化。
- **现有方法局限**：
  - 重建类方法需多视角或多状态图像，采集成本高、标定复杂。
  - 单图像生成方法（如SINGAPO）因缺乏显式运动信息，难以准确预测部件运动学关系，在复杂或视觉模糊场景下性能下降明显。
- **核心问题**：如何以较低的数据采集代价，实现**可控且高泛化**的铰接三维物体生成，尤其针对结构复杂、部件密集的物体。
- **研究动机**：利用双状态图像对（静止+铰接）提供运动线索，同时构建一个结构复杂度高、多样性强的数据集，以增强模型的泛化能力。

### 2. 论文提出的方法论

- **整体框架DIPO**：基于扩散Transformer架构，从一个“静止状态图像”和一个“铰接状态图像”中生成铰接物体的部件布局、关节参数与连接图。
- **双状态图像注入模块（Dual-State Injection Module）**：
  - 利用DINOv2提取两张图像的特征图（FR, FA）。
  - 在扩散去噪过程中，先让部件嵌入X与静止特征FR做交叉注意力，再将铰接特征FA以FR为引导做交叉注意力，最后将增强后的特征注入X。公式为：  
    `X = X + CA(X, FR) + CA(X, CA(FA, FR))`
  - 该设计让模型通过对比双状态，更准确地预测部件运动和关节行为。
- **图推理器（Graph Reasoner）**：
  - 采用**思维链（CoT）** 范式：先识别候选部件，估计空间布局；再验证布局是否满足铰接规则；最后推断附着关系，生成部件连接图（邻接矩阵）。
  - 利用GPT-4生成结构多样的双状态图像作为视觉提示，实现**少样本学习**，提升图推理的稳定性和泛化性。
  - 生成的邻接矩阵作为注意力掩码，约束扩散模型中的自注意力，确保结构合理性。
- **数据集构建管道LEGO-Art**：
  - 全自动合成管道，从LLM生成自然语言描述开始，经布局构建器（离散网格）、脚本工具（转为精确坐标与URDF）、检索装配（复用PartNet-Mobility原语）、渲染双状态图像，最后用VLM过滤不合理样本。
  - 产出**PM-X数据集**：600个平均部件数达19.4的复杂铰接物体，远超PartNet-Mobility（平均4.94部件）和ACD（7.48部件）。

### 3. 实验设计

- **数据集与划分**：
  - 训练集：PartNet-Mobility（PM）的493个物体 + PM-X的600个样本。每个物体渲染20个随机视角的双状态图像对。
  - 测试集：PM的77个留出物体（每个2个视角，共144个双状态样本）；ACD数据集（135个物体）用于评估分布外泛化能力。
- **对比基准**：
  - URDFormer（视觉检测+Transformer预测）
  - NAP-ICA（在NAP基础上插入图像交叉注意力）
  - SINGAPO（仅基于静止状态图像的扩散模型）
- **评估指标**：
  - 重建质量：dgIoU（广义IoU）、dcDist（部件中心距离）、dCD（倒角距离），均在静止态(RS)和铰接态(AS)分别评估。
  - 图预测准确率Acc（部件连接关系正确率）。
- **消融实验**：
  - 逐一移除/添加PM-X数据集、双状态注入模块(DIM)、图推理器(GR)，观察各组件贡献。
  - 对比不同PM-X数据比例（0%、25%、50%、75%、100%）对IoU的影响。
  - 分析CoT、视觉输入、双状态输入对图推理器精度的影响。

### 4. 资源与算力

- **硬件**：8块NVIDIA 4090 GPU。
- **训练配置**：
  - 优化器：AdamW（β=0.9, 0.99），学习率：图像条件模块 5×10⁻⁴，基础模型 5×10⁻⁵。
  - 训练轮数：200 epochs，batch size 20。
  - 初始化：使用CAGE预训练权重加速收敛。
- 论文未提及单次训练总时长。

### 5. 实验数量与充分性

- **实验组数**：
  - 在PM和ACD两个测试集上与3个基线方法进行定量对比（表2、表3）。
  - 消融实验包含7种组合（表5）及额外比例实验（图6、表4），覆盖主要模块和数据集影响。
- **充分性与公平性**：
  - 扩散生成类方法均进行了五次重复取平均，减少随机性。
  - 各基线均采用相同的训练集和测试集，SINGAPO重新训练，URDFormer进行微调，确保了比较的公平性。
  - 图像输入条件一致（渲染或真实图像），定性结果涵盖合成数据和真实场景，增强了结论说服力。
  - 整体实验设计严谨，消融分析充分，结论可靠。

### 6. 论文的主要结论与发现

- DIPO在所有重建质量和图预测准确率上均显著优于URDFormer、NAP-ICA和SINGAPO，尤其在铰接状态的指标降幅更小，证明双状态输入提供了有效的运动控制信号。
- 在更具挑战性的ACD数据集上，DIPO同样保持领先，展示了良好的分布外泛化能力。
- PM-X数据集大幅提升了模型处理复杂结构的能力，训练中加入PM-X后各指标持续改善。
- 双状态注入模块和图推理器对性能提升均有贡献，特别是结合PM-X时图推理器的作用更显著。
- 定性结果证明，DIPO能正确推断密集相似纹理部件的运动关系，处理真实世界图像时也比单图像方法更加鲁棒。

### 7. 优点

- **创新性输入模式**：仅需一对双状态图像，采集成本略高于单图像，但运动信息丰富，有效解决了单图方法运动模糊的难题。
- **结构化推理机制**：融合CoT的图推理器显式推断部件连接，并通过视觉提示获得了良好的少样本学习能力。
- **自动数据生成管道**：LEGO-Art全自动生成复杂铰接物体，PM-X数据集在部件数量与结构多样性上远超现有数据集，为模型训练提供了宝贵资源。
- **实验扎实全面**：在两个有代表性的数据集上、与多种基线对比，并做了详尽的消融与数据比例实验，评估维度覆盖静止/铰接态和连接关系。
- **可扩展性强**：管道可拓展至更多类别，模型也可与检索或生成式几何结合。

### 8. 不足与局限

- **类别局限**：实验主要针对存储家具和桌子等柜体类物体，其他类型（如工具、机械臂、可变形物体）尚未验证，泛化边界不明。
- **几何为检索而非生成**：最终三维模型通过检索原语装配得到，形状多样性受限于基础部件库，无法生成全新几何。
- **真实数据依赖VLM生成铰接图**：对于仅有静止图的互联网图片，需用GPT-4o生成对应的铰接状态图，这可能引入生成误差，且对真实铰接状态的精确还原存疑。
- **资源需求较大**：训练使用8块4090 GPU，虽然有预训练初始化，但对于资源有限的研究者可能门槛较高。
- **数据集偏差风险**：PM-X由程序化管道生成，虽然结构复杂，但可能与真实世界物体的分布仍存在差异。

（完）
