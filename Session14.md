# 第１3回 級数による解法
## 2階微分方程式
級数による解法が最も有効なのは、以下のような変数係数2階微分方程式。

2階微分方程式
$$
 P_0(x) y'' + p_1(x) y' + P_2(x) y =0
 \tag{1}
$$
の係数 $P_0(x), p_1(x), P_2(x)$ は $x$ の多項式とする。

- $P_0(a) \neq 0$ : $a$ は**通常点**
- $P_0(a) =    0$ : $a$ は**特異点**
  
### 確定特異点
2階微分方程式
$$
 (x-a)^2 y'' + (x-a) P_1(x) y' + P_2(x) y =0
 \tag{2}
$$
について点 $x=a$ は**特異点**である。
$P_1(x)$、$P_2(x)$ が $x$ の多項式のとき、点 $x=a$ を (2) の**確定特異点**という。

このとき、以下が成り立つ。

(2)は、以下の形の解を持つ。
$$
 \begin{align*}
 y = A_0 (x-a)^\lambda + A_1 (x-a)^{\lambda+1} &+ A_2 (x-a)^{\lambda+2} + \cdots \\
 &+ A_n (x-a)^{\lambda+n} + \cdots
 \end{align*}
 \tag{3}
$$
ここで、$A_0 \neq 0$。
$\lambda$は、
$$
 \lambda (\lambda-1) + P_1(a) \lambda + P_2(a) =0
 \tag{4}
$$
の解である。(4) を**決定方程式**と呼ぶ。

#### (1)の解き方
(4)の２つの解を $\lambda_1$、$\lambda_2$ とする。
- $\lambda_1$、$\lambda_2$ の差が**整数でない**場合
$\lambda_1$、$\lambda_2$のそれぞれに対応する解 $y=y_1(x)$ と $y=y_2(x)$ は一次独立であり、一般解は
$$
 y = c_1 y_1(x) + c_2 y_2(x)
$$
となる。

- $\lambda_1$、$\lambda_2$ の差が**整数**の場合
扱わない

### p.71 例題2
$$
 4x y'' + 2y' + y=0
 \tag{a}
$$
与式 $\times x/4$
$$
 x^2 y'' + \frac{1}{2} x y' + \frac{1}{4} xy = 0
 \tag{b}
$$
$x=0$ は微分方程式 (b) の**確定特異点**。
(b) の解を
$$
 y = x^\lambda (a_0 + a_1 x + a_2 x^2 + \cdots + a_n x^n + \cdots )
 \tag{c}
$$
とおく。
$P_1(x) = 1/2$、$P_2(x)=x/4$ → $P_1(0) = 1/2$、$P_2(x)=0$ より**決定方程式**は以下となる。
$$
 \lambda (\lambda-1) + \frac{1}{2} \lambda = \lambda \left( \lambda - \frac{1}{2} \right) = 0
 \tag{d}
$$
決定方程式 (d) の解は $\lambda=0, 1/2$。

#### $\lambda=0$ に対して、
(c) より、
$$
 \begin{align*}
  y &= a_0 + a_1 x + a_2 x^2 + \cdots + a_n x^n + \cdots \\
  y' &= a_1 + 2 a_2 x + 3 a_3 x^2 + \cdots + (n+1) a_{n+1} x^n + \cdots \\
  y'' &= 2 \cdot 1 a_2 + 3 \cdot 2 a_3 x + 4 \cdot 3 a_4 x^2 + \cdots + (n+2)(n+1) a_{n+2} x^n + \cdots \\
 \end{align*}
$$
これを (a) に代入して、以下を得る。（←がんばって解くこと）
$$
 \begin{align*}
 a_1 = -\frac{1}{2!} a_0 , \; a_2 &= \frac{1}{4!} a_0, \; a_3 = - \frac{1}{6!} a_0, \; \cdots , \\
 a_n &= (-1)^n \frac{1}{(2n)!} a_0 , \; \cdots
 \end{align*}
$$
$\lambda=0$ に対する解として以下を得る。
$$
 y = a_0 \left\{ 1 - \frac{1}{2!} x + \frac{1}{4!} x^2 - \cdots + (-1)^n \frac{1}{(2n)!} x^n + \cdots \right\}
 \tag{e}
$$
ここで、
$$
 \cos x = 1 - \frac{1}{2!} x^2 + \frac{1}{4!} x^4 - \cdots + (-1)^n \frac{1}{(2n)!} x^{2n} + \cdots
$$
より、$(e) = a_0 \cos \sqrt{x}$ を得る。


#### $\lambda=1/2$ に対して、
(c) より、
$$
 \begin{align*}
  y &= \sqrt{x} (a_0 + a_1 x + a_2 x^2 + \cdots + a_n x^n + \cdots ) \\
  y' &= \frac{1}{2 \sqrt{x}} \left( a_0 + 3 a_1 x + 5 a_2 x^2 + \cdots + (2n+1) a_{n} x^n + \cdots \right) \\
  y'' &= \frac{1}{4x\sqrt{x}} \left( -a_0 + 3a_1 x + 3 \cdot 5 a_2 x^2 + \cdots + (2n-1)(2n+1) a_{n} x^n + \cdots \right) \\
 \end{align*}
$$
これを (a) に代入して、以下を得る。（←がんばって解くこと）
$$
 \begin{align*}
 a_1 = -\frac{1}{3!} a_0 , \; a_2 &= \frac{1}{5!} a_0, \; a_3 = - \frac{1}{7!} a_0, \; \cdots , \\
 a_n &= (-1)^n \frac{1}{(2n+1)!} a_0 , \; \cdots
 \end{align*}
$$
$\lambda=1/2$ に対する解として以下を得る。
$$
 y = a_0 \sqrt{x} \left\{ 1 - \frac{1}{3!} x + \frac{1}{5!} x^2 - \cdots + (-1)^n \frac{1}{(2n+1)!} x^n + \cdots \right\}
 \tag{f}
$$
ここで、
$$
 \begin{align*}
 \sin x &= x - \frac{1}{3!} x^3 + \frac{1}{5!} x^5 - \cdots + (-1)^n \frac{1}{(2n-1)!} x^{2n-1} + \cdots \\
 \sin \sqrt{x} &= \sqrt{x} - \frac{1}{3!} x^2 \sqrt{x} + \frac{1}{5!} x^2 \sqrt{x} - \cdots + (-1)^n \frac{1}{(2n-1)!} x^{n} \sqrt{x} + \cdots \\
 \end{align*}
$$
より、$(f) = a_0 \sin \sqrt{x}$ を得る。

以上より、(a) の一般解は、$y = c_1 \cos \sqrt{x} + c_2 \sin \sqrt{x} \;\;\; （c_1, c_2 \text{は任意定数}$）