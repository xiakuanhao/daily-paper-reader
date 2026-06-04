---
title: General Articulated Objects Manipulation in Real Images via Part-Aware Diffusion Process
title_zh: 基于部件感知扩散过程的真实图像铰接物体通用操作
authors: "Zhou FANG, Yong-Lu Li, Lixin Yang, Cewu Lu"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=WRd9LCbvxN"
tags: ["query:part-aware"]
score: 4.0
evidence: 基于部件感知扩散模型的真实图像中铰接物体操作
tldr: 该论文提出了部件感知扩散模型，用于真实图像中铰接物体的编辑操作。通过抽象3D模型和动态特征图，实现外观迁移和新部件生成。尽管专注于图像层面，但其部件感知思路对三维生成任务具有一定的参考价值。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1411, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1436, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1397, \"height\": 611, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1419, \"height\": 828, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1432, \"height\": 186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1420, \"height\": 985, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1429, \"height\": 194, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1420, \"height\": 300, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1273, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1372, \"height\": 1213, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1400, \"height\": 851, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1390, \"height\": 1031, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1424, \"height\": 1106, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1412, \"height\": 246, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-wrd9lcbvxn/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1411, \"height\": 291, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-wrd9lcbvxn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 635, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wrd9lcbvxn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 756, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wrd9lcbvxn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1452, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-wrd9lcbvxn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1045, \"height\": 329, \"label\": \"Table\"}]"
motivation: 现有方法在真实图像中编辑铰接物体时易产生伪影或失败。
method: 开发抽象3D模型表示铰接物体，并结合部件感知扩散模型和动态特征图进行编辑。
result: 在图像中实现更真实的铰接物体操作，减少伪影。
conclusion: 该方法在二维编辑中融入了三维部件感知，但其核心并非三维生成。
---

## Abstract
Articulated object manipulation in real images is a fundamental step in computer and robotic vision tasks. Recently, several image editing methods based on diffusion models have been proposed to manipulate articulated objects according to text prompts. However, these methods often generate weird artifacts or even fail in real images. To this end, we introduce the Part-Aware Diffusion Model to approach the manipulation of articulated objects in real images. First, we develop Abstract 3D Models to represent and manipulate articulated objects efficiently. Then we propose dynamic feature maps to transfer the appearance of objects from input images to edited ones, meanwhile generating the novel-appearing parts reasonably. Extensive experiments are provided to illustrate the advanced manipulation capabilities of our method concerning state-of-the-art editing works. Additionally, we verify our method on 3D articulated object understanding for
embodied robot scenarios and the promising results prove that our method supports this task strongly. The project page is https://mvig-rhos.com/pa_diffusion.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将以 Markdown 形式，对《General Articulated Objects Manipulation in Real Images via Part-Aware Diffusion Process》这篇论文进行结构化、深入、客观的总结。

### **1. 论文的核心问题与整体含义**

*   **研究动机**：在真实图像中编辑铰接物体（如打开笔记本电脑、拉开抽屉）是计算机视觉和机器人领域的基础任务。现有的基于扩散模型的图像编辑方法在处理此类任务时，常常在物体发生旋转、形变或出现新视角时产生奇怪的伪影甚至失败，尤其是在真实图像上表现不佳。
*   **整体目标**：论文旨在提出一种新颖、鲁棒的**部件感知扩散模型 (Part-Aware Diffusion Model, PA-Diffusion)**，专门用于在真实图像中高质量地操控铰接物体，解决现有方法的伪影和失败问题。
*   **应用价值**：该方法不仅可用于高质量的图像编辑，还能通过生成大规模合成数据，有力支持下游的具身智能（机器人）任务，如三维铰接物体理解。

### **2. 论文提出的方法论**

论文的核心思想是**利用抽象的3D模型来引导2D扩散模型的编辑过程**，实现部件级别的感知与操控。

*   **核心思想**：通过一个“抽象3D模型”为铰接物体提供一个轻量级但高效的结构先验，并设计“动态特征图”机制，确保在编辑过程中精确迁移“已见部件”的外观，并合理生成“新现部件”的外观。
*   **关键技术细节**：
    1.  **抽象3D模型 (Abstract 3D Model)**：
        *   构建一个**原型基元库 (Primitive Prototype Library)**，包含如平面、立方体、盒子等基本三维形状。
        *   不依赖精确的CAD模型，而是通过组合基本原型来快速表征常见铰接物体（如笔记本电脑用两个平面表示）。这使其能轻松覆盖新物体类别，无需额外训练。
        *   利用大分割模型（Grounded SAM）获取部件级掩膜，检测极端角点，并通过PnP（Perspective-n-Points）算法对齐2D图像与3D空间中的相机视角。
    2.  **3D空间中的多样化操控**：
        *   在3D空间（Blender）中，可通过文本指令（如"将笔记本电脑打开120°"）或直接的人际交互来高效操控抽象3D模型。
        *   操控完成后，从3D软件导出**操控后的部件级掩膜**，并将物体结构解耦为“已见部件”和“新现部件”。
    3.  **动态特征图 (Dynamic Feature Maps)**：
        *   **操控后的反转噪声图**：利用DDIM Inversion得到初始噪声图。根据3D操控计算出的变换函数，将初始噪声图“已见部件”的特征变换到编辑图像中的正确位置，生成操控后的噪声图。
        *   **合成式激活图与图像**：在去噪过程中，模型以批次处理初始、随机和操控后的三种噪声图。通过掩膜分别生成并合并前景（已见部件）和背景的激活图，实现特征的精确保留。同时，从随机噪声分支生成“新现部件”，并将其合成到最终图像中，使新部件的生成更为合理。
    4.  **评分函数 (Score Functions)**：
        *   **纹理一致性评分损失 (TCSL)**：通过计算引导分支（原图）和生成分支（编辑图）特征图之间的余弦相似度损失，解决因变换噪声图引起的图像模糊问题，确保物体和背景外观的一致性。
        *   **风格一致性评分损失 (SCSL)**：通过计算随机分支和引导分支特征图之和的L1损失，约束“新现部件”（如柜子内部）的生成风格与原物体保持一致。这两种损失作为额外的能量函数，在每一步去噪迭代中通过分类器引导来修正去噪方向。

