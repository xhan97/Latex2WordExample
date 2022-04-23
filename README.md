<!--
 Copyright 2022 Xin Han. All rights reserved.
 Use of this source code is governed by a BSD-style
 license that can be found in the LICENSE file.
-->

# Latex2wordExample

本仓库展示了使用 Pandoc 将 [Springer Lecture Notes in Computer Science (LNCS)](https://www.overleaf.com/latex/templates/springer-lecture-notes-in-computer-science/kzwwpvhwnvfj) LaTeX 模板转化为 Word 的示例

转化中使用的工具安装和命令细节请查看 [Zhihu 文章](https://zhuanlan.zhihu.com/p/455713759) 或者 [My Blog](https://xhan97.github.io/latex/PandocLatex2Word.html)。

## 项目依赖

- Pandoc-2.17.1.1

- Texlive 2021

## 运行

1. 使用 LaTex 正确编译 `.tex` 文件

2. 使用 pandoc 转化

    ```bash
    pandoc samplepaper.tex   --filter pandoc-crossref --citeproc --csl springer-lecture-notes-in-computer-science-alphabetical  --bibliography=reference.bib -M reference-section-title=Reference  -M autoEqnLabels -M tableEqns  -t docx+native_numbering --number-sections -o output.docx
    ```

## 注意

- 由于 Word 无法显示矢量图，因此提前将原 LNCS 模板中使用的矢量图转为 `.PNG` 格式。

- LaTex 编译后确保参考文献已经正确生成。

- 目录中的 `pandoc-crossref.exe` 只匹配  `Pandoc-2.17.1.1`。

## License

BSD license
