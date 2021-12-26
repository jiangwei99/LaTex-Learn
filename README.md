[toc]

# LaTex Blog

## 一、图的插入

### 1.pdf格式的图片的插入

```tex
\begin{figure}[htb] 
	\centering
	\includegraphics[keepaspectratio, width = 1\columnwidth]{Figures/Horizontal Federated Learning.pdf}
	\caption{Horizontal Federated Learning
	\label{fig:Horizontal}}  %用于引用的标签
\end{figure}
```

效果：![](https://github.com/jiangwei99/LaTex_Blog/blob/main/fig/Federated Learning.png)



[h]  表示的当前位置（here），也就是说图片排在你设置的当前位置，但是如果这一页的空间不足以放下这个图片，此时图片会转到下一页。

[t]  顶端(top)。此时系统会将图片放置在页面的顶部。

[b] 底部. (bottom) 这里是优先将图片放置在底部，也就是页面的底部。

[p]  这个是将图片设置为浮动状态，也就是可以根据系统排版的，自动放置图片的位置。

### 2.eps格式的图片的插入

#### 2.1两个图并排

```tex
 \begin{figure}[!ht]
 	\centerline{$\begin{array}{cc}
 		\includegraphics[width=1.4in]{unsecure1.eps} &		 
 		\hspace{-1mm}\includegraphics[width=1.6in]{unsecure2.eps}\\
 		\hspace{-1mm}\mbox{\footnotesize a)    general illustration of $ \textbf{E} $. } &
 		\hspace{-1mm}\mbox{\footnotesize d)    optimal placement of highlighted entries.} \\
 		\end{array}$}\caption{Illustration 
 		of RPC.}  \label{fig.uns}
 	\end{figure}  
```

效果：![image](https://github.com/jiangwei99/LaTex_Blog/blob/main/fig/Illustration%20.png)

#### 2.2三个图并排

```tex
 \begin{figure*}[!ht]
  	\centerline{$\begin{array}{ccc}
  		\includegraphics[width=2.0in]{secure1.eps} &		 
  		\hspace{-1mm}\includegraphics[width=2.0in]{secure2.eps} &
  		\hspace{-1mm}\includegraphics[width=2.5in]{secure3.eps}\\
  		\hspace{-1mm}\mbox{\footnotesize a)   structure of 
  		  		 $ \textbf{E} $. } &
  		\hspace{-1mm}\mbox{\footnotesize b)   structure of 
  		 $ \bar{\textbf{E}} $.} &
  		\hspace{-1mm}\mbox{\footnotesize c)   structure of 
  		 $ \tilde{\textbf{E}} $.} \\
  		\end{array}$}\caption{The placements of highlighted entries in SBMM.}  \label{fig.sbmm}
  \end{figure*}
```

效果：![](\fig\The placements of highlighted entries in SBMM..png)

#### 2.3五个图并排

```tex
  \begin{figure*}[!ht]
  	\centerline{$\begin{array}{ccccc}
  		\includegraphics[width=1.3in]{ex1.eps} &		 
  		\hspace{-1mm}\includegraphics[width=1.3in]{ex2.eps} &
  		\hspace{-1mm}\includegraphics[width=1.3in]{ex3.eps} &
  		\hspace{-1mm}\includegraphics[width=1.5in]{ex4.eps} &
  		\hspace{-1mm}\includegraphics[width=1.5in]{ex5.eps}\\
  		\hspace{-1mm}\mbox{\footnotesize a) $ r_a = 0, r_b =0 $.} &
  		\hspace{-1mm}\mbox{\footnotesize b) $ r_a = 2, r_b =0 $.}&
  		\hspace{-1mm}\mbox{\footnotesize c) $ r_a = 3, r_b =0 $.}&
  		\hspace{-1mm}\mbox{\footnotesize d) $ r_a = 3, r_b =5 $.} &
  		\hspace{-1mm}\mbox{\footnotesize e) $ r_a = 3, r_b =4 $.} \\
  		\end{array}$}\caption{Examples of the placement of highlighted entries.}  \label{fig.ex}
  \end{figure*}
```

效果：![](\fig\Examples of the placement of highlighted entries.png)

## 二、表的插入



## 三、算法块

**算法块需要调用包**

```tex
\usepackage[ruled,linesnumbered]{algorithm2e}
```

### 1.算法块的插入

```tex
\begin{algorithm}\label{alg1}
	\LinesNumbered
	\begin{small}
		\KwIn{$ N $, $ r_a $, $ r_b $, $ M $, $ P $}
		\KwOut{$ Q $, $ Q_b $}
		$ Q_1 = 0 $;\\
		\For{$ j \ge 2 $; $j < r_b $; $j=j+1$}{
			\If {$ m+1 - \tilde{N}_{j-1}^{r_a,r_b}  \le \tilde{N}_{j}^{r_a,r_b}-1 $}{
				$ Q_j = Q_{j-1} + \tilde{N}_{j-1}^{r_a,r_b} $;\\
			}
			\Else
			{ $ Q_j = Q_{j-1} +m - \tilde{N}_{j}^{r_a,r_b}+2 $;\\}
		}
		$ Q_{b} = Q_{r_b - 1} + \tilde{N}_{r_b-1}^{r_a,r_b} $;\\
		$ Q_{r_b} = Q_{b} +m - \tilde{N}_{r_b+1}^{r_a,r_b}+2 $;\\
		\For {$ j \ge r_b + 1 $; $ j \le m $; $ j=j+1 $ }{
			\If {$ m+1 - N_{j}^{r_a,r_b}  \le N_{j+1}^{r_a,r_b}-1 $}{
				$ Q_j = Q_{j-1} + N_{j}^{r_a,r_b} $;\\
			}
			\Else
			{ $Q_j = Q_{j-1} +m - N_{j+1}^{r_a,r_b}+2 $;\\}
		}    		
		
		\Return  $ Q $, $ Q_b $ ;
		\caption{The Optimal Values of $ Q $ with a Given Placement of Highlighted Entries.} \label{optimal}
	\end{small}
\end{algorithm}
```

效果：![](\fig\The Optimal Values of $ Q $ with a Given Placement of Highlighted Entries..png)

## 四、参考文献系列

### 1.正文中[引用]高亮显示+超链接

```tex
\usepackage[backref]{hyperref}   %用于引用突出，会报错，但能编译
```

效果如图

![](\fig\reference1.png)

![](\fig\reference1.1.png)



## 附录：出现的问题及解决方案

### 1.参考文献中出现横线

![](\fig\q&a\question1.png)

原因：这是因为相邻两篇文献的作者相同，在IEEE模板下会出现横线。

找到TexLive安装目录下的**“IEEEtran.bst”**文件

```
路径：D:\Program Files\TexLive\2021\texmf-dist\bibtex\bst\IEEEtran.bst
```

**找到如下代码(大约在128行)，将代码中的**#1**变为**#0

```
FUNCTION {default.is.dash.repeated.names} { #1 }
```

重新编译，解决问题

![](\fig\q&a\answer1.png)

