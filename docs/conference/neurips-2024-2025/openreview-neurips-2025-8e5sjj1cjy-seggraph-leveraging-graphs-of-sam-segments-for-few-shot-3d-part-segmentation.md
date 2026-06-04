---
title: "SegGraph: Leveraging Graphs of SAM Segments for Few-Shot 3D Part Segmentation"
title_zh: SegGraph：利用SAM片段图进行少样本三维部件分割
authors: "Yueyang Hu, Haiyong Jiang, Haoxuan Song, Jun Xiao, Hao Pan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=8e5SJJ1cjY"
tags: ["query:part-aware"]
score: 10.0
evidence: 利用SAM片段图的少样本三维部件分割
tldr: SegGraph提出了一种基于SAM片段图传播的少样本三维部件分割方法。通过显式建模片段间的重叠和相邻关系，有效融合2D基础模型的先验知识，改善了现有方法忽略几何结构导致的欠分割问题。实验表明，该方法能够产生更一致的部件标签，推动了低资源下的三维语义理解。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-8e5sjj1cjy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1459, \"height\": 487, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8e5sjj1cjy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1458, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8e5sjj1cjy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 664, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8e5sjj1cjy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 730, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8e5sjj1cjy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1462, \"height\": 786, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8e5sjj1cjy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1456, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8e5sjj1cjy/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1456, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-8e5sjj1cjy/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1458, \"height\": 193, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-8e5sjj1cjy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1448, \"height\": 529, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8e5sjj1cjy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1441, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8e5sjj1cjy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8e5sjj1cjy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 790, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8e5sjj1cjy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 647, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8e5sjj1cjy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 986, \"height\": 142, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-8e5sjj1cjy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 439, \"height\": 125, \"label\": \"Table\"}]"
motivation: 现有少样本3D部件分割方法未能有效利用SAM的高质量分组线索，导致欠分割和标签不一致。
method: 构建SAM片段图，通过建模片段间的重叠和邻接关系显式学习几何特征以用于图传播。
result: 取得了更一致的部件分割结果，性能优于此前方法。
conclusion: SegGraph通过图结构增强了2D到3D的知识迁移，显著提升了少样本部件分割的精度。
---

## Abstract
This work presents a novel framework for few-shot 3D part segmentation. Recent advances have demonstrated the significant potential of 2D foundation models for low-shot 3D part segmentation. However, it is still an open problem that how to effectively aggregate 2D knowledge from foundation models to 3D. Existing methods either ignore geometric structures for 3D feature learning or neglects the high-quality grouping clues from SAM, leading to under-segmentation and inconsistent part labels. We devise a novel SAM segment graph-based propagation method, named SegGraph, to explicitly learn geometric features encoded within SAM's segmentation masks. Our method encodes geometric features by modeling mutual overlap and adjacency between segments while preserving intra-segment semantic consistency. We construct a segment graph, conceptually similar to an atlas, where nodes represent segments and edges capture their spatial relationships (overlap/adjacency). Each node adaptively modulates 2D foundation model features, which are then propagated via a graph neural network to learn global geometric structures. To enforce intra-segment semantic consistency, we map segment features to 3D points with a novel view-direction-weighted fusion attenuating contributions from low-quality segments. Extensive experiments on PartNet-E demonstrate that our method outperforms all competing baselines by at least 6.9% mIoU. Further analysis reveals that SegGraph achieves particularly strong performance on small components and part boundaries, demonstrating its superior geometric understanding.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：如何在仅有少量标注样本的条件下，将2D基础模型（如SAM、DINOv2）的强大知识有效迁移至3D点云的部件级语义分割任务中。
- **现有方法的不足**：
  - **标签聚合方法**（如PartSLIP系列）仅将2D分割标签通过投票反投影到3D，完全忽略3D几何结构，导致欠分割与相邻点标签不一致。
  - **特征聚合与蒸馏方法**虽引入了3D特征学习，但采用KNN或超点降采样等方式，既难以编码复杂的几何模式，也未能充分利用SAM提供的高质量分组线索。
  - 通用流程中的下采样（如PartNet-E约100倍）会模糊边界点与小部件的特征。
- **核心动机**：利用SAM多视图分割结果构建一种图结构，显式建模片段之间的空间关系（重叠/相邻），在保持片内语义一致性的前提下，通过图神经网络传播2D基础模型特征，从而得到具有几何感知的3D部件分割。

---

### 2. 论文提出的方法论

核心思路是构建一个**SAM片段图（Segment Graph）**，将每个3D片段视作节点，片段之间的重叠与相邻关系作为边，通过图传播实现2D→3D的知识深度融合。

