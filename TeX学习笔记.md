# TeX学习笔记

徐栩涛 2021/1/15

***

[toc]

***

## 数学模式

在LaTeX数学模式中，公式有两种形式——行内公式和行间公式。前者公式嵌入在行内，适用于简单短小的公式；后者居中独占一行，适用于比较长或重要的公式。公式中的空格均会被忽略，可以使用命令`\quad`或`\qquad`实现
在行间公式中，命令`\tag{n}`可以进行手动编号

- 行内公式

  $这是一个公式$

  这是一个函数的表达式
  $$
  f(x) = x+1
  $$

- 行间公式（见上）

- 手动编号
  $$
  f(x) = x +1 \tag{1.1}
  $$

- 空格
  $$
  f(x)\quad = x\quad+ \quad 1 \space
  $$

## 数学结构

### 简单运算

拉丁字母、阿拉伯数字和` +-*/= `运算符均可以直接输入获得，命令`\cdot`表示乘法的圆点，命令`\neq`表示不等号，命令`\equiv`表示恒等于，命令`\bmod`表示取模

- 拉丁字母、阿拉伯数字、四则运算符
  $$
  a+b=2\qquad c*c  \quad (a+1)/2-b-101
  $$
  
- 乘法的圆点
  $$
  F\cdot x=W\tag{2}
  $$
  
- 不等号
  $$
  a\neq a+1
  $$
  
- 恒等于
  $$
  F(G(x))\equiv C
  $$
  
- 取模
  $$
  301\equiv 1(\bmod 100)
  $$
  
- 除法
  $$
  \div
  $$

- 不等号
  $$
  \leq\\
  \geq
  $$

- 

- 

### 上下标

语法`_`表示下标、`^`表示上标，但上下标内容不止一个字符时，需用大括号括起来。单引号`'`表示求导

- 上下标
  $$
  a_1x_1+a_2x_2+a_3x_3=C\qquad A_{12}\cdot a_{12}+A_{12}^{n}=0 \qquad x^{x^{x^{x}}}
  $$
  
- 求导

