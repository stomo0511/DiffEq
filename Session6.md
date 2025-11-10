# 第6回 線形微分方程式
## 逆演算子
### p.51 定理3.5
非同次微分方程式 $L(y)=F(x)$ の一般解は、同次微分方程式 $L(y)=0$ の一般解（基本解）$y_f$ と、非同次方程式の特殊解 $y_p$ の和で表される。
$$
 y = y_f + y_p
$$

<span style="color: red; ">逆演算子</span>法は、非同次方程式の特殊解を求める一つの方法。

定数係数線形微分方程式
$$
　\begin{align*}
   L(y) =y'' + b y' + cy &= F(x) \\
   (D^2 + bD + c) y &= F(x) \text{　<- 微分演算子による表現}
 \end{align*}
$$
$f(D) = D^2 + bD + c$ として、
$$
 y = \frac{1}{f(D)} F(x)
$$
は微分方程式 $L(y)=F(x)$ の<span style="color: red; ">特殊解</span>となる。

### p.43 公式(1)
$Dy = F(x)$ を考える。
$$
 \begin{align*}
 Dy=y' & =F(x) \\
 y &= \int F(x) dx = \frac{1}{D} F(x) \tag{1}
 \end{align*}
$$

### p.44 公式(2)
p.36 (1) $f(D) e^{\alpha x} = f(\alpha) e^{\alpha x}$ から、
$$
　\frac{1}{f(D)} e^{\alpha x} = \frac{1}{f(\alpha)} e^{\alpha x} \tag{2}
$$
ただし、$f(\alpha) \neq 0$。

p.45 例題1 (1)
$$
 \frac{1}{D^2 + D + 1} e^{2x} = \frac{1}{2^2 + 2 + 1} e^{2x} = \frac{1}{7} e^{2x}
$$

### p.44 公式(3)
p.36 (2) $f(D) [e^{\alpha x} y] = e^{\alpha x} f(D+\alpha) y$ より、
$$
 \frac{1}{f(D)} F(x) = e^{\alpha x} \frac{1}{f(D+\alpha)} [e^{-\alpha x} F(x)] \tag{3}
$$
（p.44 の証明参照）
公式 (2) が使えない時、公式 (3) を使う。