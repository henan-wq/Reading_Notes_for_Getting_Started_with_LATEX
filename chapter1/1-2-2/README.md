# 从提纲开始
这应该只是一个提纲，不能直接排版：
```
%-*- coding: UTF-8 -*-
% gougu.tex
% 勾股定理
\documentclass[UTF8]{ctexart}

\title{杂谈勾股定理}
\author{张三}
\date{\today}

\bibliographystyle{plain}

\begin{document}

\maketitle
\tableofcontents
\section{勾股定理在古代}
\section{勾股定理的近代形式}
\bibliography{math}

\end{document}
```
导言区（preamble)：通常用来对文档的性质做一些设置，或自定义一些命令。  
- `%-*- coding: UTF-8 -*-`注释：文件编码UTF-8  
- `% gougu.tex`注释：源文件名gougu.tex  
- `% 勾股定理`注释：源文件的内容  
`\documentclass[UTF8{ctexart}`文档类，因为用到中文所以使用ctexart，还用到`[UTF8]`选项说明编码  
- 以下三条信息并不会马上出现在编译结果中，需要通过后面的`\maketitle`排版：  
    - `\title{杂谈勾股定理}`文章标题  
    - `\author{张三}`作者  
    - `\date{\today}`写作日期  

- `\bibliographystyle{plain}`声明参考文献的格式  

document环境：  
- `\begin{document}`与`\end{document}`声明了一个document环境，论文正文部分。  
- `\maketitle`实际输出论文标题  
- `\tableofcontexts`输出目录  
- `section`开始新的一节。  
- `\bibliographystyle{math}`提示TEX从文献数据库math中获取文献信息，打印参考文献列表。  
  
在正文外的部分，空行不表示任何意义。  

