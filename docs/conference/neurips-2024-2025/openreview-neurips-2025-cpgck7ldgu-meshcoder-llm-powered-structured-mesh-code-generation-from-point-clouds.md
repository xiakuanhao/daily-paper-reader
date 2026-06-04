---
title: "MeshCoder: LLM-Powered Structured Mesh Code Generation from Point Clouds"
title_zh: MeshCoder：基于LLM的从点云生成结构化网格代码
authors: "BingQuan Dai, Luo Li, Qihong Tang, Jie Wang, Xinyu Lian, Hao Xu, Minghan Qin, Xudong XU, Bo Dai, Haoqian Wang, Zhaoyang Lyu, Jiangmiao Pang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=cpgCK7LdgU"
tags: ["query:part-aware"]
score: 8.0
evidence: 将三维物体重建为具有不同语义部件的可编辑代码
tldr: MeshLLM提出了一种从点云重建三维物体为可编辑Blender Python脚本的框架。利用大规模对象-代码数据集，生成的代码显式分解为语义部件。这一方法不仅实现了复杂几何的精确重建，更通过程序化表示支持高级的部件编辑和生成任务。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 1124, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1382, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1368, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1418, \"height\": 898, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1427, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1435, \"height\": 709, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1423, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1419, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 667, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1396, \"height\": 496, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1367, \"height\": 278, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1409, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1441, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1433, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1440, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1433, \"height\": 465, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1451, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1416, \"height\": 1306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1424, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1283, \"height\": 752, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1318, \"height\": 1167, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1313, \"height\": 956, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1139, \"height\": 2197, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1437, \"height\": 971, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1430, \"height\": 679, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1450, \"height\": 787, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-cpgck7ldgu/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1425, \"height\": 805, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-cpgck7ldgu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cpgck7ldgu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 1762, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cpgck7ldgu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1421, \"height\": 1494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cpgck7ldgu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 652, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cpgck7ldgu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1054, \"height\": 337, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cpgck7ldgu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 958, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cpgck7ldgu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 867, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cpgck7ldgu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 915, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cpgck7ldgu/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1419, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-cpgck7ldgu/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 694, \"height\": 214, \"label\": \"Table\"}]"
motivation: 现有方法在将3D物体重建为可编辑程序时受领域特定语言和小数据集的限制。
method: 设计表达丰富的Blender Python API，构建部件分解的数据集，训练多模态LLM从点云生成代码。
result: 能够从点云重建出包含独立语义部件的复杂3D模型。
conclusion: 通过程序化部件分解，实现了三维重建和编辑的深度结合。
---

## Abstract
Reconstructing 3D objects into editable programs is pivotal for applications like reverse engineering and shape editing. However, existing methods often rely on limited domain-specific languages (DSLs) and small-scale datasets, restricting their ability to model complex geometries and structures. To address these challenges, we introduce MeshLLM, a novel framework that reconstructs complex 3D objects from point clouds into editable Blender Python scripts. We develop a comprehensive set of expressive Blender Python APIs capable of synthesizing intricate geometries. Leveraging these APIs, we construct a large-scale paired object-code dataset, where the code for each object is decomposed into distinct semantic parts. Subsequently, we train a multimodal large language model (LLM) that translates 3D point cloud into executable Blender Python scripts. Our approach not only achieves superior performance in shape-to-code reconstruction tasks but also facilitates intuitive geometric and topological editing through convenient code modifications. Furthermore, our code-based representation enhances the reasoning capabilities of LLMs in 3D shape understanding tasks. Together, these contributions establish MeshLLM as a powerful and flexible solution for programmatic 3D shape reconstruction and understanding.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将使用中文、以Markdown形式，对《MeshCoder: LLM-Powered Structured Mesh Code Generation from Point Clouds》这篇论文进行结构化、深入、客观的总结。

### **1. 论文核心问题与整体含义**

*   **核心问题**：现有的三维物体重建方法，特别是将3D形状重建为可编辑程序（如代码）的方法，面临两大瓶颈：
    1.  **表达能力受限**：依赖的领域特定语言通常只能描述简单几何体（如立方体、球体），难以复现真实世界中具有复杂几何和内部结构的物体。
    2.  **数据匮乏**：训练“从形状到代码”的模型需要大规模成对的<3D物体，对应代码>数据集，而此类数据极为稀缺。
