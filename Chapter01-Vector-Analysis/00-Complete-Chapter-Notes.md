# 第一章完整学习笔记：矢量分析

> 资料主线：教材第一章、课堂 PPT/黑板重点、课堂疑问，以及作业 1-3、1-6、1-11、1-12、1-14、1-19。本文按“定义 → 理解 → 计算 → 做题 → 易错点/疑问 → 老师重点”组织；习题与答案仍分别放在 [03-Exercises.md](03-Exercises.md) 和 [04-Exercise-Solutions.md](04-Exercise-Solutions.md)。

## 一、定义：先知道每个量是什么

### 1. 标量场、矢量场与场线

- 标量场：空间每一点对应一个标量，写成 $u=u(x,y,z)$ 。温度、密度、电势都是标量场。
- 等值面：$u(x,y,z)=C$ 。同一等值面上场值相同；单值标量场中，不同数值的等值面不能相交。
- 矢量场：空间每一点对应一个矢量，写成 $\mathbf F=F_x\mathbf e_x+F_y\mathbf e_y+F_z\mathbf e_z$ 。
- 矢量线：曲线在每一点的切向与该点场矢量平行。直角坐标中的方程为

$$
\frac{dx}{F_x}=\frac{dy}{F_y}=\frac{dz}{F_z}.
$$

### 2. 方向导数与梯度

沿单位方向 $\mathbf e_l$ 的方向导数为

$$
\frac{\partial u}{\partial l}=\nabla u\cdot\mathbf e_l.
$$

梯度为

$$
\nabla u=\mathbf e_x\frac{\partial u}{\partial x}
+\mathbf e_y\frac{\partial u}{\partial y}
+\mathbf e_z\frac{\partial u}{\partial z}.
$$

$\nabla u$ 的方向是增长最快方向，大小 $|\nabla u|$ 是最大方向导数，并且 $\nabla u$ 垂直于等值面。

### 3. 通量、散度与散度定理

穿过有向曲面 $S$ 的通量为

$$
\Phi=\iint_S\mathbf F\cdot d\mathbf S,
\qquad d\mathbf S=\mathbf e_n\,dS.
$$

散度是单位体积净流出率：

$$
\nabla\cdot\mathbf F
=\lim_{\Delta V\to0}\frac1{\Delta V}
∯_{\Delta S}\mathbf F\cdot d\mathbf S.
$$

散度定理把局部散度和闭合曲面总通量联系起来：

$$
∯_S\mathbf F\cdot d\mathbf S
=\iiint_V(\nabla\cdot\mathbf F)\,dV.
$$

### 4. 环流、旋度与斯托克斯定理

沿闭合曲线 $C$ 的环流为

$$
\Gamma=\oint_C\mathbf F\cdot d\mathbf l.
$$

旋度是局部环流面密度；其在单位法向 $\mathbf e_n$ 上的分量满足

$$
(\nabla\times\mathbf F)\cdot\mathbf e_n
=\lim_{\Delta S\to0}\frac1{\Delta S}
\oint_{\Delta C}\mathbf F\cdot d\mathbf l.
$$

斯托克斯定理为

$$
\oint_C\mathbf F\cdot d\mathbf l
=\iint_S(\nabla\times\mathbf F)\cdot d\mathbf S.
$$

### 5. 场的分类

| 类型 | 判据 | 直观特征 | 常用表示 |
|---|---|---|---|
| 无旋无散场 | $\nabla\times\mathbf F=0$ 且 $\nabla\cdot\mathbf F=0$ | 无局部旋转，也无局部净流出 | 势函数满足 $\nabla^2u=0$ |
| 有散无旋场 | $\nabla\cdot\mathbf F\ne0$ 且 $\nabla\times\mathbf F=0$ | 有源汇，无局部旋转 | $\mathbf F=-\nabla u$ |
| 无散有旋场 | $\nabla\cdot\mathbf F=0$ 且 $\nabla\times\mathbf F\ne0$ | 无净源汇，有局部旋转 | $\mathbf F=\nabla\times\mathbf A$ |
| 有散有旋场 | 两者一般均不为零 | 同时有源汇和旋转 | 亥姆霍兹分解 |

以上表示关系需要场和定义区域满足适当的光滑性、连通性及边界条件。

### 6. 拉普拉斯、格林公式与亥姆霍兹定理

拉普拉斯运算是“梯度的散度”：

$$
\nabla^2u=\nabla\cdot(\nabla u)
=u_{xx}+u_{yy}+u_{zz}.
$$

