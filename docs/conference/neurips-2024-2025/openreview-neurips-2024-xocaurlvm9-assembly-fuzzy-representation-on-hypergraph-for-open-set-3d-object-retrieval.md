---
title: Assembly Fuzzy Representation on Hypergraph for Open-Set 3D Object Retrieval
title_zh: 基于超图的装配模糊表示用于开放集三维物体检索
authors: "Yang Xu, Yifan Feng, Jun Zhang, Jun-Hai Yong, Yue Gao"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=xOCAURlVM9"
tags: ["query:part-aware"]
score: 6.0
evidence: 利用部件装配关系进行三维物体检索，用超图建模装配模糊表示。
tldr: 针对开放集三维物体检索缺乏标签的挑战，提出基于超图的装配模糊表示框架HARF。该方法自下而上通过部件装配建模，利用超图同构卷积和装配嵌入实现几何-语义一致性。实验表明在开放集检索任务中有效，为部件装配表示提供了新思路。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-xocaurlvm9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1430, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xocaurlvm9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xocaurlvm9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 870, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xocaurlvm9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xocaurlvm9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1422, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xocaurlvm9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1336, \"height\": 692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xocaurlvm9/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 636, \"height\": 696, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-xocaurlvm9/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 630, \"height\": 695, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-xocaurlvm9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 797, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xocaurlvm9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xocaurlvm9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1456, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xocaurlvm9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1444, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xocaurlvm9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xocaurlvm9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 177, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xocaurlvm9/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 667, \"height\": 183, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-xocaurlvm9/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 812, \"height\": 385, \"label\": \"Table\"}]"
motivation: 开放集三维物体检索缺乏标签，而部件形状跨类别共享特性未被利用。
method: 提出基于超图的装配模糊表示(HARF)框架，包含超图同构卷积和装配嵌入模块。
result: 在开放集三维物体检索中利用部件装配表示取得优越性能。
conclusion: 部件级装配表示有效捕捉三维物体形状，提升开放集检索能力。
---

## Abstract
The lack of object-level labels presents a significant challenge for 3D object retrieval in the open-set environment. However, part-level shapes of objects often share commonalities across categories but remain underexploited in existing retrieval methods. In this paper, we introduce the Hypergraph-Based Assembly Fuzzy Representation (HARF) framework, which navigates the intricacies of open-set 3D object retrieval through a bottom-up lens of Part Assembly. To tackle the challenge of assembly isomorphism and unification, we propose the Hypergraph Isomorphism Convolution (HIConv) for smoothing and adopt the Isomorphic Assembly Embedding (IAE) module to generate assembly embeddings with geometric-semantic consistency. To address the challenge of open-set category generalization, our method employs high-order correlations and fuzzy representation to mitigate distribution skew through the Structure Fuzzy Reconstruction (SFR) module, by constructing a leveraged hypergraph based on local certainty and global uncertainty correlations. We construct three open-set retrieval datasets for 3D objects with part-level annotations: OP-SHNP, OP-INTRA, and OP-COSEG. Extensive experiments and ablation studies on these three benchmarks show our method outperforms current state-of-the-art methods.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **核心问题**：在开放集（open-set）环境下，三维物体检索面临训练时未见过的物体类别，缺乏完整的对象级标签，导致传统闭集方法泛化能力差。
- **整体含义**：本文探索了一种“自底向上”的部件装配视角，利用物体零部件（part-level shapes）跨类别共享的特性，通过部件装配表示提升开放集三维物体检索性能。提出基于超图的装配模糊表示（HAFR）框架，旨在解决：
  - 零部件特征在装配成物体表示时的同构与统一难题；
  - 开放集场景下类别分布偏移（distribution skew）带来的泛化困难。

## 2. 方法论

### 2.1 核心思想
- 将三维物体视为若干局部的语义部件的装配组合（例如汽车的轮子、车门、车顶等），利用部件级别特征构建对物体整体语义的表示。
- 通过超图建模部件之间局部与全局的高阶相关性，并结合模糊重构使表示适应开放集环境。

### 2.2 关键技术细节

#### 2.2.1 同构装配嵌入（Isomorphic Assembly Embedding, IAE）
- **输入**：每个物体多个部件的基特征（通过点云部件分割网络 PointNet 提取的部件平均点特征）。
- **超图同构卷积（HIConv）**：
  - 构建装配超图：顶点 = 部件特征，超边 = 同一物体的所有部件。
  - 使用式(4)进行平滑，消除输入顺序及重复部件导致的几何/语义不一致，得到同构嵌入。
- **装配自编码器**：将每个部件的同构嵌入压缩到统一隐空间，并通过聚合函数（如平均）得到整个物体的装配嵌入。
- **损失函数**：
  - 装配损失 \(L_{as}\)：拉近同一物体不同部件的统一嵌入距离。
  - 跨部件损失 \(L_{xp}\)：促进不同部件编码器-解码器之间的交叉重构，增强部件间泛化。
  - 总损失 \(L_{IAE} = \alpha L_{as} + (1-\alpha) L_{xp}\)。