### **3. 实验设计**

*   **数据集与场景**：
    *   论文自建了一个包含**存储柜、笔记本电脑、微波炉、垃圾桶、冰箱、抽屉**等6个常见铰接物体类别的测试集，包含660张真实图像，覆盖了旋转和平移两种关节类型。
    *   针对3D铰接物体理解的下游任务，生成了一个包含660个序列（每个序列含4步开启过程）的合成数据集。
*   **对比基准 (Benchmark)**：
    *   在图像编辑任务中，与四种基于扩散模型的SOTA方法进行了比较：**Imagic (文本驱动)、DragDiffusion (点拖拽)、MasaCtrl (特征共享，配合T2I Adapter) 和 Image Sculpting (2D-3D-2D)**。
*   **对比方法**：
    *   定性对比：展示不同方法在同一编辑任务下的视觉效果。
    *   定量对比：使用**FID（Fréchet Inception Distance）** 分数评估编辑图像的真实性和与原图的关联性。在3D理解任务中，使用**BBox IoU, 旋转轴/平移轴EA-score, 表面法线角度误差**等指标进行评估。

### **4. 资源与算力**

*   **算力资源**：论文明确指出所有实验均运行在**单张NVIDIA A100 GPU**上。
*   **训练时长**：论文强调图像编辑过程**无需训练或微调模型**，因此没有提及模型训练时间，主要耗时在于生成过程，但未给出单张图像的编辑耗时。

### **5. 实验数量与充分性**

*   **实验组数**：
    1.  **多类型操控结果展示**：展示了移动、缩放、旋转、开启等基本操控，以及非刚体、非均匀形状物体的操控结果。
    2.  **定性对比实验**：与4种SOTA方法在多个物体类别上进行可视化比较。
    3.  **定量对比实验**：在自建数据集的6个类别上与2种典型方法（Imagic, MasaCtrl）比较FID分数。
    4.  **消融研究**：定性验证TCSL（去模糊）和SCSL（风格一致性）两个损失项的作用，并定量对比它们的FID分数。
    5.  **下游任务验证**：通过两组实验（不同训练集规模对比、与真实数据集混合训练）验证生成数据对3D铰接物体理解任务的有效性。
*   **充分性与客观性**：实验设计相对全面，覆盖了定性、定量、消融和迁移任务。对比方法选择具有代表性，包含了文本驱动、点交互、特征迁移等不同技术路线的SOTA方法。评价指标（FID）是图像编辑领域的常用指标。消融实验清晰地展示了所提模块的有效性。下游任务验证增强了方法的实用性说服力。整体上看，实验是充分且客观公平的。

### **6. 论文的主要结论与发现**

*   PA-Diffusion模型在真实图像中操控铰接物体时，能生成无伪影、高保真度的编辑结果，显著优于现有的SOTA方法。
*   通过抽象3D模型，该方法能高效、灵活地支持多种操控，并能轻松扩展到新的物体类别，无需为每个新类重新训练模型。
*   所提出的动态特征图机制和一致性评分损失，成功解决了外观精确保留、新部件合理生成及模糊等问题。
*   该方法可作为一种有效的数据增强工具，通过生成高质量合成数据，显著提升下游的3D铰接物体理解等机器人视觉任务的性能。

### **7. 优点**

*   **创新性**：提出了“抽象3D模型”与“部件感知扩散”相结合的新颖框架，巧妙地在2D编辑中引入了轻量级的3D结构先验。
*   **高效且灵活**：无需精确CAD模型，无需额外训练，能快速覆盖新物体类别并支持多种操控方式（文本、交互）。
*   **部件感知能力**：首次在扩散编辑中明确区分并分别处理“已见部件”和“新现部件”，这是解决铰接物体编辑难题的关键。
*   **实用性强**：不仅图像编辑效果好，还能直接赋能下游的具身智能任务，展示了其作为基础工具的巨大潜力。

### **8. 不足与局限**

*   **对输入图像质量敏感**：由于基于DDIM Inversion，模糊或低分辨率的输入图像会导致编辑效果严重退化。
*   **处理大形变能力有限**：当物体发生剧烈形变或非均匀形变时，变换噪声图会严重破坏数据分布，导致方法失效。
*   **场景覆盖不足**：目前的实验主要集中在相对简单的背景和有限种类的常见刚性铰接物体，对复杂光照、大面积遮挡、以及复杂铰接物体（如多关节机械臂）的泛化能力未得到充分验证。
*   **非刚体和流体局限**：论文明确指出，处理可变形物体和流体等仍是该方法的挑战，当前框架难以胜任。

（完）
