---
title: "ShapeCraft: LLM Agents for Structured, Textured and Interactive 3D Modeling"
title_zh: "ShapeCraft: 面向结构化、带纹理与交互式三维建模的LLM代理"
authors: "Shuyuan Zhang, Chenhan Jiang, Zuoou Li, Jiankang Deng"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=skS03tzYNw"
tags: ["query:part-aware"]
score: 9.0
evidence: 将自然语言分解为子任务结构化图，进行零件级程序化形状生成
tldr: 针对现有文本到3D生成常产生非结构化网格且交互性差的问题，ShapeCraft提出基于图形程序化形状表示的多智能体框架，将复杂自然语言分解为子任务图，由LLM代理层次化生成零件级形状程序。该方法支持结构化、带纹理的交互式三维建模，降低了手动建模门槛，增强了艺术工作流的实用性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1377, \"height\": 778, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1426, \"height\": 658, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1359, \"height\": 837, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1346, \"height\": 819, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 642, \"height\": 280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 644, \"height\": 275, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1304, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1393, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1353, \"height\": 1024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1208, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1420, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1400, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1226, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1259, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1089, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1009, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-sks03tzynw/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1329, \"height\": 1035, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-sks03tzynw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1442, \"height\": 307, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sks03tzynw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1404, \"height\": 229, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sks03tzynw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sks03tzynw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1218, \"height\": 150, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sks03tzynw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1388, \"height\": 574, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-sks03tzynw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1387, \"height\": 347, \"label\": \"Table\"}]"
motivation: 传统文本到3D生成产生非结构化网格，缺乏交互性，难以用于实际艺术设计。
method: 采用基于图的程序化形状表示和多LLM代理，将自然语言分层分解为零件子任务再合成。
result: ShapeCraft能生成带纹理的结构化模型并支持交互式编辑，优于现有方法。
conclusion: 通过程序化分解与多代理协作，实现了零件感知的结构化三维生成。
---

## Abstract
3D generation from natural language offers significant potential to reduce expert manual modeling efforts and enhance accessibility to 3D assets. However, existing methods often yield unstructured meshes and exhibit poor interactivity, making them impractical for artistic workflows. To address these limitations, we represent 3D assets as shape programs and introduce ShapeCraft, a novel multi-agent framework for text-to-3D generation. At its core, we propose a Graph-based Procedural Shape (GPS) representation that decomposes complex natural language into a structured graph of sub-tasks, thereby facilitating accurate LLM comprehension and interpretation of spatial relationships and semantic shape details. Specifically, LLM agents hierarchically parse user input to initialize GPS, then iteratively refine procedural modeling and painting to produce structured, textured, and interactive 3D assets. Qualitative and quantitative experiments demonstrate ShapeCraft's superior performance in generating geometrically accurate and semantically rich 3D assets compared to existing LLM-based agents. We further show the versatility of ShapeCraft through examples of animated and user-customized editing, highlighting its potential for broader interactive applications.

---

## 论文详细总结（自动生成）

好的，请查收根据您提供的论文内容生成的中文总结。

### 1. 论文的核心问题与整体含义

*   **研究动机**：传统的文本到3D生成方法主要分为两类：
    *   基于优化的方法：生成的是非结构化中间表示（如神经场），需要经过复杂的等值面提取才能得到网格，常常产生拓扑错误、平滑伪影和过度细分等问题，可编辑性差。
    *   基于自回归的方法：直接生成网格，但通常缺乏语义部件分割，同样难以修改，且泛化能力有限。
    *   这两类方法都难以产出适合专业艺术工作流的、结构化且可交互的3D资产。
