# 第一章 矢量分析：概念与课堂笔记

> 学习目标：看到一个量时，先判断它是标量还是矢量；看到一个积分时，先判断它沿线、过面还是在体内；看到 \(\nabla\) 时，先看它后面是空乘、点乘还是叉乘。

## 1. 标量、矢量与场

### 定义

- **标量**只有大小，例如温度、电势。
- **矢量**既有大小又有方向，例如速度、电场强度。
- **场**表示某个物理量在空间各点的分布。\(u(x,y,z)\) 是标量场，\(\mathbf F(x,y,z)\) 是矢量场。

### 直观理解

标量场像一张“空间温度地图”；矢量场则像在每一点都画了一支有长短、有方向的小箭头。

## 2. 点积、叉积与方向分量

### 定义与计算

在正交单位基底中，

\[
\mathbf A\cdot\mathbf B=A_xB_x+A_yB_y+A_zB_z,
\qquad
\mathbf A\times\mathbf B=
\begin{vmatrix}
\mathbf e_x&\mathbf e_y&\mathbf e_z\\
A_x&A_y&A_z\\
B_x&B_y&B_z
\end{vmatrix}.
\]

### 为什么点积只剩对应分量

因为

\[
\mathbf e_i\cdot\mathbf e_j=
\begin{cases}1,&i=j,\\0,&i\ne j.\end{cases}
\]

同方向单位矢量点乘为 1，不同方向为 0。因此“在 \(\mathbf C\) 方向上的标量分量”必须用单位方向：

\[
A_C=\mathbf A\cdot\mathbf e_C,
\qquad \mathbf e_C=\frac{\mathbf C}{|\mathbf C|}.
\]

若题目问矢量投影，则结果是 \((\mathbf A\cdot\mathbf e_C)\mathbf e_C\)。

## 3. 三种常用坐标系

### 直角坐标

\[
\mathbf r=x\mathbf e_x+y\mathbf e_y+z\mathbf e_z,
\qquad dV=dx\,dy\,dz.
\]

### 柱坐标

\[
x=\rho\cos\phi,\quad y=\rho\sin\phi,\quad z=z,
\qquad dV=\rho\,d\rho\,d\phi\,dz.
\]

### 球坐标

\[
x=r\sin\theta\cos\phi,
\quad y=r\sin\theta\sin\phi,
\quad z=r\cos\theta.
\]

\[
\mathbf e_r=\frac{x}{r}\mathbf e_x+\frac{y}{r}\mathbf e_y+\frac{z}{r}\mathbf e_z,
\qquad dV=r^2\sin\theta\,dr\,d\theta\,d\phi.
\]

做题先看“场用什么坐标表示、积分区域用什么坐标最简单”，不要机械换坐标。

## 4. 方向导数与梯度

### 定义

标量场 \(u\) 在单位方向 \(\mathbf e_l\) 上的方向导数是

\[
\frac{\partial u}{\partial l}=\nabla u\cdot\mathbf e_l.
\]

梯度定义为

\[
\operatorname{grad}u=\nabla u
=\mathbf e_x\frac{\partial u}{\partial x}
+\mathbf e_y\frac{\partial u}{\partial y}
+\mathbf e_z\frac{\partial u}{\partial z}.
\]

### 直观理解

- \(\nabla u\) 的方向：\(u\) 增长最快的方向。
- \(|\nabla u|\)：最大方向导数。
- \(\nabla u\) 垂直于等值面。

方向导数回答“沿指定方向变多快”；梯度一次给出“最快往哪走、最快有多快”。方向向量必须先单位化，否则会混入它本身的长度。

### 计算模板

1. 求 \(\nabla u\)。
2. 代入指定点。
3. 将给定方向 \(\mathbf a\) 单位化为 \(\mathbf e_l=\mathbf a/|\mathbf a|\)。
4. 点乘 \(\nabla u\cdot\mathbf e_l\)。

## 5. 哈密顿算子 \(\nabla\)

### 定义

\[
\nabla=\mathbf e_x\frac{\partial}{\partial x}
+\mathbf e_y\frac{\partial}{\partial y}
+\mathbf e_z\frac{\partial}{\partial z}.
\]

它不是普通矢量，而是一个由偏导数组成的微分算子。后面的运算决定意义：

| 写法 | 名称 | 输入 | 输出 |
|---|---|---|---|
| \(\nabla u\) | 梯度 | 标量 | 矢量 |
| \(\nabla\cdot\mathbf F\) | 散度 | 矢量 | 标量 |
| \(\nabla\times\mathbf F\) | 旋度 | 矢量 | 矢量 |
| \(\nabla^2u\) | 拉普拉斯运算 | 标量 | 标量 |

