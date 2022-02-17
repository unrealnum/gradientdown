# 线性代数

<a id="toc"></a>

[toc]

## 排列与对换



### 基本构造与定义



#### 排列



**把 n 个不同的元素排成一列，叫做这 n 个元素的全排列（也简称排列）**

**n 个不同元素的所有排列的种数，通常用 P~n~ 表示**

**对于 n 个不同的元素，先规定各元素之间有一个标准次序（例如 n 个不同的 自然数，可规定由小到大为标准次序）**

**在这 n 个元素的任一排列中，当某一对元素的先后次序与标准次序不同时，就说它构成 1 个逆序.一个排列中所有逆序的总数叫做这个排列的逆序数.**

**逆序数为奇数的排列叫做奇排列，逆序数为偶数的排列叫做偶排列.**



#### 对换



**在排列中，将任意两个元素对调，其余的元素不动，这种作出新排列的手续叫做对换.将 相邻两个元素对换，叫做相邻对换.**

**定理 1：一个排列中的任意两个元素对换，排列改变奇偶性.**

**推论：奇排列对换成标准排列的对换次数为奇数，偶排列对换成标准排列的对换次数 为偶数.**



<a href ="#toc">回到目录</a>



## 行列式（一般用D代指）



### 基本构造与定义


$$
D=
\left |
\matrix{
	a_{11}&a_{12}&...&a_{1n}\\
	a_{21}&a_{22}&...&a_{2n}\\
	\vdots&\vdots&\ddots&\vdots\\
	a_{n1}&a_{n2}&...&a_{nn}
}
\right |
$$
定义：线性方程组中所有系数排成的数表。

如上式：

