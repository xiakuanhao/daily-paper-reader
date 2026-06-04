---
title: "MV2Cyl: Reconstructing 3D Extrusion Cylinders from Multi-View Images"
title_zh: MV2Cyl：从多视角图像重建3D挤出圆柱体
authors: "Eunji Hong, Nguyen Minh Hieu, Mikaela Angelina Uy, Minhyuk Sung"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=jDF2ZXI8AX"
tags: ["query:part-aware"]
score: 7.0
evidence: 从多视角图像将3D形状重建为挤出圆柱体组合
tldr: MV2Cyl提出一种从多视角图像重建3D几何为草图挤出CAD模型的方法，提取挤出圆柱体作为几何基元。该方法利用2D CNN从图像中提取挤出表面信息，并结合外显约束解决遮挡和分割挑战，实现了高质量的挤出圆柱体重建，为CAD逆向工程和3D建模提供新途径。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1454, \"height\": 769, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1448, \"height\": 671, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1423, \"height\": 222, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1455, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 958, \"height\": 639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1422, \"height\": 861, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 728, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1453, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1444, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1441, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1401, \"height\": 1925, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1430, \"height\": 646, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1442, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1137, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1438, \"height\": 774, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1016, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1419, \"height\": 1794, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1408, \"height\": 1798, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-jdf2zxi8ax/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1444, \"height\": 839, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-jdf2zxi8ax/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1453, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jdf2zxi8ax/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1454, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jdf2zxi8ax/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1447, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jdf2zxi8ax/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1454, \"height\": 450, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jdf2zxi8ax/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1454, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jdf2zxi8ax/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1455, \"height\": 286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jdf2zxi8ax/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1454, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jdf2zxi8ax/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1463, \"height\": 1223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jdf2zxi8ax/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jdf2zxi8ax/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1436, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-jdf2zxi8ax/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1455, \"height\": 243, \"label\": \"Table\"}]"
motivation: 从多视角图像重建挤出圆柱体CAD模型存在遮挡与分割困难。
method: 提出MV2Cyl，利用2D CNN提取挤出表面信息，协同外显约束重建挤出圆柱体。
result: 在合成与真实数据上优于基线，准确重建挤出圆柱体CAD模型。
conclusion: MV2Cyl为基于多视图的零件级CAD重建提供了有效方案。
---

## Abstract
We present MV2Cyl, a novel method for reconstructing 3D from 2D multi-view images, not merely as a field or raw geometry but as a sketch-extrude CAD. Extracting extrusion cylinders from raw 3D geometry has been extensively researched in computer vision, while the processing of 3D data through neural networks has remained a bottleneck. Since 3D scans are generally accompanied by multi-view images, leveraging 2D convolutional neural networks allows these images to be exploited as a rich source for extracting extrusion cylinder information. However, we observe that extracting only the surface information of the extrudes and utilizing it results in suboptimal outcomes due to the challenges in the occlusion and surface segmentation. By synergizing with the extracted base curve information, we achieve the optimal reconstruction result with the best accuracy in 2D sketch and extrude parameter estimation. Our experiments, comparing our method with previous work that takes a raw 3D point cloud as input, demonstrate the effectiveness of our approach by taking advantage of multi-view images.

---

## 论文详细总结（自动生成）

# MV2Cyl：从多视角图像重建3D挤出圆柱体——论文深度分析总结

## 1. 核心问题与整体含义
- **研究背景**：大多数日常人造物体由计算机辅助设计（CAD）创建。将3D扫描等原始几何数据恢复为结构化CAD表示，对制造和形状编辑至关重要。“草图-挤出”（Sketch-Extrude）是最通用且最常见的CAD范式，由2D闭合草图沿挤出轴拉伸而成，形成挤出圆柱体。
- **现有痛点**：从原始几何中提取挤出圆柱体虽已被广泛研究（如Point2Cyl），但3D骨干网络的分割性能有限，且依赖高质量3D点云。3D数据通常伴随多视角2D图像，而2D CNN性能显著优于3D网络。
- **核心问题**：如何仅从多视角RGB图像中重建3D形状为一系列挤出圆柱体，无需任何原始3D几何输入，并克服遮挡、光照歧义等挑战。
- **整体含义**：MV2Cyl提出一种全新的框架，利用2D图像分割先验与神经场融合，实现从多视图图像到CAD模型的端到端逆向工程，超越了现有依赖于精确3D几何的方法。

