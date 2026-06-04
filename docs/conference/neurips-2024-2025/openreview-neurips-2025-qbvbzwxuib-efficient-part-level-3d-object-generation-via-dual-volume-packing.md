---
title: Efficient Part-level 3D Object Generation via Dual Volume Packing
title_zh: 高效部件级三维物体生成：基于双体积打包
authors: "Jiaxiang Tang, Ruijie Lu, Max Li, Zekun Hao, Xuan Li, Fangyin Wei, Shuran Song, Gang Zeng, Ming-Yu Liu, Tsung-Yi Lin"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=qbVbZWxUib"
tags: ["query:part-aware"]
score: 10.0
evidence: 从单张图像端到端生成任意数量语义部件的三维物体。
tldr: 现有三维生成方法多生成融合网格，难以编辑独立部件。本文提出双体积打包框架，从单张图像端到端生成具有任意数量完整且语义明确部件的三维物体。实验表明方法能生成可装配的优质部件，支持编辑与操控，为部件级三维内容创建提供了新途径。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbvbzwxuib/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1441, \"height\": 1020, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbvbzwxuib/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbvbzwxuib/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1415, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbvbzwxuib/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1430, \"height\": 1034, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbvbzwxuib/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1440, \"height\": 1181, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbvbzwxuib/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1413, \"height\": 297, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbvbzwxuib/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1412, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbvbzwxuib/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1445, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbvbzwxuib/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1429, \"height\": 1423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-qbvbzwxuib/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1424, \"height\": 557, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-qbvbzwxuib/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1414, \"height\": 324, \"label\": \"Table\"}]"
motivation: 现有三维生成方法将物体部件融合，限制了独立编辑与操控。
method: 提出端到端框架，通过双体积打包策略组织所有部件，生成完整且可装配的语义部件。
result: 从单张图像生成具有任意数量语义部件的高质量三维物体。
conclusion: 实现了高效部件级三维生成，支持部件编辑与操控。
---

