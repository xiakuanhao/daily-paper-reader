---
title: 3D Geometric Shape Assembly via Efficient Point Cloud Matching
title_zh: 通过高效点云匹配实现3D几何形状装配
authors: "Nahyuk Lee, Juhong Min, Junha Lee, Seungwook Kim, Kanghee Lee, Jaesik Park, Minsu Cho"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=FYQIgQWH3d"
tags: ["query:part-aware"]
score: 10.0
evidence: 通过匹配零件配合面将几何形状装配成更大目标结构
tldr: 该论文针对将多个独立零件组合成完整目标结构的3D几何形状装配任务，提出一种基于代理匹配变换（PMT）的高效点云匹配框架PMTR。方法通过粗精两级匹配捕获零件配合面间的对应关系，在低计算开销下实现可靠装配。在Breaking Bad基准上验证了优越性能，为零件感知的3D模型构建提供了关键技术。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-fyqigqwh3d/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 740, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fyqigqwh3d/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1736, \"height\": 734, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fyqigqwh3d/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 821, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fyqigqwh3d/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1757, \"height\": 859, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fyqigqwh3d/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1774, \"height\": 1590, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fyqigqwh3d/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1767, \"height\": 1469, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-fyqigqwh3d/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1767, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fyqigqwh3d/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 850, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fyqigqwh3d/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 849, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fyqigqwh3d/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 857, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fyqigqwh3d/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 857, \"height\": 503, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fyqigqwh3d/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1757, \"height\": 859, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fyqigqwh3d/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1766, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fyqigqwh3d/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1765, \"height\": 357, \"label\": \"Table\"}]"
motivation: 解决3D零件装配中高效、准确的零件间匹配问题。
method: 提出Proxy Match Transform和PMTR框架，通过粗精两级点云匹配实现零件装配。
result: 在Breaking Bad数据集上性能显著优于现有方法，且计算高效。
conclusion: PMTR为3D几何装配提供了有效解决方案，推动了零件级3D建模的发展。
---

## Abstract
Learning to assemble geometric shapes into a larger target structure is a pivotal task in various practical applications. In this work, we tackle this problem by establishing local correspondences between point clouds of part shapes in both coarse- and fine-levels. To this end, we introduce Proxy Match Transform (PMT), an approximate high-order feature transform layer that enables reliable matching between mating surfaces of parts while incurring low costs in memory and compute. Building upon PMT, we introduce a new framework, dubbed Proxy Match TransformeR (PMTR), for the geometric assembly task. We evaluate the proposed PMTR on the large-scale 3D geometric shape assembly benchmark dataset of Breaking Bad and demonstrate its superior performance and efficiency compared to state-of-the-art methods. Project page: https://nahyuklee.github.io/pmtr

---

## 论文详细总结（自动生成）

## 论文核心问题与研究背景

- 论文研究 **3D 几何形状装配 (geometric shape assembly)** 任务：给定一组独立零件的点云，预测每个零件的 6D 位姿（旋转与平移），使它们精确拼合成一个完整的目标结构。
- 核心挑战在于：**准确识别零件的“配合表面”（mating surfaces）并建立零件间的局部对应关系**。这需要同时利用粗粒度的空间布局信息和细粒度的局部几何细节。
- 现有方法可分为两类：
  - **回归式方法**：将每个零件编码为全局特征，直接回归绝对位姿，但损失了局部几何信息，难以精确定位配合面。
  - **匹配式方法**：建立零件间的对应关系，然后求解相对位姿。常用高阶特征变换（如注意力、高维卷积）来滤除错误匹配并获取一致对应，但这类操作通常具有 **关于输入点数二次方的时间和空间复杂度**，难以直接应用于高分辨率点云。
- 因此，亟需一种既能有效捕捉零件间配合面局部对应、又具备低计算复杂度的高效匹配方法。

## 方法论：Proxy Match TransformeR (PMTR)

