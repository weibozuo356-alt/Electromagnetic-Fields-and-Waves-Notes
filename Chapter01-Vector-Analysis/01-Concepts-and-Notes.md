# 第一章 矢量分析：概念与课堂笔记

> 学习目标：看到一个量时，先判断它是标量还是矢量；看到一个积分时，先判断它沿线、过面还是在体内；看到 $\nabla$ 时，先看它后面是空乘、点乘还是叉乘。

## 1. 教材 1.1：标量场与矢量场

### 1.1.1 标量场

**标量**只有大小，没有方向，例如温度、密度、电势。若空间区域内每一点都对应一个确定的标量，就形成标量场：

$$
u=u(x,y,z).
$$

若还随时间变化，则写成 $u(x,y,z,t)$ ，称为时变标量场；与时间无关时称为静态或稳定标量场。

标量场可用**等值面**描述：

$$
u(x,y,z)=C.
$$

同一等值面上， $u$ 的数值相同。例如地形图的等高线就是二维情况下的等值线。

在单值标量场中，不同数值的等值面不能相交。若 $u=C_1$ 与 $u=C_2$ 在一点相交，该点就会同时具有两个不同的场值，与“每一点对应唯一标量”矛盾。

### 1.1.2 矢量场

**矢量**既有大小又有方向，例如速度、电场强度、磁感应强度。若空间每一点都有一个确定矢量，就形成矢量场：

$$
\mathbf A(x,y,z)=A_x\mathbf e_x+A_y\mathbf e_y+A_z\mathbf e_z.
$$

若各分量还依赖时间，则是 $\mathbf A(x,y,z,t)$ 。矢量场常用带箭头的场线表示：场线上每一点的切线方向与该点矢量方向一致，场线疏密可辅助表示场的强弱。

若矢量线写成参数曲线 $\mathbf r(s)$ ，其切向应与场 $\mathbf A$ 平行，因此

$$
\frac{d\mathbf r}{ds}\parallel\mathbf A.
$$

在直角坐标中常写成矢量线方程

$$
\frac{dx}{A_x}=\frac{dy}{A_y}=\frac{dz}{A_z}.
$$

求矢量线时，把它拆成两个独立的常微分方程并积分，再用给定经过点确定积分常数。

### 1.1.3 位置矢量与单位方向

直角坐标中一点 $P(x,y,z)$ 的位置矢量为

$$
\mathbf r=x\mathbf e_x+y\mathbf e_y+z\mathbf e_z,
\qquad r=|\mathbf r|=\sqrt{x^2+y^2+z^2}.
$$

从点 $P_1$ 指向点 $P_2$ 的矢量为

$$
\mathbf R_{12}=\mathbf r_2-\mathbf r_1,
\qquad
\mathbf e_{12}=\frac{\mathbf R_{12}}{|\mathbf R_{12}|}.
$$

单位矢量只表达方向，长度恒为 1。求“沿某方向的分量”时必须使用单位矢量，原因就在这里。

### 直观理解

标量场像一张“空间温度地图”；矢量场则像在每一点都画了一支有长短、有方向的小箭头。

### 怎么判断题目给的是场还是单个量

- 只给一个固定数或固定矢量：描述的是一个量。
- 给出坐标函数 $u(x,y,z)$ 或 $\mathbf A(x,y,z)$ ：描述的是场。
- 同一个矢量场在不同位置通常大小、方向都可能不同；坐标单位矢量在柱坐标、球坐标中也会随位置变化。

## 2. 教材 1.2：矢量运算

### 1.2.1 矢量加法、减法与数乘

在同一组基底下，对应分量分别运算：

$$
\mathbf A\pm\mathbf B
=(A_x\pm B_x)\mathbf e_x
+(A_y\pm B_y)\mathbf e_y
+(A_z\pm B_z)\mathbf e_z.
$$

数乘 $k\mathbf A$ 将大小变为 $|k||\mathbf A|$ ；当 $k<0$ 时方向反转。

矢量加法满足交换律和结合律；减法可理解为加上反向矢量。几何上，加法使用平行四边形法则或首尾相接法则。