#### 2.1 3D点特征编码
- 将输入点云从预设的M个视点渲染为多视图RGB图像，并做遮挡剔除。
- 使用像DINOv2这样的视觉基础模型提取图像特征图，经双三次插值上采样至原图尺寸，再通过线性层降维（768→96）。
- 对每个3D点，将其在多个未遮挡视图下的投影特征取平均，得到初始点特征 \( F^p \)。

#### 2.2 片段生成
- 利用SAM对每张渲染图进行实例分割，并将同一视图内重叠的mask分解为互不重叠的过分割区域。
- 将所有投影落在同一2D mask内的3D点组成一个3D **片段（segment）**，片段集合记为 \( S \)。

#### 2.3 片段图构建与特征传播
- **片段编码**：对每个片段 \( S_i \)，计算其内部各点相对于片段质心的归一化位置 \( p_r^j \)：
  \[
  p_r^j = \frac{p_j - c_i}{\max_{k\in S_i} (p_k) - \min_{k\in S_i} (p_k)}
  \]
  将点法向与 \( p_r^j \) 拼接后经MLP得到局部几何特征 \( F^l_j \)，再通过 max pooling 得到初步片段特征，最后用注意力加权聚合点特征 \( F^p_j \) 得到片段特征 \( F^s \)。
- **图构建**：节点为各片段 \( S_i \)。
  - **重叠边 \( E_o \)**：不同视图的两个片段覆盖的3D点集交并比（mIoU）大于10%则连接。
  - **相邻边 \( E_a \)**：片段间几乎无重叠，但其最近点距离小于0.01（归一化空间）时连接。
  - 重叠与邻接边互斥。整张图类似于微分几何中的“图册（atlas）”，实现形状的几何一致映射。
- **图传播**：使用GATv2网络，将重叠关系和相邻关系各用独立的GATv2层处理，每层输出拼接后经MLP作为下一层节点特征。共使用三层GATv2。
- **视角质量感知的特征反池化**：将传播后的片段特征映射回各成员点。定义点 \( j \) 在片段 \( i \) 的视角质量权重：
  \[
  w_v^{ij} = \left| \mathbf{n}_j \cdot \frac{p_j - c_i}{\|p_j - c_i\|} \right|
  \]
  其中 \( c_i \) 为对应相机光心，\( \mathbf{n}_j \) 为点法向。该权重再通过可学习的MLP和softmax进行修正。最终3D点特征更新为：
  \[
  F^{p'}_i = F^{p}_i + \sum_{i \in S_j} w_v^{ij} \cdot F^s_j, \quad \hat{Y}_i = \text{MLP}(F^{p'}_i)
  \]
  使用交叉熵损失进行少样本训练。

---

### 3. 实验设计

#### 3.1 数据集与设置
- **PartNet-Ensemble（PartNet-E）**：1906个形状，45个类别，有RGB颜色。遵循[12]的数据划分，采用**8-shot**设定。评测指标为mIoU。
- **ShapeNetPart**：31963个形状，16个类别，无颜色，下采样至2048点并平滑。同样使用8-shot评测。

#### 3.2 对比方法
- **全监督模型**（作为参考）：PointNet++、SoftGroup、PointNext。这些方法在PartNet重叠类别的28K数据 + 少样本数据上训练。
- **标签聚合方法**：PartSLIP、PartSLIP++、PartSTAD、3-By-2（用*标记，直接引用原论文结果）。
- **蒸馏方法**：PartDistill（*）、PartField（零样本，提取特征后微调MLP适配少样本）。
- **少样本点云分类方法（用于ShapeNetPart）**：PointCLIP、PointCLIPv2，将文本嵌入替换为可训练的MLP分类器进行少样本学习。
- **本文的SegGraph**：主要使用DINOv2+SAM，另提供GLIP+SAM的版本以公平比较。

#### 3.3 主要实验结果
- **PartNet-E**：SegGraph（DINOv2+SAM）总体mIoU **72.8%**，比当前最佳PartDistill（65.9%）提升6.9%，在45类中的32类达到最高。GLIP+SAM版本也达到70.4%，显著高于其他GLIP方法。尤其在小部件（如按钮、把手）上，mIoU提升超过20个百分点（例如Door、Lamp等类别）。
- **ShapeNetPart**：SegGraph（CLIP+SAM）mIoU **62.6%**，比PointCLIPv2（57.0%）提升5.6%。

#### 3.4 消融实验
- 逐步验证各模块：基础基线（仅平均池化特征+MLP）65.2%；加入SAM片段 70.5%；进一步加入片段编码（SE）和视角质量加权（Eq.(2)）提升至71.0%；加入相邻边或重叠边分别提升至72.2%和72.3%；同时使用两类边达到**72.8%**。证明各组件均有贡献，且边关系建模尤其关键。
- 特征提取器鲁棒性：将DINOv2换成CLIP、Diffusion、GLIP、PartField等，在MLP header下性能较低，但全部使用SegGraph后性能均大幅提升（如GLIP：61.1→70.4；PartField：66.3→70.3），表明图传播结构具有通用增益。