### 核心思想
- 提出 **Proxy Match Transform (PMT)** 层，一种**低复杂度的近似高阶特征变换**，能够在无需显式构建代价高昂的成对相关矩阵的情况下，利用共享的代理张量 (proxy tensor) 交换两个特征集之间的信息，从而以亚二次复杂度实现可靠的特征匹配。
- 基于 PMT 构建 **PMTR 框架**，通过**粗粒度匹配（定位配合表面）→ 细粒度匹配（精确对齐）** 的流程实现高效零件装配。

### 关键技术细节

- **PMT 层设计**：
  - 给定源特征 \(F_X\) 和目标特征 \(F_Y\)，PMT 不是直接计算 \(F_X F_Y^\top\)（复杂度 \(O(|X||Y|)\)），而是分别对两个特征独立地进行变换，通过一组共享的代理张量 \(P^{(h)} \in \mathbb{R}^{D_{\text{proxy}}\times D_{\text{emb}}}\) 传递信息，其中 \(D_{\text{proxy}} \ll |X|,|Y|\)。
  - 对于每个注意力头 \(h\)，PMT 对 \(F_X\) 的输出定义为：
    \[
    \text{PMT}(F_X) = \sum_{h} A^{(h)}_X \left(F_X P^{(h)\top} w^{(h)}_X \right),
    \]
    \(A^{(h)}_X\) 为局部注意力矩阵（每个点只关注其空间邻域内的点，避免二次方注意力），\(w^{(h)}_X\) 为可学习标量权重。对 \(F_Y\) 类似，但使用独立的参数。
  - 代理张量满足正交性和零矩阵约束：\(P^{(i)\top}P^{(j)} = I\) 当 \(i=j\)，否则为 \(0\)。**理论证明**（Theorem 1）：在此条件下，两个 PMT 输出的点积等价于一个标准的高阶卷积结果，即 \(\text{PMT}(F_X) \cdot \text{PMT}(F_Y)^\top \approx \text{Conv}(F_X, F_Y)\)，从而隐式实现了跨特征的信息整合。

- **PMTR 整体流程**：
  1. **特征提取**：使用 KPConv‑FPN 从两个零件点云中提取三对不同空间分辨率的特征对 \((F_{X_n}, F_{Y_n})_{n=1}^3\)，从粗到细。
  2. **粗匹配**：在最粗的特征上应用 PMT 层，得到精炼后的粗特征 \(F_{X_c}, F_{Y_c}\)。基于它们的点积计算粗相关性，并通过 top‑k 选择可靠匹配，定位配合表面所在的大致区域。
  3. **细匹配**：以串行方式在更精细的两对特征上分别应用 PMT 层，逐步得到细粒度特征 \(F_{X_f}, F_{Y_f}\)。利用点‑到‑节点分组将粗匹配映射到细特征，再用 Sinkhorn 最优运输层求出最终对应关系。
  4. **位姿预测**：根据最终对应关系计算两个零件间的相对旋转和平移 \(\{R|t\}\)。
  5. **训练目标**：使用重叠感知圆损失 \(L_{oc}\)（粗匹配）、点匹配损失 \(L_p\)（细匹配），加上正交性损失 \(L_{\text{orth}}\) 和零矩阵损失 \(L_{\text{zero}}\) 来约束代理张量。

## 实验设计

- **数据集**：
  - **Breaking Bad**：包含从 PartNet 和 Thingi10K 生成的超过 100 万个破碎物体，分为 everyday 和 artifact 两个子集。
  - 双零件装配实验选取仅含 2 个零件的样本；多零件装配实验则包含 2～20 个零件的所有样本。