### 1.2.2 标量积（点积）

### 定义与计算

在正交单位基底中，

$$
\mathbf A\cdot\mathbf B
=|\mathbf A||\mathbf B|\cos\theta
=A_xB_x+A_yB_y+A_zB_z.
$$

点积结果是标量。它衡量两个矢量方向的一致程度：同向为正，垂直为零，夹角为钝角时为负。

### 为什么点积只剩对应分量

因为

$$
\mathbf e_i\cdot\mathbf e_j=
\begin{cases}1,&i=j,\\0,&i\ne j.\end{cases}
$$

同方向单位矢量点乘为 1，不同方向为 0。因此“在 $\mathbf C$ 方向上的标量分量”必须用单位方向：

$$
A_C=\mathbf A\cdot\mathbf e_C,
\qquad \mathbf e_C=\frac{\mathbf C}{|\mathbf C|}.
$$

若题目问矢量投影，则结果是 $(\mathbf A\cdot\mathbf e_C)\mathbf e_C$ 。

由点积还能求夹角：

$$
\cos\theta=\frac{\mathbf A\cdot\mathbf B}{|\mathbf A||\mathbf B|}.
$$

### 1.2.3 矢量积（叉积）

$$
|\mathbf A\times\mathbf B|=|\mathbf A||\mathbf B|\sin\theta,
$$

方向垂直于 $\mathbf A$ 、 $\mathbf B$ 所在平面，由右手定则确定。直角坐标下

$$
\mathbf A\times\mathbf B=
\begin{vmatrix}
\mathbf e_x&\mathbf e_y&\mathbf e_z\\
A_x&A_y&A_z\\
B_x&B_y&B_z
\end{vmatrix}.
$$

叉积结果是矢量，且

$$
\mathbf A\times\mathbf B=-\mathbf B\times\mathbf A,
\qquad
\mathbf A\times\mathbf A=0.
$$

几何上， $|\mathbf A\times\mathbf B|$ 等于两矢量张成的平行四边形面积。若需要单位法向量，可用

$$
\mathbf e_n=\frac{\mathbf A\times\mathbf B}{|\mathbf A\times\mathbf B|}.
$$

### 1.2.4 标量三重积与矢量三重积

标量三重积

$$
\mathbf A\cdot(\mathbf B\times\mathbf C)
$$

的绝对值是三矢量构成的平行六面体体积，并满足循环置换不变：

$$
\mathbf A\cdot(\mathbf B\times\mathbf C)
=\mathbf B\cdot(\mathbf C\times\mathbf A)
=\mathbf C\cdot(\mathbf A\times\mathbf B).
$$

若它等于 0，三矢量共面。

矢量三重积不能随意交换括号：

$$
\mathbf A\times(\mathbf B\times\mathbf C)
=\mathbf B(\mathbf A\cdot\mathbf C)
-\mathbf C(\mathbf A\cdot\mathbf B).
$$

记忆为“BAC-CAB”。一般

$$
(\mathbf A\times\mathbf B)\times\mathbf C
\ne\mathbf A\times(\mathbf B\times\mathbf C).
$$

### 1.2.5 方向余弦

若矢量 $\mathbf A$ 与 $x,y,z$ 轴正向夹角分别为 $\alpha,\beta,\gamma$ ，则

$$
\cos\alpha=\frac{A_x}{|\mathbf A|},
\quad
\cos\beta=\frac{A_y}{|\mathbf A|},
\quad
\cos\gamma=\frac{A_z}{|\mathbf A|},
$$

且

$$
\cos^2\alpha+\cos^2\beta+\cos^2\gamma=1.
$$

## 3. 教材 1.3：坐标系

坐标系不只是换三个数字，还要同时处理：坐标变量、单位矢量、矢量分量以及线/面/体微元。直角坐标基底固定；柱坐标和球坐标的单位矢量会随位置改变。

### 1.3.1 直角坐标系

$$
\mathbf r=x\mathbf e_x+y\mathbf e_y+z\mathbf e_z,
\qquad
d\mathbf l=\mathbf e_xdx+\mathbf e_ydy+\mathbf e_zdz.
$$

