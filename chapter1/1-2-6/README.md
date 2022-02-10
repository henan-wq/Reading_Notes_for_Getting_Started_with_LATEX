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
- 使用了figure环境，就是插图使用的浮动体环境：  
- `[ht]`是figure环境的可选参数，表示浮动体可以出现在“环境周围的文本所在处(here)和一页的顶部(top)”。  
- figure环境的内部相当于普通的段落（默认没有缩进）。  
```
\begin{figure}[ht]
\end{figure}
```
  
  `  \centering`声明，表示后面的内容居中:  
`  \includegraphics[scale=0.6]{xiantu.pdf}`插入图形  
`\caption`命令给插图加上自动编号和标题。  
`\label`命令给图形定义了一个标签，使用这个标签可以在文章的其他地方引入`\caption`产生的编号（后面的章节“编号引用”）。  
