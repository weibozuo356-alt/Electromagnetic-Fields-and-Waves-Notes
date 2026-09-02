# 第一章题型库：从基本用法到综合进阶

本页不局限于教材作业，而是训练“看到题目以后先想到什么”。教材作业的完整答案仍单独放在[练习题答案](04-Exercise-Solutions.md)中。

## 使用方法

| 层级 | 题型 | 学习目标 |
|---|---|---|
| A 基础 | 题型 1–6 | 会进行矢量、坐标和微分运算 |
| B 积分 | 题型 7–11 | 会计算线积分、通量，并选择积分定理 |
| C 判断 | 题型 12–15 | 会判断场的性质并寻找势函数 |
| D 进阶 | 题型 16–20 | 会处理奇点、恒等式、拉普拉斯和波动方程 |

每道题先问四件事：输入是什么？输出是标量还是矢量？直接计算还是使用定理？坐标、方向、区域和奇点条件是否满足？

---

## A. 基础运算题型

### 题型 1：矢量大小、单位矢量与方向余弦

#### 识别信号

题目要求矢量的大小、方向、单位矢量，或者与三个坐标轴的夹角。

#### 方法

对 $\mathbf A=A_x\mathbf e_x+A_y\mathbf e_y+A_z\mathbf e_z$ ，

$$
|\mathbf A|=\sqrt{A_x^2+A_y^2+A_z^2},
\qquad
\mathbf e_A=\frac{\mathbf A}{|\mathbf A|}.
$$

$$
\cos\alpha=\frac{A_x}{|\mathbf A|},
\quad
\cos\beta=\frac{A_y}{|\mathbf A|},
\quad
\cos\gamma=\frac{A_z}{|\mathbf A|}.
$$

#### 例题

设 $\mathbf A=2\mathbf e_x-\mathbf e_y+2\mathbf e_z$ 。则 $|\mathbf A|=3$ ，且

$$
\mathbf e_A=\frac23\mathbf e_x-\frac13\mathbf e_y+\frac23\mathbf e_z.
$$

#### 易错点

零矢量没有确定方向，不能单位化。

### 题型 2：点积、夹角与投影

#### 识别信号

题目出现“夹角”“垂直”“在某方向上的分量”或“投影”。

$$
\mathbf A\cdot\mathbf B
=A_xB_x+A_yB_y+A_zB_z
=|\mathbf A||\mathbf B|\cos\theta.
$$

在 $\mathbf C$ 方向上的标量分量与矢量投影分别为

$$
A_C=\mathbf A\cdot\frac{\mathbf C}{|\mathbf C|},
$$

$$
\mathbf A_C
=\left(\mathbf A\cdot\frac{\mathbf C}{|\mathbf C|}\right)
\frac{\mathbf C}{|\mathbf C|}.
$$

#### 例题

求 $\mathbf A=(1,2,2)$ 在 $\mathbf C=(1,-1,0)$ 方向上的标量分量。

$$
A_C=\frac{1-2}{\sqrt2}=-\frac1{\sqrt2}.
$$

负号表示投影指向 $-\mathbf C$ 一侧。最常见错误是直接计算 $\mathbf A\cdot\mathbf C$ ，忘记单位化方向。

### 题型 3：叉积、面积与法向量

#### 识别信号

题目要求垂直方向、平面法向、平行四边形面积或三角形面积。

$$
\mathbf A\times\mathbf B=
\begin{vmatrix}
\mathbf e_x&\mathbf e_y&\mathbf e_z\\
A_x&A_y&A_z\\
B_x&B_y&B_z
\end{vmatrix}.
$$

平行四边形面积是 $|\mathbf A\times\mathbf B|$ ，三角形面积是它的一半。单位法向量为

$$
\mathbf e_n=\frac{\mathbf A\times\mathbf B}{|\mathbf A\times\mathbf B|}.
$$

#### 易错点

- 交换叉积顺序会改变符号。
- 行列式展开时中间的 $\mathbf e_y$ 项带负号。
- 题目规定的法向可能与叉积所得方向相反。

### 题型 4：三重积、体积与共面判断

标量三重积

$$
V=\mathbf A\cdot(\mathbf B\times\mathbf C)
$$

