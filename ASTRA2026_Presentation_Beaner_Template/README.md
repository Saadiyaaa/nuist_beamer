# NUIST Beamer Presentation Template

南京信息工程大学风格的 16:9 Beamer 演示模板，支持中文、英文、分级观点、逐页参考文献及自适应图文布局。

## 环境要求

- TeX Live 2024 或更新版本（推荐安装完整方案）
- XeLaTeX
- latexmk
- VS Code 用户可选装 LaTeX Workshop

模板使用 TeX Live 自带的 Fandol 中文字体和 TeX Gyre Termes 后备字体；系统安装 Times New Roman 时会优先使用它。因此不依赖特定电脑上的绝对字体路径。

## 编译

在模板根目录运行：

```bash
latexmk main.tex
```

项目级 `.latexmkrc` 会强制使用 XeLaTeX。不要使用 pdfLaTeX 编译。

### VS Code / LaTeX Workshop

直接用 VS Code 打开整个模板目录，而不是只打开 `main.tex`。仓库中的 `.vscode/settings.json` 已将默认 recipe 设置为 `latexmk (XeLaTeX)`。

若 VS Code 曾打开过旧目录，请执行：

1. `Developer: Reload Window`
2. `LaTeX Workshop: Build with recipe`
3. 选择 `latexmk (XeLaTeX)`

## 文件结构

- `main.tex`：内容、占位符及页面布局
- `beamerthemeNUIST.sty`：NUIST 视觉主题
- `nuist_seal.png`：校徽水印
- `nuist_wordmark.png`：校名标识
- `.latexmkrc`：命令行 XeLaTeX 配置
- `.vscode/settings.json`：LaTeX Workshop 配置

图片请使用相对路径，放在模板根目录或 `figures/` 目录，例如：

```latex
\includegraphics[width=\linewidth]{figures/result-a.pdf}
```

## 新环境首次使用

Git 克隆后无需任何缓存文件即可编译。只要目标系统安装了上述 TeX 环境和模板所需宏包，运行 `latexmk main.tex` 即可生成 `main.pdf`。
