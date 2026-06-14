# DL-radiology-skill

> 深度学习 x 医学影像交叉方向的论文写作 Skill  
> A Codex Skill for deep learning x medical imaging manuscript writing.

`radiology-ai-manuscript-writer` 是一个面向 **深度学习-医学影像交叉论文** 的 Codex Skill。它不是泛论文 prompt 库，也不是“一句话生成 SCI 论文”的工具，而是一个围绕真实医学影像 AI 项目的写作工作流：把你的模型结果、临床表格、影像图、统计输出、图表和已有手稿，组织成更接近 Radiology: Artificial Intelligence 风格的完整论文表达。

## 先说清楚：它需要完整材料

这个 Skill 的定位不是凭空写论文。  

如果你想让它写出一篇完整、可继续修改和投稿的医学影像 AI 论文，你需要把完整项目材料喂给 Codex，例如：

- 已有 manuscript / mentor-written Methods & Results
- 模型输出结果、AUC/AP/Brier、校准曲线、DCA、pairwise tests
- 临床 Excel、患者 split 文件、cohort 信息
- MRI/CT/PET 等影像相关图像、分割图、GradCAM/SHAP/occlusion 图
- Figure、Table、caption、supplementary material
- 目标期刊或参考文章

材料越完整，它越能写出完整文章；材料不完整时，它只会帮你做结构规划、缺失项标记、文字润色和一致性检查，不会替你编数据。

## What's Inside

| 模块 | 能做什么 |
| --- | --- |
| 论文定位 | 聚焦深度学习 x 医学影像，而不是泛学术写作 |
| 材料盘点 | 识别 DOCX/PDF 手稿、Results 文件夹、临床表格、split 文件、图像、表格、示例论文 |
| 数据溯源 | 把 cohort 数量、AUC/AP/Brier、p 值、OR、fusion weights、figure annotation 对回源文件 |
| 文章结构 | 生成或修订 Title、Summary、Key Points、Abstract、Introduction、Methods、Results、Discussion |
| Radiology AI 风格 | 按临床问题、影像输入、AI workflow、外部验证、局限性来组织叙事 |
| 模型结果表达 | 处理 image-only、clinical-only、image-clinical fusion、CNN/Transformer、VOI、ablation、stability |
| 图表规划 | 规划 cohort flow、MRI-clinical workflow、model matrix、ROC/PR/calibration/DCA、SHAP/GradCAM 等图组 |
| caption/table | 扩写 figure captions，统一 table titles、notes、abbreviations、denominators |
| 一致性检查 | 对齐 title、abstract、purpose、conclusion、figures、tables、in-text references |
| 边界控制 | 不编数据、不夸大 novelty、不把 SHAP/GradCAM 写成因果证明、不写“模型替代医生” |

## 适合什么项目？

适合正在写或修改这类论文：

- MRI/CT/PET/超声等医学影像深度学习预测模型
- CNN、3D CNN、Vision Transformer、Swin Transformer、image-clinical fusion 论文
- 影像组学 / 深度学习 / 临床变量融合的医学影像 AI 研究
- 需要报告 AUC、AP、Brier score、calibration、decision curve analysis 的模型文章
- 需要 SHAP、GradCAM、occlusion map 等解释性图像的论文
- 想向 Radiology: Artificial Intelligence 或类似医学影像 AI 期刊风格靠近的手稿

## 推荐项目结构

```text
project/
  manuscript_draft.docx
  mentor_methods_results.docx
  Results/
    model_performance.csv
    pairwise_auc_tests.csv
    calibration_or_dca_outputs.csv
    shap_or_gradcam_outputs/
  clinical_data.xlsx
  patient_split.xlsx
  figures/
  tables/
  example_papers/
```

## 核心规则

1. 不编造任何研究数据。
2. 不把模型写得比结果更强。
3. 不把 SHAP、GradCAM、occlusion map、DCA 写成因果证据。
4. Methods 和 Results 如果已经由导师定稿，默认保留。
5. 标题一旦变化，Summary、Purpose、Conclusion、Introduction、Discussion、figure/table 语言都要同步。
6. 每张图都要有真正的 caption，解释 panel A/B/C/D 和缩写。
7. 最终稿必须做 placeholder、数值、图表引用、caption、table note 的一致性检查。

## 使用方式

把这个文件夹放到 Codex skills 目录后，在 Codex 里说：

```text
Use the radiology-ai-manuscript-writer skill.

请根据我的 manuscript、Results 文件夹、clinical Excel、split 文件和 figures，
帮我修订这篇深度学习-医学影像交叉方向论文。

要求：
1. 不要编造缺失数据。
2. 所有数值必须来自我提供的文件。
3. 保留导师写好的 Methods 和 Results，除非发现明显不一致。
4. 按 Radiology AI 风格补强摘要、Introduction、Discussion、figure captions 和 tables。
```

## 它不会做什么？

- 不会在没有完整数据和图像的情况下生成“完整论文”。
- 不会替代统计分析。
- 不会替代临床判断。
- 不会保证投稿录用。
- 不会把不完整证据包装成确定结论。

## 一句话定位

这是一个给 **深度学习 x 医学影像论文** 用的写作工作流：  
不是帮你“编一篇论文”，而是帮你把真实数据、真实图像、真实模型结果，写成审稿人能读懂、临床逻辑站得住、数据前后一致的医学影像 AI 手稿。

成“审稿人能读懂、临床逻辑站得住、数据不乱编”的医学影像 AI 论文。
