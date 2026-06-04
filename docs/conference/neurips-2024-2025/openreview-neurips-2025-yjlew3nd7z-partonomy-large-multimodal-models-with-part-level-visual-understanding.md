---
title: "PARTONOMY: Large Multimodal Models with Part-Level Visual Understanding"
title_zh: PARTONOMY：具备部件级视觉理解的大规模多模态模型
authors: "Ansel Blume, Jeonghwan Kim, Hyeonjeong Ha, Elen Chatikyan, Xiaomeng Jin, Khanh Duy Nguyen, Nanyun Peng, Kai-Wei Chang, Derek Hoiem, Heng Ji"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=yjLew3Nd7z"
tags: ["query:part-aware"]
score: 5.0
evidence: 像素级部件定位基准，测试大模型部件级视觉理解。
tldr: 现有大模型难以理解物体部件。本文构建PARTONOMY基准，评估大规模多模态模型的像素级部件定位能力，涵盖862个部件和5346个物体。基准要求模型比较部件、考虑部件-全体关系并验证分割结果。揭示了当前模型在细粒度部件推理上的不足，为部件级理解研究提供测试平台。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-yjlew3nd7z/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 601, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yjlew3nd7z/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1433, \"height\": 633, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yjlew3nd7z/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yjlew3nd7z/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yjlew3nd7z/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 582, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yjlew3nd7z/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1433, \"height\": 918, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yjlew3nd7z/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 345, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yjlew3nd7z/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1296, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yjlew3nd7z/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 343, \"height\": 339, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yjlew3nd7z/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 286, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yjlew3nd7z/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 286, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yjlew3nd7z/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1302, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yjlew3nd7z/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 287, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yjlew3nd7z/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1322, \"height\": 373, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1375, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 935, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1088, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 759, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1452, \"height\": 1164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 938, \"height\": 594, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1373, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1007, \"height\": 163, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1379, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1374, \"height\": 355, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 756, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yjlew3nd7z/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 588, \"height\": 265, \"label\": \"Table\"}]"
motivation: 大模型缺乏部件级视觉理解，难以进行细粒度组成推理。
method: 构建包含862个部件和5346个物体的像素级部件定位基准PARTONOMY。
result: 评估揭示当前大模型在部件级推理上的局限性。
conclusion: PARTONOMY促进部件级视觉理解研究，推动组成推理能力发展。
---

## Abstract
Real-world objects are composed of distinctive, object-specific parts. Identifying these parts is key to performing fine-grained, compositional reasoning—yet, large multimodal models (LMMs) struggle to perform this seemingly straightforward task. In this work, we introduce PARTONOMY, an LMM benchmark designed for pixel-level part grounding. We construct PARTONOMY from existing part datasets and our own rigorously annotated set of images, encompassing 862 parts and 5346
objects for evaluation. Unlike existing datasets that simply ask models to identify generic parts, PARTONOMY utilizes highly technical concepts and challenges models to compare objects’ parts, consider part-whole relationships, and justify textual predictions with visual segmentations. Our experiments demonstrate significant limitations in state-of-the-art LMMs (e.g., LISA-13B achieves only 5.9% gIoU), highlighting a critical gap in their part grounding abilities. We note that existing segmentation-enabled LMMs (segmenting LMMs) have two key architectural shortcomings: they use special [SEG] tokens not seen during pretraining which induce distribution shift, and they discard predicted segmentations instead of using past predictions to guide future ones. To address these deficiencies, we train several part-centric LMMs and propose PLUM, a novel segmenting LMM that utilizes span tagging instead of segmentation tokens and that conditions on prior predictions in a feedback loop. We find that pretrained PLUM dominates existing segmenting LMMs on reasoning segmentation, VQA, and visual hallucination benchmarks. In addition, PLUM finetuned on our proposed Explanatory Part Segmentation task is competitive with segmenting LMMs trained on significantly more segmentation data. Our work opens up new avenues towards enabling fine-grained, grounded visual understanding in LMMs.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将使用中文、以 Markdown 形式，对该论文进行结构化、深入、客观的总结。

# 论文深度解析：《PARTONOMY: Large Multimodal Models with Part-Level Visual Understanding》

### 1. 论文的核心问题与整体含义
本研究聚焦于**大规模多模态模型在细粒度视觉理解上的核心缺陷——部件级识别与推理能力不足**。

