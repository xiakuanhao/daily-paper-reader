---
title: "AutoPartGen: Autoregressive 3D Part Generation and Discovery"
title_zh: AutoPartGen：自回归三维部件生成与发现
authors: "Minghao Chen, Jianyuan Wang, Roman Shapovalov, Tom Monnier, Hyunyoung Jung, Dilin Wang, Rakesh Ranjan, Iro Laina, Andrea Vedaldi"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=ljJGBcpn7q"
tags: ["query:part-aware"]
score: 10.0
evidence: 以自回归方式生成由3D部件组成的物体
tldr: AutoPartGen提出了一种自回归生成模型，能够基于图像、部件掩码或现有3D物体输入，逐部件预测并合成完整的3D对象。该方法利用3DShape2VecSet潜在空间的组合特性，有效支持部件感知的生成任务。实验表明，该模型在部件级3D重建和生成方面具有显著优势，为构建可编辑、可解释的3D模型提供了新思路。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ljjgbcpn7q/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 994, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ljjgbcpn7q/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ljjgbcpn7q/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 656, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ljjgbcpn7q/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1452, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ljjgbcpn7q/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1449, \"height\": 309, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ljjgbcpn7q/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1440, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ljjgbcpn7q/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ljjgbcpn7q/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 188, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ljjgbcpn7q/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1439, \"height\": 1195, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ljjgbcpn7q/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 714, \"height\": 239, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ljjgbcpn7q/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1387, \"height\": 1844, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ljjgbcpn7q/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1415, \"height\": 1064, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ljjgbcpn7q/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1323, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ljjgbcpn7q/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 893, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ljjgbcpn7q/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1153, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ljjgbcpn7q/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1527, \"height\": 278, \"label\": \"Table\"}]"
motivation: 现有3D生成模型往往将物体视为整体，缺乏对部件结构的显式建模，限制了可编辑性和可解释性。
method: 基于3DShape2VecSet潜在表示，以自回归方式逐个生成物体部件，并利用图像、掩码或3D输入进行条件控制。
result: 模型能够从多种输入生成由独立部件构成的3D物体，并在组合性重建任务中表现优异。
conclusion: AutoPartGen实现了部件级3D生成，为后续的编辑、装配和交互应用奠定了基础。
---

## Abstract
We introduce AutoPartGen, a model that generates objects composed of 3D parts in an autoregressive manner.
This model can take as input an image of an object,  2D masks of the object's parts, or an existing 3D object, and generate a corresponding compositional 3D reconstruction.
Our approach builds upon 3DShape2VecSet, a recent latent 3D representation with powerful geometric expressiveness.
We observe that this latent space exhibits strong compositional properties, making it particularly well-suited for part-based generation tasks.
Specifically, AutoPartGen generates object parts autoregressively, predicting one part at a time while conditioning on previously generated parts and additional inputs, such as 2D images, masks, or 3D objects.
This process continues until the model decides that all parts have been generated, thus determining automatically the type and number of parts.
The resulting parts can be seamlessly assembled into coherent objects or scenes without requiring additional optimization.
We evaluate both the overall 3D generation capabilities and the part-level generation quality of AutoPartGen, demonstrating that it achieves state-of-the-art performance in 3D part generation.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的详细中文总结。

### **1. 论文的核心问题与整体含义**

*   **核心问题**：当前许多3D生成模型将物体或场景视为单一的、不可分割的整体（如外壳），忽略了其内部的组合结构。这限制了后续对3D模型进行更细粒度的推理、编辑和操控（如动画、更换部件、交互等）。
*   **研究动机**：为了解决上述问题，本文旨在生成具有明确**组合结构**的3D物体，即将物体分解为有意义的、独立的3D部件。
*   **整体含义**：论文提出了`AutoPartGen`，一个能够以**自回归**方式直接生成由3D部件组成的物体的模型。该模型支持从图像、2D部件掩码或现有3D物体等多种输入模态出发，完成“部件级”的3D重建与生成，从而推动可编辑、可解释的3D内容创建。

### **2. 论文提出的方法论**

*   **核心思想**：
    *   **组合性观察**：首次发现并利用`3DShape2VecSet`这一潜在3D表示空间的**组合特性**，即两个潜在向量的拼接可以解码为对应两个表面区域的并集。
    *   **自回归部件生成**：将部件生成问题建模为一个序列预测问题，模型逐个生成部件，并且每个新部件的生成都以前面已生成的部件为条件，确保部件间的协调性。

*   **关键技术细节**：
    *   **潜在3D空间**：采用`3DShape2VecSet`作为基础表示。一个3D物体`x`被编码为一个由`M`个标记(token)组成的潜在向量序列`z`，解码器可根据`z`查询任意3D点的有符号距离函数(SDF)。
    *   **自回归生成流程**：
        1.  模型从给定的证据`y`（如整体物体的编码`z̃`或图像`I`）开始。
        2.  在第`k`步，模型基于两个条件生成第`k`个部件的潜在码`z^(k)`：
            *   **整体上下文**：目标物体的全局信息（如`z̃` 或图像`I`）。
            *   **历史部件**：已生成的所有前序部件的聚合表示 `z^(1,...,k-1)`。聚合方式通常为“重新编码”，即将已生成的部件解码、合并、再编码为一个固定长度的潜在码。
        3.  部件生成由**潜在扩散模型**实现，它在噪声逐步去除的过程中预测流速度。
        4.  该过程持续进行，直到模型输出一个特殊的`[EoT]`（生成结束）标记，从而自动决定部件的数量。
    *   **多模态条件控制**：该模型是一个统一框架，可通过调整输入`y`来处理三种场景：
        *   **对象到部件**：`y` = 目标3D对象本身。
        *   **图像到部件**：`y` = 目标物体的单张图像。
        *   **掩码到部件**：`y` = 物体图像 + 当前要生成部件的2D掩码`J^(k)`
    *   **条件生成分布**：模型学习的核心分布为 `p(z^(k) | z̃, z^(1,...,k-1), y)`。
    *   **推理时的无分类器引导(CFG)**：如公式(2)所示，通过调整`w_img`和`w_geom`两个权重，分别控制图像证据与几何先验对生成过程的引导强度。

