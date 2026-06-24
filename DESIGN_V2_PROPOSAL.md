# AI4Rad Lab 主页 v2 设计提案

> 归档版本：`v1-classic`（标签已推送）  
> 当前基线：`340fd56` — 卡片化多页站点，Hero + 研究方向 + 项目 + 资源 + 新闻 + Join Us + 页脚  
> 参考风格：[Weidi Xie](https://weidixie.github.io/) 极简学术主页  
> 核心诉求：降低「AI 味」与模板感，在「极简名片」和「结构完整」之间找到平衡点。

---

## 1. 当前 v1 的问题诊断

1. **视觉噪音过多**：图标、卡片、阴影、按钮、徽章、装饰线密集叠加，模板感强。
2. **信息层级被装饰稀释**：每个 section 都有 `.section-head__line`、卡片标题、图标，读者注意力分散。
3. **Hero 仍像产品落地页**：大标题 + 副标题 + 两个 CTA 按钮，更像 SaaS 产品而非学术实验室。
4. **内容重复**：Projects / Resources / News / Join Us 各自成 section，但内容不多，显得页面冗长。
5. **团队页仍偏产品化**：头像、卡片、标签、hover 动效，与「克制学术」目标有距离。
6. **英文文案不够自然**：如 "Medical Imaging AI Research"、"Meet the Team" 仍偏营销。

---

## 2. 设计原则（v2 统一遵循）

| 原则 | 具体表现 |
|------|---------|
| **内容优先** | 文字与信息本身成为视觉焦点，而非容器和图标。 |
| **减少装饰** | 去掉 section 装饰线、卡片阴影、图标背景、按钮圆角强调。 |
| **字体克制** | 收敛到 1-2 个字体，正文用无衬线，标题用有衬线或同字体不同字重。 |
| **留白充足** | 增加段间距，减少 section 数量，让读者能「呼吸」。 |
| **链接 inline** | 联系方式、论文、GitHub 直接写在句子里，不单独做成按钮或资源卡片。 |
| **可信而非包装** | 用具体期刊、项目、机构名替代形容词和 buzzword。 |

---

## 3. 方案 A：Minimal Academic（向 Weidi Xie 靠拢）

### 整体定位
把 AI4Rad 主页当作一张「实验室名片」：单页、纯文本、无导航、无卡片。

### 首页结构（单页长文）

```
AI4Rad Lab
上海市第六人民医院 · 上海交通大学医学院附属 · 放射介入科

我们研究医学影像人工智能，聚焦于视觉基础模型、多模态大语言模型、影像生成与临床 AI 泛化性。相关工作发表于 npj Digital Medicine、Radiology、European Radiology、ICLR、CVPR 等。

团队由李跃华教授领衔，张瑞鹏、孙正为课题负责人。更多信息见团队页面与 Google Scholar。

研究方向：
· 视觉基础模型与医学影像分析
· 多模态大语言模型与结构化报告
· 影像生成、去噪与质量增强
· 临床 AI 的跨分布泛化性

代表性项目：
· BrainMIND — 基于 LLM 的脑 MRI 报告诊断印象生成（npj Digital Medicine 2026）
· 脑血管与卒中 AI — 动脉瘤检测、ASPECTS、血栓分析（Radiology / European Radiology）

联系：zhangrp@sjtu.edu.cn · GitHub · Google Scholar
加入我们：招收医学影像 AI 方向博士、硕士研究生。

© 2026 AI4Rad Lab
```

### 改动点
- 删除固定导航栏，仅保留语言切换（右上角小字或页脚）。
- 删除 Hero 区、按钮、卡片、图标、装饰线。
- 研究方向用 4 个 bullet points 呈现。
- 项目只保留标题 + 期刊/会议，链接 inline。
- 新闻、资源、Join Us 合并为 1-2 个段落。
- 页脚极简：只保留一行版权和机构名。

### 风险
- 信息密度高，对初次访问者不够友好。
- 失去多页结构，团队详情需要展开或跳转。
- 与医院/科室品牌视觉（logo、配色）的关联变弱。

---

## 4. 方案 B：Structured Restraint（结合版，推荐）

### 整体定位
保留「实验室主页」的完整结构（多页、团队、项目），但大幅降低视觉噪音，让页面更像学术机构的「印刷品」而非「网页模板」。

### 首页结构

```
[顶部导航：仅文字链接，无 logo、无背景、无模糊]
AI4Rad Lab    Team    Publications    Contact    中文

[Hero：一行名字 + 一句话 + 一行 inline 链接]
AI4Rad Lab
医学影像人工智能研究，上海市第六人民医院放射介入科。
Email · Google Scholar · GitHub · Team

[研究方向：无图标，纯文本列表或两列短文]
Research
1. 视觉基础模型与影像分析
2. 多模态大语言模型与结构化报告
3. 影像生成与质量增强
4. 临床 AI 的跨分布泛化性

[项目：标题 + 一句话 + 链接，无卡片]
Selected Projects
BrainMIND — 基于 LLM 的脑 MRI 报告诊断印象生成（npj Digital Medicine 2026）
脑血管与卒中 AI — 动脉瘤检测、ASPECTS、血栓分析（Radiology / European Radiology）

[新闻：日期 + 短句，无背景色]
News
2026.04  BrainMIND 发表于 npj Digital Medicine
2025.09  卒中 ASPECTS 研究被 European Radiology 接收
2024.10  脑动脉瘤 CTA 检测工作发表于 Radiology

[页脚：极简一行]
© 2026 AI4Rad Lab · Shanghai Sixth People's Hospital · SJTU School of Medicine
```

### 改动点
- 导航栏保留，但去掉 logo、背景模糊、圆角 active 状态，改为纯文字链接。
- Hero 区保留标题，但去掉副标题、按钮、机构 logo，链接 inline。
- 研究方向去掉图标和卡片，改为 2×2 或单列文本。
- 项目去掉卡片、图片、标签，改为列表或带下划线的链接文本。
- 资源 section 删除，合并进 Hero 的 inline 链接。
- Join Us 删除或合并进页脚/联系段落。
- 页脚只保留一行文字，去掉完整 lab logo 和机构 logo。
- 字体从 3 个收敛到 2 个（正文 + 标题）。
- 深色模式保留，但降低饱和度和阴影。

### 团队页改动
- 删除 leader/PI 的大卡片和头像，改为按类别文本列表。
- 成员信息：名字 + 学位 + 学校 + 年份 + 链接（若有个人页）。
- 保留头像但缩小，或统一为首字母占位符。
- 去掉 hover 动效、标签、边框。

### 个人页改动
- 保留照片，但布局更简洁：照片 + 名字/职位 + 一段简介 + 联系方式 + 论文列表。
- 论文列表去掉图片、标签、引用数，只保留标题/作者/期刊/链接。
- 删除学术服务、荣誉奖项等 section（或折叠）。

### 优势
- 保留多页结构和完整信息，适合实验室官网。
- 视觉更克制，降低模板感和 AI 味。
- 仍然符合医院/学术机构的正式感。

---

## 5. 推荐

**推荐方案 B（Structured Restraint）**。原因：
1. 团队主页需要承载多人、多项目、招生信息，完全单页会损失结构性。
2. 医院/科室背景需要一定正式感，Weidi Xie 的个人极简风格对实验室可能过于随意。
3. 方案 B 可以分阶段实施：先改首页，再改团队页，最后改个人页。

---

## 6. 实施建议

1. 从 `main` 切出新分支 `v2-structured-restraint`。
2. 先重写首页（`index.html` / `index_ch.html`）和 CSS 主样式。
3. 再简化团队页（`team.html` / `team_ch.html`）和 `js/main.js` 的渲染逻辑。
4. 最后精简个人页（`members/index.html`）。
5. 每完成一页用本地 server + 截图验证。
6. 完成后合并到 `main` 并打标签 `v2-structured-restraint`。

---

## 7. 需要用户确认的问题

1. 是否选择方案 B 作为方向？还是倾向方案 A？
2. 首页是否保留导航栏？（方案 A 删除，方案 B 保留极简导航）
3. 团队页是否保留头像？（方案 B 建议缩小或改为首字母占位）
4. 是否保留深色模式？
5. 是否需要保留机构 logo（六院/交大）？方案 B 建议仅在页脚保留文字。
