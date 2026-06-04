---
title: "URDF-Anything: Constructing Articulated Objects with 3D Multimodal Language Model"
title_zh: URDF-Anything：利用三维多模态语言模型构建铰接对象
authors: "Zhe Li, Xiang Bai, Jieyu Zhang, Zhuangzhe Wu, Che Xu, Ying Li, Chengkai Hou, Shanghang Zhang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=g3EF5XsapH"
tags: ["query:part-aware"]
score: 10.0
evidence: 端到端自动重建铰接对象，包含部件级分割和运动学参数
tldr: URDF-Anything提出了一种基于3D多模态大语言模型的端到端框架，能够从点云和文本输入自动重建铰接物体。通过专门的令牌机制同时优化几何分割和运动学参数，实现精确的部件级表示。该方法显著降低了铰接对象建模的人力成本，为机器人仿真和具身AI提供了高效的解决方案。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3ef5xsaph/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1402, \"height\": 516, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3ef5xsaph/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1432, \"height\": 536, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3ef5xsaph/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1384, \"height\": 1247, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3ef5xsaph/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1420, \"height\": 775, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3ef5xsaph/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1432, \"height\": 909, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3ef5xsaph/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1427, \"height\": 643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3ef5xsaph/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1386, \"height\": 837, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3ef5xsaph/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1377, \"height\": 1918, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-g3ef5xsaph/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1277, \"height\": 556, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3ef5xsaph/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1453, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3ef5xsaph/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1460, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3ef5xsaph/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1115, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3ef5xsaph/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1482, \"height\": 319, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3ef5xsaph/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1406, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3ef5xsaph/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 785, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3ef5xsaph/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 655, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3ef5xsaph/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1204, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3ef5xsaph/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1290, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3ef5xsaph/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1453, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3ef5xsaph/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1111, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-g3ef5xsaph/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1086, \"height\": 183, \"label\": \"Table\"}]"
motivation: 铰接物体的数字孪生构建通常依赖繁琐的手工建模或多阶段流程，自动化程度低。
method: "使用3D多模态大语言模型，采用自回归预测和专用[SEG]令牌，联合优化部件分割与运动学参数。"
result: 模型能够从点云和文本中准确重建铰接物体的几何和运动结构。
conclusion: URDF-Anything实现了铰接物体的全自动重建，极大提升了相关应用的效率。
---

## Abstract
Constructing accurate digital twins of articulated objects is essential for robotic simulation training and embodied AI world model building, yet historically requires painstaking manual modeling or multi-stage pipelines. In this work, we propose \textbf{URDF-Anything}, an end-to-end automatic reconstruction framework based on a 3D multimodal large language model (MLLM). URDF-Anything utilizes an autoregressive prediction framework based on point-cloud and text multimodal input to jointly optimize geometric segmentation and kinematic parameter prediction. It implements a specialized [SEG] token mechanism that interacts directly with point cloud features, enabling fine-grained part-level segmentation while maintaining consistency with the kinematic parameter predictions.
Experiments on both simulated and real-world datasets demonstrate that our method significantly outperforms existing approaches regarding geometric segmentation (mIoU 17\% improvement), kinematic parameter prediction (average error reduction of 29\%), and physical executability (surpassing baselines by 50\%). Notably, our method exhibits excellent generalization ability, performing well even on objects outside the training set. This work provides an efficient solution for constructing digital twins for robotic simulation, significantly enhancing the sim-to-real transfer capability.

---

## 论文详细总结（自动生成）

# URDF-Anything 论文深度分析总结

## 1. 核心问题与研究动机
- **研究背景**：构建铰接物体（如门、抽屉、剪刀）的高保真数字孪生对机器人仿真训练和具身AI世界模型至关重要。传统方法依赖费时的手工建模或多阶段管线，自动化程度低、迁移性差。
- **核心挑战**：从视觉观测中自动重建铰接物体需同时推断各部件的几何形状及其连接的 kinematic 参数（关节类型、原点、轴、限位等），这对感知、推理和结构化输出的耦合提出极高要求。
- **整体含义**：本文旨在提供一个端到端的统一框架，将3D多模态大语言模型引入铰接物体重建，实现从点云/图像到可直接用于物理仿真的 URDF 模型的自动化转换。

