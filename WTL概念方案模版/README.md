# WTL · 概念方案模版（白底版）— 设计系统

> 由 Claude Design 导出的设计稿（`wtl-template`）实现到本仓库。
> 原始项目名：`WTL 概念方案模版-白色调版 (Template)`。

这是一套**概念方案阶段**的白底设计系统，提供两种汇报形态，并附带品牌
token、字体、规范展示卡与 skill 文档。所有文件为自包含的 HTML/CSS/JS，
双击即可在浏览器打开。

## 目录结构

```
colors_and_type.css     设计系统核心 token（颜色 / 字体 / 字号 / 间距）
styles.css              设计系统 CSS 入口（@import colors_and_type.css）
动态文本模版.html        动态文本模版 · 根目录交付件（自包含 · 内嵌 logo）
fonts/
  Bahnschrift.ttf       拉丁 + 数字字体（变宽 75–100%）
assets/
  wtl-logo.png          横向 logo lockup
  pdf/                  60 张示例项目图片（模版默认占位图）
slides/
  huakong-white.html    A · 翻页式概念方案（14 页 / 3 章 · 静态 PPT）
  dynamic-brief.html    B · 动态文本模版（电影化叙事 · 系统版）
  huakong.html          办公版式参考稿
  slides.css            共用 chrome（页眉 / 页脚 / 页码）
  huakong.css           3 章办公版式（白底为默认）
  layouts.css           5 章住宅版式（兼容保留）
  deck-stage.js         缩放 + 翻页 + 演讲备注
  image-slot.js         拖放图片占位
preview/                Design System 标签页规范卡（颜色 / 字体 / 间距 / 品牌）
skill/                  打包版 skill（含 README.md / SKILL.md / 自带副本）
```

## 两种汇报形态

- **A · 翻页式（静态 PPT）** — `slides/huakong-white.html`
  14 页 / 3 章（平面布局 · 概念方向 · 细节概念），每页带 WTL logo、项目名、
  页码。设计师把项目实拍图拖进 `<image-slot>` 占位即可出稿。

- **B · 动态文本模版（电影化叙事）** — `动态文本模版.html` / `slides/dynamic-brief.html`
  带自动播放、中英双语字幕、运镜淡入的沉浸式叙事骨架，由 `scenes[]` 数组驱动，
  预置 8 种幕型（封面 / 目录 / 章节分隔 / 三栏观点 / 数字统计 / 时间轴 /
  空间介绍 / 结尾）。支持就地编辑 + 一键导出新 HTML。

## 字体说明（重要）

- 拉丁 / 数字走随包的 `fonts/Bahnschrift.ttf`。
- 中文默认走**系统字体栈**（微软雅黑 / PingFang SC / 思源黑体 / Noto Sans SC）。
- 原始设计稿附带的 `MSYH.TTC` / `MSYHL.TTC` / `MSYHBD.TTC`（共约 48 MB）
  在 `colors_and_type.css` 中**默认被注释、未启用**，因此**未纳入本仓库**以
  避免无谓体积。如需绝对一致的中文呈现：把这三个 `.TTC` 放回 `fonts/` 目录，
  并取消 `colors_and_type.css` 顶部 `@font-face` 注释即可。

## 不可破坏的品牌规则

- 不用 emoji 与装饰花字，只用中点 `·` 与破折号 `—`。
- 无紫蓝渐变，文字无阴影（仅主体图片可带阴影）。
- 全部直角（`border-radius: 0`），唯一例外：平面图上的 terra 圆点。
- 细线只用 1px，颜色 `--rule`（浅底）或 `--rule-dark`（深底）。
- 数字用 Bahnschrift 拉丁数字，不用汉字数字。
- 正文用第三人称或无主语。

完整设计系统说明见 `skill/README.md` 与 `skill/SKILL.md`。