$$
x'y^2+x^2y'=a^2\qquad x'''''''''''\quad f^{[n]}(x)
$$

### 分式和根式

命令：`\sqrt`表示平方根，`\sqrt[n]`表示n次方根，`\frac`表示分式
$$
\frac{\sqrt{x+\sqrt[3]y}}{2} \equiv 8
$$

### 几种括号

`langle`,`rangle`,`lceil`,`rceil`,`lfloor`,`rfloor`,`lbrace`,`rbrace`,（前面都要加上反斜杠）
$$
\langle e^{i\pi}+1=0\rangle\\
\lceil e^{i\pi}+1=0\rceil\\
\lfloor e^{i\pi}+1=0\rfloor\\
\lbrace e^{i\pi}+1=0\rbrace
$$


### 上下标记

- `\overline` and `\underline`

$$
\overline{a+bi}=a-bi\quad \underline{x+y}
$$

- `\overbrace` and `\underbrace`，要在括号上面（下面）添加标注，用`^`and`_`.

  > `\cdots` refers to `···`

  $$
  \underbrace{a_1+a_2+\cdots+a_n}_{n个}\qquad\overbrace{a+b+c+d+\cdots +x+y+z}^{26}
  $$

  

### 向量

`\vec` 表示向量 `\overrightarrow`表示箭头向右 `\overleftarrow`表示箭头向左
$$
\vec a\quad\vec{AB}\quad\overrightarrow{CDE}\quad \overleftarrow{DE}
$$

$$
\vec F\cdot\vec x=W
$$

### 积分、极限、求和、累乘

- 积分使用`\int^{}_{}f(x)\mathrm{d}x`
  $$
  求\quad\frac{\mathrm{d}}{\mathrm{d}x}\int^x_0sin(x-t^2)\mathrm{d}t
  $$

- 极限使用`\lim_{x \to a}f(x)`

  > `\to` refers to `->`, `\infty`refers to `∞`

$$
\lim_{x \to 0}\frac{sin(cosx)-sinx}{x^4}\quad \lim_{n\to+\infty}\sqrt[n]{n}
$$

- 求和使用`\sum_{}^{}f(x)`
  $$
  \sum_{n\to+\infty}\frac{1}{n^{\alpha +1}}(1^{\alpha}+2^{\alpha}+\cdots+n^{\alpha}) = ?
  $$

- 累乘使用`\prod`
  $$
  \prod_{i=0}^{\infty}\frac{2i+1}{i^2(i+1)}
  $$

### 环路积分、多重积分、偏微分

- 多重积分使用`\iint`,`\iiint`（几重积分就有几个`i`）

- 环路积分使用`\oint`（多重积分的环路积分直接在前面加上`o`）

- 偏微分使用`\partial`

  例如，**流体力学中的连续性方程和质量守恒：**
  $$
  \oiint\rho\vec{v}\mathrm{d}\vec{S}+\iiint\frac{\partial\rho}{\partial t}\mathrm{dV}=0
  $$
  

### 其他符号

`\hat` ====>$\hat{x}$

`\bar` ====>$\bar{x}$

`\tilde` ====>$\tilde{x}$

### 矩阵

矩阵有几种矩阵环境，区别在于括号不一样

| 矩阵环境 | 形状   |
| -------- | ------ |
| matrix   | 无括号 |
| bmatrix  | []     |
| vmatrix  | \|\|   |
| pmatrix  | ()     |

> 基本语法，使用`\begin{matrix}`开头，使用`\end{matrix}`结尾，中间用`&`分隔列，用`\`分隔行；
>
> 注：`\vdots`表示竖着的三个点，`\ddots`表示斜着的三个点

- matrix
  $$
  \begin{matrix}
  1&2&3\\
  4&5&6\\
  \end{matrix}
  $$
  
- bmatrix
  $$
  \begin{bmatrix}
  1&0&\cdots&0\\
  0&1&\cdots&0\\
  \vdots&\vdots&\ddots&\vdots\\
  0&0&\cdots&1
  \end{bmatrix}
  $$
  
- vmatrix
  $$
  \begin{vmatrix}
  x_1-a_1&x_2&x_3&\cdots&x_n\\
  x_1&x_2-a_3&x_3&\cdots&x_n\\
  x_1&x_2&x_3-a_3&\cdots&x_n\\
  \vdots&\vdots&\vdots&&\vdots\\
  x_1&x_2&x_3&\cdots&x_n-a_n
  \end{vmatrix}
  $$
  
- pmatrix
  $$
  \begin{pmatrix}
  0&1&0\\
  1&0&0\\
  0&0&1
  \end{pmatrix}
  \begin{pmatrix}
  a_1&a_2&a_3&a_4\\
  b_1&b_2&b_3&b_4\\
  c_1&c_2&c_3&c_4
  \end{pmatrix}
  $$

### 希腊字母

$\alpha$	$\theta$	$o$	$\upsilon$	$\beta$	$\vartheta$	$\pi$	$\phi$	$\gamma$	$\iota$	$\varpi$	$\varphi$	$\delta$	$\kappa$	$\rho$	$\chi$	$\epsilon$	$\lambda$	$\varrho$	$\psi$	$\varepsilon$	$\mu$	$\sigma$	$\omega$	$\zeta$	$\nu$	$\varsigma$	$\eta$	$\xi$	$\tau$

$\Gamma$	$\Lambda$	$\Sigma$	$\Psi$	$\Delta$	$\Xi$	$\Upsilon$	$\Omega$	$\Theta$	$\Pi$	$\Phi$

## 多行组合

### 公式组合

通过`cases`实现公式的组合，用`&`分隔公式和条件
$$
F(x)=\begin{cases}
x,&x>0\\
0,&x=0\\
-x,&x<0
\end{cases}
$$

### 拆分单个公式

使用`align`环境，并在等号之前加上`&`，使得等号对齐
$$
\begin{align}
x+1&=y+2\\
&=z+3\\
&=w+4
\end{align}
$$

$$
\begin{align}
y+1&=x^2+2x+1\\
y&=x^2+2x
\end{align}
$$