## 2. 方法论
- **核心思想**：以3D MLLM 为骨干，利用其跨模态理解和结构化输出能力，联合预测几何部件分割和运动学参数，并引入专门的 `[SEG]` token 机制实现两者深度耦合。
- **技术流程**：
  1. **输入表示**：从单视图或多视图 RGB 图像生成稠密点云（多视图用 DUSt3R，单视图用生成式方法 LGM）。得到整体点云 \(P_{\text{obj}}\)。
  2. **多模态铰接解析**：采用 ShapeLLM 作为骨干，输入点云特征与文本指令。模型自回归生成结构化 JSON 输出，其中每个 link 描述中包含 `[SEG]` 标记。
  3. **基于特殊 Token 的几何分割**：对于每个 `[SEG]` token，将其隐状态与前一类别 token 隐状态融合作为 query，通过交叉注意力与点云特征交互，生成逐点的二值分割掩码。
  4. **网格转换与 URDF 生成**：分割的点云通过经典方法转换为网格，结合预测的 kinematic 参数组装成完整的 URDF 文件。
- **训练目标**：端到端优化语言建模损失 \(L_{\text{text}}\) 和分割损失 \(L_{\text{seg}}\)（二元交叉熵 + Dice 损失的组合）。

## 3. 实验设计
- **数据集**：PartNet-Mobility，包含大量带 URDF 标注的铰接物体。划分为分布内（5个类别）和分布外（41个类别）两部分。
- **评价指标**：
  - 部件分割：mIoU、部件数量准确率（Count Acc）
  - 关节参数：类型误差、轴角度误差、原点位置误差
  - 物理可执行率：在仿真器中成功加载并驱动的比例
- **对比方法**：
  - Articulate-Anything（基于 VLM 和网格检索的迭代优化系统）
  - Real2Code（用 OBB 抽象部件并生成代码）
  - URDFormer（从真实图像构建仿真场景的管线）
- **补充实验**：形状重建质量对比（CARTO、PARIS），零样本 sim-to-real 测试（PARIS 真实数据），输入模态消融，几何-运动学联合训练消融等。

## 4. 资源与算力
- **GPU 配置**：使用 **1 张 NVIDIA A800 (80GB)**。
- **训练时长**：微调时间约 **2.5 小时**。
- **优化设置**：AdamW 优化器，学习率 0.0003，LoRA rank=8，batch size=2（设备设置），梯度累积10步，cosine 调度，warmup 迭代比 0.03。

## 5. 实验数量与充分性
- **主要实验组数**：包含分割性能对比（表1）、关节参数预测对比（表2）、物理可执行性对比（表3）、输入模态消融（表4）、联合预测 vs. 解耦预测消融（表5）、形状重建质量对比（表6）、真实世界泛化测试（表11）、上下文融合机制消融（表12）等，总计不少于 12 个对比/消融实验表格。
- **充分性与公平性**：
  - 覆盖了分布内/外、合成/真实数据，指标涵盖几何、运动学和仿真可用性，实验设计全面。
  - 对比基线选择了近两年的代表性方法，并使用统一的 Oracle 设置或相同测试条件，保证公平性。
  - 消融研究针对输入模态、联合训练的必要性、上下文融合机制等关键设计展开，结论支撑有力。
  - 零样本真实数据测试展示了模型的实际迁移能力，但真实数据规模和类别较少（仅冰箱和储物柜），可进一步扩展。

## 6. 主要结论与发现
- 提出的 URDF-Anything 在所有评测指标上显著超越现有方法：mIoU 提升 17%，关节参数平均误差降低 29%，物理可执行率提升 50%。
- 方法展现极强的泛化能力，在训练时未见的类别上仍保持出色性能，验证了 3D MLLM 的开放世界理解优势。
- 联合几何分割与运动学预测是成功的关键，单方面解耦训练均会导致性能下降。
- 详尽的姿态信息（点云）+语言指导的组合比单纯 OBB 或二维图像输入更有效。

## 7. 优点
- **范式创新**：首次将 3D MLLM 引入铰接物体重建，实现了从感知到结构化输出的端到端闭环。
- **技术耦合巧妙**：`[SEG]` token 和上下文融合机制将符号推理与密集预测深度绑定，既保证一致性又提升各子任务性能。
- **实验扎实**：多维度评估、丰富的消融实验和零样本真实场景测试增强了结论的可信度。
- **高效实用**：单卡 2.5 小时微调即可达到领先性能，推理速度快，适合实际部署。

## 8. 不足与局限
- **输出属性不完整**：当前方法未预测质量、惯量等物理属性，限制了在精确物理仿真中的直接应用。
- **非完全端到端**：点云到网格的转换依赖外部模块，可能引入额外误差。
- **数值精度限制**：参数生成基于 token 预测，连续值的表示精度受限于离散化方式。
- **真实数据实验有限**：零样本测试仅在两类别、少量样本上进行，对复杂多样真实场景的鲁棒性有待验证。
- **错误模式**：失败案例主要由 kinematic 参数误差引起（21%），未来可针对性地提升轴和原点预测精度。

（完）
