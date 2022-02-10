# 1.2.6 使用图表
插图的两种途径：  
1. 事前准备好的外部图片。（大部分情况下）  
2. LaTeX代码直接在文档中画图。（比如数学的交换图）  
  
## graphicx的插图功能
不由LaTeX内核直接提供，而是由graphicx宏包提供。  
使用方法，在源文件的导言区使用`\usepackage`命令引入宏包：  
```
\documentclass{ctexart}
\usepackage{graphicx}
% ……导言区的其他内容
```
引入graphicx宏包后，可以使用`\includegraphics`命令插图：  
```
\includegraphics[width=3cm]{xiantu.pdf}
```
`\includegraphics`含有两个参数：  
1. 方括号中的可选参数`width=3cm`设置图形在文档中的显示尺寸为**3cm**。  
2. 第二个参数`xiantu.pdf`是图形的文件名（放在源文件所在目录）。  
  
### 其他的参数
`scale=(放缩因子)`  
`height=(高度)`等……  
  
该例子中使用的是`scale=0.6`。  
## 插图命令
插图命令支持的图形文件格式与所使用的编译程序有关，这个例子中使用的是`xelatex`命令编译，支持的图形格式包括**PDF PNG JPG EPS**,这里的图形实际是利用Asymptote语言制作的。  
## 如何放置插图命令
### 错误示范
最好不要在正文的下一行直接写插图命令，如下的写法会把插图夹在第一行字`aaaabbbb`的右边，并使得`aaaabbbb`这一行占用的行空间很大：  
```
aaaabbbb
\includegraphics[width=3cm]{xiantu.pdf}
ccccccccc
```
### 比较好的做法
把图形放在一个“可以变动相对位置”的环境中，称为浮动体（float）。  
浮动体：内部可以给图形加入说明性的标题。  
例子中的插图，完整代码如下：  
```
\begin{figure}[ht]
  \centering
  \includegraphics[scale=0.6]{xiantu.pdf}
  \caption{宋赵爽在《周髀算经》注中作的弦图（仿制），该图给出了勾股定理的一个极具对称美的证明。}
  \label{fig:xiantu}
\end{figure}
```
---

代码解释：  
```
\begin{figure}[ht]
\end{figure}
```
- 使用了figure环境，就是插图使用的浮动体环境：  
- `[ht]`是figure环境的可选参数，表示浮动体可以出现在“环境周围的文本所在处(here)和一页的顶部(top)”。  
- figure环境的内部相当于普通的段落（默认没有缩进）。  
  
  `  \centering`声明，表示后面的内容居中:  
`  \includegraphics[scale=0.6]{xiantu.pdf}`插入图形  
`\caption`命令给插图加上自动编号和标题。  
`\label`命令给图形定义了一个标签，使用这个标签可以在文章的其他地方引入`\caption`产生的编号（后面的章节“编号引用”）。  
---
## LaTex 表格
1. 可以用其他软件做好表格插入LaTeX；  
2. 也可以在LaTeX里完成表格。  
  
设置一个`tabular`环境：  
```
\begin{tabular}{|rrr|}
\hline
直角边 $a$ & 直角边 $b$ & 斜边 $c$ \\
\hline
        3 &         4 &         5 \\
        5 &        12 &        13 \\
\hline
\end{tabular}
```
- `tabular`环境有一个参数；  
- `|rrr|`表示表格有3列，都是右对齐，在第1列前面和第3列后面各有一条垂直的表格线。  
- 在`tabular`环境内部：行与行之间用`\\`隔开。  
- 每行内部的表项使用`&`分割。  
- 表格的横线用`\hline`产生。  
  
将表格看作是一个盒子，它需要被放入一个浮动环境中，也就是table环境。  
完整代码如下：  
```
\begin{table}[H]
\begin{tabular}{|rrr|}
\hline
直角边 $a$ & 直角边 $b$ & 斜边 $c$\\
\hline
3 & 4 & 5 \\
5 & 12 & 13 \\
\hline
\end{tabular}%
\qquad
($a^2 + b^2 = c^2$)
\end{table}
```
在这里`\qquad`用于分隔表格与公式，该命令产生长为2em（大约两个“M”的宽度）的空白。  
因为已经用`\qquad`生成足够长度的空格，所以再用`\end{table}`后的注释符取消换行产生的一个多余空格，正好是预想中的结果。  
table表示位置的参数`[H]`表示：放在这里，不浮动。  
> 因为本例子中表格与正文的语境关系是连在一起的，所以我们本不该用浮动的环境，但在用了浮动环境的情况下，用参数`[H]`就能让它不浮动……  
### 关于`[H]`
`[H]`选项不是LaTeX的table环境使用的参数，而是由float宏包提供的特殊功能。为了让`[H]`能正常运行，还需要再导言区使用`\usepackage{float}`。