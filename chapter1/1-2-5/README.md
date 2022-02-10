# 1.2.5 遭遇数学公式
## 正文公式（in-text formula)或行内公式(inline formula)  
最简单的输入方法，两个美元符号即可：  
```
$a+b$
```
## 显示公式
对于比较长的公式，一般单独居中写一行；还给公式编号便于后面引用。这种公式被称为“显示公式”或“列表公式”(displayed formula）。  
使用equation环境就可以方便地输入这种公式  
```
\begin{equation}
  a(b+c) = ab + ac
\end{equation}
```
## 角符号
`$\angle ACB = \pi / 2$`  
## 数学结构（上下标、分式、根式等）。
上标：  
```
\begin{equation}
AB^2 = BC^2 + AC^2.
\end{equation}
```
数字后面的角度（空心圆）符号，也是通过上标输入的：
```
$^\circ$
```
> `\circ`其实是一个通常用来表示函数复合的二次运算符“o”。我们把它的上标借用来表示角度。  
那么90°就可以这么表示：  
```
$90^\circ$
```
其他的数学公式在第四章节。  

## 本章关于例子的一个困惑：
曾在正文中插入过定理：  
1. `\begin{thm}`与`\end{thm}`  
2. 在定理后插入正文和公式  
3. `\end{thm}`的位置似乎可以放在正文和公式后面的位置，只要在下一个`\section`之前就不会有问题。  
4. “把定理的`\end{thm}`放在了紧跟定理内容的后方”产生的定理与正文行间距会更宽。  
  
例子如下：  
```
\section{勾股定理的近代形式}
勾股定理可以用现代语言表述如下：
\begin{thm}[勾股定理]
直角三角形斜边的平方等于两腰的平方和。

可以用符号语言表述为：设直角三角形 ABC，其中 $\angle C = 90^\circ$，则有
\begin{equation}
  AB^2 = BC^2 + AC^2.
\end{equation}
\end{thm}

\bibliography{math}
```
与  
```
\section{勾股定理的近代形式}
勾股定理可以用现代语言表述如下：
\begin{thm}[勾股定理]
直角三角形斜边的平方等于两腰的平方和。
\end{thm}

可以用符号语言表述为：设直角三角形 ABC，其中 $\angle C = 90^\circ$，则有
\begin{equation}
  AB^2 = BC^2 + AC^2.
\end{equation}


\bibliography{math}
```