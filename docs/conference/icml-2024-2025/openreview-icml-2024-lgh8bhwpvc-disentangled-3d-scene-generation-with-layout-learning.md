---
title: Disentangled 3D Scene Generation with Layout Learning
title_zh: 解耦的3D场景生成与布局学习
authors: "Dave Epstein, Ben Poole, Ben Mildenhall, Alexei A Efros, Aleksander Holynski"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=Lgh8bhWpVC"
tags: ["query:part-aware"]
score: 10.0
evidence: 通过优化多个NeRF与布局生成解耦成组件物体的3D场景
tldr: 提出无监督的3D场景生成方法，自动将场景分解为独立物体。核心思路是寻找可空间重排仍保持合理性的场景部件，通过联合优化多个代表各自物体的NeRF及其布局，利用预训练文本到图像模型鼓励组合场景符合分布。方法成功生成分离的物体，支持独立操控和组合。这为生成式3D建模中的部件级控制铺平了道路，使得用户可以自由编辑场景中的物体布局，甚至将不同物体组合成新场景，极大提升了3D内容创作的灵活性。实验展示了对合成场景与真实图像的有效分解，验证了方法的实用性与泛化能力。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-lgh8bhwpvc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 2179, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lgh8bhwpvc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1612, \"height\": 761, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lgh8bhwpvc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1070, \"height\": 699, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lgh8bhwpvc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1789, \"height\": 1308, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lgh8bhwpvc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 854, \"height\": 224, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lgh8bhwpvc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 855, \"height\": 222, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lgh8bhwpvc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 853, \"height\": 222, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lgh8bhwpvc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 853, \"height\": 718, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lgh8bhwpvc/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 862, \"height\": 184, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-lgh8bhwpvc/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1784, \"height\": 851, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-lgh8bhwpvc/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 679, \"height\": 606, \"label\": \"Table\"}]"
motivation: 3D场景生成需解耦为独立物体，但缺乏监督。
method: 通过重排部件保持有效性，联合优化多NeRF与布局，利用文生图先验。
result: 成功生成分解为多个物体的3D场景，支持独立编辑与重布局。
conclusion: 无监督场景分解为可控3D内容创建开辟了新可能性。
---

## Abstract
We introduce a method to generate 3D scenes that are disentangled into their component objects. This disentanglement is unsupervised, relying only on the knowledge of a large pretrained text-to-image model. Our key insight is that objects can be discovered by finding parts of a 3D scene that, when rearranged spatially, still produce valid configurations of the same scene. Concretely, our method jointly optimizes multiple NeRFs---each representing its own object---along with a *set of layouts* that composite these objects into scenes. We then encourage these composited scenes to be in-distribution according to the image generator. We show that despite its simplicity, our approach successfully generates 3D scenes decomposed into individual objects, enabling new capabilities in text-to-3D content creation.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **核心问题**：现有的文本到3D生成方法（如 DreamFusion）虽能生成高质量物体，但通常产生一个不可分割的单一3D表征，无法自动将复杂场景分解为独立的组成物体。这限制了用户对生成内容的局部编辑、重排与组合。
- **研究动机**：借鉴人类视觉中“物体辨识”的能力，希望为生成式模型赋予一种 **无监督的物体发现机制**，仅依靠预训练大模型（文生图扩散模型）中蕴含的先验知识，将3D场景自动解耦为有意义的物体。
- **整体含义**：提出一种名为“布局学习”（Layout Learning）的方法，通过优化多个神经辐射场（NeRF）以及它们在不同布局下的空间排列，迫使每个 NeRF 去表示一个独立的、可以自由移动的物体，从而在无任何物体级监督的情况下实现可操控的、组分化的3D场景生成。

### 2. 方法论

- **核心定义**：将“物体”定义为场景中可以被**独立操控且依旧能构成合理场景**的部分。
- **关键组件**：
    - **多个 NeRF 实例**：同时初始化 K 个 NeRF，每个预期容纳一个物体。采用 Mip-NeRF 360 作为基础架构。
    - **可学习的多布局集合**：每个布局 Ln 包含对每个 NeRF 的仿射变换参数（旋转 Rk、平移 tk、尺度 sk）。训练时随机采样一个布局，对相机射线进行变换后分别送入各 NeRF 渲染，最后通过体密度累加与反照率加权平均，合成整个场景的体渲染图像。
    - **训练信号**：使用分数蒸馏采样（SDS）损失，以文本提示 y 为条件，利用预训练扩散模型对合成图像进行评分，梯度同时反向传播更新 **所有 NeRF 参数** 和 **布局变换参数**。
    - **正则化**：
        - 继承 Mip-NeRF 360 的方向、失真、累积等损失，但 **按 NeRF 单独施加**。
        - 引入 **空 NeRF 损失**，惩罚单个 NeRF 累积密度占画布比例过低的情况，防止出现退化的空模型。
- **算法流程（文字描述）**：
    1. 初始化 K 个 NeRF 与 N 组布局（仿射变换参数）。
    2. 每步迭代：
        - 随机选择一组布局 Ln。
        - 采样相机参数，生成一批相机射线。
        - 对每条射线应用各 NeRF 对应的仿射变换，得到 K 组变换后的射线。
        - 分别查询 K 个 NeRF 得到各自的密度和颜色。
        - 在共享坐标系下合成累积密度与加权颜色，渲染出图像。
        - 计算 SDS 损失与各项正则化损失，反向传播更新 NeRF 权重与布局参数。