## Abstract
Recent progress in 3D object generation has greatly improved both the quality and efficiency.
However, most existing methods generate a single mesh with all parts fused together, which limits the ability to edit or manipulate individual parts.
A key challenge is that different objects may have a varying number of parts.
To address this, we propose a new end-to-end framework for part-level 3D object generation.
Given a single input image, our method generates high-quality 3D objects with an arbitrary number of complete and semantically meaningful parts.
We introduce a dual volume packing strategy that organizes all parts into two complementary volumes, allowing for the creation of complete and interleaved parts that assemble into the final object.
Experiments show that our model achieves better quality, diversity, and generalization than previous image-based part-level generation methods.
Our project page is at \url{https://research.nvidia.com/labs/dir/partpacker/}.

---

## 论文详细总结（自动生成）

好的，这是根据您提供的论文内容生成的结构化中文总结。

### 1. 论文的核心问题与整体含义

*   **研究动机与背景**：近年来，三维物体生成虽然在质量和效率上取得了巨大进步，但绝大多数模型都生成一个所有部件融合在一起的单一网格。这种“融合”的表示方式严重限制了后续对物体独立部件进行编辑、操控或关节驱动的能力，而这些能力在游戏开发、机器人仿真等下游应用中至关重要。
*   **核心问题**：实现部件级三维生成主要有两大挑战：1）不同物体包含的部件数量是未知且可变的，这与许多需要固定长度输入/输出的主流生成模型不兼容。2）现有的解决方案（如分割-补全流水线）不仅依赖可能引入误差的外部二维分割先验模型，而且需要逐个部件顺序处理，推理效率低下。
*   **整体含义**：本文旨在提出一种**端到端**的框架，能够从**单张图像**直接生成由**任意数量**、**完整**且**语义上有意义**的独立部件组成的三维物体，从而为可编辑和结构化的三维内容创建铺平道路。

### 2. 论文提出的方法论

论文的核心思想是通过分析部件间的接触关系，将复杂的部件打包问题简化为一个固定输出（两个体积）的生成问题。

*   **核心思想：双体积打包**
    *   **关键洞察**：部件难以分离的根本原因在于部件间存在接触。如果部件互不接触，它们在提取出的网格中自然属于不同的连通分量，很容易被隔离。
    *   **策略**：将尽可能多的互不接触的部件打包到同一个体积内。由于许多真实物体的部件邻接图具有简单的二分图结构，理论上使用两种颜色即可对图进行着色，使得相邻部件分属不同颜色。因此，可以将所有部件分配到**两个互补的体积**中，每个体积内部的部件均不相邻（接触）。
*   **关键技术细节**
    1.  **部件邻接图与二分图提取**：
        *   构建图 `G = (V, E)`，其中顶点 `V` 代表部件，边 `E` 代表部件间的接触关系。
        *   采用碰撞检测并轻微膨胀部件来构建边。接触深度作为边的权重 `w(e)`。
        *   对于非二分图，通过启发式算法贪心地收缩奇数环上权重最大的边（即合并部件），直至图中不存在奇数环，从而将其转换为二分图。
    2.  **部件级数据整理**：
        *   从GLB文件的场景图中提取部件标注，若无场景图则以连通分量作为替代。并采用修复边界环、合并微小/重叠组件等规则来弥补数据噪声。
        *   对非水密部件进行缝合修复，以减少几何失真和训练时符号距离函数值分布不平衡的问题。
        *   过滤掉打包后两个体积占用率（occupancy）极度不均衡的样本，以保证训练稳定性。
    3.  **双潜在变量生成模型**：
        *   **VAE模型**：采用双交叉注意力编码器和自注意力解码器，将两个打包后的体积压缩为一对潜在代码。
        *   **流模型**：基于矫正流框架，使用堆叠的注意力层**同时**对两个潜在代码进行去噪。两个潜在代码在通道维度被串联，并加入一个可学习的部件嵌入向量以区分彼此，允许信息交换。
        *   **条件编码**：使用DINOv2作为图像编码器提取输入图像的特征，通过交叉注意力机制注入流模型。

### 3. 实验设计

*   **数据集与场景**：主要采用Objaverse-XL数据集中的`Trellis500k`子集，经过部件提取、修复和过滤后，最终使用约**25.4万**个网格进行训练。测试集为从多元化领域整理的**40张图像**。
*   **对比基准方法**：
    *   **三维物体生成质量对比**：与**TripoSG**和**Hi3DGen**进行定性对比。
    *   **部件级三维生成对比**：与**HoloPart**进行定性对比。该基线需先将TripoSG生成的融合网格用PartField进行分割，再进行部件补全。
    *   **定量评估**：与**Hunyuan3D-2**、**Hi3DGen**、**TripoSG**进行定量比较。采用**ULIP**、**ULIP-2**和**Uni3D**作为评价指标，计算生成的点云与输入图像之间的余弦相似度。

### 4. 资源与算力

论文在附录的实现细节中明确提到了训练所需的计算资源：
*   **GPU型号**：NVIDIA A100 GPU。
*   **训练阶段与资源消耗**：
    *   **基础VAE预训练**：使用64块A100 GPU，耗时约一周。
    *   **流模型渐进式训练**：最多使用256块A100 GPU，耗时约两周。
    *   **部件级VAE微调**：未明确说明资源。
    *   **部件级流模型微调**：在最大潜在尺寸（总维度8192）上进行，使用256块A100 GPU，耗时约两周。

### 5. 实验数量与充分性

论文设计了较为全面和充分的实验来验证其核心主张：
*   **定性对比**：针对三维生成质量和部件级生成效果，分别与最新的主流方法进行了视觉对比，结果展示了本文方法在结构完整性和部件合理性上的优势。
*   **定量对比**：在标准测试集上，通过多个指标（ULIP, ULIP-2, Uni3D）对三维生成质量进行了客观评估，结果显示本文方法具有竞争力。同时还对比了部件生成的推理速度，指出本方法（约30秒）相比HoloPart（数分钟）具有巨大加速优势。
*   **消融研究**：通过消融实验验证了三个关键设计的必要性：1）部件级VAE微调对减少伪影的作用；2）数据清洗对提升分割质量和多样性的作用；3）部件嵌入向量对防止生成重复或重叠部件的作用。
*   **多样性展示**：展示了在不同随机种子下，从同一输入图像生成多样化的部件组合的能力。
*   **局限性讨论**：诚实地分析了方法存在的局限，如部件粒度不可控和双体积打包的表达能力限制。

总体而言，实验设计**客观、公平**，从质量、效率、设计有效性等多个维度进行了验证，并充分讨论了失败案例，具有说服力。

### 6. 论文的主要结论与发现

*   提出的端到端框架能够成功地从单张图像直接生成具有任意数量、完整且语义明确部件的三维物体。
*   双体积打包策略是处理可变数量部件的一种高效且有效的方法，它将复杂的图着色问题转化为固定输出长度的生成任务，很好地适配了现有的潜在去噪模型。
*   相比依赖外部先验和顺序处理的现有部件生成方法，本方法在生成质量、结构一致性、多样性和推理效率（固定约30秒）上都展现出了显著优势。

### 7. 优点

*   **方法创新性**：首创性地提出双体积打包策略来解决部件级生成的核心难题，思路新颖且有效。
*   **流程简洁高效**：实现了单图端到端部件生成，彻底避免了对外部二维分割模型的依赖，简化了处理流水线，并大幅提升了推理速度，无论部件多少，时间固定。
*   **生成质量高**：生成的部件几何完整、表面平滑、可与整体装配，且支持通过不同初始噪声产生多样化的划分方式。

### 8. 不足与局限

*   **实验覆盖**：
    *   定量评估指标（ULIP, Uni3D）主要衡量形状与图像的整体一致性，**缺乏直接评估部件划分准确性、部件完整性的定量指标**。
    *   对比的基线方法较少，特别是针对部件级生成，仅与HoloPart进行了主要对比。
*   **方法局限**：
    *   **部件粒度不可控**：部件划分完全由数据驱动且结果多样但不可预测，用户无法精确控制部件的合并或拆分。
    *   **双体积打包的表达上限**：对于三个部件之间互相接触的复杂情形，二分图无法表示，强制打包会引入误差，导致不理想的生成结果。
    *   **稳定性不足**：由于训练数据标注不一致和缺乏控制，在不同随机种子下，部件的划分结果可能不稳定，出现错误合并或分割。
*   **应用限制**：论文提到的这些局限性直接限制了模型在需要精细部件编辑和关节驱动等高要求应用场景下的表现。

（完）
