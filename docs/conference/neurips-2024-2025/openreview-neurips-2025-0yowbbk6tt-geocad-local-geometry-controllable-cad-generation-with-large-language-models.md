---
title: "GeoCAD: Local Geometry-Controllable CAD Generation with Large Language Models"
title_zh: "GeoCAD: 基于大语言模型的局部几何可控CAD生成"
authors: "Zhanwei Zhang, kaiyuan liu, Junjie Liu, Wenxiao Wang, Binbin Lin, Liang Xie, Chen Shen, Deng Cai"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=0yowBBK6tT"
tags: ["query:part-aware"]
score: 9.0
evidence: 根据几何指令生成CAD模型的局部零件
tldr: 针对现有CAD生成方法无法遵循局部几何指令或忽略零件细节的问题，GeoCAD提出互补描述策略为局部零件生成几何指令，并利用大语言模型实现局部几何可控的CAD生成。实验表明该方法能按用户要求精确生成或修改特定零件形状，提升了CAD设计的灵活性和效率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-0yowbbk6tt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1459, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0yowbbk6tt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1452, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0yowbbk6tt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0yowbbk6tt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 258, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0yowbbk6tt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0yowbbk6tt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1458, \"height\": 1024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0yowbbk6tt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 811, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0yowbbk6tt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1452, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0yowbbk6tt/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1454, \"height\": 598, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0yowbbk6tt/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 191, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0yowbbk6tt/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 859, \"height\": 196, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-0yowbbk6tt/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1452, \"height\": 1980, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-0yowbbk6tt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1439, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0yowbbk6tt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1382, \"height\": 341, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0yowbbk6tt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1437, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-0yowbbk6tt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1436, \"height\": 334, \"label\": \"Table\"}]"
motivation: 现有CAD生成方法难以遵循文本指令或聚焦于局部零件，限制了设计效率。
method: 提出互补描述策略生成局部几何指令，结合大语言模型实现零件级可控生成。
result: GeoCAD能够根据用户文本指令精确控制CAD模型局部零件的几何形状。
conclusion: 该方法实现了对CAD模型中局部零件的精细化生成，推动可交互设计。
---

## Abstract
Local geometry-controllable computer-aided design (CAD) generation aims to modify local parts of CAD models automatically, enhancing design efficiency. 
It also ensures that the shapes of newly generated local parts follow user-specific geometric instructions (e.g., an isosceles right triangle or a rectangle with one corner cut off).
However, existing methods encounter challenges in achieving this goal.
Specifically, they either lack the ability to follow textual instructions or are unable to focus on the local parts.
To address this limitation, we introduce GeoCAD, a user-friendly and local geometry-controllable CAD generation method. 
Specifically, we first propose a complementary captioning strategy to generate geometric instructions for local parts.
This strategy involves vertex-based and VLLM-based captioning for systematically annotating simple and complex parts, respectively.
In this way, we caption $\sim$221k different local parts in total.
In the training stage, given a CAD model, we randomly mask a local part.
Then, using its geometric instruction and the remaining parts as input, we prompt large language models (LLMs) to predict the masked part.
During inference, users can specify any local part for modification while adhering to a variety of predefined geometric instructions.
Extensive experiments demonstrate the effectiveness of GeoCAD in generation quality, validity and text-to-CAD consistency.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：如何在保持 CAD 模型其余部分不变的前提下，根据用户提供的几何文本指令（如“等腰直角三角形”、“切除一个角的长方形”），自动修改局部零件（即草图中的局部闭合环）的形状。
- **研究动机**：现实的 SEM（草图-拉伸）建模流程中，用户在完成草稿后常需修改局部零件以满足功能或美学要求。现有可控 CAD 生成方法存在两类缺陷：
  - 基于属性/部分输入的模型（如 SkexGen、HNC-CAD）无法遵循自然语言几何指令。
  - 基于文本的生成模型（如 Text2CAD、FlexCAD）要么从零生成无法聚焦局部，要么所用的 3D 视角遮挡或扭曲导致无法捕捉精确几何属性（长度、角度），缺乏对局部几何的细粒度控制。
- **整体含义**：论文提出 **GeoCAD**，首次实现了对 CAD 模型的局部几何可控生成，让用户通过自然语言描述直观地指定局部零件的形状，从而提高设计效率。

## 2. 论文提出的方法论
### 2.1 互补描述策略（Complementary Captioning）
- **问题**：缺乏局部零件的几何指令标注。
- **分类**：根据组成边类型与数量，将局部环分为两类：
  - **简单零件**：常见几何形状（三角形、四边形、扇形等），约占总量一半。
  - **复杂零件**：更复杂的视觉模式。
- **标注方法**：
  - **顶点基准描述**（简单零件）：提取顶点坐标，利用几何属性（边长、角度）精确分类和命名（如四边等长且含直角→正方形），并可选附加关键尺寸（半径、边长等）。
  - **VLLM基准描述**（复杂零件）：渲染为 2D 图像，用 Qwen2.5‑VL‑72B‑Instruct 等视觉大语言模型生成形状描述。
- **成果**：共标注约 22.1 万个不同的局部零件（11.6 万复杂，10.5 万简单）。

### 2.2 两阶段 LLM 微调
- **CAD 表示**：采用 FlexCAD 的层次化文本序列，每个局部环表示为“边类型 + 顶点坐标”的字符串。
- **阶段 1（可选）：预训练——CAD‑文本对齐**
  - 目的：使 LLM 理解 CAD 专用的几何文本表示。
  - 操作：对每个局部环进行平移、缩放、旋转、反射的数据增强（复杂零件仅平移/缩放以免语义偏差），用几何指令与真实序列对 LLM 进行微调。