*   **核心问题**：如何从自然语言描述中生成**结构化、带纹理且可交互**的3D模型，以降低建模门槛并提升实用性。
*   **整体含义**：本文提出了**ShapeCraft**，一个基于多智能体（LLM Agents）的文本到3D生成框架。核心思想是将3D资产表示为**形状程序**，并引入一种称为**基于图的程序化形状（GPS）** 的表示方法，将复杂的自然语言指令分解为结构化的子任务，使大语言模型能更准确地理解空间关系和语义细节，从而生成可直接用于工业软件（如Blender）的程序化3D资产。

### 2. 论文提出的方法论

*   **核心思想**：通过将一个复杂的3D形状生成任务，分解为由多个专用LLM代理协作完成的、基于图结构表示的程序化建模流程。
*   **关键技术细节**：
    *   **基于图的程序化形状表示（GPS）**：
        *   它是一个扁平、单层的有向无环图 `G = (V, E, A)`，包含一个虚拟根节点 `v0` 和多个代表独立几何部件的子节点 `vi`。
        *   每个部件节点 `vi` 包含四个属性：**几何描述** `n^g_i`、**位置描述** `n^p_i`、**包围盒** `b_i ∈ R^6` 和**代码片段** `p_i`（可执行的Blender Python API脚本）。
        *   这种表示作为所有代理的**共享记忆**，便于并行建模。
    *   **多代理系统架构**：
        *   **解析器（Parser）**：接收用户输入，通过层次化解析将形状分解为GPS图，生成初始的拓扑结构、几何和位置描述。
        *   **编码器（Coder）**：负责为每个节点生成具体的包围盒参数和用于几何建模的Python代码片段。它采用**多路径采样**策略，并行探索多种建模方案。
        *   **评估器（Evaluator）**：作为质量控制机制，通过渲染图像对编码器生成的包围盒和代码进行评估，并生成文本反馈和量化分数，引导迭代式的自我修正。
    *   **算法流程**：
        1.  **图初始化与自举**：解析器和编码器先生成一个初始GPS图 `G^0`。然后通过评估器反馈，对图的结构和包围盒进行自举式更新，得到精炼的 `G*`。
        2.  **迭代式形状建模**：对 `G*` 中的每个部件节点，编码器并行生成 `M` 条建模路径。每条路径经过 `T` 次迭代更新：评估器对当前生成的形状渲染图给出评分和反馈，编码器基于反馈修正代码。最终选择评分最高的路径更新GPS。
        3.  **组件感知的BRDF材质绘制**：
            *   定义一个可学习的纹理场 `ψ_θ`，将UV坐标映射为BRDF参数（漫反射、粗糙度、金属感）。
            *   提出**组件感知的分数蒸馏采样（CASD）** 损失函数。该损失同时包含全局的SDS损失和针对每个独立部件的SDS损失，以此优化纹理场，让表面材质更好地贴合描述。

### 3. 实验设计

*   **数据集与场景**：主要评估使用了 **MARVEL-40M+** 数据集中的一个子集，包含**26个长文本功能型提示**。此外，还展示了在动画、用户自定义编辑等交互式场景下的应用。
*   **对比基准（Baselines）**：
    *   **基于优化的方法**：MVDream（带纹理评估）。
    *   **基于自回归的方法**：LLaMA-Mesh。
    *   **基于LLM的方法**：3D-PreMise, CADCodeVerify, L3GO, BlenderLLM。
    *   为保证公平，所有LLM相关方法在代码生成等任务上，均使用相同的底层LLM模型（Qwen3-235B-A22B）和VLM模型（Qwen-VL-Max）。
*   **评估指标**：
    *   **几何质量**：IoGT（交并比），Hausdorff距离。
    *   **文本-3D对齐度**：CLIP Score，VQA Pass Rate（通过VLM回答关于生成/真实模型的是非题来计算）。
    *   **运行时间**和**API调用次数**。

### 4. 资源与算力

*   **文中未明确说明**训练纹理场或运行代理流程所使用的**GPU型号、数量及具体训练时长**。
*   论文主要报告了生成一个模型所需的**推理时间和API调用成本**（例如，ShapeCraft平均耗时11.68分钟，API调用21次），这表明其计算开销主要来自对商业LLM/VLM的查询，而非本地大规模GPU训练。