*   **研究动机**：解决上述问题对于逆向工程、形状编辑和3D结构理解等应用至关重要。程序化表示（代码）是3D物体的高级抽象，可极大地提升可编辑性和可解释性。
*   **整体含义**：本文提出了一个名为 **MeshCoder** 的框架，旨在将复杂的3D物体从点云直接重建为结构化的、可执行的Blender Python脚本。这些脚本不仅是精确的几何重建，更将物体明确地分解为具有语义信息的独立部件，从而实现了高保真重建与直观代码编辑的深度结合。

### **2. 论文提出的方法论**

核心思想是构建一个强大的“点云到代码”的生成模型。为解决数据匮乏问题，论文提出了一套精妙的**分步数据构建流水线**，并结合强大的API设计，最终训练一个多模态大语言模型。

**关键技术细节与流程：**

1.  **设计表达性Blender Python API**：
    *   开发了一套远超简单基元的API，能构建复杂几何体。主要包括：
        *   **基元**：立方体、球体等基本形状，参数化位置、旋转、缩放。
        *   **平移**：将二维截面沿三维轨迹扫掠，形成复杂形状（如瓶体）。
        *   **桥接**：连接多个不同形状的二维截面生成连续几何体（类似CAD中的放样），克服了平移中截面必须垂直于切线且不能变形的限制。
        *   **布尔运算**：对基本形状进行并、交、差集运算，生成带孔或组合结构。
        *   **阵列**：沿一维曲线或二维平面重复实例化某一几何体，用于生重复模式（如百叶窗）。
    *   这些API以Blender Python脚本形式存在，其参数可控制几何形状、拓扑和分辨率。

2.  **构建大规模对象-代码数据集（三步走）**：
    *   **第一步：合成部件-代码数据集并训练“部件-代码”推理模型**。
        1.  **数据合成**：通过编写概率程序，随机采样上述API的函数及参数，生成了约**1000万**个单部件点云-代码对。
        2.  **模型训练**：训练一个包含“形状分词器”和“精调LLM”的模型`h`。形状分词器将点云编码为LLM可理解的固定长度Token序列，LLM再自回归地生成该部件的Blender代码。
    *   **第二步：组装部件为完整物体**。
        1.  **物体分解**：使用Infinigen-Indoor程序化生成框架，生成约41类、包含独立语义部件的完整3D物体数据集。
        2.  **部件推理**：对于物体的每个部件`q_i`，先将其归一化到单位立方体，用模型`h`推理其代码`y'_i`。
        3.  **代码还原与组装**：设计算法将`y'_i`中的位置、缩放、姿态参数还原为`q_i`的原始值，得到`y_i`。最后，按照自底向上、从左到右的空间规则，将所有部件代码`y_i`拼接，并添加语义注释（如物体名、部件名），形成完整物体的代码`y`。至此，构建出约**100万**对“物体-代码”数据集。

    *   **第三步：训练“物体-代码”推理模型（MeshCoder）**。
        *   **模型架构**：与步骤一中的模型结构相同。
        *   **训练策略**：用预训练好的“部件-代码”模型权重初始化，然后在构建好的100万“物体-代码”数据集上进行端到端精调。训练时采用随机旋转、缩放、点云密度变化和高斯噪声扰动等数据增强。

3.  **形状分词器详解**：
    *   **Triplane投影**：将点云分别投影到三个正交平面上，聚合特征得到三个特征图。
    *   **Token化**：将三个特征图分块并展平为一维序列，通过Transformer块进行编码。
    *   **信息压缩**：引入一组可学习的查询Token，通过交叉注意力机制从编码后的Triplane特征中聚合全局信息，最终得到固定长度`L`的形状Token序列`z`，其维度与LLM的词嵌入维度`D`对齐。

### **3. 实验设计**

*   **数据集**：
    *   **训练集**：自建的“合成部件数据集”（约1000万对）和基于Infinigen-Indoor修改扩展的“物体数据集”（约100万对，覆盖41个常见室内物体类别）。
    *   **测试集**：从上述数据集中按类别划分出的测试部分，同时也在非Infinigen数据（如用Trellis生成的Mesh）上测试了泛化能力。
*   **Benchmark & 基线方法**：
    *   **评估指标**：`L2 Chamfer Distance` (CD) 和 **体素 `IoU`** ( 分辨率 `32^3` )。
    *   **对比方法**：两个代表性的形状到代码方法 `Shape2Prog` 和 `PLAD`。