## 2. 方法论
### 2.1 核心思想
- **双路2D先验学习**：分别训练两个U-Net分割网络，从单张图像提取**表面信息**（实例分割、Start/End/Barrel面标签）和**曲线信息**（实例分割、Start/End曲线标签）。利用2D CNN的强表征能力弥补3D分割的不足。
- **三维场融合**：将多视图的2D分割结果，通过可微体积渲染优化为一致的3D密度场和语义场，分别对应表面和曲线。
- **参数协同估计**：从曲线场恢复精确的2D草图，从表面场恢复可靠的挤出轴、高度和中心，解决单一模态的局限性。

### 2.2 关键技术细节
- **2D表面分割网络 \( M_{surface} \)**：输入RGB，输出实例标签 \( P_{surface} \) 和 Start/End/Barrel 标签 \( Q_{surface} \)。使用交叉熵损失，用匈牙利匹配解决排列歧义。
- **2D曲线分割网络 \( M_{curve} \)**：输入RGB，输出实例标签 \( P_{curve} \) 和 Start/End 标签 \( Q_{curve} \)。由于曲线像素极度稀疏，结合焦点损失和Dice损失处理类别不平衡。
- **密度场 \( \mathcal{F} \)**：
  - 对表面和曲线分别学习标量密度场，通过可学习sigmoid函数转换为不透明度 \(\sigma\)。
  - 采用体积渲染积分得到每条光线的期望密度 \(\hat{E}(r)\)。
  - 使用自适应L2损失与稀疏性正则化项训练，平衡前景/背景像素权重。
- **语义场 \( \mathcal{A} \)**：
  - 在密度场基础上分支MLP，预测实例和Start/End等语义。
  - 同样用体积渲染得到渲染语义，与2D先验网络预测的伪标签进行交叉熵损失，训练中用匈牙利匹配跨视图对齐标签。
- **三维场实现**：基于TensoRF，对每个形状独立优化1500次迭代，约5分钟/形状（单块RTX 3090）。
- **逆向工程步骤**：
  1. **挤出轴 \( \mathbf{n} \) 估计**：对表面基面点进行RANSAC平面拟合，法线即为轴；若表面基面缺失则用曲线点替代。
  2. **2D草图 \( \tilde{\mathbf{S}} \) 估计**：将同实例曲线点投影至垂直轴的平面，使用IGR优化隐式距离场，提取零等值面得到草图轮廓。
  3. **挤出高度 \( h \) 估计**：计算同一实例的Start和End曲线中心点在轴上的投影距离；若某端面被遮挡，改用表面桶身点计算。
  4. **中心 \( \mathbf{c} \) 估计**：取该实例所有曲线点3D坐标均值，或用表面桶身点估算。

### 2.3 流程图概述（文字描述）
多视图图像 → 2D表面分割 + 2D曲线分割 → 分别优化表面密度/语义场与曲线密度/语义场 → 从场中提取带标签点云 → 综合表面与曲线点云估计 \( \mathbf{n}, \mathbf{c}, h, \tilde{\mathbf{S}}, s \) → 重建挤出圆柱体。

## 3. 实验设计
- **数据集**：
  - **Fusion360**：包含3,921个训练形状，798个测试形状（遵循Point2Cyl划分）。渲染50个视角的400×400无纹理图像，并提供真实的曲线/表面分割标签。
  - **DeepCAD**：包含约34,909个训练形状，1,950个测试形状，与上类似处理。
- **评价指标**：
  - 挤出轴误差（E.A., 度）、挤出中心误差（E.C.）、挤出高度误差（E.H.，L1距离）、每圆柱体拟合损失（Fit Cyl.）、全局拟合损失（Fit Glob.）。
  - 还补充了Chamfer距离评估重建质量。
- **对比方法**：
  - **Point2Cyl**：以精确3D点云为输入的有监督基线。
  - **NeuS2 + Point2Cyl**：先由多视图图像用NeuS2重建表面网格，再采样点云送入Point2Cyl，模拟直接连用多视图重建+CAD参数估计的可能。
  - **SECAD-Net**：无监督的挤出圆柱体重建方法（输入为3D体素）。
  - **Curve + Point2Cyl**：在输入点云中额外加入曲线点标签的变体。
  - 自身消融：仅用表面、仅用曲线、联合U-Net等。