格林第一、第二公式把体内的梯度/拉普拉斯信息与边界上的函数值、法向导数联系起来：

$$
\iiint_V\left(\nabla u\cdot\nabla v+u\nabla^2v\right)dV
=∯_S u\frac{\partial v}{\partial n}\,dS,
$$

$$
\iiint_V\left(u\nabla^2v-v\nabla^2u\right)dV
=∯_S\left(u\frac{\partial v}{\partial n}
-v\frac{\partial u}{\partial n}\right)dS.
$$

其中 $\partial v/\partial n=\nabla v\cdot\mathbf e_n$ 。本课要求知道其作用和基本形式，优先级低于散度定理与斯托克斯定理。

亥姆霍兹定理的课堂表述：矢量场处处单值，所需阶导数连续且有界，源分布在有限空间区域内（或场在无穷远衰减足够快），并给定适当边界条件时，矢量场由散度和旋度唯一确定，且可写成

$$
\boxed{\mathbf F=-\nabla u+\nabla\times\mathbf A}.
$$

## 二、理解：把公式对应到几何图像

### 1. $\nabla$ 后面的符号决定它在做什么

| 写法 | 输入 | 输出 | 人话 |
|---|---|---|---|
| $\nabla u$ | 标量 | 矢量 | 往哪边增长最快 |
| $\nabla\cdot\mathbf F$ | 矢量 | 标量 | 一点附近净流出多少 |
| $\nabla\times\mathbf F$ | 矢量 | 矢量 | 一点附近绕哪根轴转、多强 |
| $\nabla^2u$ | 标量 | 标量 | 梯度再取散度 |

### 2. 为什么一张纸能算通量，却不能判断体内净流出

开曲面能计算“穿过这张面多少”，但它没有包住一个体积，无法统计所有入口和出口。闭合曲面完整包围体积，面积元统一取外法向：流入与外法向相反，贡献为负；流出与外法向同向，贡献为正。因此均匀场从一侧进入、另一侧离开时，净通量可以相互抵消。

### 3. “把小球缩到一点”是什么意思

先用一个小闭合曲面包住某点，计算净通量，再除以所包体积，最后让体积趋于零，得到的就是该点散度。散度大于零像源，小于零像汇，等于零只表示局部没有净产生或净消失，并不表示场为零。

### 4. 为什么散度看闭合曲面，旋度看闭合曲线

- 散度统计体积内的源汇，体积的边界是闭合曲面。
- 旋度统计面片内的局部旋转，面片的边界是闭合曲线。
- 通量取场的法向分量；环流取场沿曲线的切向分量。

### 5. 怎样从图判断散度和旋度

- 箭头平行、等长直线流：通常无散、无旋。
- 从一点向外发散或向一点汇聚：散度非零，若不绕圈则旋度为零。
- 绕中心成同心圆：旋度非零；若没有向外或向内的净流动，散度为零。
- 螺旋发散/汇聚：一般同时有散度和旋度。

图像只给直观判断；严格结论仍以 $\nabla\cdot\mathbf F$ 和 $\nabla\times\mathbf F$ 的计算为准，并注意奇点。

### 6. 亥姆霍兹定理在说什么

散度描述“源汇部分”，旋度描述“旋转部分”。亥姆霍兹定理说明：在合适条件下，这两类局部信息加上边界条件足以重建整个矢量场；一般场就是无旋部分 $-\nabla u$ 与无散部分 $\nabla\times\mathbf A$ 的叠加。

## 三、计算：考试时要能直接写出的公式

### 1. 矢量运算

$$
\mathbf A\cdot\mathbf B=A_xB_x+A_yB_y+A_zB_z,
\qquad
\cos\theta=\frac{\mathbf A\cdot\mathbf B}{|\mathbf A||\mathbf B|}.
$$

沿 $\mathbf C$ 方向的标量分量必须先单位化：

$$
A_C=\mathbf A\cdot\frac{\mathbf C}{|\mathbf C|}.
$$

$$
\mathbf A\times\mathbf B=
\begin{vmatrix}
\mathbf e_x&\mathbf e_y&\mathbf e_z\\
A_x&A_y&A_z\\
B_x&B_y&B_z
\end{vmatrix}.
$$

### 2. 梯度、散度、旋度

$$
\nabla u=(u_x,u_y,u_z),
$$

$$
\nabla\cdot\mathbf F
=\frac{\partial F_x}{\partial x}
+\frac{\partial F_y}{\partial y}
+\frac{\partial F_z}{\partial z},
$$