## 6. 通量与散度

### 6.1 通量的定义

矢量场穿过有向曲面 \(S\) 的通量为

\[
\Phi=\iint_S\mathbf F\cdot d\mathbf S,
\qquad d\mathbf S=\mathbf e_n\,dS.
\]

点积只保留法向分量：切着曲面流动不穿过曲面，对通量没有贡献。

### 6.2 开曲面与闭合曲面

一张纸当然可以算通量；它能回答“有多少场穿过这张纸”。但开曲面没有完整包住体积，所以不能单靠它统计某一体积的净流入、净流出。

闭合曲面 \(S\) 完整围住一个有限体积 \(V\)，面积元统一取外法线。流出与外法线同向，贡献为正；流入与外法线反向，贡献为负。均匀场若进多少、出多少，净通量便为零。

因此，闭合曲面不是因为“内部变成绝对独立的空间”，而是因为它把统计对象的全部边界都包含了。

### 6.3 散度的定义

\[
\nabla\cdot\mathbf F
=\lim_{\Delta V\to0}
\frac{1}{\Delta V}
\oiint_{\Delta S}\mathbf F\cdot d\mathbf S.
\]

这正是“把包围一点的小球不断缩小”的严格表达：散度是单位体积的净流出率。

\[
\nabla\cdot\mathbf F>0\text{：局部像源},\quad
\nabla\cdot\mathbf F<0\text{：局部像汇},\quad
\nabla\cdot\mathbf F=0\text{：局部净流出为零}.
\]

### 重要纠正：散度为零不等于场为零

散度为零只说明“这里没有净产生或净消失”，场仍可存在并穿过区域。均匀流场就是典型例子。讨论“有没有源”还要说明区域以及是否含奇点；例如点源场在源点之外散度可为零，但源点本身不能忽略。

### 直角坐标计算

\[
\nabla\cdot\mathbf F=
\frac{\partial F_x}{\partial x}+
\frac{\partial F_y}{\partial y}+
\frac{\partial F_z}{\partial z}.
\]

记忆：\(x\) 分量对 \(x\)，\(y\) 分量对 \(y\)，\(z\) 分量对 \(z\)，再相加。

### 柱坐标和球坐标

\[
\nabla\cdot\mathbf F
=\frac1\rho\frac{\partial(\rho F_\rho)}{\partial\rho}
+\frac1\rho\frac{\partial F_\phi}{\partial\phi}
+\frac{\partial F_z}{\partial z},
\]

\[
\nabla\cdot\mathbf F
=\frac1{r^2}\frac{\partial(r^2F_r)}{\partial r}
+\frac1{r\sin\theta}\frac{\partial(F_\theta\sin\theta)}{\partial\theta}
+\frac1{r\sin\theta}\frac{\partial F_\phi}{\partial\phi}.
\]

## 7. 散度定理

### 定义

\[
\oiint_S\mathbf F\cdot d\mathbf S
=\iiint_V(\nabla\cdot\mathbf F)\,dV.
\]

### 直观理解

整个闭合表面的净流出量，等于内部每一点局部净流出率的总和：

\[
\text{边界上的净通量}=\text{体内所有源汇效应之和}.
\]

### 什么时候用

- 题目给闭合曲面通量，而直接逐面算很繁琐。
- 散度容易算，体积积分范围简单。
- 反过来，也可用已知通量判断体内源的总量。

## 8. 环流与旋度

### 8.1 环流的定义

\[
\Gamma=\oint_C\mathbf F\cdot d\mathbf l.
\]

它度量矢量场沿闭合曲线切向“推着你绕一圈”的总效果。通量看法向穿过，环流看切向推动。

### 8.2 旋度的定义

旋度是局部环流面密度的极限；其方向由右手定则确定：

\[
(\nabla\times\mathbf F)\cdot\mathbf e_n
=\lim_{\Delta S\to0}\frac1{\Delta S}
\oint_{\Delta C}\mathbf F\cdot d\mathbf l.
\]

所以“旋度代表面积上的什么”应准确说成：**某点附近、以给定法向为朝向的单位面积环流强度**。旋度是矢量，不只是一个面积上的数。

### 8.3 直角坐标计算

\[
\nabla\times\mathbf F=
\begin{vmatrix}
\mathbf e_x&\mathbf e_y&\mathbf e_z\\
\partial_x&\partial_y&\partial_z\\
F_x&F_y&F_z
\end{vmatrix}.
\]

