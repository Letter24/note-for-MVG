# 第四章算法测试
本章主要讲述对第四章算法的分析和测试
我们就罗列一下测评的标准

## 5.1.1 代数误差
讲这个之前我们首先再来明确一下$\hat{x}'$的定义, $x \leftrightarrow x'$是一对**有噪声的**对应点, 所以从$x \leftrightarrow x'$估计出的$H$ 其实不满足$x'=Hx$, 总是又误差的, 那么我们可以记$\hat{x}'=Hx$, 那么$\hat{x}$就和$x$是完美匹配的, 对$x'$也可以找出这么一对完美匹配的点. 那么在一张图上的误差就是
$$
\epsilon_{res} = (\frac{1}{2n}\sum d(x'_i,\hat{x_i}'))^{\frac{1}{2}}
$$

两张图的误差就是

$$
\epsilon_{res} = (\frac{1}{\sqrt{4n}}\sum d(x'_i,\hat{x_i}'))^{\frac{1}{2}}
$$

## 最大后验概率误差的期望 (几何误差)

书中提高一个观点 最小化几何误差等于求最大后验概率, 既然从概率角度考虑, 那么我们就就误差的期望

书中给出的结论是: 在N维空间中有协方差为$N\sigma$的高斯噪声, 我们要求d个自由度的投影变换,那么有如下公式

1. $x$到$\hat{x}$的误差是$\sigma(1-d/N)^{1/2}$
2. $x$到$\bar{x}$的误差是$\sigma(1-d/N)^{1/2}$. $\bar{x}$是真实值, ground truth, 没有噪声的点.

## 5.2 $H$的协方差

$H$的协方差主要是来计算方差的, 方差衡量$H$本身有多准确, $H$有9个变量, 那么他的协方差矩阵就是$9 \times 9$

那么一张图上的这个协方差矩阵怎么算, 书中给出了如下公式:
$$
\Sigma_h=(J_f^T \Sigma_x J_f)
$$

$\Sigma_x$是噪声,也就是高斯分布的协方差矩阵, $J_f$是雅可比矩阵, 可以根据对应点用p146 5.11式算出

两张图上的协方差可以用p147 5.2.5节的公式计算

## 5.3 蒙特卡洛法

先找若干对匹配点, 算出一个$H$, 然后再给点人为加上噪声, 再计算一个$H'$, 这样就可以计算协方差矩阵,进而计算方差