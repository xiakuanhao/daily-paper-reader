---
title: Learning CAD Modeling Sequences via Projection and Part Awareness
title_zh: 通过投影与部件感知学习CAD建模序列
authors: "Yang Liu, Daxuan Ren, Yijie Ding, Jianmin Zheng, Fang Deng"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=0rGJzKTqMs"
tags: ["query:part-aware"]
score: 9.0
evidence: 将点云分解为零件感知的潜在表示，用于CAD建模序列重建
tldr: PartCAD提出从点云直接重建CAD建模序列的方法，通过投影引导的零件感知推理将点云分解为可解释的潜在表示，并生成草图-拉伸参数。该框架弥合了几何信号与语义理解，生成了可编辑的CAD模型，为逆向工程和设计重用提供了新途径。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1397, \"height\": 795, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1420, \"height\": 799, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 709, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 715, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1393, \"height\": 702, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 724, \"height\": 145, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1388, \"height\": 718, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1380, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1363, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1407, \"height\": 590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1386, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1410, \"height\": 802, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1402, \"height\": 734, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1402, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1433, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1409, \"height\": 659, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1422, \"height\": 240, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0rgjzktqms/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1375, \"height\": 594, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-0rgjzktqms/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1404, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0rgjzktqms/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 725, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0rgjzktqms/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 727, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0rgjzktqms/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1405, \"height\": 447, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0rgjzktqms/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1430, \"height\": 1075, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0rgjzktqms/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 562, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0rgjzktqms/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1082, \"height\": 206, \"label\": \"Table\"}]"
motivation: 从点云重建可编辑CAD模型极具挑战，需同时捕捉几何细节与设计意图。
method: 采用自回归分解点云为零件感知特征，投影引导提供设计意图线索，非自回归解码生成参数。
result: 在CAD序列生成上，PartCAD实现了高效、结构连贯的草图-拉伸参数合成。
conclusion: 该方法使点云到可编辑CAD模型的自动转换成为可能，促进设计自动化。
---

## Abstract
This paper presents PartCAD, a novel framework for reconstructing CAD modeling sequences directly from point clouds by projection-guided, part-aware geometry reasoning. It consists of (1) an autoregressive approach that decomposes point clouds into part-aware latent representations, serving as interpretable anchors for CAD generation; (2) a projection guidance module that provides explicit cues about underlying design intent via triplane projections; and (3) a non-autoregressive decoder to generate sketch-extrusion parameters in a single forward pass, enabling efficient and structurally coherent CAD instruction synthesis. By bridging geometric signals and semantic understanding, PartCAD tackles the challenge of reconstructing editable CAD models—capturing underlying design processes—from 3D point clouds. Extensive experiments show that PartCAD significantly outperforms existing methods for CAD instruction generation in both accuracy and robustness. The work sheds light on part-driven reconstruction of interpretable CAD models, opening new avenues in reverse engineering and CAD automation.

---

## 论文详细总结（自动生成）

## 论文核心问题与整体含义
- 该论文聚焦于从**非结构化点云**中自动重建 **CAD 建模序列**（即一系列草图、拉伸等参数化指令），而非仅恢复最终的三维几何形状。
- 背景与动机：
  - 传统 CAD 表示（网格、B-Rep、CSG）仅捕获最终几何，而**建模序列**携带设计意图、编辑性、版本控制等高层次语义。
  - 从扫描点云人工恢复可编辑的 CAD 模型极其耗时且需要专家经验，自动将点云转化为可执行的建模指令将极大推动逆向工程、再设计和 CAD 自动化。
  - 现有方法存在不足：全自回归模型易累积误差，非自回归模型难以捕捉层次依赖；普遍缺乏将底层几何特征与高层建模指令对齐的机制，且未能利用 CAD 设计过程中自然的部件化结构。

## 方法论
### 核心思想
提出 **PartCAD**，一种**半自回归框架**：
1. 先将输入点云**自回归分解**为一系列部件感知的潜在表示（每个潜在表示对应一个建模步骤），从而捕捉设计意图和流程结构。
2. 再通过**三平面投影**提供明确的几何线索（设计意图在不同视图中的表现）。
3. 最后使用**非自回归解码器**一次性生成完整的草图-拉伸参数，兼具效率与结构一致性。

### 关键技术细节
- **自回归隐式部件分解**  
  - 用 3D EdgeConv 编码器从点云提取全局特征 \( f^{pc3d}_X \)。  
  - 部件解码器以全局特征为条件，自回归生成部件潜在向量序列 \( \{z_n\}_{n=1}^N \)，每个 \( z_n \) 对应一个有效建模操作。  
  - 引入**部件判别器**（二分类）监督每个潜在向量的有效性，以控制序列终止。

- **三平面投影引导与自适应投影**  
  - 从 \( z_n \) 预测旋转参数，将点云旋转至规范视图，分别投影到 XY、XZ、YZ 平面。  
  - 提出**自适应投影策略**：先用法线滤波（阈值 \( \delta_{\text{normal}} \)）剔除与投影方向不一致的表面点，再用自适应网格采样（间距 \( \delta_{\text{grid}} \)）防止点过度聚集、覆盖稀疏区域。  
  - 设计**层次化 KNN 聚合核**：逐层筛选邻居——先按 2D 欧氏距离取 3k 候选，再按径向距离保留 2k，最后按表面法线相似性保留最终 k 个，从而在投影平面上保持几何语义一致性。用 EdgeConv 层提取投影特征 \( f^{pc2d}_n = \{f^{xy}_n, f^{xz}_n, f^{yz}_n\} \)。