#### 3.5 特征可视化与分析
- PCA降维可视化和跨形状特征相似度图表明，SegGraph学习到的3D特征具有清晰的部件可分性，且在不同形状的同类部件间具有一致性。
- 失败案例：USB类别中两个外观相似但空间分离的部件（接口）因DINOv2特征相似而被误分为同一类，说明对重复子结构存在混淆风险。

---

### 4. 资源与算力

- 所有运行时间在单块**NVIDIA V100 GPU**上测量（per shape）。
- 预处理阶段：64.92秒（SAM），若使用FastSAM可降至13.82秒，但精度轻微下降（72.8→70.9 mIoU）。
- 训练阶段：每shape一个epoch约2.25秒。
- 推理阶段：每shape 1.46秒（含DINOv2特征提取）。
- **未明确说明**：训练的总epoch数、batch size、总训练时长或使用的GPU数量（仅提及“single NVIDIA V100”）。虽然给出了单shape训练/推理时间，但无法推算完整实验的总算力消耗。

---

### 5. 实验数量与充分性

- **实验数量**：核心实验包含两个大型基准数据集（PartNet-E的45类和ShapeNetPart的16类）上的全面对比；至少10组消融实验（表4、表5、表6的不同配置）；与超过6种现有方法的比较；特征可视化与相似度分析；小部件单独分析；失败案例分析。
- **充分性与客观性**：
  - 对比方法涵盖监督、标签聚合、蒸馏等多种路线，且尽可能使用原作者代码或报告结果，并明确标注未复现的方法（*）。
  - 考虑到了不同基础模型（DINOv2, GLIP, CLIP等）的影响，提供公平比较。
  - 通过三次训练并报告均值和标准差（如总体72.8%±1.09%）来反映训练稳定性。
  - 消融实验逐步添加模块，严格分析每个设计的作用。
- 总体来看，实验设计较为充分、系统，对比客观，能支撑论文的核心结论。

---

### 6. 论文的主要结论与发现

- SegGraph通过将SAM多视图片段组织为图，并利用重叠和相邻关系进行特征传播，成功将2D基础模型的表征适配到3D几何域，大幅提升少样本3D部件分割的性能。
- 相比现有先进方法，在PartNet-E上取得至少6.9%的mIoU绝对提升，在小部件和边界区域的精度优势尤为突出。
- 所提出的图传播结构具有极强的可扩展性，更换不同2D/3D基础模型特征均能带来一致的性能增益。
- 视角质量感知的特征融合能有效抑制不良视图带来的劣质片段影响，进一步保证标签一致性。

---

### 7. 优点

- **新颖的结构化表示**：将SAM片段构建为图册（atlas-like graph），同时建模重叠与相邻关系，是对现有“视图池化”或“KNN传播”思路的本质升级。
- **保留高分辨率与几何细节**：直接基于片段（~1000个）而非大幅下采样点云，避免了小部件和边界信息的丢失。
- **视角质量意识**：设计基于法向与视线方向的权重机制，智能抑制低质量片段，提升特征融合的鲁棒性。
- **模型无关的通用性**：图传播模块能适配多种基础模型（DINOv2, CLIP, GLIP, PartField等），表现出优越的泛化能力。
- **计算效率**：推理阶段仅需1.46秒/形状，远快于PartSLIP++（5.83秒），适用于交互式应用。
- **详实的实验与分析**：覆盖两个主流数据集、多种基线、细致的消融和可视化，结论可信度高。

---

### 8. 不足与局限

- **无法处理遮挡与内部结构**：基于多视图渲染的特征聚合范式天然无法建模被遮挡或内部几何的部件。
- **分割尺度固定**：当前方法工作于单一分割粒度，缺乏对多尺度、层次化部件语义的支持，难以直接适应粗细粒度变化的任务。
- **对重复相似子部件敏感**：当不同部件外观高度相似但空间分离时（如USB的两个接口），DINOv2特征本身无法区分，图传播也难以纠正，易导致误分类。
- **算力细节不完全透明**：虽给出单shape的预处理/训练/推理耗时，但未说明完整训练所需的GPU总时长或超参（如总epoch、batch size），对复现总资源的估计仍有缺失。
- **依赖于SAM分割质量**：在渲染质量差（如ShapeNetPart的稀疏点云）或视角极端时，SAM masks可能出现欠分割，进而影响片段图的构建与最终精度。
- **训练随机种子的影响**：虽然平均标准差仅1.09%，但在某些语义模糊的类别上性能波动较大（如Lamp标准差2.19%），表明模型对初始化仍有一定敏感性。

---

（完）
