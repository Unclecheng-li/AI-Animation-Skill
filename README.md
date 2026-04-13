<div align="center">

# AI-Animation.skill

> *使用 AI 生成 HTML 演示动画的工具集，让视频创作者能够快速将科普文本转换为炫酷的演示动画。*

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![OpenClaw](https://img.shields.io/badge/OpenClaw-Skill-green)](https://openclaw.ai/)
[![HTML5](https://img.shields.io/badge/HTML5-Demo-orange)](web_animation/)

<br>

**不是模板合集，是可运行的 AI 动画生成工作流。**

<br>

基于整理好的 Prompt 模板集成的 Skill，
配合 OpenClaw、Workbuddy、QClaw 等 AI 使用，
三步自动完成「科普文本 → 炫酷动画」的转换。

[快速开始](#快速开始) · [Prompt 分类](#prompt-分类) · [效果示例](#效果示例) · [模板预览](#模板预览)

</div>

---

## 它能做什么

输入一段技术科普文本，AI 自动生成演示动画：

```
用户输入：OSI 七层模型是什么？(相关科普文档)

Step 1 → 生成 7 页基础 HTML 幻灯片
Step 2 → 选择模板重构（PPT 风格 / 流程图风格）
Step 3 → 选择模板输出炫酷的动画演示文件
```

<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/c09e0f57-7f5a-4014-8809-b5e99d11e9f5" />

适用于 B 站视频素材、课堂教学、技术分享等场景。

---

## 快速开始

### 安装 (Workbuddy)

```
1. 下载本项目
2. 将 AI-Animation-Skill 文件夹复制到 ~/.workbuddy/skills/ 目录
3. 重启 WorkBuddy
```

### 使用

1. 在对话中输入科普内容，说「帮我生成动画」
2. 选择模板（1-4），等待重构
3. 可选：说「生成流程图」进行第三步

---

## 蒸馏了什么

| 类别            | 内容                           |
| ------------- | ---------------------------- |
| **Prompt 模板** | 60+ 条经过验证的 AI 生成提示词          |
| **PPT 风格模板**  | 7 个可复用的 HTML 轮播演示模板          |
| **RNN 风格模板**  | 14 个流程图风格的 HTML 模板           |
| **工作流**       | 文本 → HTML → 模板重构 → 流程图 的完整链路 |

---

## Prompt 分类

| 分类                        | 数量   | 说明            |
| ------------------------- | ---- | ------------- |
| [页面生成](#1-页面生成)           | 8 条  | 生成炫酷暗色调页面     |
| [动画效果](#2-动画效果)           | 16 条 | 缓入、强调、循环、3D 等 |
| [3D 效果](#3-3d-效果)         | 4 条  | 3D 旋转、鼠标跟随    |
| [PPT 风格](#4-ppt-风格)       | 12 条 | 轮播、翻页、图文并茂    |
| [美化与 UI 重构](#5-美化与-ui-重构) | 6 条  | 发光、图形化、立绘嵌入   |
| [UI 置换](#6-ui-置换)         | 4 条  | 参考图片进行视觉重构    |

---

## 效果示例

### PPT 风格（模板重构后）

<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/6ffb76f6-0dea-4b02-b983-617a284b9c80" />
<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/8c1be8cc-8293-4893-8b56-b695e5daf6fe" />

### 流程图风格（RNN 模板重构后）

<img width="2560" height="1440" alt="image" src="https://github.com/user-attachments/assets/5a65dd82-b690-4d1a-87ba-1b6196b01273" />

---

## 模板预览

### PPT 风格模板

| 模板                 | 特点         | 预览       |
| ------------------ | ---------- | -------- |
| PPT-Generate-1     | 简洁风格       | 基础演示     |
| PPT-Generate-2     | 图表丰富       | 数据类内容    |
| **PPT-Generate-3** | **视觉效果最佳** | **通用推荐** |
| PPT-Generate-4     | 布局灵活       | 复杂内容     |
| PPT-Generate-5     | 科技感        | 技术演示     |
| PPT-Generate-6     | 多图表        | 数据分析     |
| PPT-Generate-7     | 简洁专业      | 商务汇报     |

### RNN 风格模板

| 模板        | 特点       | 预览       |
| --------- | -------- | -------- |
| RNN-2     | 分步展示     | 基础流程     |
| **RNN-3** | **分层卡片** | **通用推荐** |
| RNN-4     | 纵向流程     | 线性步骤     |
| RNN-5     | 分层结构     | 层级关系     |
| RNN-6     | 树状图      | 层级关系     |
| RNN-7     | 动态连线     | 关系可视化    |
| LSTM-1    | LSTM展示    | 序列模型     |
| onehot    | one-hot编码  | 离散特征     |
| onehot-drawback | one-hot缺陷 | 特征问题 |
| word2vec-1 | word2vec | 词向量     |
| Comprehension | 理解模型 | 认知类 |
| GPU       | GPU架构     | 硬件展示     |
| Cross-modal disentanglement - 2 | 跨模态解耦 | 多模态 |
| The fatal flaw of DNN | DNN缺陷 | 深度学习问题 |

---

## 技术栈

- **前端**：HTML5 + CSS3 + JavaScript（原生，无框架依赖）
- **动画**：CSS Animation / Keyframes / 3D Transform
- **兼容性**：现代浏览器（Chrome、Firefox、Safari、Edge）

---

## 调研来源

| 来源            | 说明              |
| ------------- | --------------- |
| prompt.txt    | 60+ 条 AI 生成提示词  |
| PPT Template/ | 7 个 HTML 演示模板   |
| Animation/    | 14 个 AI/ML 概念演示 |
| RNN-Template/ | 14 个流程图模板       |

---

## 开源协议

本项目采用 [MIT License](LICENSE)。

---

<div align="center">

**如果对你有帮助，欢迎 Star ⭐**

</div>
