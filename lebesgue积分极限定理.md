#! https://zhuanlan.zhihu.com/p/372503507
# Lebesgue积分的极限定理 （Levi单调收敛定理、Fatou引理、Lebesgue控制收敛定理）
> 以上三个定理用于讨论可测函数列极限的积分性质
> 积分号与极限号交换顺序问题
## 1.Levi单调收敛定理
设$\left\{ f_n \right\}_{n=1}^{\infty}$是$\mathbb{E}$上的**递增**非负可测函数列 ，若$\left\{ f_n a.e.\right\}_{n=1}^{\infty}$在$\mathbb{E}$上a.e.收敛至$f$，则 
$$
\lim_{n \to \infty} \int_\mathbb{E}f_{n}x \, \mathrm{d}m=\int_\mathbb{E}f(x)\, \mathrm{d}m=\int_\mathbb{E}\lim_{n \to \infty} f_{n}(x)\, \mathrm{d}m
$$
**Proof:**
不妨设$\left\{ f_n \right\}_{n=1}^{\infty}$ 在$\mathbb{E}$上逐点收敛于$f$。
设每个$\left\{ f_n \right\}$的积分由$\mathbb{E}$上的非负简单可测函数列$\left\{\varphi_{n,k}\right\}_{k=1}^{\infty}$，
则对任何的$x\in\mathbb{E}\ \text{及}n\in \mathbb{N}$有$\left\{\varphi_{n,k}\right\}_{k=1}^{\infty}$递增收敛至$f_n(x)$.
对每个$k\in \mathbb{N}_{+}$,定义
$$
    \begin{aligned}
        \psi_k\colon \mathbb{E} &\longrightarrow \mathbb{R} \\
                 x &\longmapsto \psi_k(x) =\max_{1\leqslant i\leqslant k}\psi_{i,k}(x) 
    \end{aligned}
$$
则$\left\{\varphi_{k}\right\}_{k=1}^{\infty}$为$\mathbb{E}$上的一个递增非负可测函数列，且有
$$
  \psi_{i,k}(x)  \leqslant \psi_k(x) \leqslant f_k(x)  \tag{aa} \\ 