​	有原式：
$$
\left\{
\begin{array}{c}
		a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=b_1\\
		a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=b_2\\
		\vdots\\
		a_{n1}x_1+a_{n2}x_2+\cdots+a_{nn}x_n=b_n
	\end{array}
\right.
$$


<a href ="#toc">回到目录</a>



### 行列式类型



>名词注释：
>
>​	**主对角线**
>$$
>\left |
>\matrix{
>a_{11}\\
>&a_{22}\\
>&&a_{33}\\
>&&&\ddots\\
>&&&&a_{nn}
>}
>\right|
>$$
>
>
>​	**副对角线**
>$$
>\left |
>\matrix{
>&&&&a_{1n}\\
>&&&a_{2(n-1)}\\
>&&a_{3(n-2)}\\
>&\cdot^{\Large\cdot^{\huge\cdot}}\\
>a_{n1}
>}
>\right|
>$$
>
>
>​	**上三角行列式**
>$$
>\left|
>\matrix{
>a_{11}&a_{12}&a_{13}&\cdots&a_{1n}\\
>&a_{22}&a_{23}&\cdots&a_{2n}\\
>&&a_{33}&\cdots&a_{3n}\\
>&&&\ddots&\vdots\\
>0&&&&a_{nn}
>}
>\right|
>$$
>
>
>​	**下三角形行列式**
>$$
>\left|
>\matrix{
>a_{11}&&&&0\\
>a_{21}&a_{22}\\
>a_{31}&a_{32}&a_{33}\\
>\vdots&\vdots&\vdots&\ddots\\
>a_{n1}&\cdots&\cdots&\cdots&a_{nn}
>}
>\right|
>$$
>
>
>​	**对角行列式**
>$$
>\left |
>\matrix{
>a_{11}\\
>&a_{22}\\
>&&a_{33}\\
>&&&\ddots\\
>&&&&a_{nn}
>}
>\right|
>$$
>
>
>
>
>对于**上（下）三角形行列式或对角行列式**，有：
>$$
>D=\prod^n_{i=1}(a_{nn})
>$$



<a href ="#toc">回到目录</a>



### 转置行列式

$$
D=
\left |
\matrix{
	a_{11}&a_{12}&...&a_{1n}\\
	a_{21}&a_{22}&...&a_{2n}\\
	\vdots&\vdots&\ddots&\vdots\\
	a_{n1}&a_{n2}&...&a_{nn}
}
\right |
$$

$$
D^T=
\left |
\matrix{
	a_{11}&a_{21}&...&a_{n1}\\
	a_{12}&a_{22}&...&a_{n2}\\
	\vdots&\vdots&\ddots&\vdots\\
	a_{1n}&a_{2n}&...&a_{nn}
}
\right |
$$



**行列式 D^T^称为行列式 D 的转置行列式**



#### 性质

* **行列式与它的转置行列式相等**



<a href ="#toc">回到目录</a>



### 余子式



对于n阶行列式D：
$$
D=
\left |
\matrix{
	a_{11}&a_{12}&...&a_{1n}\\
	a_{21}&a_{22}&...&a_{2n}\\
	\vdots&\vdots&\ddots&\vdots\\
	a_{n1}&a_{n2}&...&a_{nn}
}
\right |
$$


对于a~22~元素的余子式=
$$
M_{22}=\left |
\matrix{
	a_{11}&a_{13}&a_{14}&\cdots&a_{1n}\\
	a_{31}&a_{33}&a_{34}&\cdots&a_{2n}\\
	\vdots&\vdots&\vdots&\ddots&\vdots\\
	a_{n1}&a_{n3}&a_{n4}&\cdots&a_{nn}
}
\right |
$$


对于a~22~元素的代数余子式=
$$
A_{ij}=(-1)^{i+j}M_{ij}
$$


#### 性质

<a id="fg"></a>

* 一个 n 阶行列式，如果其中第i行所有元素除（i，j）元 a~ij~外都为零，那 么这行列式等于 a~ij~与它的代数余子式的乘积.

即：
$$
D=a_{ij}M_{ij}
$$


*  **行列式按行（列）展开法则：**行列式等于它的任一行（列）的各元素与其对应的代数余子式乘积之和

$$
D=a_{i1}A_{i1}+a_{i2}A_{i2}+\cdots+a_{in}A_{in}\\
其中(i=1,2,3,4,\cdots,n)
$$



* 范德蒙德（Vandermonde）行列式

$$
D_n=
\left|
\matrix{
1&1&\cdots&1\\
x_1&x_2&\cdots&x_n\\
x_1^2&x_2^2&\cdots&x_n^2\\
\vdots&\vdots&\ddots&\vdots\\
x_1^n&x_2^n&\cdots&x_n^n
}
\right |=\prod_{n \geq i>j \geq 1}(x_i-x_j)
$$

* 行列式某一行（列）的元素与另一行（列）的对应元素的代数余子式 乘积之和等于零



<a href ="#toc">回到目录</a>



### 计算方法：



#### 	（针对于2，3阶行列式）对角线法则：

* 二阶行列式便是主对角线上的两元素之积减去副对角线上两 元素之积所得的差。
* 每项均为不同行不同列的三个元素的乘积再冠以正负号，其规律遵循图 1.2 所示的对角线法则：三条实线看做是平行于主对角线的连线，三条虚线看做是平行于副对角线的连线，实线上三元素的乘积冠正号，虚线上三元素的乘积冠负号。





#### 	（针对n阶行列式）<a href="#fg">按行（列）展开公式</a>



<a href ="#toc">回到目录</a>



### 变换法则：



* **对换行列式的两行（列），行列式变号**
* **如果行列式有两行（列）完全相同，则此行列式等于零.**
* **行列式的某一行（列）中所有的元素都乘同一数 k，等于用数 k 乘此 行列式.**
* **行列式中某一行（列）的所有元素的公因子可以提到行列式记号的外面.**
* **行列式中如果有两行（列）元素成比例，则此行列式等于零**
* **若行列式的某一行（列）的元素都是两数之和，则 D 等于那一行（列）的两数拆开分别于其他元素构成的行列式之和**

* **把行列式的某一行（列）的各元素乘同一数然后加到另一行（列）对 应的元素上去，行列式不变**



<a href ="#toc">回到目录</a>



## 矩阵



### 基本构造与定义



**由 m×n 个数 a~ij~（i= 1，2，…，m；j= 1，2，…，n）排成的 m 行 n 列的数表：**
$$
\matrix{
a_{11}&a_{12}&\cdots&a_{1n}\\
a_{21}&a_{22}&\cdots&a_{2n}\\
\vdots&\vdots&\ddots&\vdots\\
a_{n1}&a_{n2}&\cdots&a_{nn}
}
$$
**称为m 行 n 列矩阵，简称m×n 矩阵。为表示它是一个整体，总是加一个括弧，并用 大写黑体字母表示它。**

> * 元素是实数的矩阵称为实矩阵，元素是复数的矩阵称为复矩阵
>
> * 行数与列数都等于 n 的矩阵称为n 阶矩阵或n 阶方阵
> * 只有一行的矩阵称为行矩阵，又称行向量
> * 只有一列的矩阵称为列矩阵，又称列向量
> * 两个矩阵的行数相等、列数也相等时，就称它们是同型矩阵
>   * （接上，若二者对应元素相等则说：A=B）
> * 

$$
\textbf{A}=
\left (
\matrix{
a_{11}&a_{12}&\cdots&a_{1n}\\
a_{21}&a_{22}&\cdots&a_{2n}\\
\vdots&\vdots&\ddots&\vdots\\
a_{n1}&a_{n2}&\cdots&a_{nn}
}
\right)
$$

### 矩阵类型



#### 系数矩阵

$$
A=\left (
a_{ij}
\right)
$$

#### 单位矩阵

$$
E=\left(
\matrix{
1&&&\\
&1&&\\
&&\ddots&\\
&&&1
}
\right)
$$



#### 未知数矩阵

$$
x=\left(
\matrix{
x_1\\x_2\\\vdots\\x_n
}
\right)
$$

#### 常数项矩阵

$$
b=\left(
\matrix{
b_1\\b_2\\\vdots\\b_n
}
\right)
$$

#### 增广矩阵（B）

**对于**
$$
\left\{
\begin{array}{c}
		a_{11}x_1+a_{12}x_2+\cdots+a_{1n}x_n=b_1\\
		a_{21}x_1+a_{22}x_2+\cdots+a_{2n}x_n=b_2\\
		\vdots\\
		a_{n1}x_1+a_{n2}x_2+\cdots+a_{nn}x_n=b_n
	\end{array}
\right.
$$
**有：**
$$
B=\left(
\matrix{
a_{11}&a_{12}&\cdots&a_{1n}&b_1\\
a_{21}&a_{22}&\cdots&a_{2n}&b_2\\
\vdots&\vdots&\ddots&\vdots&\vdots\\
a_{n1}&a_{n2}&\cdots&a_{nn}&b_n
}
\right)
$$



#### 对称矩阵


$$
对于\forall a_{ij}:有a_{ij}=a_{ji};
$$
即：
$$
A=\left(
\matrix{
a_{11}&a_{12}&\cdots&a_{1m}\\
a_{12}&a_{22}&\cdots&a_{2m}\\
\vdots&\vdots&\ddots&\vdots\\
a_{1m}&a_{2m}&\cdots&a_{mm}
}
\right)
$$






### 矩阵运算

> **以下A，B均为矩阵**


$$
A=\left(
\matrix{
a_{11}&a_{12}&\cdots&a_{1n}\\
a_{21}&a_{22}&\cdots&a_{2n}\\
\vdots&\vdots&\ddots&\vdots\\
a_{m1}&a_{m2}&\cdots&a_{mn}
}
\right)
$$

$$
B=\left(
\matrix{
b_{11}&b_{12}&\cdots&b_{1n}\\
b_{21}&b_{22}&\cdots&b_{2n}\\
\vdots&\vdots&\ddots&\vdots\\
b_{m1}&b_{m2}&\cdots&b_{mn}
}
\right)
$$




#### A+B（仅在A,B同型（均为m*n型矩阵））


$$
A+B=
\left(
\matrix{
a_{11}+b_{11}&a_{12}+b_{12}&\cdots&a_{1n}+b_{1n}\\
a_{21}+b_{21}&a_{22}+b_{22}&\cdots&a_{2n}+b_{2n}\\
\vdots&\vdots&\ddots&\vdots\\
a_{n1}+b_{n1}&a_{n2}+b_{n2}&\cdots&a_{nn}+b_{nn}
}
\right)
$$


#### A-B（仅在A,B同型（均为m*n型矩阵））


$$
A-B=
\left(
\matrix{
a_{11}-b_{11}&a_{12}-b_{12}&\cdots&a_{1n}-b_{1n}\\
a_{21}-b_{21}&a_{22}-b_{22}&\cdots&a_{2n}-b_{2n}\\
\vdots&\vdots&\ddots&\vdots\\
a_{n1}-b_{n1}&a_{n2}-b_{n2}&\cdots&a_{nn}-b_{nn}
}
\right)
$$


#### AB(矩阵相乘)(仅当A为m\*n型，B为n\*k型矩阵)(不满足交换律，满足结合律与分配律)


$$
A=\left(
\matrix{
a_{11}&a_{12}&\cdots&a_{1n}\\
a_{21}&a_{22}&\cdots&a_{2n}\\
\vdots&\vdots&\ddots&\vdots\\
a_{m1}&a_{m2}&\cdots&a_{mn}
}
\right)
$$

$$
B=\left(
\matrix{
b_{11}&b_{12}&\cdots&b_{1k}\\
b_{21}&b_{22}&\cdots&b_{2k}\\
\vdots&\vdots&\ddots&\vdots\\
b_{n1}&b_{n2}&\cdots&b_{nk}
}
\right)
$$

$$
A \times B=
\left(
\matrix{
\sum^n_1 a_{1n}*b_{n1} & \sum^n_1 a_{1n}*b_{n2} & \cdots &\sum^n_1 a_{1n}*b_{nk}\\
\sum^n_1 a_{2n}*b_{n1} & \sum^n_1 a_{2n}*b_{n2} & \cdots &\sum^n_1 a_{2n}*b_{nk}\\
\vdots & \vdots & \ddots & \vdots\\
\sum^n_1 a_{mn}*b_{n1} & \sum^n_1 a_{mn}*b_{n2} & \cdots &\sum^n_1 a_{mn}*b_{nk}
}
\right)
$$

> **纯量阵**
> $$
> \lambda E=\left(
> \matrix{
> \lambda&&&\\
> &\lambda&&\\
> &&\ddots&\\
> &&&\lambda
> }
> \right)
> $$



> **矩阵的幂**
>
>  
>
> 对于：
> $$
> 
> A=\left(
> \matrix{
> a_{11}&a_{12}&\cdots&a_{1n}\\
> a_{21}&a_{22}&\cdots&a_{2n}\\
> \vdots&\vdots&\ddots&\vdots\\
> a_{m1}&a_{m2}&\cdots&a_{mn}
> }
> \right)
> $$
>  
>
> 有：
> $$
> A^n=\prod_1^nA
> $$





#### 转置矩阵（A^T^）

> **与转置行列式相似**


$$
A^T=\left(
\matrix{
a_{11}&a_{12}&\cdots&a_{1m}\\
a_{21}&a_{22}&\cdots&a_{2m}\\
\vdots&\vdots&\ddots&\vdots\\
a_{n1}&a_{n2}&\cdots&a_{nm}
}
\right)
$$
**对于：**
$$
A=\left(
\matrix{
a_{11}&a_{12}&\cdots&a_{1n}\\
a_{21}&a_{22}&\cdots&a_{2n}\\
\vdots&\vdots&\ddots&\vdots\\
a_{m1}&a_{m2}&\cdots&a_{mn}
}
\right)
$$
并且有：
$$
(A^T)^T=A\\
(A+B)^T=A^T+B^T\\
(\lambda A)^T=\lambda A^T\\
(AB)^T=B^T A^T(对于满足矩阵乘法的A与B)
$$


#### 方阵行列式（det A或|A|）

> 把（）换成||极为det A



注意：
$$
A\neq|A|
$$
但是：
$$
|A^T|=|A|\\
|\lambda A|=\lambda^n |A|\\
|A B|=|A||B|
$$

#### 伴随矩阵（A^*^）


$$
AA^*=|A|E\\
A^*A=|A|E
$$






#### 矩阵求逆(A^-1^)

$$
对于A，\exists B使得\\
AB=E
$$



则称A可逆。



##### 性质

* 若矩阵A 可逆，则|A|≠0.
* 若|A︳≠0，则矩阵A 可逆，且

$$
A^{-1}=\frac{1}{|A|}	A^*
$$

* A 是可逆矩阵的充分必要条件是|A︳≠0，即可逆矩阵就是非奇异矩阵.
* 若 AB = E （或 BA = E），则 B = A^-1^.



#### n次多项式



对于矩阵A,称
$$
\phi(A)=b_0E+b_1A+b_2A^2+\cdots b_nA^n
$$
为A的n次多项式







## 向量组







## 线性空间与线性变换



