# 1.2.4 命令与环境
## 脚注
例如在正文“在欧几里德”后加脚注：  
```
欧几里德\footnote{欧几里德，……}
```
`\footnote`后面花括号的部分是命令的参数，也是脚注的内容。  
## 强调（emphasis）
```
……的整数称为\emph{勾股数}。
```
用`\emph`命令改变字体形状。  
## LaTEX 命令宏的格式
- 无参数：`\command`;  
- 有n个参数：`\command(arg1)(arg2)...(argn)`  
- 有可选参数：`\command[(argopt)](arg1)(arg2)...(argn)`  
  
## quote 环境
### quote 环境缩进
quote环境即以`\begin{quote}`和`\end{quote}`为起止位置的部分。（将环境中的内容单独分行，增加缩进和上下间距排印，以突出引用的部分。）  
  
### quote 字体样式
> 若需要改变quote环境中的引用的内容的字体，还需要使用改变字体的命令：  
```
\begin{quote}
\zihao{-5}\kaishu 引用的内容。
\end{quote}
```
- `\zihao`是有一个参数的命令，选择字号（-5就是小五号）；  
- `\kaishu`是没有参数的命令。（这里的意思是将字体切换为楷书。需要用“空格”将命令`\kaishu`与需要引用的内容分隔开。  