三个坐标面的有向面积元分别为

$$
d\mathbf S_x=\mathbf e_x\,dy\,dz,
\quad
d\mathbf S_y=\mathbf e_y\,dz\,dx,
\quad
d\mathbf S_z=\mathbf e_z\,dx\,dy,
$$

$$
dV=dx\,dy\,dz.
$$

### 1.3.2 柱坐标系

$$
x=\rho\cos\phi,\quad y=\rho\sin\phi,\quad z=z,
$$

$$
\rho=\sqrt{x^2+y^2},
\qquad
\phi=\text{atan2}(y,x).
$$

单位矢量关系为

$$
\mathbf e_\rho=\cos\phi\,\mathbf e_x+\sin\phi\,\mathbf e_y,
$$

$$
\mathbf e_\phi=-\sin\phi\,\mathbf e_x+\cos\phi\,\mathbf e_y,
\qquad
\mathbf e_z=\mathbf e_z.
$$

线元为

$$
d\mathbf l=\mathbf e_\rho d\rho+\mathbf e_\phi\rho d\phi+\mathbf e_zdz.
$$

三个坐标面的面积元大小分别为

$$
dS_\rho=\rho\,d\phi\,dz,
\quad
dS_\phi=d\rho\,dz,
\quad
dS_z=\rho\,d\rho\,d\phi,
$$

$$
dV=\rho\,d\rho\,d\phi\,dz.
$$

### 1.3.3 球坐标系

$$
x=r\sin\theta\cos\phi,
\quad y=r\sin\theta\sin\phi,
\quad z=r\cos\theta.
$$

$$
\mathbf e_r
=\sin\theta\cos\phi\,\mathbf e_x
+\sin\theta\sin\phi\,\mathbf e_y
+\cos\theta\,\mathbf e_z,
$$

$$
\mathbf e_\theta
=\cos\theta\cos\phi\,\mathbf e_x
+\cos\theta\sin\phi\,\mathbf e_y
-\sin\theta\,\mathbf e_z,
$$

$$
\mathbf e_\phi=-\sin\phi\,\mathbf e_x+\cos\phi\,\mathbf e_y.
$$

也可直接使用

$$
\mathbf e_r=\frac{x}{r}\mathbf e_x+\frac{y}{r}\mathbf e_y+\frac{z}{r}\mathbf e_z.
$$

线元为

$$
d\mathbf l
=\mathbf e_rdr+\mathbf e_\theta r\,d\theta
+\mathbf e_\phi r\sin\theta\,d\phi.
$$

三个坐标面的面积元大小分别为

$$
dS_r=r^2\sin\theta\,d\theta\,d\phi,
\quad
dS_\theta=r\sin\theta\,dr\,d\phi,
\quad
dS_\phi=r\,dr\,d\theta,
$$

$$
dV=r^2\sin\theta\,dr\,d\theta\,d\phi.
$$

### 1.3.4 坐标选择与易错点

做题先看“场用什么坐标表示、积分区域用什么坐标最简单”，不要机械换坐标：

- 长方体、平面边界：常用直角坐标。
- 圆柱、圆环、绕轴对称：常用柱坐标。
- 球面、径向场：常用球坐标。
- 柱、球坐标的弧长不是单纯 $d\phi$ 、 $d\theta$ ，必须带尺度因子 $\rho$ 、 $r$ 、 $r\sin\theta$ 。
- 面积元既有大小又有法向；写通量时应使用有向面积元 $d\mathbf S$ 。
- 同一个符号 $\phi$ 在不同教材中可能约定不同，应先确认本书用 $\theta$ 表示极角、 $\phi$ 表示方位角。

## 4. 方向导数与梯度

### 定义

标量场 $u$ 在单位方向 $\mathbf e_l$ 上的方向导数是

$$
\frac{\partial u}{\partial l}=\nabla u\cdot\mathbf e_l.
$$

梯度定义为

