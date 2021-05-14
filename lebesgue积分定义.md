# Lebesgue 积分的定义

> 定义方式按照下面步骤
>
> - 非负简单可测函数积分的定义
> - 非负可测函数积分的定义 （给出三种等价定义方式）
> - 一般可测函数积分的定义

## 1. 非负简单可测函数 lebesgue 积分的定义
设 $ f\colon \mathbb{E} \to [0,+\infty] $是非负简单可测函数 ，则$f$有如下典范表达式：
$$f(x)=\sum_{n=1}^{n} a_{i}I{A_{i}}(x) \qquad \forall x \in E$$
其中 $f(\mathbb{E})=\left\{ a_1,a_2,\cdots ,a_{N} \right\}  \subset [0,+\infty] ,\ \  \ \ \  \mathbb{E}_i=f ^{-1}(a_{i})   $
$$
\int_{\mathbb{E}}f(x)\, \mathrm{d}m \overset{\underset{\mathrm{def}}{}}{=}\sum_{n=1}^{N} a_{i}m(\mathbb{E}_{i})\,\ (\in [0,+\infty])
$$
## 非负可测函数Lebesgue积分的定义
设 $f\in \mathcal{MF}(\mathbb{E};[0,+\infty])$ 
则由可测函数的结构定理，存在 $\mathbb{E}$上的简单可测函数列 $\left\{ \varphi_{n} \right\} _{n=1}^{\infty}$ ($\left\{ \varphi_{n} \right\}$在 $\mathbb{E} $上单调递增收敛至 $f$)
于是根据非负简单可测函数积分的单调性有：  $\int_{\mathbb{E}}\varphi_n\leqslant \int_{\mathbb{E}}\varphi_{n+1}$
从而$\left\{ \varphi_{n} \right\} _{n=1}^{\infty}$存在广义极限 $ \displaystyle \lim_{n \to \infty}\int_{\mathbb{E}}\varphi_n $
$$
\int_{\mathbb{E}}f(x)\, \mathrm{d}m \overset{\underset{\mathrm{def}}{}}{=} \displaystyle \lim_{n \to \infty}\int_{\mathbb{E}}\varphi_n
$$
>注 需要证明非负可测函数积分的定义是良好的
>即： 设递增非负简单可测函数列$\left\{ \varphi_{n} \right\} _{n=1}^{\infty} \  ,\left\{ \psi_{n} \right\} _{n=1}^{\infty}$  在$\mathbb{E}$上a.e.收敛到相同的极限函数,则
$$
 \lim_{n \to \infty}\int_{\mathbb{E}}\varphi_n= \lim_{n \to \infty}\int_{\mathbb{E}}\psi_n
$$
>>欲证上式，只需证明 $ f,g \{ f_n ,  n=1,2,\cdots\}$是测度空间$(\mathbb{X},\mathcal{F},\mu) $上的非负简单可测函数。
>> 如果 $ f_n \,\uparrow $且$ \lim_{n \to \infty} f_{n}\geqslant g$,
则$ \lim_{n \to \infty} \int_{\mathbb{X}}f_{n}\, \mathrm{d}\mu\geqslant \int_{\mathbb{X}}g\, \mathrm{d}\mu$
>>>**证明** 
>>>>对$\forall \alpha \in (0,1)$,记$ A_{n}(\alpha)=\left\{ f_{n}\geqslant \alpha g \right\} $ ,
并表$g=\sum_{j=1}^{m} b_{j}I_{B_{j}}$ 
注意到$f_nI_{A_{n}(\alpha)}$和$g_nI_{A_{n}(\alpha)}$都是非负简单函数，
而且$f_nI_{A_{n}(\alpha)}\geqslant \alpha g_nI_{A_{n}(\alpha)}$
$$
\begin{aligned}
 \int_{\mathbb{X}}f_{n}\, \mathrm{d}\mu\geqslant \int_{\mathbb{X}}f_{n}I_{A_n(\alpha)} \, \mathrm{d}\mu &\geqslant \alpha\int_{\mathbb{X}}gI_{A_n(\alpha)}\, \mathrm{d}\mu \\ 
 &=\alpha \sum_{j=1}^{m} b_{j}\mu(B_{j} \bigcap A_{n}(\alpha) )
\end{aligned}
$$
>>>>由于$f_n \uparrow$及 
$$
\begin{aligned}
\lim_{n \to \infty} f_n\geqslant g &\implies A_n(\alpha) \uparrow \mathbb{X} \\
&\implies\mu(B_{j} \bigcap A_{n}(\alpha)) \uparrow \mu(B_{j})
\end{aligned}
$$
>>>>只要在上式中令$n\to \infty$，便得，
$$
\begin{aligned}
 \lim_{n \to \infty} \int_{\mathbb{X}} f_n\, \mathrm{d}\mu &\geqslant \lim_{n \to \infty}  \alpha \sum_{j=1}^{m} b_{j}\mu(B_{j} \bigcap A_{n}(\alpha)) \\
 &=\alpha \sum_{j=1}^{m} b_{j}\mu(B_{j})\\
 &=\alpha\int_{\mathbb{X}}g\, \mathrm{d}\mu
\end{aligned}

$$
>>>>在此式中再令$\alpha \to 1$，即得，
$$
\lim_{n \to \infty} \int_{\mathbb{X}}f_{n}\, \mathrm{d}\mu\geqslant \int_{\mathbb{X}}g\, \mathrm{d}\mu
$$