$$
\nabla\times\mathbf F=
\begin{vmatrix}
\mathbf e_x&\mathbf e_y&\mathbf e_z\\
\partial_x&\partial_y&\partial_z\\
F_x&F_y&F_z
\end{vmatrix}.
$$

柱坐标散度：

$$
\nabla\cdot\mathbf F
=\frac1\rho\frac{\partial(\rho F_\rho)}{\partial\rho}
+\frac1\rho\frac{\partial F_\phi}{\partial\phi}
+\frac{\partial F_z}{\partial z}.
$$

球坐标散度：

$$
\nabla\cdot\mathbf F
=\frac1{r^2}\frac{\partial(r^2F_r)}{\partial r}
+\frac1{r\sin\theta}\frac{\partial(F_\theta\sin\theta)}{\partial\theta}
+\frac1{r\sin\theta}\frac{\partial F_\phi}{\partial\phi}.
$$

柱、球坐标的旋度长公式应会查表和代入；直角坐标行列式必须熟练。

### 3. 线、面、体积分

| 积分 | 对象 | 典型物理量 |
|---|---|---|
| $\int_L\mathbf F\cdot d\mathbf l$ | 曲线 | 做功、环流 |
| $\iint_S\mathbf F\cdot d\mathbf S$ | 曲面 | 通量 |
| $\iiint_V f\,dV$ | 体积 | 体内总量 |

直角坐标：$d\mathbf l=\mathbf e_xdx+\mathbf e_ydy+\mathbf e_zdz$ 。球面 $r=\text{常数}$ ：

$$
d\mathbf S=\mathbf e_r r^2\sin\theta\,d\theta\,d\phi.
$$

### 4. 两个积分定理与两个恒等式

$$
∯_S\mathbf F\cdot d\mathbf S
=\iiint_V(\nabla\cdot\mathbf F)dV,
$$

$$
\oint_C\mathbf F\cdot d\mathbf l
=\iint_S(\nabla\times\mathbf F)\cdot d\mathbf S.
$$

$$
\boxed{\nabla\cdot(\nabla\times\mathbf A)=0},
\qquad
\boxed{\nabla\times(\nabla u)=0}.
$$

波动方程推导还要用

$$
\nabla\times(\nabla\times\mathbf A)
=\nabla(\nabla\cdot\mathbf A)-\nabla^2\mathbf A.
$$

## 四、做题：看到题目先怎么想

### 1. 通用决策顺序

1. 判断输入是标量场还是矢量场，目标结果应是标量还是矢量。
2. 看题目涉及曲线、开曲面、闭合曲面还是体积。
3. 选坐标系：平面/直角边界用直角坐标，轴对称用柱坐标，球对称用球坐标。
4. 检查方向：方向矢量是否单位化，曲面法向是否明确，曲线与法向是否满足右手定则。
5. 检查区域：是否闭合、是否单连通、是否含奇点。
6. 决定直接积分还是使用散度定理/斯托克斯定理。

### 2. 本章作业对应的题型模板

| 作业 | 先想到什么 | 核心方法 |
|---|---|---|
| 1-3 | “在某方向上的分量” | 先叉乘，再把目标方向单位化后点乘 |
| 1-6 | 球坐标场在直角坐标点取值 | 先求 $r$ ，再用 $\mathbf e_r=(x,y,z)/r$ 转分量 |
| 1-11 | 同一个 $\nabla$ 的三种运算 | 分清散度、旋度、梯度的输入和输出 |
| 1-12 | 两条路径的线积分是否相同 | 先查旋度和定义区域；保守场可用势函数端点差 |
| 1-14 | 能否写成梯度/旋度 | 想写成梯度先查旋度；想写成旋度先查散度 |
| 1-19 | 两个耦合旋度方程 | 再取一次旋度，代换，使用双重旋度恒等式 |

题目正文见 [练习题](03-Exercises.md)，完整计算只放在 [答案与解析](04-Exercise-Solutions.md)，避免做题时提前看到答案。更广的题型训练见 [题型库](02-Examples-and-Methods.md)。

### 3. 三种高频解题模板

**方向导数：**先求梯度 → 代入点 → 方向单位化 → 点乘。

**闭合曲面通量：**先算散度 → 判断体积积分是否更简单 → 写清外法向与积分范围。

**保守场：**算旋度 → 检查单连通和奇点 → 求势函数 → 用端点差代替路径积分。

## 五、易错点与课堂疑问

### 1. 等值面为什么不相交

不同等值面相交会使交点同时拥有两个不同场值，违背标量场的单值性。同一个等值面可以有多个互不连接的部分，这不等于两张不同数值的等值面相交。

