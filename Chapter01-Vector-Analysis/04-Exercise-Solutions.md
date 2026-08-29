# 第一章 练习题答案与解析

## 1-3

\[
\mathbf A\times\mathbf B=
\begin{vmatrix}
\mathbf e_x&\mathbf e_y&\mathbf e_z\\
2&3&-4\\
-6&-4&1
\end{vmatrix}
=-13\mathbf e_x+22\mathbf e_y+10\mathbf e_z.
\]

\[
\mathbf e_C=\frac{1}{\sqrt3}(\mathbf e_x-\mathbf e_y+\mathbf e_z).
\]

所以标量分量为

\[
(\mathbf A\times\mathbf B)\cdot\mathbf e_C
=\frac{-13-22+10}{\sqrt3}
=\boxed{-\frac{25}{\sqrt3}}.
\]

负号说明投影指向 \(-\mathbf C\) 一侧。

## 1-6

在 \((-3,4,-5)\) 处，

\[
r=\sqrt{9+16+25}=5\sqrt2,
\qquad r^2=50,
\qquad |\mathbf E|=\frac{25}{50}=\boxed{\frac12}.
\]

\[
\mathbf e_r=\frac{-3\mathbf e_x+4\mathbf e_y-5\mathbf e_z}{5\sqrt2},
\]

故

\[
E_x=\frac12\frac{-3}{5\sqrt2}
=\boxed{-\frac{3}{10\sqrt2}}
=-\frac{3\sqrt2}{20}.
\]

又 \(|\mathbf B|=3\)，且

\[
\mathbf E\cdot\mathbf B
=\frac12\frac{(-3)2+4(-2)+(-5)1}{5\sqrt2}
=-\frac{19}{10\sqrt2}.
\]

\[
\cos\alpha=\frac{\mathbf E\cdot\mathbf B}{|\mathbf E||\mathbf B|}
=-\frac{19}{15\sqrt2}.
\]

\[
\boxed{\alpha=\cos^{-1}\left(-\frac{19}{15\sqrt2}\right)\approx153.6^\circ}.
\]

## 1-11

### (1)

\[
\nabla\cdot\mathbf r
=\frac{\partial x}{\partial x}
+\frac{\partial y}{\partial y}
+\frac{\partial z}{\partial z}
=\boxed{3}.
\]

### (2)

\[
\nabla\times\mathbf r=
\begin{vmatrix}
\mathbf e_x&\mathbf e_y&\mathbf e_z\\
\partial_x&\partial_y&\partial_z\\
x&y&z
\end{vmatrix}=\boxed{\mathbf0},
\]

因为所有交叉偏导均为零。

### (3)

令 \(\mathbf k=k_x\mathbf e_x+k_y\mathbf e_y+k_z\mathbf e_z\)，则

\[
\mathbf k\cdot\mathbf r=k_xx+k_yy+k_zz,
\]

所以

\[
\nabla(\mathbf k\cdot\mathbf r)
=k_x\mathbf e_x+k_y\mathbf e_y+k_z\mathbf e_z
=\boxed{\mathbf k}.
\]

## 1-12

### 先纠正教材题面

教材印刷页 27 写的是 \(x=y^2\)，但

\[
(2,1):\ 2\ne1^2,
\qquad
(8,2):\ 8\ne2^2.
\]

所以题给两端点并不在教材所写抛物线上，这条路径无法连接它们。两端点均满足 \(x=2y^2\)，以下按修正后的曲线计算。这是教材题面错误，不是解题时任意改条件。

\[
\mathbf E\cdot d\mathbf l=y\,dx+x\,dy.
\]

### (1) 抛物线路径

取 \(y\) 为参数，\(x=2y^2\)，\(y:1\to2\)，\(dx=4y\,dy\)：

\[
\int_L\mathbf E\cdot d\mathbf l
=\int_1^2(y\cdot4y+2y^2)dy
=\int_1^2 6y^2dy
=2[y^3]_1^2
=\boxed{14}.
\]

### (2) 直线路径

令 \(x=2+6t\)、\(y=1+t\)、\(z=-1\)，\(0\le t\le1\)，则 \(dx=6dt\)、\(dy=dt\)：