- **阶段 2：指令微调——局部几何控制**
  - 训练样本：对 CAD 模型随机 mask 一个局部环，构造提示：“以下是一个 CAD 序列片段，其中 [loop mask] 被替换……注意，该字符串表示一个 {几何指令}”，要求 LLM 预测被 mask 的环。
  - 损失：对生成 token 与真实 token 计算交叉熵损失。
  - 参数高效微调：使用 LoRA（秩=8，α=32）仅更新部分参数。
- **推理**：用户指定要修改的局部环，输入 CAD 模型文本和几何指令，模型生成新的环，替换后渲染得到新 CAD 模型。

## 3. 实验设计
- **数据集**：DeepCAD（178,238 条草图-拉伸序列），按 90%/5%/5% 划分训练/验证/测试。经去重、无效过滤，转换为 FlexCAD 文本格式。
- **评估指标**：
  - *生成质量*：覆盖率（COV）、最小匹配距离（MMD）、Jensen‑Shannon 散度（JSD）。
  - *有效性*：预测有效性（PV），即生成的环闭合、无交叉、与其余部分无冲突并可渲染。
  - *文本‑CAD 一致性*：对简单零件用基于顶点几何分析的 **Ver‑score**；对复杂零件用两个 VLLM 联合给出的 **VLLM‑score**；以及人工评估的 **Realism** 分数。
- **对比方法**：
  - **OpenAI‑o3**：五样本学习（few‑shot）使其输出符合格式。
  - **FlexCAD**：现有最佳局部生成基线，手动增强其对简单形状的约束（如将边数固定为 4 以生成梯形）。
  - 两种方法的五样本学习版本。

## 4. 资源与算力
- **GPU**：8 块 NVIDIA A100 (80GB)。
- **优化器**：AdamW，学习率 5×10⁻⁴，余弦退火。
- **批次大小**：32。
- **训练轮数**：阶段 1 为 10 个 epoch，阶段 2 为 30 个 epoch。
- **推理配置**：温度 τ=0.9，Top‑p=0.9。

## 5. 实验数量与充分性
- **主实验**：在 1k 测试 CAD 模型上，对每个模型随机 mask 一个环，用 5 条简单和 5 条复杂指令各生成 10 个结果，总计 10k 个生成模型。与 4 种 baseline 对比，报告 7 项指标。
- **消融实验**：
  - *互补描述策略的有效性*：仅用顶点描述（无法生成复杂零件） vs  仅用 VLLM 描述（无法精确生成简单零件）。
  - *预训练的有效性*：移除阶段 1（w/o stage 1）、移除阶段 1 中的数据增强（w/o data augmentation）。
- **LLM 规模实验**：对比 Transformer‑4M、Llama‑3‑8B‑Full、Qwen2.5‑3B/7B‑Instruct。
- **超参数敏感性分析**：温度 τ 和 Top‑p 对质量/有效性的折衷。
- **额外分析**：定性展示、尺寸约束控制能力、对未见过的语义相似指令的泛化能力。
- 实验覆盖全面，指标多元（自动+人工），对比公平（均采用相同基础 LLM、LoRA 配置和数据集），结论可信。

## 6. 论文的主要结论与发现
- GeoCAD 在生成质量、有效性和文本‑CAD 一致性方面均大幅优于 FlexCAD 和 OpenAI‑o3，其中 Ver‑score 提升最高达 38.7%，VLLM‑score 提升 41.4%，人工真实感提升 23.4%。
- 互补描述策略能有效标注简单和复杂局部零件，避免一种方法覆盖不全的缺陷。
- 预训练阶段和数据增强对于 CAD‑文本对齐至关重要，去除会显著降低性能。
- GeoCAD 能够精确控制尺寸参数（如圆的半径、矩形的长宽），并能泛化到训练中未出现的、语义相近的几何指令。

## 7. 优点（方法或实验设计亮点）
- **首次实现局部几何可控 CAD 生成**，填补了可控生成领域的一个关键空白。
- **互补描述策略**：巧妙地将规则化几何推导与 VLLM 的图像理解相结合，以极低人工成本构建了大规模、细粒度的局部零件指令数据集。
- **两阶段微调**：阶段 1 让 LLM 学会 CAD 专用表示，阶段 2 进行任务特定的指令微调，分工清晰且有效。
- **评估体系全面**：既包含与测试集分布的对比，又有生成有效性和文本指令一致性的专用指标，还引入人工评估，多维度验证。
- **开源准备**：论文承诺公开代码，有利于复现和后续研究。

## 8. 不足与局限
- **结构冲突问题**：当被修改的局部零件是其他零件的构建基准且尺寸严格依赖时，新生成的环可能与未变部分发生冲突，当前模型缺乏显式的零件间约束关系学习。
- **文本描述瓶颈**：某些非常复杂的形状可能很难用自然语言准确描述，限制了用户意图的表达精度。
- **数据集单一**：仅在 DeepCAD 上验证，未在其他 CAD 数据集（如 ABC）或更复杂的工业级模型上测试，泛化性待考。
- **模态限制**：仅接受文本指令，若结合手绘草图等多模态输入可能进一步提升设计灵活性（论文也将其列为未来工作）。
- **伦理与社会影响**：论文未详细讨论该技术可能带来的负面应用或公平性风险。

（完）
