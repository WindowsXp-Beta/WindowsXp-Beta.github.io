---
title: "LaTeX笔记"
date: 2021-02-01T23:16:01+08:00
draft: false
toc: true
---

## $\LaTeX$学习笔记

### 获取帮助文档
在terminal中输入 `texdoc` 宏包的名字
### 注释
`%` 
段注释：`\iffalse……\fi`
### 导言区
```LaTeX
%导言区
\documentclass[]{article}
%report letter book……   
%ctexart ctexbook ctexreport 用这个类就不用usepackage{ctex}了
\usepackage[宏包选项]{宏包名}%可以一次性调用多个宏包，中间用逗号间隔。
\title{……}
\author{……}
\date{……}     \today
```
`documentclass`[ ]中可指定选项
- `10pt, 11pt, 12pt` 指定文档的基本字号。默认为 `10pt`。
- `a4paper, letterpaper, … `指定纸张大小，默认为美式信纸 `letterpaper` （8:5 × 11 英寸）。
可指定选项还包括 `a5paper， b5paper， executivepaper 和 legalpaper`。
- `twoside, oneside` 指定单面/双面排版。双面排版时，奇偶页的页眉页脚、页边距不同。 `article`和 `report` 默认为 oneside， book 默认为 twoside。
- `onecolumn`, `twocolumn` 指定单栏/双栏排版。默认为 `onecolumn`。
- `openright`, `openany` 指定新的一章 `\chapter` 是在奇数页（右侧）开始，还是直接紧跟着上一页开始。 `report` 默认为 `openany`， `book` 默认为 `openright`。对 `article` 无效。
- `landscape` 指定横向排版。默认为纵向。
- `titlepage, notitlepage` 指定标题命令 `\maketitle` 是否生成单独的标题页。 `article` 默认为
- `notitlepage， report 和 book` 默认为 `titlepage`。
- `fleqn` 令行间公式左对齐。默认为居中对齐。
- `leqno` 将公式编号放在左边。默认为右边。
- `draft, final` 指定草稿/终稿模式。草稿模式下，断行不良的地方会在行尾添加一个黑色方块。默认为 final。
### $\LaTeX$ 中的宏
#### 命令
   命令通常以反斜线开头，可以带零到多个参数。命令也可以是直接输出某种结果；也可以改变一个状态，此时$\LaTeX$用花括号 {} 分组或环境作为状态改变的作用域。
   例如 `\em abc` 改变字体以强调一些文字，得到 `abc`；而带参数的命令 \emph{abc} 可得到同样的效果。
#### 环境
   环境的格式为
   `\begin{env}`
   环境的内容
   `\end{env}`
   例如对齐环境：
   ```LaTeX
    \begin{center} … \end{center} %居中
    \begin{flushleft} … \end{flushleft} %左对齐
    \begin{flushright} … \end{flushright} %右对齐
   ```
#### 设置页面参数
`geometry`宏包
比如设置 $\textbf{Microsoft Word}$ 习惯的A4页面
`\usepackage[left=1.25in,right=1.25in,top=1in,bottom=1in]{geometry}`