#### 2.2.2 结构化模糊重构（Structured Fuzzy Reconstruction, SFR）
- **杠杆超图（Leverage Hypergraph）构建**：
  - 顶点 = 物体装配嵌入。
  - 局部确定性超边：以已知类别分组。
  - 全局不确定性超边：KNN 最近邻。
- **超图卷积传播**：利用式(8)进行信息传播，使已知类别特征隐式指导未知类别。
- **记忆银行（Memory Bank）**：
  - 存储大量均匀分布的模糊锚点。
  - 计算传播嵌入与记忆锚点的激活分数，加权组合得到模糊嵌入，缓解开放集分布偏移。
- **损失函数**：
  - 交叉熵损失 \(L_{ce}\)：约束模糊嵌入的分类能力。
  - 模糊重构损失 \(L_{fz}\)：传播嵌入与模糊嵌入的L2距离。
  - 总损失 \(L_{SFR} = \beta L_{fz} + (1-\beta) L_{ce}\)。

### 2.3 算法流程
1. 从点云分割网络获取部件基特征。
2. 通过 HIConv 和装配自编码器生成装配嵌入（IAE 阶段）。
3. 构建杠杆超图进行传播，再利用记忆银行进行模糊重构，得到最终用于检索的模糊嵌入（SFR 阶段）。
4. 检索时基于模糊嵌入的欧氏距离进行相似性匹配。

## 3. 实验设计

- **数据集**：自建三个开放集三维物体检索基准：OP-SHNP（基于 ShapeNetPart）、OP-INTRA（基于 IntrA）、OP-COSEG（基于 COSEG）。每个数据集将类别分为已知类别（训练集）和未知类别（测试集），并包含部件分割标注。
- **对比方法**：当前最佳的闭集三维物体检索方法（MMJN, TCL, SDML, MMSAE）和开放集学习方法（PROSER, HGM²R），均改造多模态融合模块为多部件融合，以适配装配输入。
- **评估指标**：mAP, NDCG, ANMRR, PR 曲线。
- **实现细节**：部件基特征由 PointNet 提取，使用排名前4的部件。IAE 训练40 epoch (lr=0.1)，SFR 训练30 epoch (lr=0.001)。超参：\(\alpha=0.5, \beta=0.9\)。

## 4. 资源与算力

- **算力描述**：文中提到实验在 Tesla V100-32G GPU 和 Intel Xeon Silver 4210 CPU 上进行，但未给出具体训练时长或 GPU 数量。

## 5. 实验数量与充分性

- **主要对比实验**：在三个数据集上与6种已有方法进行对比，提供了完整的定量指标（表2）与 PR 曲线（图4）。
- **消融实验**（表3与图5）：
  - 替换/移除 HIConv（换为 GIN 或 MLP）；
  - 移除装配损失或跨部件损失；
  - 移除杠杆超图（仅剩 HGNN 图）；
  - 将 SFR 的超图替换为 MLP 或 GCN；
  - 验证完整组合 IAE+SFR 的效果。
- **充分性与客观性**：实验覆盖多个数据集、多个对比方法以及细致的消融研究，定量和定性分析全面，具有客观性和公平性。作者也提供了嵌入空间的可视化（t-SNE）。

## 6. 主要结论与发现

- 提出的 HAFR 框架在三个基准上均大幅超越现有最优方法，证明了部件装配表示在开放集检索中的有效性。
- 超图同构卷积（HIConv）和装配损失能有效保证几何-语义一致性，提升嵌入质量。
- 基于杠杆超图与记忆银行的模糊重构能有效缓解分布偏移，增强对未知类别的泛化。
- 即使在训练类别极少的情况下（如 OP-INTRA），方法仍能显著改进检索表现，显示对分类器性能依赖度低。

## 7. 优点

- **新颖的视角**：从部件装配的角度解决开放集三维物体检索，区别于传统全局特征方法。
- **有效的技术组件**：
  - HIConv 利用超图建模部件间同构关系，解决了部件顺序和重复带来的不一致性。
  - 杠杆超图巧妙结合局部确定性（按类分组）和全局不确定性（KNN），为开放集传播提供结构引导。
  - 记忆银行模糊重构思路清晰，实验表明能显著提升泛化能力。
- **实验扎实**：自建标准数据集、与多种前沿方法对比、详尽的消融实验和可视化，论证充分。

## 8. 不足与局限

- **部件数量固定**：方法假设每个物体使用固定数量（前4个）的部件，不能自适应处理不同零件数的物体，限制了对真实多变三维模型的适用性；文中亦指出此为未来工作方向。
- **依赖预分割**：需要部件分割标注，实际应用中可能限制方法的通用性。
- **算力细节缺失**：只提及 GPU 型号，未报告具体训练时间和能耗，难以评估实际成本。
- **数据集规模偏小**：尽管构建了三个数据集，但 OP-INTRA 和 OP-COSEG 训练样本量较少（100～200+），可能影响结论普适性。

（完）