### 5. 实验数量与充分性

*   **实验组数较为丰富**，涵盖了：
    *   **1个主对比实验**：在26个提示上与6种不同的基线方法进行定性和定量比较。
    *   **3组消融实验**：验证**多路径采样（M）**、**路径内迭代更新（T）** 以及**层次化形状解析（GPS表示）** 的有效性。特别地与使用“思维模式”的高级LLM（如ChatGPT-o3, Gemini）进行了对比。
    *   **1个定性展示**：针对不同提示类型（模糊、简短、创意）的失败案例分析。
    *   **多个应用展示**：交互式动画、模型编辑、与外部3D生成工具（如Hunyuan3D）的集成。
*   **实验的充分性与客观性**：
    *   **充分性**：实验设计较完善，通过消融研究明确了各个组件（M, T, 层次解析）的贡献，并分析了其对性能和时间的权衡。失败案例的分析也增加了研究的深度。
    *   **客观性与公平性**：在与同类LLM方法的比较中，统一了底层LLM和VLM，这是确保公平的关键。然而，评估所用的数据集规模（26个提示）相对较小，可能限制了结论的普适性。

### 6. 论文的主要结论与发现

*   ShapeCraft在生成几何精度高、语义丰富且具有结构化拓扑的3D模型方面，性能优于现有的基于LLM的代理方法。
*   与基于优化的方法（MVDream）相比，ShapeCraft能产出更结构化的网格，且在生成速度上具有巨大优势。
*   所提出的**GPS表示**能有效约束LLM的推理空间，使其在理解和生成复杂空间关系时比自由文本思路链推理的高级LLM更可靠。
*   **多路径采样**和**迭代式视觉反馈**策略是生成高质量和多样化模型的关键。
*   其程序化本质使得生成的模型具有高度的**可交互性**，能够直接用于后续的编辑、动画制作等任务。

### 7. 优点

*   **结构化输出**：生成的3D资产是干净、带语义部件分割的程序化网格，可直接用于工业标准工作流，克服了传统非结构化网格的缺点。
*   **任务分解策略**：创新的GPS表示将复杂的全局生成任务分解为大量简单、可控的部件级子任务，显著降低了LLM的推理难度。
*   **智能体协作与自我修正**：解析器、编码器、评估器三代理通过共享记忆（GPS）协同工作，并配合视觉反馈进行迭代优化，增强了系统的鲁棒性和生成质量。
*   **强交互性**：输出的是可执行的 Python 代码（形状程序），天然具备极强的可编辑性，支持动画、编辑等复杂后处理，应用潜力巨大。
*   **组件感知的材质生成**：CASD损失利用了部件的分解信息来优化纹理，改善了复杂文本描述下的材质对齐效果。

### 8. 不足与局限

*   **对复杂/有机几何体的生成能力有限**：由于依赖于预定义的封装库，编码器代理难以生成高度复杂或有机的形状（如生物的尾巴、翅膀等），尽管论文指出可通过集成外部3D生成工具来缓解。
*   **提示质量依赖性**：系统性能对用户提示的质量高度敏感。模糊、过于简短或过于创意的提示会导致解析器分解错误、评估器反馈无效，从而生成不合格的模型。
*   **计算效率问题**：多路径采样和迭代式自举虽然提高了质量，但也显著增加了推理时间和LLM API的调用成本（相较于简单的一次性生成方法）。
*   **评估基准规模有限**：定量实验仅在一个包含26个长提示的小型数据集上进行，其在更广泛、更多样化的提示上的表现和泛化能力有待进一步验证。
*   **潜在偏差**：系统的性能严重依赖于所选用的LLM和VLM（如评估器的审美和评价标准），这可能引入模型本身固有的偏差。

（完）
