# LaTex相关注释与命令

## 日常使用

verbatim：原文插入

\verb=：文本间原文插入

itemize：无序列表

enumerate：有序列表

> [!INPORTANT]
> 分项时，需用\item进行标注
>
> **彼此之间可以进行不同种类的嵌套**

分行：\ \ 或者 \newline

分段：\par 或 空一行

等级与段落：

1. \verb=\part{}= 篇(最高级) \par
2. \verb=\chapter{}= 章（第二级） \par
3. \verb=\section{}= 节（第三级） \par
4. \verb=\subsection{}= 小节（第四级） \par
5. \verb=\subsubsection{}= 小小节（第五级） \par

文本加粗：\textbf

文本斜体：\textit

文本下划线：\underline

figure必备环境：

1. 提供浮动机制，使得图片根据文本分布进行自动排列
2. 对图片进行**标序**，自动生成标号，**可用 \caption{} 在标注后进行图片说明**

## 数学公式与表达

equation：**单个公式且居中处理**

align：**多行公式组合且有对其效果**

辅助数学公式网站：https://www.latexlive.com/