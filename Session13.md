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
  
### 通常点
$x=0$ が「通常点」のとき、一般解 $y$ は以下で表せる。
$$
 y = c_1 \left( \sum_{n=0}^{\infty} a_n x^n \right) + c_2 \left( \sum_{n=0}^{\infty} b_n x^n \right)
$$
ここで、$c_1, c_2$ は任意定数。

### p.69 例題１
$$
 (1-x^2) y'' + -2xy' + 2y = 0
$$

$P_0(x) = 1-x^2, P_0(0)=1 \neq 0$ より $x=0$ は**通常点**なので、
$$
 y = a_0 + a_1 x + a_2 x^2 + \cdots + c_n x^n + \cdots
$$
とおく。
$$
 \begin{align*}
  y &= a_0 + a_1 x + a_2 x^2 + \cdots + c_n x^n + \cdots = \sum_{n=0}^{\infty} a_n x^n \\
  y' &= a_1 + 2 a_2 x + \cdots + n c_n x^n + \cdots = \sum_{n=1}^{\infty} n a_n x^{n-1} \\
  y'' &= 2 a_2 + 2 \cdot 3 a_3 x + \cdots + (n-1) \cdot n c_n x^{n-2} + \cdots = \sum_{n=2}^{\infty} (n-1) n a_n x^{n-2}
 \end{align*}
$$
$$
 \begin{align*}
  x^2 y'' &= \sum_{n=2}^{\infty} (n-1) n a_n x^{n} \\
  x y' &= \sum_{n=1}^{\infty} n a_n x^{n} \\
  (1-x^2) y'' + -2xy' + 2y &=
   \sum_{n=2}^{\infty} (n-1) n a_n x^{n-2} \\
  & - \sum_{n=2}^{\infty} (n-1) n a_n x^{n} \\
  & -2  \sum_{n=1}^{\infty} n a_n x^{n} \\
  & +2 \sum_{n=0}^{\infty} a_n x^n \\
  &= \sum_{n=0}^{\infty} (n+1) (n+2) a_{n+2} x^{n} \tag{a}\\
  & - \sum_{n=2}^{\infty} (n-1) n a_n x^{n} \tag{b}\\
  & -2  \sum_{n=1}^{\infty} n a_n x^{n} \tag{c}\\
  & +2 \sum_{n=0}^{\infty} a_n x^n \tag{d} \\
 \end{align*}
$$

- $n=0$ のとき: $(a),(d)$より、$2a_2 + 2 a_0 = 0$ → $a_2 = -a_0$ 
- $n=1$ のとき: $(a),(c),(d)$より、$2 \cdot 3 a_3 -2 a_1 + 2 a_1 =0$ → $a_3 = 0$
- $n=2$ のとき: $(a),(b),(c),(d)$より、$3 \cdot 4 a_4 -2 a_2 -2 \cdot 2 a_2 + 2 a_2 =0$ → $a_4 = (1/3) a_2 = -(1/3)a_0$
- $n=n$ のとき: $(a),(b),(c),(d)$より、$(n+1)(n+2) a_{n+2} - (n-1) n a_n -2n a_n + 2 a_n =0$ → $a_{n+2} = \{ (n-1) / (n+1) \} a_n$

$a_3 = 0$ より、
$$
 a_{2m+1} = 0 \;\; (m \geq 1)
$$
$$
 \begin{align*}
 a_{2m} &= \frac{(2m-2)-1}{(2m-2)+1} a_{2m-2} = \frac{2m-3}{2m-1} a_{2m-2} = \frac{2m-3}{2m-1} \frac{2m-5}{2m-3} a_{2m-4} \\
 &= \frac{(2m-3)(2m-5) \cdots 3 \cdot 1}{(2m-1)(2m-3) \cdots 5 \cdot 3} a_2 = \frac{1}{2m-1} a_2 = - \frac{1}{2m-1} a_0\;\; (m \geq 2)
 \end{align*}
$$

以上より、
$$
 y = a_0 + a_1 x - a_0 x^2 - \frac{1}{3} a_0 x^4  - \frac{1}{5} a_0 x^6 - \cdots = a_0 (1 - x^2 - \frac{1}{3} x^4 - \cdots) + a_1 x
$$
ここで、$a_1, a_2$ は任意定数。