### **3. 实验设计**

*   **数据集**：
    *   **训练集**：使用约30万个经过许可的3D资产（包含约200万个独立部件）进行模型训练。
    *   **评估集**：
        *   `PartObjaverse-Tiny`：用于定量的部件补全评估，包含人工标注的3D部件分割。
        *   `Google Scanned Objects (GSO)`：用于与`PartGen`进行定性比较。
*   **基准对比方法**：
    *   `PartGen`：基于多视图扩散模型的最新部件生成方法。
    *   `HoloPart`：一种从部分3D外壳和3D部件分割出发，进行非模态部件补全的方法。
*   **评估指标**：
    *   **交并比(IoU)**：在64³体素网格上计算。
    *   **倒角距离(CD)**：评估几何准确性。
    *   **F-Score**：距离阈值为0.02。
    *   分别报告了**部件级别**和**整体物体级别**的重建质量。
*   **评估场景**：在掩码到部件（mask-to-part）设定下，与需要3D部件掩码的`HoloPart`和需要多视图的`PartGen`进行对比。

### **4. 资源与算力**

*   **硬件配置**：训练主要使用NVIDIA H100 GPU。
*   **训练时长与规模**：
    *   基础扩散模型在128块H100 GPU上训练300个epochs。
    *   最终微调阶段，在256块H100 GPU上训练约30万步，总时间约**4天**。
    *   文中也提到了VAE（变分自编码器）的训练细节，是在128块H100 GPU上训练150个epochs。

### **5. 实验数量与充分性**

*   **实验数量**：
    1.  **主要结果对比**：与`PartGen`和`HoloPart`在`PartObjaverse-Tiny`数据集上进行了定量和定性的对比实验（表1，图7）。
    2.  **消融实验**：包括3组主要消融研究，旨在验证核心设计：
        *   **自回归机制的作用**：对比有无自回归条件(`z^(1,...,k-1)`) 的效果（表2，图8a）。
        *   **引导尺度的影响**：探究了不同图像引导权重`w_img`和几何引导权重`w_geom`组合的影响（表3，图8b）。
        *   **重新编码策略的效果**：对比了“重新编码”、直接“拼接”和“潜在融合器”三种聚合历史部件信息的方法（表4）。
*   **充分性与公平性**：
    *   **充分性**：实验设计较为全面，覆盖了与前沿方法的性能比较以及关键组件的消融，定量与定性结果并重，能够有力地支撑论文的主要论点。
    *   **公平性**：对比方法均为近期发表的SOTA工作，评估在同一基准数据集和标准指标下进行。在对比`PartGen`和`HoloPart`时，论文根据它们各自的输入要求适配了测试流程，确保了比较的公平性。

### **6. 论文的主要结论与发现**

*   `AutoPartGen`在所有关键指标（IoU、F-Score、CD）上均**超越了`PartGen`和`HoloPart`**，证明了其在部件补全和整体物体重建上的SOTA性能。
*   **自回归机制至关重要**：该机制能有效防止部件间的重叠和交叉，确保生成一个连贯的整体。
*   **统一的生成框架**：单个模型即可通过简单的输入条件切换，处理对象到部件、图像到部件和掩码到部件三种不同任务，具备很高的灵活性和实用性。
*   **应用广泛**：该方法能无缝扩展到小场景生成和大型城市场景生成，展示了其可扩展性。

### **7. 优点**

*   **新颖的组合性洞察**：首次发现并巧妙利用了`3DShape2VecSet`潜在空间的组合特性，为部件生成提供了优雅的技术基础。
*   **端到端的自回归框架**：模型能够自动决定部件数量和生成顺序，无需像先前工作那样依赖额外的模型来指定“下一个要生成哪个部件”，简化了整体流程。
*   **灵活的多模态输入**：单模型统一支持图像、2D掩码和3D对象等多种输入模态，为交互提供了细粒度控制。
*   **性能卓越**：在3D部件生成这一具体任务上，定量和定性结果均达到顶尖水平，尤其是在几何连贯性上表现突出。

### **8. 不足与局限**

*   **场景范围受限**：当前模型继承自潜在空间表示的限制，只能生成有边界的场景，无法处理无边界的世界生成。
*   **部件粒度不可控**：除了通过提供2D掩码的方式外，在自动生成（对象到部件、图像到部件）时，用户无法显式控制部件分解的颗粒度（如分解为粗粒度大部件还是细粒度小部件）。
*   **训练数据偏差**：模型的部件生成偏好完全由训练数据决定，存在继承数据偏差的风险。文中也指出了在存在成对相同部件时，模型可能一次性生成多个部件等失败案例。
*   **计算资源消耗大**：模型的训练需要大量的GPU资源（数百块H100），训练成本较高，这可能限制了其更广泛的复现和应用。

（完）
