# 1.2.7 自动化工具
在提纲中已经用过`\bibliographystyle`命令声明了参考文献的格式；  
又用`\bibliography`命令要求打印出参考文献列表。  
但是目前还没有产生任何文献列表，因为我们没有定义“参考文献数据库”。  
  
BIBTEX使用的参考文献数据库是一个后缀名为`.bib`的文件，我们可以在代码中定义一个包含3条文献的数据库文件`math.bib`：  
```
% This file was created with JabRef 2.6
% Encoding: UTF8

@BOOK{Kline,
  title = {古今数学思想}，
  publisher = {上海科学技术出版社},
  year = {2002},
  author = {克莱因}
}

@ARTICLE{quanjing,
  author = {曲安京},
  title = {商高、赵爽与刘徽关于勾股定理的证明},
  journal = {数学传播},
  year = {1998},
  volume = {20},
  number = {3}
}

@BOOK{Shiye,
  title = {几何的有名定理},
  publisher = {上海科学技术出版社},
  year = {1986},
  author = {矢野健太郎}
}
```