## 4. 资源与算力
- **2D分割网络训练**：
  - Fusion360：U-Net训练3 epoch，表面模型316分钟、曲线模型307分钟；DeepCAD表面模型381分钟、曲线模型20.8小时（1 epoch），均在**单块NVIDIA RTX A6000** GPU上完成。
- **三维场优化**：
  - 每个形状独立训练1500迭代，约**5分钟**，使用**单块NVIDIA RTX 3090** GPU。
- **推理时间**：未明确报告总推理时间，但三维场优化是主要开销，每个形状约5分钟。
- **总体算力**：论文未汇总总 GPU 时，但给出了各组件训练时长，提供了可复现的参考。

## 5. 实验数量与充分性
- **主要对比实验**：
  - 在两个公开数据集上对 Point2Cyl、NeuS2+Point2Cyl、SECAD-Net、Curve+Point2Cyl等多个基线进行定量比较（6张表格）。
  - 定性对比展示多组重建结果。
- **消融实验**：
  - 仅表面 vs 仅曲线 vs 联合使用（附表A2），验证双模态协同的必要性。
  - 合并 U-Net 与分开 U-Net 对比（附表A3）。
  - 实例数量变化影响（附表A4）。
  - 输入视图数量变化（50, 25, 15, 10）（附表A5）。
  - 曲线分割图线宽变化（2.5, 5, 7.5 像素）（附表A6）。
- **扩展实验**：
  - 真实物体 3D 打印实物拍摄重建（演示 5 个样例）。
  - 与 SECAD-Net 额外定量对比（附表A8）。
  - 与 Curve+Point2Cyl 对比（附表A10）。
  - 2D 分割与 3D 分割精度对比（表A11）。
  - Chamfer距离评估整体形状质量（表A12）。
- **充分性与公平性**：
  - 实验设计较全面，涵盖主流数据集、多种基线、多维度消融。对比对象均基于官方代码或合理实现，指标与先前工作一致，具有说服力。
  - **不足**：未提供多次运行的标准差/置信区间，缺乏统计显著性检验；训练/测试拆分同Point2Cyl，但未说明随机种子固定等细节；未见超参数敏感度全量分析。

## 6. 主要结论与发现
- MV2Cyl 仅从多视角2D图像即可高精度重建挤出圆柱体，超越所有依赖精确3D几何的方法。
- 关键创新在于联合表面与曲线信息：曲线提供精确草图轮廓和抗遮挡能力，表面提供可靠的挤出轴和中心估算，二者协同显著提升重建质量。
- 2D CNN 的强先验有效弥补了3D神经网络分割能力不足的瓶颈。
- 方法对视图数量减少（如10张）有一定鲁棒性，对曲线线宽等超参数不敏感。

## 7. 优点
- **纯2D输入**：无需3D传感器或点云，拓宽了应用场景（如手机拍照）。
- **性能优异**：评价指标全面领先基于精确几何的Point2Cyl，甚至仅用2D图像就实现更好结果。
- **思路新颖**：首次将“2D曲线/表面分割+神经场优化+CAD参数协同估计”用于挤出圆柱体重建，填补了从图像直接到CAD元件的技术空白。
- **实验详实**：包含合成与真实数据验证，多角度消融分析支撑方法设计合理性。
- **实际可行性**：在3D打印实物上展示了 domain gap 下的重建能力，证明了实用性。

## 8. 不足与局限
- **布尔运算缺失**：MV2Cyl 未显式预测圆柱体之间的布尔（交集/差集）操作，仅提供了一个穷举搜索的后处理方案，但未完全解决该问题。
- **纹理干扰**：训练数据为无纹理渲染图，对真实纹理物体需依赖 Segment Anything 等大模型预处理（灰度化、背景去除），不能直接处理原始彩色纹理。
- **遮挡敏感**：当圆柱体一端完全被其他部件遮挡时，2D分割模型无法检测，导致该实例重建失败。
- **最小实例数限制**：预设最大8个实例，且单实例形状占比较高，对于更复杂组合可能受限。
- **计算开销**：每个形状仍需独立优化5分钟，难以实时应用。
- **实验局限**：未提供统计误差条，缺乏多运行稳定性证据；未分析网络初始化或相机位姿噪声的影响；真实场景只在少量物体上验证，泛化性仍需更多测试。

（完）