的绝对值是平行六面体体积；若结果为 0，则三个矢量共面。

矢量三重积使用

$$
\mathbf A\times(\mathbf B\times\mathbf C)
=\mathbf B(\mathbf A\cdot\mathbf C)
-\mathbf C(\mathbf A\cdot\mathbf B).
$$

叉积不满足结合律，不要随意移动括号。

### 题型 5：三种坐标系之间的转换

#### 识别信号

场用柱坐标或球坐标给出，却要求直角坐标分量、指定点的值或夹角。

柱坐标常用关系：

$$
x=\rho\cos\phi,
\qquad
y=\rho\sin\phi.
$$

$$
\mathbf e_\rho=\cos\phi\,\mathbf e_x+\sin\phi\,\mathbf e_y,
\qquad
\mathbf e_\phi=-\sin\phi\,\mathbf e_x+\cos\phi\,\mathbf e_y.
$$

球坐标的径向单位矢量为

$$
\mathbf e_r
=\frac{x\mathbf e_x+y\mathbf e_y+z\mathbf e_z}
{\sqrt{x^2+y^2+z^2}}.
$$

#### 做题顺序

1. 把指定点转换为场所使用的坐标。
2. 计算场在该点的分量。
3. 若要求直角坐标分量，再转换单位矢量。

柱、球坐标的单位矢量会随位置改变，不能把 $\mathbf e_r$ 当成固定的 $\mathbf e_x$ 。

### 题型 6：方向导数、梯度与最大变化率

#### 识别信号

题目出现“沿某方向变化率”“增长最快方向”“最大方向导数”或“等值面法向”。

$$
\nabla u
=\mathbf e_x\frac{\partial u}{\partial x}
+\mathbf e_y\frac{\partial u}{\partial y}
+\mathbf e_z\frac{\partial u}{\partial z}.
$$

沿单位方向 $\mathbf e_l$ 的方向导数为

$$
\frac{\partial u}{\partial l}=\nabla u\cdot\mathbf e_l.
$$

最大方向导数是 $|\nabla u|$ ，其方向是 $\nabla u$ 。

#### 例题

设 $u=x^2+y^2+z^2$ 。在点 $(1,-2,2)$ 处， $\nabla u=(2,-4,4)$ ，所以最大变化率为 6，最快方向为 $(1,-2,2)/3$ 。

---

## B. 微分、积分与定理题型

### 题型 7：散度与旋度的基本计算

- $\nabla\cdot\mathbf F$ 的结果是标量。
- $\nabla\times\mathbf F$ 的结果是矢量。

$$
\nabla\cdot\mathbf F
=\frac{\partial F_x}{\partial x}
+\frac{\partial F_y}{\partial y}
+\frac{\partial F_z}{\partial z}.
$$

$$
\nabla\times\mathbf F=
\begin{vmatrix}
\mathbf e_x&\mathbf e_y&\mathbf e_z\\
\partial_x&\partial_y&\partial_z\\
F_x&F_y&F_z
\end{vmatrix}.
$$

#### 例题

设 $\mathbf F=x^2\mathbf e_x+xy\mathbf e_y+yz\mathbf e_z$ ，则

$$
\nabla\cdot\mathbf F=2x+x+y=3x+y.
$$

若场在柱坐标或球坐标中给出，通常应直接使用相应坐标系的公式。

### 题型 8：曲线参数化与线积分

令

$$
\mathbf r(t)=(x(t),y(t),z(t)),
\qquad a\le t\le b.
$$

则

$$
\int_L\mathbf F\cdot d\mathbf l
=\int_a^b\mathbf F(\mathbf r(t))\cdot\mathbf r'(t)dt.
$$

#### 例题

设 $\mathbf F=(-y,x,0)$ ，沿单位圆逆时针一周。取 $\mathbf r(t)=(\cos t,\sin t,0)$ ，则

$$
\oint_C\mathbf F\cdot d\mathbf l=2\pi.
$$

路径反向时线积分变号；分段路径要分段积分后相加。

### 题型 9：直接计算曲面通量

通量为

$$
\Phi=\iint_S\mathbf F\cdot d\mathbf S.
$$

若曲面写成 $z=f(x,y)$ ，向上的有向面积元为