$$
$$
\text{且有} \ \ \ \ \int_\mathbb{E}\psi_{i,k} \leqslant \int_\mathbb{E}\psi_K  \leqslant \int_\mathbb{E}f_k  \tag{bb}
$$
在$(aa),(bb)$中固定i,令$k\to \infty$得：
$$
f_i(x)=\lim_{k \to \infty} \psi_{i,k}(x)  \leqslant \lim_{k \to \infty} \psi_k(x) \leqslant \lim_{k \to \infty} f_k(x)=f(x) \\ \tag{aa'}  
$$
$$
\int_\mathbb{E}f_i=\lim_{k \to \infty} \int_\mathbb{E}\psi_{i,k} \leqslant \lim_{k \to \infty} \int_\mathbb{E}\psi_K  \leqslant \lim_{k \to \infty} \int_\mathbb{E}f_k \\ \tag{bb'}
$$
再在上式中令$i\to \infty$，有
$$
\lim_{k \to \infty} \psi_k=f(x) \\
 \lim_{k \to \infty} \int_\mathbb{E}\psi_K = \lim_{k \to \infty} \int_\mathbb{E}f_k 
$$
再根据$f$的积分由$\left\{ \psi_k \right\}_{n=1}^{\infty}$来定义，知
$$
\int_\mathbb{E}f=\lim_{k \to \infty} \int_\mathbb{E}\psi_k=\lim_{k \to \infty} \int_\mathbb{E}f_k
$$
### 1.1（推论） 非负可测函数列的逐项积分定理
设$\left\{ \mu_n \right\}_{n=1}^{\infty}$为$\mathbb{E}$上的一个非负可测函数列，则有
$$
\int_\mathbb{E}(\sum_{n=1}^{\infty} \mu_n(x))\, \mathrm{d}m=\sum_{n=1}^{\infty} \int_\mathbb{E}\mu_n(x)\, \mathrm{d}m
$$
**Proof：** 

令$f_N=\sum_{n=1}^{N} \mu_n,N=1,2\cdots$      以及$f \overset{\underset{\mathrm{def}}{}}{=}\sum_{n=1}^{\infty} \mu_n$,则$\left\{ f_N \right\}_{n=1}^{\infty}$为$\mathbb{E}$上的一个非负可测函数列并且在$\mathbb{E}$上单调递增收敛至$f$.于是由Levi单调收敛定理知：
$$
\int_\mathbb{E}(\sum_{n=1}^{\infty} \mu_n)=\int_\mathbb{E}\lim_{N \to \infty} f_N
=\lim_{N \to \infty} \int_\mathbb{E}f_N
=\lim_{N \to \infty} \int_\mathbb{E}(\sum_{n=1}^{N} u_n)
=\lim_{N \to \infty} \sum_{n=1}^{N}\int_\mathbb{E} u_n
= \sum_{n=1}^{\infty}\int_\mathbb{E} u_n
$$
证毕。
## 2.Fatou引理
设$\left\{ f_n \right\}_{n=1}^{\infty}$为$\mathbb{E}$上一个非负可测函数列，则有
$$
\int_\mathbb{E}(\liminf_{n \to \infty}f_n(x) )\, \mathrm{d}m
\leqslant \liminf_{n \to \infty}  \int_\mathbb{E}f_n(x)\, \mathrm{d}m
$$
>**后面证明会用到，前面学的忘记了，补一下**
>如果$\left\{ f_n ,n=1,2\cdots \right\}$是可测函数列，则
$$
\inf_{n\geqslant 1}f_n ,
\sup_{n\geqslant 1}f_n,
\liminf_{n \to \infty}f_n,
\limsup_{n \to \infty} f_n
$$
>仍未可测函数。 
>注意到$\forall a \in \mathbb{R}$ 
$$
\left\{ \sup_{n\leqslant  1}f_n\leqslant  a \right\}=\bigcap_{n=1}^{\infty}\left\{f_n\leqslant  a  \right\} \in \mathcal{F} \\
\left\{ \inf_{n \geqslant  1}f_n\geqslant   a \right\}=\bigcap_{n=1}^{\infty}\left\{f_n\geqslant  a  \right\} \in \mathcal{F} \\
\limsup_{n \to \infty}f_n =\inf_{n\geqslant 1}\sup_{k\geqslant n}f_k \\ 
\liminf_{n \to \infty}f_n =\sup_{n\geqslant 1}\inf_{k\geqslant n}f_k
$$






**Proof:**

令$\displaystyle g_n \overset{\underset{\mathrm{def}}{}}{=}\inf_{k\geqslant n}f_k,n=1,2\cdots$,则$\left\{ g_n \right\}_{n=1}^{\infty}$为$\mathbb{E}$上的一个非负可测函数列，且递增收敛至$\displaystyle \sup_{n\to \infty}(inf_{k\geqslant n}f_k)=\liminf_{n \to \infty} f_n$   
于是由Levi单调收敛定理知：  
$$
\int_\mathbb{E}(\liminf_{n \to \infty} f_n)
=\int_\mathbb{E}(\lim_{n \to \infty} g_n)
=\lim_{n \to \infty} \int_\mathbb{E}g_n
$$
又由于$g_n\leqslant f_n,n=1,2\cdots$,故$\int_\mathbb{E}g_n\leqslant \int_\mathbb{E}f_n,n=1,2\cdots$  
令$n\to \infty$取下极限可得：
$$
\int_\mathbb{E}(\liminf_{n \to \infty} f_n)=\lim_{n \to \infty}\int_\mathbb{E}g_n\leqslant \liminf_{n \to \infty} \int_\mathbb{E}f_n 
$$
证毕。

## 3.Lebesgue控制收敛定理
设$f_n,f\in \mathcal{MF}(\mathbb{E})$若下面的条件成立：
+ $\{f_n\}_{n=1}^{\infty}$在$\mathbb{E}$上几乎处处收敛于$f$;
+ $\exist g\in \mathcal{L} (\left\vert f_n \right\vert \leqslant g  \,a.e.,n=1,2\cdots )$  

则$f,f_n \in \mathcal{L}$且有
$$
\lim_{n \to \infty} \int_\mathbb{E}\left\vert f_n(x)-f(x) \right\vert \, \mathrm{d}m=0
$$
从而也有
$$
\lim_{n \to \infty} \int_\mathbb{E}f_n(x)\, \mathrm{d}m
=\int_\mathbb{E}f(x)\, \mathrm{d}m
=\int_\mathbb{E}\lim_{n \to \infty} f_n(x)\, \mathrm{d}m
$$
**Proof：**  

易知$f_n\leqslant g ,\left\vert f \right\vert\leqslant g$于是根据可积性的比较判别法可知： $f,f_n$可积。
令$g_n \overset{\underset{\mathrm{def}}{}}{=}\left\vert f_n-f \right\vert,n=1,2\cdots$,则$g_n$非负可测且$\left\vert g_n \right\vert \leqslant 2g a.e.$   
又由于$g$可积，再根据可积性的比较判别法可知，$g_n$非负可积。  
由Fatou引理可得：
$$
\int_\mathbb{E}\liminf_{n \to \infty}(2g-g_n)
\leqslant \liminf_{n \to \infty}(2g-g_n)  \\
\ \text{即有：} \\ 
\int_\mathbb{E}2g-\int_\mathbb{E}\lim_{n \to \infty} g_n=\int_\mathbb{E}\liminf_{n \to \infty}(2g-g_n)
\leqslant \liminf_{n \to \infty}\int_\mathbb{E}(2g-g_n)  
=\int_\mathbb{E}2g-\limsup_{n \to \infty} \int_\mathbb{E}g_n
$$
考虑到：  
$$
\int_\mathbb{E}\lim_{n \to \infty} g_n=0
$$
从而得到： 
$$
0\leqslant \liminf_{n \to \infty} \int_\mathbb{E}g_n
\leqslant \limsup_{n \to \infty} \int_\mathbb{E}g_n
\leqslant 0
$$
即有：  
$$
\lim_{n \to \infty} \int_\mathbb{E}g_n=\lim_{n \to \infty} \int_\mathbb{E}\left\vert f_n-f \right\vert=0 
$$

### 3.2Lebesgue控制收敛定理（更一般形式）
设$\left\{ f_n,n=1,2\cdots \right\}和f$均为可测函数，如果存在非负可积可测函数g使得对每个$n=1,2\cdots$，有$\left\vert f_n \right\vert \leqslant g  \qquad a.e.$,则
$$
f_n \xrightarrow{a.e.}f 或者f_n \xrightarrow{\mu}f \\ \implies  \lim_{n \to \infty} \int_\mathbb{E}\left\vert f_n(x)-f(x) \right\vert \, \mathrm{d}m=0 
$$
>几乎处处时证明同上，依测度收敛则可以找到其子列几乎处处收敛

### 3.3推论 Lebesgue有界收敛定理
设$\left\{ f_n,n=1,2\cdots \right\}$和$f$时有限测度空间$(\mathbb{X},\mathcal{F},\mu)$上的可测函数。  
如果存在$M>0$使$f_n\leqslant M\qquad a.e.$,且有$f_n \xrightarrow{a.e.}f$或者$f_n \xrightarrow{\mu}f$,则
$$
\lim_{n\to \infty}\int_\mathbb{X} f_n\, \mathrm{d} \mu=\int_\mathbb{X}f\, \mathrm{d}\mu
$$