$$
\text{grad}\,u=\nabla u
=\mathbf e_x\frac{\partial u}{\partial x}
+\mathbf e_y\frac{\partial u}{\partial y}
+\mathbf e_z\frac{\partial u}{\partial z}.
$$

### 直观理解

- $\nabla u$ 的方向： $u$ 增长最快的方向。
- $|\nabla u|$ ：最大方向导数。
- $\nabla u$ 垂直于等值面。

方向导数回答“沿指定方向变多快”；梯度一次给出“最快往哪走、最快有多快”。方向向量必须先单位化，否则会混入它本身的长度。

### 计算模板

1. 求 $\nabla u$ 。
2. 代入指定点。
3. 将给定方向 $\mathbf a$ 单位化为 $\mathbf e_l=\mathbf a/|\mathbf a|$ 。
4. 点乘 $\nabla u\cdot\mathbf e_l$ 。

## 5. 哈密顿算子 $\nabla$

### 定义

$$
\nabla=\mathbf e_x\frac{\partial}{\partial x}
+\mathbf e_y\frac{\partial}{\partial y}
+\mathbf e_z\frac{\partial}{\partial z}.
$$

它不是普通矢量，而是一个由偏导数组成的微分算子。后面的运算决定意义：

| 写法 | 名称 | 输入 | 输出 |
|---|---|---|---|
| $\nabla u$ | 梯度 | 标量 | 矢量 |
| $\nabla\cdot\mathbf F$ | 散度 | 矢量 | 标量 |
| $\nabla\times\mathbf F$ | 旋度 | 矢量 | 矢量 |
| $\nabla^2u$ | 拉普拉斯运算 | 标量 | 标量 |

## 6. 通量与散度

### 6.1 通量的定义

矢量场穿过有向曲面 $S$ 的通量为

$$
\Phi=\iint_S\mathbf F\cdot d\mathbf S,
\qquad d\mathbf S=\mathbf e_n\,dS.
$$

点积只保留法向分量：切着曲面流动不穿过曲面，对通量没有贡献。

### 6.2 开曲面与闭合曲面

一张纸当然可以算通量；它能回答“有多少场穿过这张纸”。但开曲面没有完整包住体积，所以不能单靠它统计某一体积的净流入、净流出。

闭合曲面 $S$ 完整围住一个有限体积 $V$ ，面积元统一取外法线。流出与外法线同向，贡献为正；流入与外法线反向，贡献为负。均匀场若进多少、出多少，净通量便为零。

因此，闭合曲面不是因为“内部变成绝对独立的空间”，而是因为它把统计对象的全部边界都包含了。

### 6.3 散度的定义

$$
\nabla\cdot\mathbf F
=\lim_{\Delta V\to0}
\frac{1}{\Delta V}
∯_{\Delta S}\mathbf F\cdot d\mathbf S.
$$

这正是“把包围一点的小球不断缩小”的严格表达：散度是单位体积的净流出率。

$$
\nabla\cdot\mathbf F>0\text{：局部像源},\quad
\nabla\cdot\mathbf F<0\text{：局部像汇},\quad
\nabla\cdot\mathbf F=0\text{：局部净流出为零}.
$$

### 重要纠正：散度为零不等于场为零

散度为零只说明“这里没有净产生或净消失”，场仍可存在并穿过区域。均匀流场就是典型例子。讨论“有没有源”还要说明区域以及是否含奇点；例如点源场在源点之外散度可为零，但源点本身不能忽略。

### 直角坐标计算

$$
\nabla\cdot\mathbf F=
\frac{\partial F_x}{\partial x}+
\frac{\partial F_y}{\partial y}+
\frac{\partial F_z}{\partial z}.
$$

记忆： $x$ 分量对 $x$ ， $y$ 分量对 $y$ ， $z$ 分量对 $z$ ，再相加。

### 柱坐标和球坐标

$$
\nabla\cdot\mathbf F
=\frac1\rho\frac{\partial(\rho F_\rho)}{\partial\rho}
+\frac1\rho\frac{\partial F_\phi}{\partial\phi}
+\frac{\partial F_z}{\partial z},
$$

