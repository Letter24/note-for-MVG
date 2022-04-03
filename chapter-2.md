# 摄影几何与二维空间变换

本章主要介绍本书必要的几何知识与符号

## 2.2 2D投影平面

**行向量与列向量** 本书默认所有向量的都是列向量, 比如$x$, 那么$x^T$就是行向量. 对于一个行向量$(x,y)$, 我们就有$x=(x,y)^T$.

### 2.2.1 点和线

**线段的齐次坐标** 线是由方程$ax+by+c=0$组成的, 所以我们就用$(a,b,c)^T$来表示线段. 但是$(a,b,c)^T$不能唯一表示一条线段, 因为$(a,b,c)^T$与$k(a,b,c)^T$表示一样的线段 ($k$不能为0). 那么$k(a,b,c)^T$其实就是一类向量的表达. 这个类中所有的向量都是其次向量. 那么我们把所有的类都放在一起, 就形成了投影空间. 空间中有一个特殊点$(0,0,0)^T$, 它不属于任何直线.

**点的其次坐标** 直线方程是$ax+by+c=0$, 那么可以写成$(x,y,1)(a,b,c)^T$, 那么这个$(x,y,1)$就是点的齐次坐标.

**结论2.1** 点在直线上当且仅当$x^T l = 0$

**自由度** 自由度就是这个几何体可以由几个自由变化的变量来表达, 比如点的自由度就是2, 因为指定$x,y$就够了, 线的自由度也是2, 这是因为虽然线有三个变量, 但是他们之间的比例是$a:b:c$. 类似线性无关的变量的个数.

**直线的交点** 两个直线$l=(a,b,c), l'=(a',b',c')$, 他们的交点就是$l \times l'$

**两个点确定的直线** 两个点$x,x'$, 他们确定的直线就是$x \times x'$

## 2.2.2 理想点(ideal point)和无穷远处的直线

**平行线的交点** 如果我们考虑两个平行线的交点$ax+by+c=0,ax+by+c'=$, 做叉乘, 我们会得到$(c'-c)(b,-a,0)$, 如果我们忽略尺度因子$(c'-c)$, 那么平行线的交点就在$(b,-a,0)$, 我们再把这个齐次坐标变成非齐次, 那么就得到$(b/0,-a/0)$, 这点就在无穷远处, 所以我们说平行线就是在无穷远处相交.

**理想点与无穷远的直线** 我们考虑任一个点$(x_1,x_2,x_3)$, 把$x_3=0$, 那么$(x_1,x_2,0)$就是无穷远处的所有点, 这些点都落在一个直线上, 那就是$l_{\infty}=(0,0,1)$.

我们紧接着考虑任意一条直线$l=(a,b,c)$, $l$与$l_{\infty}$的交点就是$(-b,a)$, $(-b,a)$和直线的法向量$(a,b)$是垂直的, 所以他就是直线的方向. 注意$(a,b)$不是直线的方向, $(a,b)$和直线是垂直的. $(-b,a,0)$这个点在无穷远直线上, 那么无穷远处的直线就可以被看做是直线方向的集合.

**二维射影平面的几何模型** (可以先把书翻到p29 看fig2.1) 射影平面可以想象为三维空间中射线的集合. 可以从三个射线上挑出三个点, 并且让他们共面, 那么其他的射线都与该平面有交点. 所以该平面就是由射线上的点组成的. 射影平面上的线就是过原点的平面和射影平面的交点. 任意两个不同射线处于同一平面上, 任意两个不同的平面相较于一个射线. 可以类比两直线交于一点,两点确定一直线.  

最后一点, 无穷远处的理想点和直线平行于平面$x_3=1$