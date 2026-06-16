# 视觉素材制作指南

> 人是视觉动物。表格 > 文字，截图 > 描述，GIF > 说明书。
> README 里每个"放截图"的位置都应该真的有截图，不是一句"效果如图"。

## 什么时候需要什么素材

| 场景 | 最佳形式 | 次选 | 制作方式 |
|------|---------|------|---------|
| 展示产出物（PPT/文档/页面） | 真实截图 | 对话示例 | 手动截图 or huashu-design 生成后截图 |
| 展示交互流程（多步操作） | GIF/MP4 | 编号截图序列 | huashu-design 动画导出 or 录屏 |
| 展示 Before/After 对比 | 并排截图/diff 图 | 表格文字对比 | huashu-design 做对比信息图 |
| 展示架构/流程逻辑 | 流程图 | Mermaid 代码块 | excalidraw-diagram |
| 展示数据/指标 | 图表 | 表格 | show_widget (SVG) |
| 展示 UI/设计效果 | 高保真原型截图 | 线框图 | huashu-design or superdesign |

## 可用 Skill 工具箱

### 1. huashu-design（推荐首选）

**能力：** HTML 做高保真原型、信息图、幻灯片、动画 Demo，可导出 GIF/MP4/截图
**适用场景：**
- 产品截图模拟（没有真实产品时用 HTML 生成效果图）
- Before/After 对比信息图（一张图胜过两列文字）
- 流程动画 GIF（多步操作的最佳展示方式）
- 设计风格展示（多种视觉变体并排）

**调用示例：**
```
对 Agent 说：「用 huashu-design 帮我做一张 Before/After 对比信息图，
左边是 [旧方式]，右边是 [新方式]，风格用 [瑞士极简/杂志风/...]」
```

**README 场景映射：**
- Type 1 (Output) 的"效果展示" → 用 huashu-design 做产品截图画廊
- Type 2 (Efficiency) 的"Before/After" → 用 huashu-design 做对比信息图
- Type 6 (Platform) 的"Skill 展示卡片" → 用 huashu-design 做 GIF demo

### 2. excalidraw-diagram

**能力：** 手绘风格流程图/架构图/概念图，产出 .excalidraw + PNG
**适用场景：**
- 工作流可视化（"堂审四幕"的流程图）
- 架构图（多 Agent 协作图）
- 概念关系图

**调用示例：**
```
对 Agent 说：「用 excalidraw-diagram 画一个这个 skill 的工作流程图」
```

**README 场景映射：**
- Type 2 (Efficiency) 的"使用流程" → 流程图比表格更直观
- Type 7 (Security) 的多 Agent 架构 → 架构图
- Type 8 (Science) 的 pipeline → 流水线图

### 3. show_widget（内置，无需安装）

**能力：** SVG/HTML 内联渲染，适合图表和交互组件
**适用场景：**
- 数据图表（柱状图/饼图/趋势图）
- 简单的对比可视化
- 交互式演示

### 4. canvas-design（需从 marketplace 安装）

**能力：** 基于设计哲学创作视觉艺术，产出 PNG/PDF
**适用场景：**
- 品牌海报
- README 头图（hero image）

### 5. superdesign（前端设计）

**能力：** 着陆页/Dashboard/UI 组件设计
**适用场景：**
- 展示前端类 skill 的 UI 效果
- 做产品着陆页风格的 README 头图

## 制作流程

### 快速路径（5 分钟内完成）

1. **文字素材先行** — 先用模板写完 README 文字内容
2. **标记视觉坑位** — 在需要图片的地方留 `<!-- TODO: 视觉素材 -->` 标记
3. **批量制作** — 调用 huashu-design 一次性做完所有视觉素材
4. **替换占位符** — 把生成的图片路径填回 README

### 没有设计 Skill 时的后备方案

| 方案 | 怎么做 | 适用 |
|------|--------|------|
| Mermaid 代码块 | GitHub 原生渲染，写在 ```mermaid 里 | 流程图/时序图 |
| ASCII 表格 | 纯文本，零依赖 | 简单对比 |
| 对话示例代码块 | 用 ``` 包裹 User/Agent 对话 | 交互展示 |
| shield.io 徽章 | `![](https://img.shields.io/badge/...)` | 状态/指标 |

## 视觉规范

- **宽度：** 表格内嵌图用 `width="400"`，全宽截图用 `width="800"`
- **格式：** 截图用 PNG，动画用 GIF（<5MB），长流程用 MP4 链接
- **Alt text：** 每个图片必须有描述性 alt text（无障碍 + SEO）
- **暗色模式：** 避免纯白背景截图，用浅灰或透明底
- **存放位置：** `assets/` 目录下，按类型分子目录（`assets/screenshots/`、`assets/gifs/`）