\[
\int_0^1[(1+t)6+(2+6t)]dt
=\int_0^1(8+12t)dt
=\boxed{14}.
\]

### (3) 保守性

\[
\nabla\times\mathbf E
=\left(\frac{\partial x}{\partial x}-\frac{\partial y}{\partial y}\right)\mathbf e_z
=\mathbf0.
\]

而且

\[
d(xy)=y\,dx+x\,dy,
\qquad \mathbf E=\nabla(xy).
\]

所以势函数为 \(u=xy\)，线积分只与端点有关：

\[
u(P_2)-u(P_1)=8\times2-2\times1=\boxed{14}.
\]

只有 \(z\) 分量需要实际相减，是因为 \(E_z=0\)，且 \(E_x,E_y\) 不含 \(z\)，旋度的前两个分量各项都为零；这不是通用规则。

## 1-14

### \(\mathbf A\)

球坐标单位矢量关系给出

\[
\mathbf A=\mathbf e_x.
\]

故

\[
\nabla\times\mathbf A=0,
\qquad
\nabla\cdot\mathbf A=0.
\]

它既可写成梯度（例如 \(\mathbf A=\nabla x\)），也可在适当区域写成某矢量场的旋度；源分布为 0。

### \(\mathbf B\)

柱坐标散度为

\[
\nabla\cdot\mathbf B
=\frac1\rho\frac{\partial(\rho z^2\sin\phi)}{\partial\rho}
+\frac1\rho\frac{\partial(z^2\cos\phi)}{\partial\phi}
+\frac{\partial(2\rho z\sin\phi)}{\partial z}
=2\rho\sin\phi=\boxed{2y}.
\]

计算旋度得 \(\nabla\times\mathbf B=0\)。事实上

\[
\mathbf B=\nabla(\rho z^2\sin\phi)=\nabla(yz^2).
\]

所以 \(\mathbf B\) 可表示为梯度；由于散度非零，不能表示为旋度。

### \(\mathbf C\)

\[
\nabla\cdot\mathbf C
=\frac{\partial(3y^2-2x)}{\partial x}
+\frac{\partial x^2}{\partial y}
+\frac{\partial2z}{\partial z}
=-2+0+2=\boxed{0}.
\]

\[
\nabla\times\mathbf C
=(2x-6y)\mathbf e_z\ne0
\]

（一般情形）。所以它不能写成标量梯度，但在适当区域可表示为矢量场的旋度。

| 矢量 | 可写成梯度 | 可写成旋度 | 源分布 |
|---|---|---|---|
| \(\mathbf A\) | 是 | 是 | \(0\) |
| \(\mathbf B\) | 是 | 否 | \(2\rho\sin\phi=2y\) |
| \(\mathbf C\) | 否 | 是 | \(0\) |

## 1-19

对

\[
\nabla\times\mathbf E=-\frac1c\frac{\partial\mathbf H}{\partial t}
\]

再取旋度：

\[
\nabla\times(\nabla\times\mathbf E)
=-\frac1c\frac{\partial}{\partial t}(\nabla\times\mathbf H)
=-\frac1{c^2}\frac{\partial^2\mathbf E}{\partial t^2}.
\]

另一方面，

\[
\nabla\times(\nabla\times\mathbf E)
=\nabla(\nabla\cdot\mathbf E)-\nabla^2\mathbf E
=-\nabla^2\mathbf E.
\]

两式比较：

\[
\boxed{\nabla^2\mathbf E
=\frac1{c^2}\frac{\partial^2\mathbf E}{\partial t^2}}.
\]

同理，

\[
\boxed{\nabla^2\mathbf H
=\frac1{c^2}\frac{\partial^2\mathbf H}{\partial t^2}}.
\]

### 教材错误说明

教材第一章印刷页 28 的 1-19 末式写成

\[
\nabla^2\mathbf A=\frac1c\frac{\partial^2\mathbf A}{\partial t^2}.
\]

但题设两条旋度方程各含一个 \(1/c\)，直接推导会得到两个因子相乘，即 \(1/c^2\)。因此，在题设不变的前提下，末式的 \(1/c\) 是教材排版错误；上面的答案按题设严格推导。
