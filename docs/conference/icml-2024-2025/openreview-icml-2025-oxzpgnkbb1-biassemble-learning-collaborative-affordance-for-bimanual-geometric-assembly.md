---
title: "BiAssemble: Learning Collaborative Affordance for Bimanual Geometric Assembly"
title_zh: BiAssemble：学习双手协同在几何装配中的功能可供性
authors: "Yan Shen, Ruihai Wu, Yubin Ke, Xinyuan Song, Zeyi Li, Xiaoqi Li, Hongwei Fan, Haoran Lu, Hao Dong"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=OxzPgnkbB1"
tags: ["query:part-aware"]
score: 10.0
evidence: 形状装配，通过双手协同几何装配将碎片组合成完整物体
tldr: 针对碎片几何装配的挑战，提出BiAssemble方法，学习点级功能可供性以指导双手协同操作，实现将破碎部件重组为原始形状。引入几何装配评估指标，克服因部件多样性导致的评价模糊。机器人实验验证了长序列动作下精确装配的能力，为视觉引导的零件装配提供了新方案。该方法在残缺物体重建等任务中表现出色，证明了点级功能可供性在双手协作装配中的有效性，并展示了从感知到行动闭环的潜力。这为解决物流分拣、古物修复等实际问题提供了理论基础与技术支撑。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-oxzpgnkbb1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1711, \"height\": 1288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oxzpgnkbb1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1751, \"height\": 1246, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oxzpgnkbb1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1751, \"height\": 706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oxzpgnkbb1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1759, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oxzpgnkbb1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1728, \"height\": 839, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oxzpgnkbb1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1752, \"height\": 1076, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oxzpgnkbb1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1760, \"height\": 685, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oxzpgnkbb1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 635, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oxzpgnkbb1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1768, \"height\": 1702, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oxzpgnkbb1/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1657, \"height\": 2041, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oxzpgnkbb1/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1687, \"height\": 600, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-oxzpgnkbb1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1706, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oxzpgnkbb1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 959, \"height\": 806, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oxzpgnkbb1/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 741, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oxzpgnkbb1/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1396, \"height\": 308, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oxzpgnkbb1/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 916, \"height\": 309, \"label\": \"Table\"}]"
motivation: 几何装配需识别碎片几何线索并执行长序列协同操作，极具挑战。
method: 利用点级功能可供性泛化，设计双手协同装配的长程动作序列。
result: 成功重建破碎碗等物体，评估指标缓解了形状多样性引起的模糊。
conclusion: 为机器人执行复杂装配任务提供了有效的学习方案。
---

## Abstract
Shape assembly, the process of combining parts into a complete whole, is a crucial skill for robots with broad real-world applications. Among the various assembly tasks, geometric assembly—where broken parts are reassembled into their original form (e.g., reconstructing a shattered bowl)—is particularly challenging. This requires the robot to recognize geometric cues for grasping, assembly, and subsequent bimanual collaborative manipulation on varied fragments. In this paper, we exploit the geometric generalization of point-level affordance, learning affordance aware of bimanual collaboration in geometric assembly with long-horizon action sequences. To address the evaluation ambiguity caused by geometry diversity  of broken parts, we introduce a real-world benchmark featuring geometric variety and global reproducibility. Extensive experiments demonstrate the superiority of our approach over both previous affordance-based and imitation-based methods.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究动机**：几何装配（如将打碎的碗重新拼合）是机器人操作中极具挑战性的任务，需要机器人根据碎片几何线索完成抓取、对齐、拼合等一系列长程动作，且需进行双手协同。传统方法多停留在预测理想的目标位姿，忽略了实际执行中的碰撞、抓取点选择以及双手配合。
- **整体含义**：本文旨在赋予机器人从局部几何感知中推理出协作功能可供性（affordance）的能力，将视觉预测与机器人执行紧密结合，以端到端的方式解决双手几何装配问题，并为此设计了标准化真实世界基准，推动该领域从视觉研究走向真实机器人操作。

### 2. 论文提出的方法论
- **核心思想**：将几何装配任务分解为三个关键步骤——抓取（Pick-up）、对齐（Alignment）、拼合（Assembly），并通过模拟“拆卸”过程来获得对齐和拼合方向，从而引导点级功能可供性学习，使抓取点不仅易于抓取，且有助于后续双臂协同。
- **关键技术细节**：
    - **框架组成**：
        - **拆卸预测器（Disassembly Predictor）**：基于重构后的完整形状 S 预测无碰撞的拆卸方向 v（使用 SO(3) 等变网络 VN-DGCNN 编码形状特征，条件 VAE 生成方向）。
        - **变换预测器（Transformation Predictor）**：预测一个 SE(3) 变换 M，将完整形状 S 和拆卸方向 v 转换为对齐位姿，使得机器人能从初始碎块位姿无碰撞地运动到对齐位姿。
        - **双手功能可供性预测器（BiAffordance Predictor）**：输入观察点云 O、变换后的完整形状 S′ 和方向 v′，预测抓取点及姿态。由两个级联的子模块（Affordance Network + Actor Network）构成，第一个模块预测第一只手的抓取点和姿态，第二个模块以第一个动作为条件预测第二只手的动作。训练时采用类似 DualAfford 的协同训练策略。
    - **动作生成**：利用假设的“抓手-物体相对位姿不变”和已知的目标物位姿变换，由抓取位姿推导对齐和拼合阶段的抓手位姿。
