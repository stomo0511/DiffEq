# 第１２回 級数による解法
## １階微分方程式
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

**$x_0=0$ のとき**、**初期条件が与えられていないとき**は、
$$
 y = A_0 + A_1 x + A_2 x^2 + \cdots + A_n x^n + \cdots
$$
とする（<span style="color: red; ">マクローリン級数</span>）。

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
- $n=0$ のとき、両辺の $x$ の0次項を比較して、$A_1 = 0$
- $n=1$ のとき、両辺の $x$ の1次項を比較して、$2A_2 - 2 A_0 = 1$ → $A_2 = (1+2A_0)/2$
- $n=2$ のとき、両辺の $x$ の2次項を比較して、$3A_3 - 2 A_1 = 0$ → $A_3 = (2/3) A_1 = 0$
- $n=3$ のとき、両辺の $x$ の3次項を比較して、$4A_4 - 2 A_2 = 0$ → $A_4 = (1/2) A_2$
- $n=4$ のとき、両辺の $x$ の4次項を比較して、$5A_5 - 2 A_3 = 0$ → $A_5 = (2/5) A_3 = 0$
- $n=5$ のとき、両辺の $x$ の5次項を比較して、$6A_6 - 2 A_4 = 0$ → $A_6 = (1/3) A_4$
- $\vdots$

$$
 \begin{align*}
 偶数次項：A_2 &= \frac{1}{2} (1+2 A_0), \;\; A_{2m} = \frac{1}{m} A_{2m-2}\;(m \geq 2) \\
 A_{2m} &= \frac{1}{2} \frac{1}{m!} (1 + 2 A_0) \; (m \geq 1)　\\
 奇数次項：A_1 &= A_3 = A_5 = \cdots = A_{2m+1} = \cdots = 0 \; (m \geq 0) \\
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
  &= - \frac{1}{2} + c e^{x^2} 　←級数による解法と同じ
 \end{align*}
$$

### p.67 例題２ （2階微分方程式）
$y''-2xy'+2y=0$（<span style="color: red; ">エルミット（エルミート）</span>の微分方程式）を $x$ のべき級数による解法で解け。

（**定数係数でない**ので、これまでの解法では解けない）

$$
 \begin{align*}
 y &= a_0 + a_1 x + a_2 x^2 + \cdots + a_n x^n + \cdots = \sum_{n=0}^\infty a_n x^n \\
 y' &= a_1 + 2 a_2 x + \cdots + n a_n x^{n-1} + \cdots = \sum_{n=0}^\infty (n+1) a_{n+1} x^n \\
 y'' &= 2 a_2 + 2 \cdot 3 a_3 x + \cdots + n(n+1) a_{n+1} x^{n-1} + \cdots = \sum_{n=0}^\infty (n+1)(n+1) a_{n+2} x^n \\
 -2 xy' &= -2 \sum_{n=0}^\infty (n+1) a_{n+1} x^{n+1} = -2 \sum_{n=1}^\infty n a_{n} x^{n} \\
 y''-2xy'+2y &= \sum_{n=0}^\infty (n+1)(n+1) a_{n+2} x^n -2 \sum_{n=1}^\infty n a_{n} x^{n} + 2 \sum_{n=0}^\infty a_n x^n \\
 &= 2 a_2 + 2 a_0 + \sum_{n=1}^\infty \left\{ (n+1)(n+2) a_{n+2} -2n a_n + 2 a_n \right\} x^n \\
 &= 2(a_0 + a_2) + \sum_{n=1}^\infty \left\{ (n+1)(n+2) a_{n+2} -2(n-1) a_n  \right\} x^n = 0
 \end{align*}
$$
より、
- 両辺の0次項を比較して、$2(a_0 + a_2)=0$ → $a_2 = -a_0$
- 両辺の1次項を比較して、$2 \cdot 3 a_3 = 0$ → $a_3 =0$
- 両辺の2次項を比較して、$3 \cdot 4 a_4 -2 a_2=0$ → $a_4 = (1/6) a_2$
- 両辺の3次項を比較して、$4 \cdot 5 a_5 -2 \cdot 2 a_3=0$ → $a_5 = (1/5) a_3 = 0$
- 両辺の$n$次項を比較して、$(n+1)(n+2)a_{n+2} - 2(n-1) a_n =0$ → $a_{n+2} = 2(n-1) / (n+1)(n+2) a_n$

$$
 \begin{align*}
 偶数次項：a_{2m} &=  \frac{2(2m-3)}{(2m-1)2m} a_{2m-2}
 = \frac{2(2m-3)}{(2m-1)2m} \frac{2(2m-5)}{(2m-3)(2m-2)} a_{2m-4}\\
 &= - \frac{1}{(2m-1) m!} a_0 \;\; (m \geq 1)　\\
 奇数次項：A_3 &= A_5 = A_7 = \cdots = A_{2m+1} = \cdots = 0 \; (m \geq 1) \\
 \end{align*}
$$

以上より、
$$
 y = a_0 \left( 1-x^2 - \frac{1}{2! \, 3} x^4 - \cdots - \frac{1}{n! \; (2n-1)} x^{2n} - \cdots \right) + a_1 x
$$