### 2. “散度为零”是否等于“内部完全没有源”

只能说普通点处局部净流出为零。还要检查源点、奇点和区域边界。例如点源场在源点之外散度为零，但不能据此把源点忽略。散度为零更不等于场本身为零。

### 3. 为什么穿入与穿出能抵消

闭合曲面的面积元统一向外。穿入时 $\mathbf F\cdot d\mathbf S<0$ ，穿出时大于零；若进出相等，净通量为零。抵消的是带方向的通量，不是说场没有穿过曲面。

### 4. 环流面密度到底是什么

先沿一个很小闭合曲线计算环流，再除以该曲线围成的面积并让面积趋于零，得到旋度在该面法向上的分量。改变小面的法向，就在测旋度的不同方向分量。

### 5. 为什么有些旋度题只看 $z$ 分量

只有在题目恰好满足 $F_z=0$ 且 $F_x,F_y$ 与 $z$ 无关时，旋度的 $x,y$ 分量才会直接为零。这是题目结构造成的，不是旋度永远只有 $z$ 分量。

### 6. 无旋为什么不一定保守

$\nabla\times\mathbf F=0$ 是局部条件。若定义区域有洞或排除了奇点，绕洞一周的环流仍可能不为零。只有在适当的单连通区域内，才能安全地从无旋推出势函数单值、积分与路径无关。

### 7. 最常见的计算错误

- “沿某方向”忘记把方向矢量单位化。
- 把标量分量与矢量投影混为一谈。
- 旋度行列式展开漏掉中间项负号。
- 柱、球坐标漏掉 $\rho$、$r$、$r\sin\theta$ 等尺度因子。
- 对开曲面直接使用散度定理，忘记补面。
- 斯托克斯定理中曲线方向和曲面法向不满足右手定则。
- 求势函数时把“积分常数”误写成常数，漏掉它对其他变量的依赖。
- 双重旋度推导漏掉负号或把两次 $1/c$ 误写成一次。

### 8. 教材题面需要特别标记的两处

- 1-12：教材印刷页 27 写 $x=y^2$ ，但给定两端点不在同一条所写曲线上；按能连接两端点的 $x=2y^2$ 处理。
- 1-19：教材印刷页 28 的目标式写 $1/c$ ；由题设两条旋度方程直接推导应为 $1/c^2$ 。

## 六、老师重点：按复习优先级执行

### A 级：必须会写、会算、会判断

1. 区分标量场与矢量场，掌握基本矢量运算。
2. 等值面及“不同等值面不相交”。
3. 方向导数、梯度；知道梯度是矢量、指向最快增长方向并垂直等值面。
4. 矢量线及矢量线方程。
5. 通量、散度及散度计算公式。
6. 环流、环流面密度、旋度及旋度计算公式。
7. 散度定理与斯托克斯定理：会写公式、讲清几何对象、用于计算。
8. 从矢量图判断散度/旋度为零或非零，并用计算验证。
9. 四类场的判据与表示关系。
10. 两个恒等式：$\nabla\cdot(\nabla\times\mathbf A)=0$、$\nabla\times(\nabla u)=0$ 。

### B 级：必须会表述，计算以基础题为主

1. 亥姆霍兹定理的成立条件。
2. 分解形式 $\mathbf F=-\nabla u+\nabla\times\mathbf A$ 。
3. “散度 + 旋度 + 边界条件决定矢量场”的意义。
4. 拉普拉斯算子 $\nabla^2u=\nabla\cdot\nabla u$ 及直角坐标计算。

### C 级：认识和理解用途即可

1. 格林第一、第二公式。
2. 知道格林公式联系体积分与边界面积分，联系两个标量函数。
3. 柱坐标、球坐标下复杂的拉普拉斯/旋度公式以会查表为主。

### 考前自测清单

- [ ] 我能不看笔记写出梯度、散度、旋度的直角坐标公式。
- [ ] 我能解释开曲面与闭合曲面的区别，并判断面积元正负。
- [ ] 我能不混淆通量、环流、散度和旋度。
- [ ] 我能从四类示意图给出散度与旋度的零/非零判断。
- [ ] 我会用散度定理算闭合曲面通量。
- [ ] 我会用斯托克斯定理把环流换成面积分。
- [ ] 我能说出无旋推出保守所需的区域条件。
- [ ] 我能写出亥姆霍兹分解并说出课堂要求的三个成立条件。
- [ ] 我已独立完成六道作业，并能说明每题的第一判断步骤。