展开时中间 \(\mathbf e_y\) 项带负号。不要因为某题只有一个分量可能非零，就把其他分量永远忽略；应先看各分量依赖哪些变量，再逐项判断。

## 9. 斯托克斯定理

### 定义

\[
\oint_C\mathbf F\cdot d\mathbf l
=\iint_S(\nabla\times\mathbf F)\cdot d\mathbf S.
\]

其中 \(C=\partial S\)，曲线方向与曲面法向必须满足右手定则。

### 直观理解

边界一圈的总环流，等于该边界所围曲面上全部局部旋转效应的总和。

### 为什么散度画闭合曲面，旋度画闭合曲线

- 散度统计一个**体积**的净流出，所以边界是闭合曲面。
- 旋度统计一个**面片**内部的局部旋转总和，所以边界是闭合曲线。

## 10. 无旋场、无散场与保守场

### 定义

\[
\nabla\times\mathbf F=0\Rightarrow\text{无旋场},
\qquad
\nabla\cdot\mathbf F=0\Rightarrow\text{无散场}.
\]

若 \(\mathbf F=\nabla u\)（物理中也常写 \(-\nabla\varphi\)），则 \(\mathbf F\) 是势场。因为

\[
\nabla\times(\nabla u)=0.
\]

在**单连通区域**内，\(\nabla\times\mathbf F=0\) 才可推出存在单值势函数、线积分与路径无关。若区域有“洞”或奇点，不能省略这一条件。

类似地，

\[
\nabla\cdot(\nabla\times\mathbf A)=0.
\]

所以能写成某矢量势旋度的场必为无散场；反向表述也需要适当的区域与光滑性条件。

### 保守场的等价特征（适当区域内）

\[
\mathbf F=\nabla u
\Longleftrightarrow
\nabla\times\mathbf F=0
\Longleftrightarrow
\oint_C\mathbf F\cdot d\mathbf l=0
\Longleftrightarrow
\int_P^Q\mathbf F\cdot d\mathbf l\text{ 与路径无关}.
\]

## 11. 拉普拉斯运算

### 定义

\[
\nabla^2u=\nabla\cdot(\nabla u)
=\frac{\partial^2u}{\partial x^2}
+\frac{\partial^2u}{\partial y^2}
+\frac{\partial^2u}{\partial z^2}.
\]

一句话：**拉普拉斯是梯度的散度**。

### 需要掌握到什么程度

- 必须认识 \(\nabla^2\) 并会直角坐标计算。
- 知道 \(\nabla^2u=0\) 是拉普拉斯方程。
- 认识 \(\nabla^2u=f\) 是泊松型方程。
- 柱、球坐标长公式当前以查表会用为主，不必死背，除非教师另有要求。

以后静电场中 \(\mathbf E=-\nabla\varphi\)，所以对电场再求散度会自然出现 \(\nabla^2\varphi\)。

## 12. 格林定理（本课低优先级）

格林公式把体内的拉普拉斯信息与边界上的函数值、法向导数联系起来。

### 格林第一公式

\[
\iiint_V\left(\nabla u\cdot\nabla v+u\nabla^2v\right)dV
=\oiint_Su\frac{\partial v}{\partial n}\,dS.
\]

其中

\[
\frac{\partial v}{\partial n}=\nabla v\cdot\mathbf e_n.
\]

### 格林第二公式

\[
\iiint_V\left(u\nabla^2v-v\nabla^2u\right)dV
=\oiint_S\left(u\frac{\partial v}{\partial n}-v\frac{\partial u}{\partial n}\right)dS.
\]

### 理解而非硬背

格林第一公式可从散度定理作用于 \(u\nabla v\) 得到。当前掌握“见过、知道联系体内与边界、能认出 \(\nabla^2\) 和法向导数”即可；散度定理和斯托克斯定理优先级更高。

## 13. 最终对照表

| 内容 | 梯度体系 | 散度体系 | 旋度体系 |
|---|---|---|---|
| 输入 | 标量场 | 矢量场 | 矢量场 |
| 局部量 | \(\nabla u\) | \(\nabla\cdot\mathbf F\) | \(\nabla\times\mathbf F\) |
| 输出 | 矢量 | 标量 | 矢量 |
| 直观意义 | 最快增长 | 源/汇、净流出 | 局部旋转 |
| 对应积分 | 方向导数/势差 | 通量 | 环流 |
| 核心定理 | 线积分基本定理 | 散度定理 | 斯托克斯定理 |

