# 1.1.3 "Happy TEXing" 与 “特可爱排版”
程序`1-1-3.tex`：  
1. 打开TEX编辑器：TeXworks；
2. 新建文件；
3. 输入以下内容；
4. 排版选择：pdfLaTeX或XeLaTex；
5. PDF预览窗口会输出编译结果。
  
```
\documentclass{article}

\begin{document}
This is my first document.

Happy \TeX ing!
\end{document}
```
  
`\documentclass{article}`声明了文档的类型是一篇文章  
`\begin{document}`和`end{document}`语句标识出正文的范围；  
`\TeX`表示高低不平的符号。  
  
---
  
程序`1-1-3-chinese-version.tex`：  
```
\documentclass[UTF8]{ctexart}
\begin{document}
\section{文字}
特可爱排版。
\section{数学}
\[
  a^2 + b^2 = c^2
\]
\end{document}
```
`{ctexart}`中文TEX的文章article类型；  
`[UTF8]`文档类的选项，表明了中文所使用的编码；  
两个`\section`命令各自生成了一节的标题；  
被`\[`与`\]`所包裹的是数学公式；  