- **公式要点**：仿射变换为 `ok = sk×(Rk·o - tk)`, `dk = sk×Rk·d`；最终密度 τ′ = Σ τk，颜色为密度加权平均。

### 3. 实验设计

- **评估场景与数据**：使用 30 个自定义的、每个均包含 3 个不同物体的文本提示列表（如“一个背包、一个水瓶和一包薯片”），不存在固定的“真实”3D 数据。
- **评估指标**：使用预训练 CLIP 模型（B/16 和 L/14）计算解耦质量。具体为渲染各 NeRF 的多视角图像，与描述单个物体的提示（如“一张背包的 DSLR 照片”）计算余弦相似度，通过匈牙利匹配得到最优 NeRF-物体配对的平均分数。同时报告“彩色”和“几何”（无纹理）渲染下的分数。上界为对每个物体单独用 SDS 生成 NeRF 的分数，下界为随机物体提示与生成物体的分数。
- **对比方法（消融基线）**：
    - 随机物体的 CLIP 分数（下界）。
    - 每物体单独 SDS 生成（上界）。
    - 简单使用 K 个 NeRF（无布局学习）。
    - + 逐 NeRF 的正则化损失。
    - + 空 NeRF 损失。
    - + 学习 **1 个** 布局。
    - + 学习 **N 个布局**（完整方法）。
    - + 相对布局（Relative layouts）与视角依赖提示（View dep. prompt）变体。
- **应用验证**：除定量评估外，还展示了若干定性应用：
    - **条件优化**：冻结包含给定资产的 NeRF，生成适应文本的其他物体。
    - **布局多样性**：展示不同布局下的排列差异。
    - **纯布局优化**：冻结 NeRF 资产，仅优化布局参数排列现成 3D 模型。
    - **已有 NeRF 分解**：对预训练的多物体 NeRF 进行解析还原。

### 4. 资源与算力

- 文中未明确给出所用的具体 GPU 型号、数量或完整训练耗时。
- 实现细节中提及：使用 Imagen 128px 像素空间扩散模型，渲染分辨率 512px；优化器为 Shampoo，训练 15000 步，学习率从 \(10^{-9}\) 退火峰值 \(10^{-4}\) 至 \(10^{-6}\)。参数规模与显存消耗未披露，但可推测单个场景训练需要占用一张或多张主流 GPU。

### 5. 实验数量与充分性

- **实验组数**：
    - 定量消融实验覆盖 **7 种变体**，在 **30 个提示 x 3 个物体** = 90 组生成任务上评估，每个实验还在多个随机种子下筛选最佳匹配分数。
    - 定性展示涵盖约 **8 组以上**不同复杂度的文本提示及多项应用任务。
- **充分性与公平性**：
    - 消融设计逻辑清晰，从无布局到单布局再到多布局，逐步验证各组件贡献，对比基准包含理论下界与上界，较为公平。
    - 评估指标依赖 CLIP 相似度，虽常见但并非完美解耦度量，且仅涉及三物体场景，对更复杂臃杂场景的泛化性未充分量化。
    - 应用实验主要以个例演示为主，缺乏系统的用户研究或大规模鲁棒性测试，但在方法能力展示层面是充分的。

### 6. 主要结论与发现

- 提出的**布局学习**能够以完全无监督的方式，将由多个 NeRF 组成的复杂 3D 场景有效分解为单个物体。
- 多个布局的协同学习是关键：它强迫不同 NeRF 学习可以独立移动的语义单元，显著优于仅用 K 个 NeRF 或单布局的变体。
- 该方法不仅可从头生成解耦场景，还能围绕给定资产构建场景、优化现有模型的排列，以及解析已有 NeRF 为组成物体，拓展了文本到 3D 内容创作的可编辑性。

### 7. 优点

- **无监督与简单性**：无需任何物体标签、边界框、外部模型或人工标注，仅依赖文本提示与扩散模型先验，实现路径简洁优雅。
- **新颖的物体定义**：将“物体”定义为可独立重排且保持场景有效性的部分，为其架构设计提供了清晰的归纳偏置。
- **生成的组分化与可控性**：允许单独操控每个 NeRF（即物体），支持重布局、资产插入、场景重组等新式交互。
- **兼容性**：方法对底层 NeRF 型态（MLP 式或哈希式）和扩散模型的选择较为鲁棒，易于集成。

### 8. 不足与局限

- **解耦失效模式**：
    - **欠分割**：始终共同运动的实体（如骑士与马）可能被归为同一 NeRF。
    - **过分割/混乱**：物体复杂时（如茶具），难以选择最佳的 K 值，导致碎片化。
    - **布局塌缩**：不同布局可能收敛到几乎相同的配置，弱化多样性。
- **几何质量问题**：继承了 SDS 方法的常见缺陷，如 Janus 问题（多面脸）、非自然的几何结构（如墙壁穿插）。
- **评估局限**：CLIP 分数主要衡量语义一致性，难以精确反映 3D 空间解耦的准确性；测试场景仅限于三物体提示，复杂度有限。
- **应用约束**：需要预定义物体数量 K，且训练过程需要为每个新场景重新优化，尚不能实时生成。

（完）