$$
\nabla\cdot\mathbf F
=\frac1{r^2}\frac{\partial(r^2F_r)}{\partial r}
+\frac1{r\sin\theta}\frac{\partial(F_\theta\sin\theta)}{\partial\theta}
+\frac1{r\sin\theta}\frac{\partial F_\phi}{\partial\phi}.
$$

## 7. 散度定理

### 定义

$$
∯_S\mathbf F\cdot d\mathbf S
=\iiint_V(\nabla\cdot\mathbf F)\,dV.
$$

### 直观理解

整个闭合表面的净流出量，等于内部每一点局部净流出率的总和：

$$
\text{边界上的净通量}=\text{体内所有源汇效应之和}.
$$

### 什么时候用

- 题目给闭合曲面通量，而直接逐面算很繁琐。
- 散度容易算，体积积分范围简单。
- 反过来，也可用已知通量判断体内源的总量。

## 8. 环流与旋度

### 8.1 环流的定义

$$
\Gamma=\oint_C\mathbf F\cdot d\mathbf l.
$$

它度量矢量场沿闭合曲线切向“推着你绕一圈”的总效果。通量看法向穿过，环流看切向推动。

### 8.2 旋度的定义

旋度是局部环流面密度的极限；其方向由右手定则确定：

$$
(\nabla\times\mathbf F)\cdot\mathbf e_n
=\lim_{\Delta S\to0}\frac1{\Delta S}
\oint_{\Delta C}\mathbf F\cdot d\mathbf l.
$$

所以“旋度代表面积上的什么”应准确说成：**某点附近、以给定法向为朝向的单位面积环流强度**。旋度是矢量，不只是一个面积上的数。

### 8.3 直角坐标计算

$$
\nabla\times\mathbf F=
\begin{vmatrix}
\mathbf e_x&\mathbf e_y&\mathbf e_z\\
\partial_x&\partial_y&\partial_z\\
F_x&F_y&F_z
\end{vmatrix}.
$$

展开时中间 $\mathbf e_y$ 项带负号。不要因为某题只有一个分量可能非零，就把其他分量永远忽略；应先看各分量依赖哪些变量，再逐项判断。

## 9. 斯托克斯定理

### 定义

$$
\oint_C\mathbf F\cdot d\mathbf l
=\iint_S(\nabla\times\mathbf F)\cdot d\mathbf S.
$$

其中 $C=\partial S$ ，曲线方向与曲面法向必须满足右手定则。

### 直观理解

边界一圈的总环流，等于该边界所围曲面上全部局部旋转效应的总和。

### 为什么散度画闭合曲面，旋度画闭合曲线

- 散度统计一个**体积**的净流出，所以边界是闭合曲面。
- 旋度统计一个**面片**内部的局部旋转总和，所以边界是闭合曲线。

## 10. 无旋场、无散场与保守场

### 定义

$$
\nabla\times\mathbf F=0\Rightarrow\text{无旋场},
\qquad
\nabla\cdot\mathbf F=0\Rightarrow\text{无散场}.
$$

若 $\mathbf F=\nabla u$ （物理中也常写 $-\nabla\varphi$ ），则 $\mathbf F$ 是势场。因为

$$
\nabla\times(\nabla u)=0.
$$

在**单连通区域**内， $\nabla\times\mathbf F=0$ 才可推出存在单值势函数、线积分与路径无关。若区域有“洞”或奇点，不能省略这一条件。

类似地，

$$
\nabla\cdot(\nabla\times\mathbf A)=0.
$$

所以能写成某矢量势旋度的场必为无散场；反向表述也需要适当的区域与光滑性条件。

> 教材勘误：印刷页 20 的式（1.6.12）在 $\nabla$ 与标量 $\varphi$ 之间多印了一个点。教材印刷页 14 已定义 $\operatorname{grad}u=\nabla u$ ，所以“任一标量场梯度的旋度恒为零”的正确写法是 $\nabla\times(\nabla\varphi)=0$ 。若写成 $\nabla\cdot\varphi$ ，运算类型不成立，因为散度只能作用于矢量场。

### 保守场的等价特征（适当区域内）

