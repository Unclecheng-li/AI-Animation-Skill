---
name: AI-Animation
description: "使用 AI 生成 HTML 演示动画的自动化工作流。当用户输入一段科普内容文本并希望生成 PPT 风格的 HTML 动画演示时使用。三步流程：1) 生成基础 HTML；2) 使用 PPT 模板重构；3)（可选）使用 RNN 模板生成流程图风格的页面重构。"
trigger: ["生成动画", "生成PPT", "生成演示", "HTML动画", "AI动画"]
---

# AI-Animation：AI 生成 HTML 演示动画

## 概述

本 Skill 实现三步自动化流程，将科普文本转换为炫酷的 HTML 动画演示。

**核心特点：**

- 📦 模板内置 — 所有模板文件已集成，开箱即用
- 🔧 路径可配 — 输出路径由用户自定义，默认输出到桌面
- 🎨 图标替换 — Step 2 强制执行 emoji 转平面 UI 图标

---

## 文件结构

```
AI-Animation/
├── SKILL.md                    # 本文件
├── references/
│   └── workflow.md             # 工作流参考文档
└── templates/
    ├── PPT-Template/           # PPT 风格模板
    │   ├── PPT-Generate-1.html
    │   ├── PPT-Generate-2.html
    │   ├── PPT-Generate-3.html  ← 推荐
    │   ├── PPT-Generate-4.html
    │   ├── PPT-Generate-5.html
    │   ├── PPT-Generate-6.html
    │   └── PPT-Generate-7.html
    └── RNN-Template/           # 流程图风格模板
        ├── Comprehension.html
        ├── Cross-modal disentanglement - 2.html
        ├── GPU.html
        ├── LSTM-1.html
        ├── onehot.html
        ├── onehot-drawback.html
        ├── RNN-2.html
        ├── RNN-3.html          ← 推荐
        ├── RNN-4.html
        ├── RNN-5.html
        ├── RNN-6.html
        ├── RNN-7.html
        ├── The fatal flaw of DNN.html
        └── word2vec-1.html
```

---

## 工作流程

### Step 1：生成基础 HTML

1. 读取用户输入的科普内容文本
2. 将文本拼接至以下 Prompt：

```
根据以上内容生成基于纯前端页面单页布局仿PPT换页轮播进行直观图形化可视化的介绍，
加大文字大小，并运用加粗、下划线、斜体、文字颜色、文字背景等强调方式方便进行视频演示。
添加每次切换页面时页面中的各个元素依次"缓入"出现的动画效果(细化到每行文字)。
```

3. 将拼接后的完整 Prompt 发送给 AI（GPT-4o、Claude 等）
4. 等待生成完毕后，将输出保存为 `AI_Animation.html`

**输出路径（由用户指定）：**

- 默认：`桌面/AI_Animation.html`
- 用户指定：`用户指定路径/AI_Animation.html`

---

### Step 2：使用 PPT 模板重构

用户从以下模板中选择一个：

| 选项  | 模板文件                  | 特点             |
| --- | --------------------- | -------------- |
| 1   | `PPT-Generate-1.html` | 简洁风格           |
| 2   | `PPT-Generate-2.html` | 图表丰富           |
| 3   | `PPT-Generate-3.html` | **视觉效果最佳（推荐）** |
| 4   | `PPT-Generate-4.html` | 布局灵活           |
| 5   | `PPT-Generate-5.html` | 科技感             |
| 6   | `PPT-Generate-6.html` | 多图表            |
| 7   | `PPT-Generate-7.html` | 简洁专业           |

**模板路径：** `templates/PPT-Template/`

将以下 Prompt 发送给 AI，重构 Step 1 生成的 HTML 文件：

```
以 templates/PPT-Template/[选定的模板文件] 为模板，重构 [Step1生成的文件路径] 的内容。
将AI_Animation.html的网页的风格转为选定的网页模板的风格，减少PPT演示的字数，
增大文字大小，加强图形化显示，图文并茂，方便视频展示。
将emoji图标换成平面ui库的图标。
```

**⚠️ 强制要求：** Prompt 中必须包含「将emoji图标换成平面ui库的图标」这一指示。

---

### Step 3（可选）：生成流程图风格

当用户输入「生成流程图」时执行。

将 Step 1 生成的 HTML 每相邻两页的内容合并，然后使用以下 RNN 模板之一进行视觉重构：