## 正文
### 各种符号输入
`# $ % { } \ & _ ^ ~ `需要转义输入，即符号前加上`\`输入，其中，`\^{},\~{}`应如此输入，不然会被当成重音效果。又因为`\\`表示换行，所以`\`需以`\textbackslash`输入。
双引号`“”`：` ``'' `
空格：`~`用于产生一个不会断行的空格。
具体参考symbols文档。
>希腊字母
>\alpha产生字符α;\beta产生字符β；\gamma产生字符γ；\delta产生字符δ;\epsilon产生字符ε; \zeta产生字符ζ；\eta产生字符η;\theta产生字符9; \iota产生字符$\iota$；\kappa产生字符κ；\1ambda产生字符λ；\mu产生字符μ；\xi产生字符ξ：\nu产生字符ν；\o产生字符o； \pi产生字符π；\ rho产生字符ρ；\sigma产生字符σ；\tau产生字符$\tau$;\upsilon产生字符υ；\phi产生字符Φ；\chi产生字符Χ；\psi产生字 符Ψ；\omega产生字符ω。**大写希腊字母即将首字母大写（如\Alpha产生 $\Alpha$）。**

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200726214828517.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjAwMTcyMg==,size_16,color_FFFFFF,t_70)
### 数学公式
[生成LaTeX数学公式](http://latex.codecogs.com/eqneditor/editor.php)
#### 行内（inline）公式
使用一对符号`$ $` 来标示。如 `$a+b=c$`。
#### 显示（display）公式
简单的不编号公式用命令 `\[` 和 `\]` 标示。（不要使用双美元符号 `$$ $$`）
基本的编号的公式用 equation 环境。
更复杂的结构，使用 amsmath 宏包提供的专门的数学环境。（不要使用 eqnarray 环境）
一些其他手段

```LaTeX
\begin{displaymath}
a+b=b+a
\end{displaymath}
```
多行公式：(lshort-zh-cn p44-p45)
```LaTeX
\usepackage{amsmath}
\usepackage{amssymb}
```
在document中
```LaTeX
\begin{gather(gather*不带编号的多行公式)}
a+b=b+a\\ 
%用\\进行换行，换行公式即带上编号，一个公式内部也可换行
......
\end{gather(gather*)}
```
或者使用`\notag`阻止编号
```LaTeX
\begin{align(align*不带编号)}
x &=......%按照&进行对齐
y &=......
\end{align(align*)}
```
#### 数组和矩阵
(lshort-zh-cn p45-p46)
例：
```LaTeX
\[ \mathbf{X} = \left(
\begin{array}{cccc}
x_{11} & x_{12} & \ldots & x_{1n}\\
x_{21} & x_{22} & \ldots & x_{2n}\\
\vdots & \vdots & \ddots & \vdots\\
x_{n1} & x_{n2} & \ldots & x_{nn}\\
\end{array} \right) \]
```
$$ \mathbf{X} = \left(
\begin{array}{cccc}
x_{11} & x_{12} & \ldots & x_{1n}\\
x_{21} & x_{22} & \ldots & x_{2n}\\
\vdots & \vdots & \ddots & \vdots\\
x_{n1} & x_{n2} & \ldots & x_{nn}\\
\end{array} \right) 
$$
```LaTeX
\[ |x| = \left\{
\begin{array}{rl}
-x & \text{if } x < 0,\\
0 & \text{if } x = 0,\\
x & \text{if } x > 0.
\end{array} \right. \]
```
$$ |x| = \left\{
\begin{array}{rl}
-x & \text{if } x < 0,\\
0 & \text{if } x = 0,\\
x & \text{if } x > 0.
\end{array} \right. $$
其实amsmath还提供了`cases`环境来制造这种效果
```LaTeX
\[ |x| =
\begin{cases}
-x & \text{if } x < 0,\\
0 & \text{if } x = 0,\\
x & \text{if } x > 0.
\end{cases} \]
```
$$ |x| =
\begin{cases}
-x & \text{if } x < 0,\\
0 & \text{if } x = 0,\\
x & \text{if } x > 0.
\end{cases} $$
#### 定理环境
(lshort-zh-cn p49-p51)
#### 数学字体 
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200726214936161.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjAwMTcyMg==,size_16,color_FFFFFF,t_70)

> difference between \mathrm and \operatorname
>
> `\mathrm{xyz}` behaves like an ordinary letter, while `\operatorname{xyz}` behaves like function names such as `\sin`

#### 数学符号尺寸

![apqrsH.png](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9zMS5heDF4LmNvbS8yMDIwLzA3LzI2L2FwcXJzSC5wbmc?x-oss-process=image/format,png)
#### 数学重音
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200726215020299.jpg)
#### 普通符号
`\infty`$\infty$ 
`\angle`$\angle$
`$${\lim_{x \to \infty}$$`
$$\lim_{x \to \infty}$$
#### 二元运算符 
`$a \gg b$` $a \gg b$  
`$a \ll b$`	$a \ll b$
`\approx` $\approx$
`\geq` $\geq$
`\leq` $\leq$
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200726215110795.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjAwMTcyMg==,size_16,color_FFFFFF,t_70)

#### 大型运算符
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200726215140493.jpg)

巨算符的上下标位置可由 `\limits` 和 `\nolimits` 控制，前者令巨算符类似 $\lim$ 或求和算符 $\sum$，上下标位于上下方；后者令巨算符类似积分号，上下标位于右上方和右下方。还可以利用`\substack`命令或`subarray`环境，在下限位置书写多行表达式，后者更是提供了左对齐和居中选项。(lshort-zh-cn p42)
#### 定界符
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200726215156976.jpg)

#### 括号
使用 `\left`, `\right` 放大，如大小可变的大括号为`\left\{...\right\}`
>圆括号，小括号	\left( \frac{a}{b} \right)
>方括号，中括号	\left[ frac{a}{b} \right]
>花括号，大括号	\left{ \frac{a}{b} \right}
>角括号	\left \langle \frac{a}{b} \right \rangle
>单竖线，绝对值	\left| \frac{a}{b} \right|
>双竖线  	\left | \frac{a}{b} \right |
>取整函数   \left \lfloor \frac{a}{b} \right \rfloor
>取顶函数  \left \lceil \frac{c}{d} \right \rceil

#### 标点
逗号、分号（`\colon`）
### 科技公式
#### 单位
宏包`siunitx`
```LaTeX
\num{-1.235e96} \\
\SI{299792458}{m/s} \\
\SI{2x7x3.5}{m}
```
效果
>−1.235 × $10^{96}$
>299 792 458 m/s
>2 m × 7 m × 3.5 m 

#### 化学式
宏包`chemformula`
```LaTeX
\ce{2 H2 + O2 -> 2 H2O}\\
\ce{2H2O -> 2 H2 ^ + O2 ^}
```
### 列表与文本块
#### 列表
- enumerate 编号
```LaTeX
\begin{enumerate}
\item ...
\item ...
\item ...
\end{enumerate}
```
列表可以嵌套，最多嵌套四层。
- itemize 不编号
- description 有标题 `关键字环境`
```LaTeX
\begin{description}
\item[⟨item title⟩] …
\end{description}
```

#### 插入代码
##### 单行代码
`\verb|#include <stdio.h>|`
效果：`#include<stdio.h>`
##### 多行代码
```LaTeX
\begin{verbatim}
#include <stdio>
main() {
puts("hello world.");
}
\end{verbatim}
```
##### 带语法高亮的代码
宏包`listings`
```LaTeX
\lstset{
    language=(C,C++),basicstyle=\ttfamily}
\begin{lstlisting}
#include <stdio>
int main() {
puts("hello world.");
}
\end{lstlisting}
```
具体见帮助文档
#### 引用
`quote` 用于引用较短的文字，首行不缩进； `quotation` 用引用若干段文字，首行缩进。引用环境较一般文字有额外的左右缩进。

#### 脚注
`\footnote{脚注内容}`有些时候可能无法使用`\footnote`，比如`parbox`环境或是表格，这时需使用`\footnotemark`和`\footnotetext`进行脚注。
### 图表与浮动环境
#### 表格
[生成表格LaTeX代码](https://www.tablesgenerator.com/latex_tables)
基本代码
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200726215220833.jpg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NjAwMTcyMg==,size_16,color_FFFFFF,t_70)
>(tabular){l | c | c | c | r}｜表示表格竖线 l 左对齐 c 居中对齐 r 右对齐
>不同列间用&号分隔
>\hline插入换行（两个hline是双横线)

>插入空格
>两个quad空格	`a \qquad b`		两个m的宽度
>quad空格	`a \quad b`		一个m的宽度
>大空格	`a \ b`		1/3m宽度
>中等空格	`a \; b`		2/7m宽度
>小空格	`a \, b`		1/6m宽度
>没有空格	`ab`		
>紧贴	`a \! b`		缩进1/6m宽度
>这也是数学模式中插入空格的方法。

功能各异的表格宏包
单元格处理： multirow、 makecell
长表格： longtable、 xtab
定宽表格： xtabular
表线控制： booktabs、 hhline、 arydshln
表列格式： array
综合应用： tabu
#### 插入图片
LaTeX插入图片：
```LaTeX
\begin{figure}[h] 
%figure环境，h默认参数是可以浮动，不是固定在当前位置。
%如果要不浮动，你就可以使用大写float宏包的H参数，固定图片在当前位置，禁止浮动。
\centering %使图片居中显示
\includegraphics[width=1\textwidth]{wolf} 
%中括号中的参数是设置图片充满文档的大小，你也可以使用小数来缩小图片的尺寸。
\caption{狼伴归途} %caption是用来给图片加上图题的
\label{wolf} %这是添加标签，方便在文章中引用图片。
\end{figure}%figure环境
```
### 浮动体
其实在上面插入表格和图片的时候已经接触到了，浮动体有以下环境。
- figure 环境
- table 环境
- 其他环境可以使用 float 宏包得到
```LaTeX
\begin{table}[!htbp]
!-忽略“美学”标准
h-here
t-top
b-bottom
p-page-of-its-own
\caption[在目录中使用短标题]{题}%并带上编号
\label{} %紧跟\label命令进行交叉引用。
```
### 盒子
(lshort-zh-cn p31-p33)
`\mbox` 生成一个基本的水平盒子，内容只有一行，不允许分段（除非嵌套其它盒子，比如后文的垂直盒子）。外表看上去， `\mbox` 的内容与正常的文本无二，不过断行时文字不会从盒子里断开。`\makebox[⟨width⟩][⟨align⟩]{…}` 更进一步，可以加上可选参数用于控制盒子的宽度 ⟨width⟩，以及内容的对齐方式⟨align⟩，可选居中 c（默认值）、左对齐 l、右对齐 r 和分散对齐 s。
`\fbox` 和 `\framebox` 让我们可以为水平盒子添加边框。可以通过 \setlength 命令调节边框的宽度 \fboxrule 和内边距 \fboxsep。
在垂直盒子中文字可以换行。
标尺盒子用来画一个实心的矩形盒子，也可适当调整以用来画线（标尺）。
以下命令构造一个带背景色和有色边框的盒子， ⟨fcode⟩ 或 ⟨fcolor-name⟩ 用于设置边框颜色
### 自动化工具
#### 自动生成目录
`\tableofcontents` 按`\chapter \section`等自动生成目录
`\listoffigures` 生成图片目录
`\listoftables` 生成表格目录
#### 交叉引用
在能够被交叉引用的地方，如章节、公式、图表、定理等位置使用 \label 命令：`\label{⟨label-name⟩}`
之后可以在别处使用 \ref 或 \pageref 命令，分别生成交叉引用的编号和页码：`\ref{⟨label-name⟩} \pageref{⟨label-name⟩}`可以在命令前用`~`来产生一个空格。
>\label 命令可用于记录各种类型的交叉引用，使用位置分别为：
>章节标题 在章节标题命令 \section 等之后紧接着使用。
>行间公式 单行公式在公式内任意位置使用；多行公式在每一行公式的任意位置使用。
>有序列表 在 enumerate 环境的每个 \item 命令之后、下一个 \item 命令之前任意位置使用。
>图表标题 在图表标题命令 \caption 之后紧接着使用。
>定理环境 在定理环境内部任意位置使用

#### pdf链接与书签
宏包`hyperref`提供了命令 `\hypersetup` 配置各种参数。参数也可以作为宏包选项，在调用宏包时指定：
`\hypersetup{⟨option1⟩,⟨option2⟩={value},…}`
`\usepackage[⟨option1⟩,⟨option2⟩={value},…]{hyperref}`
为避免冲突，`hyperref`一般在最后调用。
##### 超链接
`\url{⟨url⟩}` 有色彩的超链接
`\nolinkurl{⟨url⟩}` 无色彩
`\href{URL}{文字}` 将一段文字作为超链接
默认的超链接在文字外边加上一个带颜色的边框（在打印 PDF 时边框不会打印），可指定colorlinks 参数修改为将文字本身加上颜色，或修改 pdfborder 参数调整边框宽度以“去掉”边框； hidelinks 参数则令超链接既不变色也不加边框。
```LaTeX
\hypersetup{hidelinks}
% or:
\hypersetup{pdfborder={0 0 0}}
```
##### 书签
hyperref 宏包另一个强大的功能是为 PDF 生成书签。对于章节命令 `\chapter`、` \section`等，默认情况下会为 PDF 自动生成书签。
#### bibtex引用
文献数据库是以.bib结尾的文本文件。在.tex源文件中，需要做好以下三件事
##### 操作1 
使用`\bibliographystyle{}`命令设定参考文献格式。格式包括：`plain`,`unsrt`,`alpha`,`abbrv`。
##### 操作2
使用`\cite{}`命令，引用需要的参考文献。大括号中是参考文献的引用标签。
##### 操作3
使用`\bibliography{}`命令指明要使用的数据库。大括号中是数据库名，可以有多个，指定数据库名时不带`.bib`后缀。
$\LaTeX$将在这条命令的位置插入参考文献列表。
### 设计文档格式
基本思想：
**格式与内容分离，填内容的时候不要在意格式。**
**导言区写格式，正文区写内容。**
直接设置相关参数。如设置
`\parindent` 段首缩进量
`\parskip` 两段间垂直间距
`\linespread` 几倍行距 
`\pagestyle` 页眉页脚格式
修改部分命令定义。如修改 `\thesection、 \labelenumi、
\descriptionlabel、 \figurename`。
利用工具宏包完成设置。如使用 `ctex` 宏包设置中文格式，使用
`tocloft` 宏包设置目录格式。
格式与内容的分离不仅需要格式设计者的努力，也需要作者在填写内容时遵循分离原则。基本的方法就是只使用与内容相关的命令和环境。
>推荐： It is \emph{important}.
>不好： It is \textit{important}.
>推荐： \caption{流程图}
>不好： \textbf{图 1:} 流程图

#### 字体
##### 英文  
`\textrm{内容}`罗马字体  
`\textsf{内容}`无衬线字体  
`\texttt{内容}`打字机字体
或者使用字体声明  
`\rmfamily` 罗马  
`\sffamily` 无衬线 
`\ttfamily` 打字机 
声明后内容全部为该字体直到遇到下一个字体声明或用大括号划定范围
##### 中文
ctex宏包中
`\songti` 宋体 
`\kaishu` 楷书 
`\heiti` 黑体
`\fangsong` 仿宋

设置字体粗细
`\textmd{} or \mdseries{}`中等权重
`\textbf{} or \bfseries` 粗体
设置字体形状
`\textup{}`  `\upshape` 直立
`\textit{}`  `\itshape` 斜体
`\textsl{}`  `\slshape` 伪斜体
`\textsc{}`  `\scshape` 小型大写
`\textnormal{}` `\normalfont`字体属性的默认值，即中等权重的直立罗马字体
`\emph{}` `\em` 强调字体
#### 字号
##### 英文
```LaTeX
\tiny      \scriptsize      \footnotesize 
\small       \normalsize      \large      
\Large     \LARGE      \huge      \Huge
```
##### 中文
`\zihao{}`
![UOb4Wn.png](https://imgconvert.csdnimg.cn/aHR0cHM6Ly9zMS5heDF4LmNvbS8yMDIwLzA3LzIzL1VPYjRXbi5wbmc?x-oss-process=image/format,png)
#### 对齐
`\centering` 居中
`\raggedleft` 左对齐
`\raggedright` 右对齐
#### 空白间距
    `\hspace{2cm}`
    `\vspace{3cm}`
#### 版面设置
设置纸张的宏包
    `geometry`
简单应用
```LaTeX
\usepackage[a4paper, left = 2cm, right = 2cm]{geometry} 
%设置A4格式
```
设置页眉页脚的宏包`fancydr`
分页断行
`\newpage \clearpage` 分页
`\inebreak \\` 换行
### 自定义命令和环境
一般在导言区中进行
`\newcommand<命令>[<参数个数>][<首选数默认值>]{<具体定义>}`
例：`\newcommand\PRC{People's Republic of \emph{China}}`在正文区只要使用`\PRC`即可。
这个命令有两个参数，第一个 ⟨name⟩ 是你想要建立的命令的名称（带反斜杠），第二个⟨definition⟩ 是命令的定义。方括号里的参数 ⟨num⟩ 是可选的，用于指定新命令所需的参数数目（最多 9 个）。如果缺省可选参数，默认就是 0，也就是新建的命令不带任何参数。
在命令的定义中，标记 `#1` 代表指定的参数。如果想使用多个参数，可以依次使用 `#2、……、 #9` 等标记

### 标题
#### 章节标题
#### 浮动标题
`caption` 宏包
### 列表环境
`enumitem` 宏包
## sjtu模板使用记录（持续更新）
1. 浮动体中去除图片的英文注释用`\caption`替换`\bicaption`。
2. 去除空白页，在`documentclass`选项中选择`oneside`
3. 使用 `\cite{key1,key2,key3...}` 可以产生“上标引用的参考文献”，如 `\cite{Meta_CN,chen2007act,DPMG}`。使用`\parencite{key1,key2,key3...}` 则可以产生水平引用的参考文献。当需要将参考文献条目加入到文献表中但又不在正文中引用，可以使用`\nocite{key1,key2,key3...}`。使用 `\nocite{*}` 可以将参考文献数据库中的所有条目加入到文献表中。
4. 设置`twoside`参数后，前言部分及不同部分直接便会有空白页。
## 一些小tips
#### % 
%引申出的另一个比较常用的用法是，分割不允许有空格或分行的较长文本例如：
```LaTeX
This is an % start
% Better: instructive <---
example: Supercal% 
ifragilist% 
icexpialidocious
```
结果为：

>This is an example: Supercalifragilisticexpialidocious

## Beamer

> beamer-theme-uha from Pro.Li for algorithm design final project

\ccb blue font

\ccp red font