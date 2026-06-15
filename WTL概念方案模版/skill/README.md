# WTL · 概念方案模版 (白底版)

> **概念方案阶段文本模版** — 华控基金风格的白底概念设计方案模版.
> 14 页 / 3 章 / 拖图替换即出稿.

---

## 模版结构

本设计系统提供 **两种** 概念方案交付形态：

### A · 翻页式概念方案（静态 PPT 形态）

| # | 章节 (中) | 章节 (英) | 包含页 |
|---|---|---|---|
| 1 | 平面布局 | LAYOUT | 平面方案 01 · 平面方案 02 |
| 2 | 概念方向 | DIRECTION | 设计关键词 · 意向 (入口) · 意向 (办公) |
| 3 | 细节概念 | DETAILS | 材料 + 五金 · 家具 + 艺术品 |

外加: 封面 · 目录 · 三个章节开篇 · 下一步 · 致谢, 共 14 页。
文件: `slides/huakong-white.html`。

### B · 动态文本模版（电影化叙事形态）

非翻页 PPT, 而是带自动播放、字幕、运镜淡入的「电影化叙事」骨架,
用于沉浸式空间 / 展厅 / 导览类汇报。内容由一个 `scenes[]` 数组驱动。
文件: `动态文本模版.html`（根目录交付件） · `slides/dynamic-brief.html`（系统版）。

预置 8 种幕型:

| 幕型 | 用途 |
|---|---|
| 封面 | 深底 + 背景图 + 占位标记 |
| 目录 | 浅底章节导览 |
| 章节分隔 | 深底 + 大号 terra 编号 |
| 三栏观点 | 浅底卡片, 末栏 terra 强调 |
| 数字统计 | 深底 · Bahnschrift 滚动数字 |
| 时间轴 | 浅底历程节点 |
| 空间介绍 | 深底 + 背景图 + 右侧信息卡 |
| 结尾 | 深底收束 |

引擎能力: 自动播放 / 中英双语字幕 / 运镜淡入 / `data-count` 数字滚动 /
右侧信息卡 / 进度圆点 / 键盘左右切换 / 双击全屏 / **就地编辑 + 一键导出 HTML**。
配色已全部走 WTL 品牌 token（terra 主强调、moss 次强调、cream/black 版面、Bahnschrift+雅黑）。

---

## 完整文件清单

```
SKILL.md                   — Skill 清单
README.md                  — 本文件
colors_and_type.css        — CSS 变量: 颜色 / 字体 / 字号
fonts/
  Bahnschrift.ttf          — Bahnschrift VF (拉丁 + 数字)
assets/
  wtl-logo.png             — 横向 lockup
  pdf/                     — 60 张示例项目图片
slides/
  huakong-white.html       — 14 页白底模版（翻页式）
  dynamic-brief.html       — 动态文本模版（电影化叙事 · 系统版）
  slides.css               — 共用 chrome
  layouts.css              — 5 章 (住宅) 版式 (兼容保留)
  huakong.css              — 3 章 (办公) 版式 · 白底为默认
  deck-stage.js            — 缩放 + 翻页 + 演讲备注
  image-slot.js            — 拖放图片占位
preview/                   — Design System 标签页规范卡 (颜色/字体/间距/品牌/幕型)
动态文本模版.html          — 动态文本模版（根目录交付件 · 自包含 · 内嵌 logo）
styles.css                 — 设计系统 CSS 入口 (@import colors_and_type.css)
```

## 字体说明

- **拉丁 / 数字**: `fonts/Bahnschrift.ttf` (随包).
- **中文**: 走系统 fallback — 微软雅黑 (Windows) / PingFang SC (macOS) / 思源黑体 / Noto Sans SC.
  系统未安装时, 视觉会回到 system-ui, 字重/字距仍可用.
  如需绝对一致, 请额外把微软雅黑三个 .TTC 放回 `fonts/` 并取消 `colors_and_type.css` 中的注释.

---

## 配色 token

白底版已直接合入 · 核心 CSS — 默认全白背景. 内部信息卡仍保留 paper 暖色 · 在白底上呈微微浅奶层次感.

| Token | Hex | 用途 |
|---|---|---|
| `--paper` | `#f5f2ec` | 信息卡 / 拼图占位的暖底 |
| `--ink` | `#111111` | 正文 / 细线 |
| `--ink-3` | `#6b6b6b` | 标注文字 |
| `--rule` | `#d8d4cc` | 细线分隔 |
| `--terra` | `#b96f3c` | accent — 章节数字、平面图圆点、强调线 |
| `--moss` | `#6b7a5a` | 景观 / 植栽 accent |

白底为默认. 若需要原配色 (奶白 / 深色章节页), 需从原始概念模版重新调 CSS — 该 skill 不交付黑底变体.

---

## 快速上手

### 翻页式（静态 PPT）

1. 复制 `slides/huakong-white.html` 到新文件 `slides/<项目名>.html`.
2. 替换文案: 项目名 / 关键词 / 平面统计.
3. 拖图替换: 浏览器打开后, 把项目实拍图拖进任一 `<image-slot>` 占位, 自动按 id 持久化.
4. 翻页: 左右方向键 / 点击右下角箭头.
5. 导出 PDF: 浏览器打印 (Ctrl/Cmd+P), 每页 1 张 A3 横向.

### 动态文本模版（电影化叙事）

1. 复制 `动态文本模版.html` 到新文件, 或直接在浏览器打开.
2. 点右下角「✎ 编辑」→ 双击任意文字直接改 · 点背景图换图.
3. 改完点「⬇ 导出 HTML」下载一份内容写死的新 HTML.
4. 手动加一幕: 复制一个 `<section class="overlay">` 叠层, 再到底部
   `scenes[]` 数组加一行 `{ov, name, dur, zh, en}`.
5. 翻幕: 左右方向键 / 底部圆点 / 空格自动播放 · 双击全屏.

---

## 关键规则 (不可破坏)

- 不用 emoji 与装饰花字, 只用中点 `·` 与破折号 `—`.
- 无紫蓝渐变, 文字无阴影 (主体图片可以有).
- 全部直角 (`border-radius: 0`), 例外: 平面图上的 terra 圆点.
- 细线只用 1px, 颜色 `--rule` (浅底) 或 `--rule-dark` (深底).
- 数字用 Bahnschrift 拉丁数字, 不用汉字数字.
- 正文用第三人称或无主语.

---

## 调试

- 整体放在 `<deck-stage>` 自定义元素中, 自动按视口缩放.
- 每页有 `data-screen-label` 用于演讲备注与目录定位.
- 如需要给某页加备注, 在 `<head>` 中加 `<script type="application/json" id="speaker-notes">[...]</script>` 数组, 数组长度匹配页数.
