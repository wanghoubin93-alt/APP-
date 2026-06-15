---
name: wtl-concept-white
description: 使用此 skill 生成华控基金风格的白底概念设计方案模版 (3 章 14 页)。包含字体、样式 token、平面图占位、意向图拼接、规格卡。设计师拖图替换即可出稿。
user-invocable: true
---

# WTL · 概念方案模版 (白底版)

读完 `README.md` 再开始 — 包含完整的设计系统说明 (语调、配色、字体、版式、图标规则)。

## 用途

生成 **概念方案汇报** 文档。本系统提供两种形态：

**A · 翻页式（静态 PPT）** — `slides/huakong-white.html`

模版结构 (3 章 14 页):

1. **平面布局 · LAYOUT** — 平面方案 01 / 02
2. **概念方向 · DIRECTION** — 设计关键词 + 空间意向参考
3. **细节概念 · DETAILS** — 材料 + 五金 + 家具 + 艺术品

每页都带 WTL logo、项目名、页码。

**B · 动态文本模版（电影化叙事）** — `动态文本模版.html` / `slides/dynamic-brief.html`

非翻页 PPT，而是带自动播放、中英双语字幕、运镜淡入的沉浸式叙事骨架，
适合空间 / 展厅 / 导览类汇报。内容由 `scenes[]` 数组驱动，预置 8 种幕型
（封面 / 目录 / 章节分隔 / 三栏观点 / 数字统计 / 时间轴 / 空间介绍 / 结尾）。
支持就地编辑 + 一键导出新 HTML。配色已全部走 WTL 品牌 token。

## 使用方式

1. **确认项目基础信息** (若未提供则询问):
   - 项目名称 (中 + 英)
   - 业主、位置、面积
   - 项目类型 (住宅 / 办公 / 商业 / 酒店)
   - 概念关键词 (3-4 个)
   - 是否提供平面图 (SVG / PNG / CAD)?
   - 意向图分几页 — 一区一页还是合并?

2. **复制模版** `slides/huakong-white.html` 到新文件,
   逐页替换文案 + 图片. 保留 chrome (页眉、页脚、章节眉头) 不动.

3. **图片占位** 用 `<image-slot>` — 不要外链网图.
   设计师拖项目实拍图进去.

4. **配色 token** 在 `colors_and_type.css` 中. 不要新增颜色.
   如果设计师要新色, 推回最近的现有 token.

## 文件清单

```
SKILL.md
README.md
colors_and_type.css      — 全部 token (paper / ink / terra / 字号)
fonts/
  Bahnschrift.ttf        — 拉丁 + 数字 (变宽 75-100%)
                           中文字体走系统栈 (微软雅黑 / PingFang SC)
assets/
  wtl-logo.png           — 横向 lockup
  pdf/                   — 示例项目图片 (60 张)
slides/
  huakong-white.html     — 14 页白底模版 (3 章 · 办公 · 翻页式)
  dynamic-brief.html     — 动态文本模版 (电影化叙事 · 系统版)
  slides.css             — 共用 chrome
  layouts.css            — 5 章版式 (兼容)
  huakong.css            — 3 章办公版式 · 白底为默认
  deck-stage.js          — 缩放 + 翻页 + 演讲备注
  image-slot.js          — 拖放图片占位
preview/                 — Design System 标签页规范卡
动态文本模版.html        — 动态文本模版 (根目录交付件 · 自包含)
styles.css               — 设计系统 CSS 入口
```

## 不可破坏的规则

- **不用 emoji, 不用装饰花字.** 只用 `·` 和 `—`.
- **无紫蓝渐变, 文字无阴影.** 阴影仅用在主体图片上.
- **直角.** `border-radius: 0`. 唯一例外: 平面图上的 terra 圆点.
- **细线 1px.** 不用 2px, 不用虚线 (terra 示意线除外).
- **不用填充图标集.** 平面图 + Bahnschrift 数字承担图形语言.
- **正文用第三人称或无主语.** 不用 "我们" / "您" / "我".
- **数字用 Bahnschrift 拉丁数字**, 不用汉字数字.

## 接到任务但没有更多信息时

询问:

1. 项目是什么? (名称、类型、位置、面积)
2. 用 14 页 3 章办公模版, 还是定制章节?
3. 平面图、意向图、细节图由设计师提供, 还是先留拖放占位?
4. 关键词 / 定位是否已锁定?

然后输出 HTML 文档 `slides/<项目>.html`, 请设计师审阅迭代.
