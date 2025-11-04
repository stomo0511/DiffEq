# 第5回 線形微分方程式
## 微分演算子（つづき）
### 練習問題
1. $D x^2$
2. $D \cos 4x$
3. $D(x e^{2x})$
4. $D^2 e^{-3x}$
5. $D^2 (x^3 + 5x^2)$
6. $D^2 (x^3 e^{2x})$

### p.36の公式
1. $f(D) e^{\alpha x} = f(\alpha) e^{\alpha x}$
$D e^{\alpha x} = \alpha e^{\alpha x}$、$D^2 e^{\alpha x} = \alpha^2 e^{\alpha x}$、$\ldots$、$D^n e^{\alpha x} = \alpha^n e^{\alpha x}$。
$f(D) = a D^2 + b D + c$ とする。
$$
 \begin{align*}
  f(D) e^{\alpha x} &= (a D^2 + b D + c) e^{\alpha x} \\
  &= a D^2 e^{\alpha x} + b D e^{\alpha x} + c e^{\alpha x} \\
  &= (a \alpha^2 + b \alpha + c) e^{\alpha x} \\
  &= f(\alpha) e^{\alpha x}
 \end{align*}
$$

2. $f(D) [e^{\alpha x} y] = e^{\alpha x} f(D + \alpha) y$
$$
\begin{align*}
 D[e^{\alpha x}y] &= (D e^{\alpha x}) y + e^{\alpha x} Dy \\
 & = \alpha e^{\alpha x} y + e^{\alpha x} Dy \\
 &= e^{\alpha x} (D + \alpha) y \\
 D^2 [e^{\alpha x}y] &= D[ D[e^{\alpha x}y]] = D[e^{\alpha x} (D + \alpha) y] \\
 &= (D e^{\alpha x}) (D + \alpha) y + e^{\alpha x} (D + \alpha) Dy \\
 &= \alpha e^{\alpha x} (D + \alpha) y + e^{\alpha x} (D + \alpha) Dy \\
 &= e^{\alpha x} (D + \alpha)^2 y 
\end{align*}
$$
$f(D) = a D^2 + b D + c$ とする。
$$
 \begin{align*}
  f(D) [e^{\alpha x} y] &= a D^2 [e^{\alpha x} y] + b D [e^{\alpha x} y] + c e^{\alpha x} y \\
  &= a e^{\alpha x} (D + \alpha)^2 y + b e^{\alpha x} (D + \alpha) y + c e^{\alpha x} y \\
  &= e^{\alpha x} \{ a(D + \alpha)^2 + b(D + \alpha) +c \} y \\
  &= e^{\alpha x} f(D + \alpha) y
 \end{align*}
$$

## p.39 オイラーの公式
$$
 e^{i x} = \cos x + i \sin x \tag{1}
$$
ただし、$i$ は**虚数単位**（$i^2 = -1$）。

### 証明
**マクローリンの定理**より、
$$
\begin{align*}
 e^x &= 1 + x + \frac{1}{2!} x^2 + \frac{1}{3!} x^3+ \frac{1}{4!} x^4 + \frac{1}{5!} x^5 + \cdots \\
 \cos x &= 1 - \frac{1}{2!} x^2 + \frac{1}{4!} x^4 + \cdots \\
 \sin x &= x - \frac{1}{3!} x^3 + \frac{1}{5!} x^5 + \cdots \\
 e^{ix} &= 1 + {ix} + \frac{1}{2!} {(ix)}^2 + \frac{1}{3!} {(ix)}^3+ \frac{1}{4!} {(ix)}^4 + \frac{1}{5!} {(ix)}^5 + \cdots \\
 &= 1 + {ix} - \frac{1}{2!} {x}^2 - i \frac{1}{3!} {x}^3+ \frac{1}{4!} {x}^4 + i \frac{1}{5!} {x}^5 + \cdots \\
 &= \left( 1 - \frac{1}{2!} {x}^2 \frac{1}{4!} {x}^4 + \cdots \right) + i \left( {x} - \frac{1}{3!} {x}^3 + \frac{1}{5!} {x}^5 + \cdots \right) = \cos x + i \sin x
\end{align*}
$$

次もまた成り立つ。
$$
 e^{-ix} = \cos x - i \sin x \tag{2}
$$

(1)、(2) より、
$$
\begin{align*}
 \cos x &= \frac{1}{2} ( e^{ix} + e^{-ix}) \tag{3} \\
 \sin x &= \frac{1}{2i} ( e^{ix} - e^{-ix}) \tag{4}
\end{align*}
$$

### 練習問題
次の複素数 $z$ の実部 $Re{z}$、虚部 $Im{z}$ を求めよ。
1. $z = e^{\frac{\pi}{3} i}$
2. $z = e^{\pi i}$
3. $z = e^{(-5 + 2i)x}$
4. $z = (3+2i) e^{(4+2i)x}$

## 定理 3.4 （の一部）
２階定数係数同次微分方程式 $y'' + b y' + c y = 0$ の一般解は、補助方程式 $t^2 + b t +c=0$ の解が
3. 虚数解 $\lambda \pm \mu i$の場合、$y = c_1 e^{\lambda x} \sin \mu x + c_2 e^{\lambda x} \cos \mu x$