| 选项  | 模板文件                        | 特点           |
| --- | --------------------------- | ------------ |
| 1   | `RNN-2.html`                 | 对比风格         |
| 2   | `RNN-3.html`                 | **分层卡片（推荐）** |
| 3   | `RNN-4.html`                 | 纵向流程         |
| 4   | `RNN-5.html`                 | 分支结构         |
| 5   | `RNN-6.html`                 | 树状图          |
| 6   | `RNN-7.html`                 | 网格布局         |
| 7   | `LSTM-1.html`                | LSTM展示        |
| 8   | `onehot.html`                | one-hot编码     |
| 9   | `onehot-drawback.html`       | one-hot缺陷     |
| 10  | `word2vec-1.html`            | word2vec       |
| 11  | `Comprehension.html`         | 理解模型         |
| 12  | `GPU.html`                   | GPU架构         |
| 13  | `Cross-modal disentanglement - 2.html` | 跨模态解耦 |
| 14  | `The fatal flaw of DNN.html` | DNN缺陷         |

**模板路径：** `templates/RNN-Template/`

将以下 Prompt 发送给 AI：

```
将 [Step1生成的文件路径] 网页的相邻两页内容合并后
按照 templates/RNN-Template/[选定的RNN模板] 的平面UI样式进行视觉重构，
保持现有颜色方案不变。具体实施要求包括：
精确还原模板中的布局结构、元素间距、字体样式、图标设计和视觉层次；
确保所有交互元素（按钮、表单、导航等）的视觉表现与参考网页一致；
维持原有的颜色值和配色方案；保证修改后的页面在不同设备和浏览器上具有良好的响应式表现；
优化DOM结构以匹配UI设计，同时保持原有功能完整性和交互逻辑不变。
完成后需进行视觉一致性检查，确保实现效果与参考网页达到95%以上的相似度。
```

---

## 完整流程示例

**用户输入：**

```
请帮我制作一个关于TCP三次握手的科普动画，输出到桌面
```

**Step 1 — 生成基础 HTML：**
将用户内容 + PPT Prompt 发给 AI，保存为 `桌面/AI_Animation.html`

**Step 2 — PPT 模板重构：**

> 请以 `PPT-Generate-3.html` 为模板，重构 `桌面/AI_Animation.html`...
> （强制包含 emoji 转图标提示词）

**Step 3（可选）— 流程图风格：**

> 用户输入「生成流程图」
> 请将相邻两页合并后按照 `RNN-3.html` 的样式重构...

---

## 输出路径配置

| 配置方式 | 输出位置                       |
| ---- | -------------------------- |
| 默认   | `桌面/AI_Animation.html`     |
| 用户指定 | `用户指定路径/AI_Animation.html` |

**路径指定方式：** 用户可在输入时说明输出路径，如：

- 「输出到桌面」
- 「保存到 D:\Videos\」
- 「输出到当前项目文件夹」

---

## 注意事项

1. **Step 1 生成时**：确保 Prompt 包含「缓入动画」「加大文字」「图形化」等关键词
2. **Step 2 重构时**：
   - 强制包含「将emoji图标换成平面ui库的图标」
   - 建议使用 `PPT-Generate-3.html`，效果最佳
3. **Step 3 流程图**：仅在用户明确要求时执行，每次合并两页
4. 所有生成的文件路径使用**正斜杠 `/`**，避免跨平台兼容性问题
5. **模板内置**：本 Skill 已包含所有模板文件，无需额外下载或配置

---

## 实战案例：OSI 七层模型

**用户输入：**

> 为了使不同计算机厂家生产的计算机能够相互通信，以便在更大的范围内建立计算机网络，国际标准化组织（ISO）在1978年提出了"开放系统互联参考模型"，即著名的OSI/RM模型...

**Step 1 结果：**
生成 7 页基础 HTML，包含：

- 封面页：OSI 七层模型
- OSI 模型背景介绍
- 七层概览（彩色层级展示）
- 各层核心职责（表格）
- OSI vs TCP/IP 对比
- 传输层核心枢纽
- 总结

**Step 2 结果（PPT-Generate-3）：**

- 青色主题配色 + 粒子效果背景
- 封面旋转圆环装饰
- 交互式七层模型（hover 放大效果）
- OSI vs TCP/IP 对比表格
- 传输层核心枢纽流程图

**Step 3 结果（RNN-3）：**

- 深绿色背景 + 青色粒子效果
- 分层卡片架构：
  - 用户层（L7-L5）：应用层、表示层、会话层
  - 传输层（L4）：TCP/UDP · 数据段
  - 网络层（L3）：IP · 数据包
  - 物理层（L2-L1）：帧/比特流
- 数据封装流程可视化
- 协议标签（每层对应协议用不同颜色标识）
- 底部对比卡片

**最终输出：** `桌面/AI_Animation.html`
