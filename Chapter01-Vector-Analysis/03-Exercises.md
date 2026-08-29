# 第一章 练习题

> 本页不提供答案。先独立完成，再查看[答案与解析](04-Exercise-Solutions.md)。

## 1-3 叉积与方向分量

已知

$$
\mathbf A=2\mathbf e_x+3\mathbf e_y-4\mathbf e_z,
\quad
\mathbf B=-6\mathbf e_x-4\mathbf e_y+\mathbf e_z,
$$

求 $\mathbf A\times\mathbf B$ 在 $\mathbf C=\mathbf e_x-\mathbf e_y+\mathbf e_z$ 方向上的标量分量。

提示： $\mathbf C$ 不是单位矢量。

## 1-6 球坐标矢量与夹角

已知

$$
\mathbf E=\mathbf e_r\frac{25}{r^2}.
$$

1. 求点 $(-3,4,-5)$ 处的 $|\mathbf E|$ 和 $E_x$ 。
2. 求该点处 $\mathbf E$ 与 $\mathbf B=2\mathbf e_x-2\mathbf e_y+\mathbf e_z$ 的夹角。

提示：先把 $\mathbf e_r$ 展成直角坐标单位矢量。

## 1-11 三种 $\nabla$ 运算

设

$$
\mathbf r=x\mathbf e_x+y\mathbf e_y+z\mathbf e_z,
$$

$\mathbf k$ 为常矢量。证明：

1. $\nabla\cdot\mathbf r=3$ ；
2. $\nabla\times\mathbf r=0$ ；
3. $\nabla(\mathbf k\cdot\mathbf r)=\mathbf k$ 。

## 1-12 线积分与保守场

设

$$
\mathbf E=y\mathbf e_x+x\mathbf e_y,
$$

从 $P_1=(2,1,-1)$ 到 $P_2=(8,2,-1)$ ：

1. 沿平面 $z=-1$ 内、连接两端点的抛物线 $x=2y^2$ 计算 $\int_L\mathbf E\cdot d\mathbf l$ ；
2. 沿连接两点的直线计算同一积分；
3. 判断 $\mathbf E$ 是否为保守场，并解释两条路径结果的关系。

> 教材错误说明：教材印刷页 27 将第 (1) 问写成 $x=y^2$ ，但 $(2,1)$ 、 $(8,2)$ 均不在该曲线上，无法沿这条曲线从题给起点走到终点。两个端点满足的是 $x=2y^2$ ，本题按这一可连接端点的修正形式列出。

## 1-14 梯度场、旋度场与源分布

三个矢量为

$$
\mathbf A=\mathbf e_r\sin\theta\cos\phi
+\mathbf e_\theta\cos\theta\cos\phi
-\mathbf e_\phi\sin\phi,
$$

$$
\mathbf B=\mathbf e_\rho z^2\sin\phi
+\mathbf e_\phi z^2\cos\phi
+\mathbf e_z2\rho z\sin\phi,
$$

$$
\mathbf C=\mathbf e_x(3y^2-2x)+\mathbf e_yx^2+\mathbf e_z2z.
$$

1. 哪些可由标量函数的梯度表示？哪些可由矢量函数的旋度表示？
2. 求各矢量的源分布 $\nabla\cdot\mathbf F$ 。

## 1-19 从旋度方程推出波动方程

设 $\mathbf E(x,y,z,t)$ 、 $\mathbf H(x,y,z,t)$ 满足

$$
\nabla\cdot\mathbf E=0,
\qquad
\nabla\times\mathbf E=-\frac1c\frac{\partial\mathbf H}{\partial t},
$$

$$
\nabla\cdot\mathbf H=0,
\qquad
\nabla\times\mathbf H=\frac1c\frac{\partial\mathbf E}{\partial t}.
$$

证明 $\mathbf E$ 和 $\mathbf H$ 分别满足波动型方程。

> 教材错误说明：教材印刷页 28 的目标式将时间二阶导数前的系数印为 $1/c$ ；按题设两条旋度方程推导应为 $1/c^2$ 。