- **非自回归 CAD 指令生成**  
  - 草图解码器使用 XY 投影特征 \( f^{xy}_n \)，拉伸解码器使用拼接的侧面特征 \( [f^{xz}_n; f^{yz}_n] \)。  
  - 通过**交叉注意力**将 \( z_n \) 与点级投影特征融合（局部聚合），再通过**自注意力**与全局池化特征交互（全局上下文）。  
  - 两个 Transformer 解码层输出后，分别经线性层预测离散化的草图参数 \( c^{\text{skt}}_n \) 和拉伸参数 \( c^{\text{ext}}_n \)。

- **多目标优化**  
  \[
  \mathcal{L}_{\text{total}} = \lambda_{\text{skt}} \mathcal{L}_{\text{skt}} + \lambda_{\text{ext}} \mathcal{L}_{\text{ext}} + \lambda_{\text{rot}} \mathcal{L}_{\text{rot}} + \lambda_{\text{val}} \mathcal{L}_{\text{val}}
  \]
  包含草图参数交叉熵、拉伸参数交叉熵、旋转角度交叉熵、部件有效性二值交叉熵。

## 实验设计
### 数据集与评估基准
- **主数据集**：DeepCAD，经几何去重后 ~140k 训练 / ~7k 验证&测试样本。点云通过均匀采样 2,048 个点生成，参数统一量化至 8 位。
- **跨数据集泛化**：Fusion 360 Gallery，用于评估分布外性能。
- **实扫验证**：使用 SIMSCAN-42 激光扫描仪扫描 3D 打印模型，直接输入真实点云测试。

### 评价指标
- **倒角距离（CD）**：均值和中位数，衡量生成形状与真实形状的几何差异（×10³）。
- **F1 分数**：分别计算草图参数（线、弧、圆）和拉伸参数的指令级一致性，采用匈牙利算法匹配。
- **无效率（IR）**：无法生成有效几何的预测比例。

### 对比方法
- **序列生成类**：DeepCAD、DeepCAD*（点云直接解码变体）、TransCAD。
- **基元拟合类**（仅比较几何和有效性）：Point2Cyl、ExtrudeNet、SECAD、HNC-CAD。

## 资源与算力
- **硬件**：8 块 NVIDIA A100-PCIE-40GB GPU。
- **训练配置**：batch size = 32，共训练 200 epoch。
- **训练耗时**：约 18 小时。
- **优化器**：AdamW，初始学习率 1e-4，配合 ExponentialLR 调度器。

## 实验数量与充分性
实验设计全面、对比系统：
- **主实验**：DeepCAD 数据集上的定量结果（表 1 对比序列方法，表 2 对比基元方法）。
- **跨数据集实验**：在 Fusion 360 Gallery 上评估泛化性（表 3）。
- **消融实验**：逐一移除部件分解、投影引导、自适应投影、层次 KNN、局部特征聚合、全局特征交互等模块，共 6 组变体（表 4），所有变体均报告 F1、CD 和 IR。
- **鲁棒性实验**：注入不同强度高斯噪声、随机移除不同比例点云，评估模型对输入质量的鲁棒性。
- **统计稳定性**：对 DeepCAD 和 Fusion 360 分别重复推理 10 次，报告标准差。
- **可视化**：提供大量定性结果，包括复杂草图、复杂拓扑、逐步解码、失败案例等。
实验设置公平，所有基线均使用官方实现或严格按照论文重新实现，并采用相同的数据预处理和评估协议。

## 主要结论与发现
- PartCAD 在所有指标上均**大幅超越**现有序列生成方法，在几何精度（CD）和指令有效性（IR）上优势尤为显著，IR 降至 0.91%。
- 相较于基元拟合方法，PartCAD 能以更高有效率和更低 CD 恢复出**可编辑的参数化历史**。
- 在跨数据集实验中，PartCAD 的 CD 较序列方法降低一个数量级以上，且 IR 仅 1.31%。
- 消融实验证实：部件分解、投影引导、自适应投影及层次 KNN 每个模块的缺失均会导致性能显著下降，证明各组件不可或缺。
- 模型对噪声、部分缺失和真实扫描均表现出较强鲁棒性。

## 优点
- **半自回归设计**：平衡了自回归的序列一致性和非自回归的并行效率，通过部件潜在表示将结构信息与几何生成解耦。
- **部件感知先验**：隐式部件分解自然地与 CAD 建模流程对齐，增强可解释性和设计意图的捕获。
- **投影引导机制**：利用三平面投影和自适应采样，为解码提供了与设计视图对应的精确几何线索，缓解了直接从点云生成指令的歧义性。
- **层次 KNN 聚合**：针对投影特性设计的邻居选择策略，有效保留了三维几何的语义一致性。
- **实验完备**：涵盖多个数据集、丰富基线、多维指标、消融和鲁棒性分析，结论可信度高。

## 不足与局限
- **数据集限制**：训练数据多样性和规模仍制约性能，尤其对长尾分布的复杂模型或未见过的操作类型（如旋转、放样）泛化能力有限。
- **几何到指令的多义性**：同一形状可有多种有效建模路径，模型当前采用确定性解码，无法处理这种“一对多”映射。
- **复杂形状挑战**：当模型包含极复杂的草图轮廓、深层次或非结构化零件时，局部几何细节（如位移、缺失部件、不完全曲线）仍可能出错。
- **操作类型单一**：仅支持草图-拉伸操作，限制了设计创造力和对更自由曲面/实体操作的支持。
- **量化精度损失**：将连续参数离散化为 8 位整数，可能导致精细结构的几何精度下降。

（完）