- **算法流程**：输入观测点云 O 和想象的完整形状 S → 预测拆卸方向 v → 预测变换 M → 得到变换后的 S′ 和 v′ → 基于 S′ 和 v′ 预测双手抓取点与姿态 → 执行抓取、对齐、拼合。

### 3. 实验设计
- **数据集/场景**：
    - **仿真**：基于 Breaking Bad 数据集（物体破碎数据集），覆盖 15 个类别、445 个物体、11739 个碎片对。训练集含 10 类（237 物体），测试集包含训练类内新实例（131 物体）和全新类别（5 类）。
    - **真实世界**：作者构建了一套真实世界基准，使用手机扫描 6 类物体（酒杯、盘子、啤酒瓶、碗、杯子、茶壶），经 COLMAP + SDFStudio 重建网格，并用 Blender 标注真值。该基准兼具几何多样性和可复现性。
- **对比方法**：ACT（模仿学习）、Heuristic（手写启发式策略）、SE(3)-Equiv（基于等变网络预测拼合位姿，抓取用启发式）、DualAfford（短程双手 affordance）、以及自身消融模型（w/o SE(3) 用 PointNet++ 替代等变编码器，w/ GT Target 直接提供真值拆卸方向和变换）。
- **评估指标**：拼合后两碎片的相对距离（单位长度）和旋转角度（度）是否在阈值内。

### 4. 资源与算力
- **GPU**：使用单块 NVIDIA V100 GPU。
- **训练时长**：总训练时间约 48 小时（其中拆卸预测器与变换预测器约 20 小时收敛，双手功能可供性预测器约 48 小时收敛）。
- **推理资源**：推理时占用约 1600 MB GPU 内存，每样本平均耗时 0.1 秒。

### 5. 实验数量与充分性
- **实验组数**：
    - 主实验：在仿真环境下，对比 6 个方法（含消融）在 15 个类别、共 100 个测试样本/类的表现，分别在训练类内新实例和新类别上评估。
    - 消融实验：针对 Affordance 网络、变换预测器、拆卸方向预测分别进行消融，分析了缺失模块的影响。
    - 多碎片扩展实验：在三碎片装配任务上测试方法。
    - 真实世界实验：在 6 个真实扫描物体上可视化演示。
    - 更多分析：评估了不完美的想象完整形状输入下的鲁棒性。
- **充分性**：实验体系较为完整，对比了模仿学习、纯视觉预测、短程 affordance、启发式等基线，消融实验解释了各模块的贡献。但真实世界实验仅提供了定性演示，缺乏定量成功率统计，且未见与真实世界基线的系统对比；测试样本数量虽多，但每类仅 100 个测试场景，对于几何多样性大的任务，可能仍不足以完全反映泛化能力。总体设计公平，所有方法在相同初始化条件下测试。

### 6. 论文的主要结论与发现
- **BiAssemble 方法**在训练类内新实例和新类别上均显著优于以往基于功能可供性或模仿学习的方法，证明了点级功能可供性结合长程拆卸引导对双手几何装配任务的有效性。
- SO(3) 等变编码器有助于形状几何的解耦，提高泛化能力。
- 变换预测器和功能可供性预测器的协同设计，使抓取点考虑后续对齐和拼合，大幅减少了碰撞。
- 真实世界实验展示了所提方法从仿真到真实场景的迁移潜力，即使面对不完美的想象完整形状输入，性能下降也较小。

### 7. 优点
- **方法创新**：首次将点级功能可供性推广到涉及长程动作序列的双手几何装配任务，通过“先想象拆卸再学习装配”的思路简化动作空间。
- **模块化设计**：将任务分解为拆卸方向预测、变换预测和双手功能可供性预测，各部分可以独立训练和消融，可解释性强。
- **基准构建**：贡献了一个可复现的真实世界几何装配基准，包含扫描流程和多种类别，有助于社区公平比较。
- **泛化与鲁棒性**：展示了显著的跨形状、跨类别泛化能力，以及对输入形状不完美的容忍度。

### 8. 不足与局限
- **假设限制**：方法依赖“想象完整形状”作为输入，尽管实验表明对不完美输入有一定容忍度，但在真实应用中精确的完整形状预测本身仍是一个挑战。
- **真实世界评估不足**：真实世界实验缺乏定量指标和与其他方法的对比，难以评估实际装配成功率。
- **双手协同的固定顺序**：模型预测时先固定第一只手，再基于条件生成第二只手动作，可能限制了更灵活的协同策略。
- **物理属性忽略**：未考虑碎片的重量、摩擦等物理因素，在仿真和真实实验中仍存在因抓取不稳或滑动导致的失败。
- **多碎片装配较简单**：多碎片扩展只演示了三碎片，且采用贪婪选择最近碎片对的方式，复杂多碎片场景下的顺序规划仍待探索。

（完）