*   **实验场景**：
    *   **重建性能**：在41个类别上全面比较与基线的重建精度。
    *   **形状编辑**：展示通过修改代码参数实现的几何编辑（如改变桌子形状）和拓扑编辑（如调整网格分辨率）。
    *   **形状理解**：将MeshCoder生成的带注释代码输入GPT-4，测试其回答关于物体结构、部件数量和尺寸问题的能力，并与多视图图像输入进行对比。

### **4. 资源与算力**

*   **GPU 型号与数量**：均使用 **NVIDIA A100** GPU。
*   **训练细节**：
    *   **部件-代码模型**：在**64块** A100上训练，Batch Size为512。训练约**一周**。
    *   **物体-代码模型 (MeshCoder)**：在**64块** A100上训练，Batch Size为256。训练约**2天**。
*   **其他硬件**：论文中未提及CPU或内存等其他算力资源的详细信息。

### **5. 实验数量与充分性评估**

*   **实验组数**：实验设计较为全面，包含约：
    1.  **主实验**：在41个物体类别上，与2个基线方法定量比较重建性能。
    2.  **泛化性实验**：在非Infinigen数据（Trellis生成）上进行跨域测试。
    3.  **消融实验 (4项)**：
        *   Triplane分辨率和可学习Token数量的影响。
        *   是否从“部件-代码”模型权重初始化。
        *   是否使用可学习Token作为查询（对比直接投影）。
        *   对比不同点云编码方式（Triplane vs 逐点Token）。
    4.  **应用导向实验**：定性地展示了**几何编辑**、**拓扑编辑**和辅助LLM进行**3D形状理解**的能力。
    5.  **鲁棒性实验**：测试了不同点云密度（4096, 8192, 16384点）对重建质量的影响。
*   **充分性与公平性**：实验设计充分且客观。定量比较涵盖了完整的41类测试集，指标标准；消融实验旨在独立验证关键设计组件的有效性，对比公平；泛化性测试进一步验证了模型并非仅记忆训练数据。定性结果直观地展示了方法的优势和应用潜力。

### **6. 主要结论与发现**

*   MeshCoder在形状到代码的重建任务上取得了卓越性能，在`Chamfer Distance`和`IoU`两项指标上，均以显著优势超越现有基线方法，尤其擅长处理复杂几何和内部结构。
*   通过将3D形状表示为结构化的、模块化的代码，MeshCoder实现了直观且强大的几何与拓扑编辑能力，仅需简单修改代码参数即可。
*   这种包含语义注释的代码表示能显著**增强大语言模型（如GPT-4）的3D形状理解能力**，使其能回答关于物体结构和尺寸的复杂问题，这是纯视觉输入难以做到的。

### **7. 优点：方法与实验的亮点**

*   **创新的数据构建范式**：通过“部件-代码”到“物体-代码”的两步法，巧妙地解决了大规模程序化物体数据难以获取的痛点，思路新颖。
*   **强大的API设计**：设计的Blender Python API表达能力远超传统基元，能构建多种复杂几何形态，是支撑整个工作的基础。
*   **结构化与可编辑性**：输出代码显式按部件分解并带语义标签，这种结构化表示不仅便于编辑，也为3D理解提供了新途径。
*   **形状分词器设计**：采用Triplane投影加可学习查询Token的压缩编码方式，能有效将3D信息高效地传递给LLM，消融实验证明了其设计的优越性。
*   **实验全面扎实**：不仅包含全面的定量对比和消融，还通过编辑、理解等应用实验，充分展示了方法的潜力和价值。

### **8. 不足与局限**

*   **内容与材质缺失**：生成的代码仅包含几何信息，不包含物体的颜色、纹理等外观属性，限制了其部分应用。
*   **主要面向人造物体**：论文明确指出，该方法目前主要针对结构分明的人造物体，在动物、人体等有机形态上的应用仍是未来方向。
*   **泛化边界**：虽然展示了跨域能力，但模型在训练类别之外的物体上重建效果会下降，其泛化能力仍有提升空间。
*   **对部件分割的依赖**：构建物体级数据集时，假设了物体已被完美分割为语义部件。该前置假设能否在真实扫描数据上成立，未做讨论。

（完）