$$
d\mathbf S
=\left(-\frac{\partial f}{\partial x},
-\frac{\partial f}{\partial y},1\right)dx\,dy.
$$

#### 例题

设 $\mathbf F=z\mathbf e_z$ 。它穿过平面 $z=2$ 上单位圆盘、法向向上的通量为 $2\pi$ 。

面积元必须包含方向；法向反向时答案变号。

### 题型 10：散度定理与补面法

曲面闭合、直接逐面计算繁琐，而散度简单时，优先考虑

$$
∯_S\mathbf F\cdot d\mathbf S
=\iiint_V(\nabla\cdot\mathbf F)dV.
$$

若原曲面 $S_1$ 不闭合，补上简单曲面 $S_2$ ：

$$
\Phi_{S_1}=\Phi_{S_1+S_2}-\Phi_{S_2}.
$$

#### 例题

设 $\mathbf F=(x,y,z)$ 。半径为 $a$ 的球面外向通量为

$$
\Phi=3\cdot\frac43\pi a^3=4\pi a^3.
$$

补面的法向必须与闭合曲面的统一外法向一致。

### 题型 11：斯托克斯定理与换面技巧

$$
\oint_C\mathbf F\cdot d\mathbf l
=\iint_S(\nabla\times\mathbf F)\cdot d\mathbf S.
$$

只要边界 $C$ 相同，就可以把复杂曲面换成简单曲面。曲线方向与曲面法向必须满足右手定则。

#### 例题

设 $\mathbf F=(-y/2,x/2,0)$ ， $C$ 是 $xy$ 平面内单位圆的逆时针边界。因为 $\nabla\times\mathbf F=\mathbf e_z$ ，取单位圆盘为 $S$ ，得到

$$
\oint_C\mathbf F\cdot d\mathbf l=\pi.
$$

---

## C. 场的判断与势函数题型

### 题型 12：判断保守场与路径无关

在适当的单连通区域内，

$$
\mathbf F=\nabla u
\Longleftrightarrow
\nabla\times\mathbf F=0
\Longleftrightarrow
\oint_C\mathbf F\cdot d\mathbf l=0.
$$

它们还等价于两点间线积分与路径无关。

#### 做题方法

1. 计算旋度。
2. 检查区域是否有洞或奇点。
3. 若为保守场，寻找势函数。
4. 用端点势函数之差代替线积分。

只写“旋度为零，所以一定保守”不够严谨；必须检查定义区域。

### 题型 13：由矢量场反求标量势函数

若 $\mathbf F=(P,Q,R)=\nabla u$ ，则

$$
\frac{\partial u}{\partial x}=P,
\quad
\frac{\partial u}{\partial y}=Q,
\quad
\frac{\partial u}{\partial z}=R.
$$

#### 逐分量积分法

1. 对 $P$ 关于 $x$ 积分，保留未知函数 $g(y,z)$ 。
2. 与 $Q$ 比较，求 $g$ 对 $y$ 的依赖。
3. 再与 $R$ 比较，求剩余函数。
4. 最后加任意常数。

例如 $\mathbf F=(2x,2y,2z)$ 的势函数为 $u=x^2+y^2+z^2+C$ 。

### 题型 14：判断能否表示为旋度

若 $\mathbf F=\nabla\times\mathbf A$ ，则必有

$$
\nabla\cdot\mathbf F=0.
$$

所以想判断一个场能否写成旋度，先算散度。在适当区域和光滑条件下可进一步构造矢量势。

矢量势通常不唯一，因为

$$
\nabla\times(\mathbf A+\nabla\psi)
=\nabla\times\mathbf A.
$$

### 题型 15：源分布、汇与局部判断

源分布由 $\nabla\cdot\mathbf F$ 给出：散度大于零像源，小于零像汇，等于零表示局部净流出为零。

#### 例题

对 $\mathbf F=(ax,by,cz)$ ，

$$
\nabla\cdot\mathbf F=a+b+c.
$$

即使 $a+b+c=0$ ，也只能说明场无散，不能说明场本身为零。

---

## D. 综合与进阶题型

### 题型 16：坐标选择与对称性降维

- 平面对称问题常用直角坐标。
- 轴对称问题常用柱坐标。
- 球对称问题常用球坐标。

