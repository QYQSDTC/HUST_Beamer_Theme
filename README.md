# HUST Beamer Theme

华中科技大学 (Huazhong University of Science and Technology) LaTeX Beamer 演示文稿主题。

基于 Berkeley 侧边栏风格设计，采用华科蓝 (`#00518F`) 配色方案。

## 预览

![demo](demo.pdf)

## 特性

- **华科蓝配色** — 标题、侧边栏、区块等统一使用 HUST 品牌色
- **Berkeley 侧边栏布局** — 左侧导航栏自动显示章节和小节
- **自定义标题页** — 支持三个 Logo 位（左/中/右），带装饰条
- **多种区块样式** — `block`、`alertblock`、`exampleblock` 均有对应配色
- **页脚信息栏** — 显示页码、作者和标题
- **16:9 和 4:3 双比例支持**

## 快速开始

1. 将 `beamerthemeHUST.sty` 放到 `.tex` 文件同目录下
2. 在文档中使用主题：

```latex
\documentclass[aspectratio=169]{beamer}
\usepackage{ctex}  % 中文支持
\usetheme{HUST}

% 设置 Logo（可选，留空则不显示）
\hustlogo{your-hust-logo.png}
\physicslogo{your-school-logo.png}
\gravitylogo{your-lab-logo.png}

\title{Your Title}
\subtitle{Your Subtitle}
\author{Your Name}
\institute{华中科技大学}
\date{\today}

\begin{document}
\begin{frame}[plain]
  \titlepage
\end{frame}
\end{document}
```

> **注意：** 标题页必须使用 `[plain]` 选项以隐藏侧边栏。

## 编译

使用 XeLaTeX 编译（需编译两次以获得正确页码和导航）：

```bash
xelatex demo.tex && xelatex demo.tex
```

## 自定义

### 配色

主题定义了以下颜色，可在导言区覆盖：

| 颜色名 | 色值 | 用途 |
|--------|------|------|
| `HUSTBlue` | `#00518F` | 主色调 |
| `HUSTBlueDark` | `#003A66` | 深色辅助 |
| `HUSTBlueLight` | `#B8D4E8` | 浅色辅助 |
| `HUSTGray` | `#F2F2F2` | 区块背景 |

### Logo

三个 Logo 命令均为可选，留空即不显示：

- `\hustlogo{}` — 标题页左上
- `\physicslogo{}` — 标题页顶部居中
- `\gravitylogo{}` — 标题页右上

## 依赖

- TeX Live 2020+（推荐 2024+）
- XeLaTeX + `ctex` 宏包（中文支持）
- `tikz`、`graphicx`

## 许可证

MIT License