*   **研究动机**：现实世界中的物体由独特的部件组成（如香蕉船的“座位管”、“充气阀”）。识别这些部件是进行复杂组合性推理的基础。然而，当前主流的LMM虽然擅长整体视觉问答或场景描述，却难以准确识别和定位物体的构成部件，甚至会从纯文本预训练知识中产生幻觉（如认为所有鱼都应该有鳍）。
*   **核心问题**：
    1.  **性能鸿沟**：现有LMM（如LISA，GLaMM）在像素级部件定位任务上表现极差，无法满足现实应用中（如机器人操作、可解释物体识别）对细粒度理解的需求。
    2.  **架构缺陷**：作者指出当前具备分割能力的LMM存在两个架构性短板：一是使用特殊的`[SEG]`令牌，引入了与其预训练阶段不匹配的分布偏移，损害了通用推理能力；二是在顺序生成遮挡掩码时，丢弃了先前的预测信息，未能利用历史视觉上下文来优化未来预测。
*   **整体含义**：论文旨在通过构建一个全新的、具有挑战性的基准数据集，并设计一个更优的模型架构，来量化和弥补LMM在部件级理解上的差距，为未来实现更精细、可解释的视觉AI系统奠定基础。

### 2. 论文提出的方法论
论文的贡献分为两部分：一个全新的基准数据集**PARTONOMY**和一个创新的模型架构**PLUM**。

*   **PARTONOMY 数据集与任务**
    *   **核心任务：解释性部件分割**。模型接收一张图像和一个关于部件的问题，必须从多个文本选项中选择正确答案，**同时**为答案中提到的部件生成对应的分割掩码，以提供视觉解释。
    *   **三类问题设计**，全面评估部件理解能力：
        1.  **部件识别**：识别并分割出图中物体的可见部件。
        2.  **部件比较**：找出两个物体的公共部件（**部件交集**）或独有部件（**部件差集**）。
        3.  **部分-整体推理**：从部件推断物体类别（**部件到整体**），或从物体类别识别其部件（**整体到部件**）。
    *   **数据集构建**：整合了现有的部分数据集（PACO, PartImageNet, PASCAL-Part），并贡献了一个高标准的、手动标注的评价子集**PARTONOMY-Core**。该子集包含1068张专业领域物体图像（如农用飞机、武器），涵盖534个物体类别和862个独特部件标签，其多样性和规模远超现有数据集。
    *   **训练数据生成**：提出一种**问答突变框架**。通过训练逻辑回归模型预测部件共现关系，或基于词嵌入相似度选择易混淆物体，来生成具有挑战性、语义上接近的错误答案选项，确保评估的难度。

*   **PLUM 模型架构**
    *   **整体框架**：基于一个视觉语言模型（LLaVA）作为骨干网络，并结合SAM的掩码解码器。其核心创新在于摒弃了`[SEG]`令牌，并引入了反馈机制。
    *   **关键技术细节**：
        1.  **文本跨度标记**：在LLM输出嵌入后接一个**双向自注意力模块（跨度提取器）**，使用BIO标注方案识别出文本回复中需要被分割的实体词（如“spraying rig”）。这避免了引入未见过的特殊令牌，保留了预训练模型的语言分布。
        2.  **查询投影与KL正则化约束**：将标记为`B/I`的令牌投影为“掩码查询”向量`q_k`，并用**KL散度损失**约束这些向量，使之不偏离冻结的“教师”VLM的原始表示空间，以保持模型的文本推理能力。
        3.  **掩码反馈循环**：这是PLUM的关键设计。它修改了SAM解码器的掩码编码器，加入了**特征线性调制 (FiLM)** 层。该机制将**先前预测的掩码**编码为特征图，并与当前文本跨度的语义信息结合，通过一个**逐块注意力池化层**整合所有历史掩码信息，再送入掩码解码器，从而让模型在生成新掩码时能参考已生成的视觉上下文，保证一致性和准确性。
        4.  **损失函数**：总损失由语言生成损失 `L_LM`、跨度分类损失 `L_span`、KL正则化损失 `L_KL`、Focal-Tversky分割损失 `L_seg` 和像素级二元交叉熵损失 `L_BCE` 加权求和而成。采用Focal-Tversky Loss旨在鼓励生成更精确、更高IoU的掩码。

### 3. 实验设计
*   **数据集与基准**：
    *   **主要评估集**：**PARTONOMY-Core**，在该数据集上执行解释性部件分割任务。
    *   **其他评估集**：PACO-LVIS, PartImageNet, PASCAL-Part的测试分割。
    *   **通用能力基准**：在**ReasonSeg**（推理分割），**TextVQA, GQA**（视觉问答）和**POPE**（视觉幻觉评估）上评估模型的通用性。
