# 投影几何与三维空间变换

## 3.1 点和投影变换

三维空间的其次坐标就是$x_1,x_2,x_3,x_4$, 比二维空间多一个. $x_4$一般是1, 如果是0那就代表无穷远的点.

三维空间投影矩阵$H$是$4 \times 4$的, 有15个自由度.

## 3.2 三维投影空间中的点, 线, 面, 二次曲线

三维投影空间中点和面时对偶的, 也就是说他们可以互相交换位置.

### 3.2.1 平面

三维空间面就是
$$
\pi_1 X + \pi_2 Y +\pi_3 Z + \pi_4 = 0 
$$

$\pi_1, \pi_2, \pi_3$就是平面的法向量

**相交关系**
1. 三点确定一个平面
2. 两个相交平面确定一个线
3. 三个相交平面确定一个点

下面来讨论这几个关系的代数表述

**三个点确定一平面** 我们假设点是$X_i$, 平面式$\pi$
确定平面需要解以下方程
$$
\left[
\begin{matrix}
X_1^T \\
X_2^T \\
X_3^T \\
\end{matrix}
\right]

\pi
= 0
$$

书中p67 3.4式给了一个解析解.

**三个平面确定一个点** 很简单, 把上述方程点和面的位置换一下就行.

### 3.2.2 线段的表示
线段在三维空间中表示比较尴尬, 因为点和面是对偶的, 如果要表示线, 那就得5维向量. 本节介绍了三种方法, 我们掌握一种就可以了

**零空间理论** 我们假设$A,B$是两个点, 经过这两个点的直线除了叉乘, 还可以表示为
$$
W= \\
\left[
\begin{matrix}
A^T\\
B^T
\end{matrix}
\right]
$$

那么把$A,B$换成平面, 上式就是两个平面相交形成的点.

## 3.2.3 二次曲面和对偶二次曲面

三维空间中的二次曲面定义如下:
$$
X^T Q X = 0
$$

Q是一个$4 \times 4$的对称矩阵, 主要有以下性质:

1. Q有九个自由度
2. 8个点确定一个二次曲面
3. Q如果是奇异矩阵, 那么二次曲面退化了
4. 二次曲面可以确定一个点和一个极平面$\pi=QX$
5. 平面$\pi$和Q的交线就是圆锥
6. 如果点变换是$X'=HX$, 那么Q上的点就会被变换成$Q'=H^{-T} Q H^{-1}$

$Q$的对偶定义为$Q^*$, 是由与Q相切的面组成的.

### 3.2.4 二次曲面的分类
见书p74 表3.1 

## 3.4 三维空间中的变换

1. 投影变换15个自由度, 不变量是相交的平面,垂直的平面
2. 仿射变换12个自由度, 不变量是平行的平面,体积之间的比例,无穷远处的平面.
3. 相似变换7个自由度,不变量是无穷远处的圆锥
4. 刚体变换6个自由度,不变量是体积

## 3.5 无穷远处的平面

我们记得在二维投影空间中有一个无穷远的直线$l_{\infty}$, 那么类似的在三维投影空间就有一个无穷远平面$\pi_{\infty}$,在该平面上还有一个绝对圆锥$\Omega_{\infty}$

1. $\pi_{\infty}$是两个平行平面的交点
2. 平行线的交点在$\pi_{\infty}$上, 与平面平行的直线也在$\pi_{\infty}$上

**结论3.7** 无穷远平面在投影变换下保持不变当且仅当该变换是仿射变换.

## 3.6 绝对圆锥

绝对圆锥$\Omega_{\infty}$是$\pi_{\infty}=(0,0,0,1)$ 上的圆锥,满足
$$
X_1^2 + X_2^2 + X_3^2 = 0 \\
X_4^2=0
$$

写成圆锥表达式就是
$$
(X_1,X_2,X_3)I(X_1,X_2,X_3)^T = 0
$$

**结论3.9** 绝对圆锥在投影变换下保持不变当且仅当该变换是相似变换.

所有的圆都和绝对圆锥相交于两点, 所有的球都和绝对圆椎相交于$\pi_{\infty}$

**度量性质** 当我们知道了绝对圆锥, 我们就可以恢复度量性质, 比如直线之间的夹角

$$
\cos \theta = \frac{d_1^T \Omega_{\infty} d_2}{\sqrt{(d_1^T \Omega_{\infty} d_2)(d_1^T \Omega_{\infty} d_2)} }
$$

## 3.7 绝对圆锥的对偶圆锥

很简单, 就是由与绝对圆锥相切的平面组成的圆锥, 记为$Q_{\infty}^*$, 对偶圆锥也在相似变换下保持不变. $\pi_{\infty}$是$Q_{\infty}^*$的零向量.