- **评价指标**：
  - **相对位姿 RMSE**：旋转误差 RMSE(R) 和 平移误差 RMSE(T)（以最大零件为锚点计算相对位姿，避免绝对位姿对齐问题）。
  - **Chamfer Distance (CD)**：组装结果与真实装配之间的倒角距离。
  - **Correspondence Distance (CRD)**：作者新提出的指标，即装配结果与真实值之间的点云 Frobenius 范数，更能全面衡量结构对齐程度。
  - 多零件装配另附加 **Part Accuracy (PA)**：倒角距离或 CRD 低于阈值的零件比例。

- **对比方法**：
  - 回归式：Global, LSTM, DGL, NSM, Wu et al. (2023b)
  - 匹配式：GeoTransformer, Jigsaw

## 资源与算力

- **硬件**：实验均在一台配备 **Intel Xeon Gold 6342 CPU 和单块 NVIDIA GeForce RTX 3090 GPU** 的机器上完成。
- **实现框架**：PyTorch Lightning。
- **训练配置**：优化器 ADAM，学习率 1e‑3（GeoTransformer 基线降为 1e‑4），训练 150 个 epoch。双零件装配中每个零件表面均匀采样约 5000 点。粗、细匹配器各使用 2 层 PMT，注意力头数 \(N_h=4\)。

## 实验数量与充分性

- **主要对比实验**：
  - 双零件装配在 everyday 和 artifact 上的全面对比（表1）。
  - 多零件装配对比（表6），包含多个评估指标。
- **消融实验**：
  - 代理共享的影响（表2）：移除共享代理或使用非共享代理均导致性能明显下降。
  - 正交损失和零损失的作用（表3）：同时使用两项损失时性能最佳。
  - 细匹配器类型对比（表4）：PMT 在准确率和内存/效率上均优于线性、MLP、高维卷积 (HDC) 和 GeoTransformer（后两者因二次复杂度超出内存无法运行）。
  - 粗匹配器类型对比（表5）：PMT 作为细匹配器时，无论粗匹配采用何种层，均一致提升性能。
- **效率分析**（表7）：PMT 的 FLOPS、参数量和训练/推断内存均显著低于 GeoTransformer（~21.5× FLOPS 降低，~3.4× 参数减少），展示了亚二次复杂度的优势。
- 实验设计较为完整，对比公平，消融研究充分，且从准确率和效率两个维度进行了验证。

## 主要结论与发现

- PMTR 在双零件装配和多零件装配任务上**全面超越所有对比方法**，在旋转、平移、CD 和 CRD 指标上均取得最优结果。
- PMT 层能够在**极低的内存和计算开销下**有效逼近传统的高阶特征变换，使得在细粒度（高分辨率）点云上执行匹配成为可能。
- 代理张量确实扮演了信息交换的桥梁角色，可视化表明其与配合表面上的点高度相关。
- 正交和零损失对代理张量的约束是 PMT 近似高阶卷积的关键，去除会显著降低性能。

## 优点

- **技术创新**：提出具有理论保证的 PMT 层，用亚二次复杂度模拟高阶特征匹配，解决了细粒度装配中的计算瓶颈。
- **框架设计**：粗‑细两级匹配流程自然对应“定位配合面‑精确对齐”的装配逻辑，有效且直观。
- **评估全面**：引入 CRD 指标、使用相对位姿避免绝对位姿偏差、扩展至多零件场景，评估更公正、更具说服力。
- **效率优势显著**：与基于注意力或高维卷积的匹配器相比，FLOPS 和内存占用大幅降低，实用性更强。

## 不足与局限

- **极低重叠场景**：在零件间重叠面积极小时，对应关系的可靠性可能下降，方法鲁棒性或受影响。
- **训练依赖性**：需要大规模领域特定数据训练，泛化到全新物体类别或数据集可能需要额外微调。
- **应用范围有限**：目前仅在几何装配任务上验证，尚未在机器人操作、制造、文物修复等其他潜在应用领域进行测试。
- **相对位姿假设**：方法依赖于零件配对并提供配对对应，对于多零件全局一致性可能还需依赖位姿图优化（文中已采用变换平均，但仍可能累积误差）。

（完）