*   **对比方法**：
    *   **分割LMM基线**：LISA、PixelLM、GLaMM。这些模型均使用LLaVA作为VLM骨干，并与SAM或其他掩码解码器集成。对比包括“零样本”和“在PARTONOMY上微调后”两种设置。
    *   **通用开放词汇分割模型**：X-Decoder、SEEM、Grounded SAM 2。由于它们不理解问答式提示，为其提供真实答案文本进行分割，作为性能参考上限。
    *   **其他高级基线**：SegLLM（基于LLaVAv1.5和HIPIE解码器，具有多轮分割能力）。
    *   **前沿模型参考**：GPT-4o（仅用于文本选择题评估）。

### 4. 资源与算力
*   **硬件配置**：论文附录中提到使用了GPU进行训练，但没有明确提及GPU的具体型号（如A100, H100）或数量。
*   **训练配置**：
    *   训练采用DeepSpeed ZeRO-2优化，并使用bf16混合精度。
    *   单个GPU的批次大小为6，梯度累积步长为10，有效批次为 `10 × batch_size × GPU数量`。
    *   优化器为AdamW，学习率峰值为3e-4。
    *   大体分为两个训练阶段，总计数十个epoch。关于总训练时长，论文未给出具体数值。

### 5. 实验数量与充分性
论文进行了相当全面的实验，设计公平且充分。
*   **主要实验组数**：超过10组核心实验。
    *   **解释性部件分割评估**：在5个问题子任务上对比了**4种PLUM变体**（7B/13B, 零样本/微调）与**LISA、PixelLM、GLaMM等至少6种基线方法**，进行了文本和分割两个维度的评估。
    *   **通用下游任务评估**：在ReasonSeg、TextVQA、GQA、POPE这4个基准上验证了模型的通用能力和抗分布偏移特性。
*   **消融实验**：针对PLUM的关键组件（反馈循环、跨度标记）和关键超参数（如`λ_KL`）进行了消融研究，清晰地证明了每个设计选择的有效性，以及分割性能与推理能力之间的权衡关系。
*   **公平性**：所有模型（除SegLLM外）都尽可能基于同一VLM（LLaVA）骨干网络和类似的预训练数据进行公平比较。对GPT-4o的文本评测也明确了其通过一次提供所有选项而获得的潜在优势。

### 6. 论文的主要结论与发现
*   **现有LMM存在严重的部件理解缺陷**：即使是训练了部件分割的LMM，其在PARTONOMY上的性能也极低（如LISA-13B gIoU仅5.9%），表明当前模型远未掌握细粒度的部件级视觉概念。
*   **PLUM架构设计有效**：
    1.  **跨度标记**成功缓解了特殊令牌引入的分布偏移问题，使得PLUM在VQA和POPE任务上的表现显著优于LISA等模型，甚至在某些任务上超越其LLaVA骨干网络。
    2.  **反馈循环**和**跨度提取**能够协同工作，前者提升了分割精度，后者提升了对长尾部件的覆盖率。
    3.  **KL正则化**在维持模型推理能力和分割性能之间起着关键的平衡作用。
*   **PLUM性能优越**：预训练的PLUM在零样本部件分割和通用推理任务中全面领先其他分割LMM。在PARTONOMY上微调后，其性能具有很强的竞争力，尤其在衡量整体部件覆盖度的宏gIoU指标上表现突出，证明了其方法的高效性。

### 7. 优点
*   **问题洞察深刻**：从架构层面（分布偏移、上下文丢弃）精确诊断了现有分割LMM症结，而非流于表面。
*   **数据贡献扎实**：**PARTONOMY-Core**数据集对专业领域物体的细粒度部件标注，极大地扩展了部件级评估的广度和深度，是社区的重要资产。
*   **方法设计优雅**：**PLUM**的“以标记代替令牌”和“反馈循环”设计思想简洁而强大，既解决了根本问题，又保留了通用能力，实现了多任务间的良好权衡。
*   **评估体系全面**：精心设计的**解释性部件分割任务**和**问答突变框架**，不仅评估了“是否分割准确”，还评估了“是否理解”背后的部件关系，为评测提供了更高维度。

### 8. 不足与局限
*   **数据覆盖偏差**：虽然PARTONOMY-Core的部件标签数量创了记录，但其物体类别偏向于“具有技术性的专业领域物体”，可能在普通日常物品上的泛化性未得到充分验证。
*   **模型鲁棒性与可扩展性**：PLUM在处理**微小或模糊部件**时仍有困难，其反馈循环机制在**高分辨率图像**下的计算效率和误差累积风险未深入探讨。虽然论文提到误差累积不严重，但缺乏更系统的鲁棒性分析。
*   **算力信息不透明**：论文未提供GPU型号、数量和总训练时间等算力细节，这为复现实验和评估其资源效率带来了不便。

（完）