若场为纯径向球对称场 $\mathbf F=F_r(r)\mathbf e_r$ ，散度可直接简化为

$$
\nabla\cdot\mathbf F
=\frac1{r^2}\frac{d}{dr}\left(r^2F_r\right).
$$

这比先转成直角坐标再求导简单得多。

### 题型 17：奇点、挖洞区域与“看似无旋”

在去掉 $z$ 轴的区域中考虑

$$
\mathbf F=\frac1\rho\mathbf e_\phi.
$$

它在普通点上的旋度为零，但绕 $z$ 轴一周有

$$
\oint_C\mathbf F\cdot d\mathbf l=2\pi.
$$

原因是区域存在被挖掉的轴，闭合曲线不能连续缩成一点。这类题考查单连通条件，而不只是偏导计算。

### 题型 18：拉普拉斯、拉普拉斯方程与泊松方程

$$
\nabla^2u
=\frac{\partial^2u}{\partial x^2}
+\frac{\partial^2u}{\partial y^2}
+\frac{\partial^2u}{\partial z^2}.
$$

- $\nabla^2u=0$ ：拉普拉斯方程， $u$ 为调和函数。
- $\nabla^2u=f$ ：泊松型方程。

#### 例题

对 $u=x^2-y^2+3z$ ，有 $\nabla^2u=2-2+0=0$ ，所以它是调和函数。

进阶题可能给出含参数函数，要求选择参数使拉普拉斯恒为零。此时求出 $\nabla^2u$ 后比较各项系数。

### 题型 19：矢量恒等式与乘积求导

$$
\nabla\times(\nabla u)=0,
\qquad
\nabla\cdot(\nabla\times\mathbf A)=0.
$$

$$
\nabla\times(\nabla\times\mathbf A)
=\nabla(\nabla\cdot\mathbf A)-\nabla^2\mathbf A.
$$

$$
\nabla\cdot(u\mathbf A)
=\nabla u\cdot\mathbf A+u\nabla\cdot\mathbf A.
$$

$$
\nabla\times(u\mathbf A)
=\nabla u\times\mathbf A+u\nabla\times\mathbf A.
$$

证明恒等式时先判断结果类型，再按直角坐标分量展开，并检查混合偏导能否交换。

### 题型 20：由耦合旋度方程推出波动方程

#### 识别信号

两个场的旋度互相包含对方的时间导数，同时题目给出两个场的散度。

#### 四步模板

1. 对第一条旋度方程再取一次旋度。
2. 用第二条旋度方程代换右侧。
3. 使用双重旋度恒等式。
4. 用散度条件消去梯度项。

所用恒等式单独写为

$$
\nabla\times(\nabla\times\mathbf A)
=\nabla(\nabla\cdot\mathbf A)-\nabla^2\mathbf A.
$$

若两次代换各带一个 $1/c$ ，最终系数必须是 $1/c^2$ 。这一检查可以发现教材 1-19 中的排版错误。

---

## 综合题的决策流程

```text
先看对象
├─ 标量场：方向导数、梯度、拉普拉斯？
├─ 矢量场：分量、散度、旋度、势函数？
└─ 积分区域
   ├─ 曲线：参数化或斯托克斯定理
   ├─ 开曲面：直接通量或补面
   ├─ 闭曲面：优先考虑散度定理
   └─ 体积：选择合适坐标和积分范围
```

然后依次检查坐标、方向、区域、方法与结果：哪个坐标最符合对称性？方向是否明确？区域是否闭合、单连通、含奇点？直接计算和积分定理哪个更短？输出类型、符号、量纲和极限情况是否合理？

## 最容易丢分的十个细节

1. 方向矢量没有单位化。
2. 把标量分量和矢量投影混淆。
3. 叉积展开时漏掉中间项负号。
4. 忘记柱、球坐标的尺度因子。
5. 开曲面直接使用散度定理。
6. 曲线方向与曲面法向不满足右手定则。
7. 求势函数时丢掉依赖其他变量的“积分常数”。
8. 无旋场判断中忽略区域的洞或奇点。
9. 把散度为零误解成场为零。
10. 双重旋度推导中漏掉系数或负号。