$$
\mathbf F=\nabla u
\Longleftrightarrow
\nabla\times\mathbf F=0
\Longleftrightarrow
\oint_C\mathbf F\cdot d\mathbf l=0
\Longleftrightarrow
\int_P^Q\mathbf F\cdot d\mathbf l\text{ 与路径无关}.
$$

## 11. 拉普拉斯运算

### 定义

$$
\nabla^2u=\nabla\cdot(\nabla u)
=\frac{\partial^2u}{\partial x^2}
+\frac{\partial^2u}{\partial y^2}
+\frac{\partial^2u}{\partial z^2}.
$$

一句话：**拉普拉斯是梯度的散度**。

### 需要掌握到什么程度

- 必须认识 $\nabla^2$ 并会直角坐标计算。
- 知道 $\nabla^2u=0$ 是拉普拉斯方程。
- 认识 $\nabla^2u=f$ 是泊松型方程。
- 柱、球坐标长公式当前以查表会用为主，不必死背，除非教师另有要求。

以后静电场中 $\mathbf E=-\nabla\varphi$ ，所以对电场再求散度会自然出现 $\nabla^2\varphi$ 。

## 12. 格林定理（本课低优先级）

格林公式把体内的拉普拉斯信息与边界上的函数值、法向导数联系起来。

### 格林第一公式

$$
\iiint_V\left(\nabla u\cdot\nabla v+u\nabla^2v\right)dV
=∯_Su\frac{\partial v}{\partial n}\,dS.
$$

其中

$$
\frac{\partial v}{\partial n}=\nabla v\cdot\mathbf e_n.
$$

### 格林第二公式

$$
\iiint_V\left(u\nabla^2v-v\nabla^2u\right)dV
=∯_S\left(u\frac{\partial v}{\partial n}-v\frac{\partial u}{\partial n}\right)dS.
$$

### 理解而非硬背

格林第一公式可从散度定理作用于 $u\nabla v$ 得到。当前掌握“见过、知道联系体内与边界、能认出 $\nabla^2$ 和法向导数”即可；散度定理和斯托克斯定理优先级更高。

## 13. 亥姆霍兹定理

### 课堂要求掌握的定义与条件

若矢量场在全空间中处处单值，具有连续且有界的所需阶导数，并且源分布限制在有限空间区域内（或场在无穷远衰减得足够快），那么在给定适当边界条件后，场由它的散度和旋度唯一确定。

### 分解形式

$$
\boxed{\mathbf F=-\nabla u+\nabla\times\mathbf A}
$$

其中 $-\nabla u$ 是无旋部分， $\nabla\times\mathbf A$ 是无散部分。它说明一个一般的有散有旋场可以拆成“源汇效应”和“旋转效应”的叠加。

若采用全空间中在无穷远衰减的常用边界条件，可由散度和旋度构造势函数：

$$
u(\mathbf r)=\frac1{4\pi}\iiint
\frac{\nabla'\cdot\mathbf F(\mathbf r')}{|\mathbf r-\mathbf r'|}\,dV',
$$

$$
\mathbf A(\mathbf r)=\frac1{4\pi}\iiint
\frac{\nabla'\times\mathbf F(\mathbf r')}{|\mathbf r-\mathbf r'|}\,dV'.
$$

现阶段重点是会写分解式、说出成立条件，并知道“散度 + 旋度 + 边界条件决定矢量场”；势函数积分式以认识为主。

## 14. 最终对照表

| 内容 | 梯度体系 | 散度体系 | 旋度体系 |
|---|---|---|---|
| 输入 | 标量场 | 矢量场 | 矢量场 |
| 局部量 | $\nabla u$ | $\nabla\cdot\mathbf F$ | $\nabla\times\mathbf F$ |
| 输出 | 矢量 | 标量 | 矢量 |
| 直观意义 | 最快增长 | 源/汇、净流出 | 局部旋转 |
| 对应积分 | 方向导数/势差 | 通量 | 环流 |
| 核心定理 | 线积分基本定理 | 散度定理 | 斯托克斯定理 |
