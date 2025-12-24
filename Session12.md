# 第１２回 級数による解法
## 一階微分方程式
$$
 y' = f(x,y) \tag{1}
$$
において、$f(x,y)$ が点 $x(x_0,y_0)$ の近くで偏微分可能で、$f_x(x,y)$、$f_y(x,y)$ が連続ならば $y(x_0)=y_0$ を満たす解 $y=g(x)$ がただ1つ存在する。（p.5 <span style="color: red; ">定理1.1</span>）

この解 $y$ を $x=x_0$ で<span style="color: red; ">テイラー級数の形</span>で表す。
$$
 y = A_0 + A_1 (x-x_0) + A_2 (x-x_0)^2 + \cdots + A_n (x-x_0)^n + \cdots
 \tag{2}
$$

微分方程式を解く → 微分方程式を満たすように係数 $A_i, \; (i=0,\ldots,n,\ldots)$ を決める。

1. $x=x_0$ で $y=y_0$ より、$A_0 = y_0$
2. (2)を微分
$$
 y' = A_1 + 2 A_2 (x-x_0) + \cdots + n A_n (x-x_0)^{n-1} + \cdots
$$
これを(1)に代入して、$A_1$、$A_2, \cdots$ を決める。

$x_0=0$ のときは<span style="color: red; ">マクローリン級数</span>。

### p.66 例題1
$y'-2xy=x$ を $x$ のべき級数による解法で解け。

$$
 \begin{align*}
 y &= A_0 + A_1 x + A_2 x^2 + \cdots + A_n x^n + \cdots = \sum_{n=0}^\infty A_n x^n \\
 y' &= A_1 + 2 A_2 x + \cdots + n A_n x^{n-1} + \cdots = \sum_{n=0}^\infty (n+1) A_{n+1} x^n \\
 -2 xy &= -2 A_0 x + -2 A_1 x^2 - \cdots - 2 A_{n-1} x^n + \cdots = \sum_{n=1}^\infty -2 A_{n-1} x^n
 \end{align*}
$$
より、
$$
 y' -2 xy = A_1 + \sum_{n=1}^\infty \left\{ (n+1) A_{n+1} -2 A_{n-1} \right\} x^n = x
$$
- $n=0$ のとき、$A_1 = 0$
- $n=1$ のとき、$2A_2 - 2 A_0 = 1$ → $A_2 = (1+2A_0)/2$
- $n=2$ のとき、$3A_3 - 2 A_1 = 0$ → $A_3 = (2/3) A_1 = 0$
- $n=3$ のとき、$4A_4 - 2 A_2 = 0$ → $A_4 = (1/2) A_2$
- $n=4$ のとき、$5A_5 - 2 A_3 = 0$ → $A_5 = (2/5) A_3 = 0$
- $n=5$ のとき、$6A_6 - 2 A_4 = 0$ → $A_6 = (1/3) A_4$
- $\vdots$

$$
 \begin{align*}
 A_2 &= \frac{1}{2} (1+2 A_0), \;\; A_{2m} = \frac{1}{m} A_{2m-2}\;(m \geq 2) \\
 A_1 &= A_3 = A_5 = \cdots = A_{2m+1} = \cdots = 0 \; (m \geq 0) \\
 A_{2m} &= \frac{1}{2} \frac{1}{m!} (1 + 2 A_0) \; (m \geq 1)
 \end{align*}
$$

以上より、
$$
 \begin{align*}
  y &= A_0 + \frac{1}{2} (1+2 A_0) \left\{ x^2 + \frac{1}{2!}x^4 + \frac{1}{3!} x^6 + \cdots + \frac{1}{m!} x^{2m} \right\}  \\
   &= - \frac{1}{2} + \frac{1}{2} (1+2 A_0) \left\{ 1 + x^2 + \frac{1}{2!}x^4 + \frac{1}{3!} x^6 + \cdots + \frac{1}{m!} x^{2m} \right\} \\
   &= - \frac{1}{2} + c \left\{ 1 + x^2 + \frac{1}{2!}x^4 + \frac{1}{3!} x^6 + \cdots + \frac{1}{m!} x^{2m} \right\} \\
   &= - \frac{1}{2} + c e^{x^2}
\end{align*}
$$

### 解の公式（p.13 (2)）による例題１の解法
$y'-2xy=x$ → $P(x)= -2x, Q(x)=x$

$$
 \begin{align*}
 y &= e^{- \int P(x)dx} \left( \int Q(x) e^{\int P(x)dx} +c \right) \\
  &= - \frac{1}{2} + c e^{x^2}
 \end{align*}
$$

ノートなので、もっとヒントを書き込む