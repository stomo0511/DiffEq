# 第4回 線形微分方程式
## 線形微分方程式
**１階線形微分方程式**
$$
 \frac{dy}{dx} + \textcolor{red}{P(x)} y = \textcolor{red}{Q(x)}
$$

１階線形微分方程式の一般解
$$
 y = e^{- \int P(x)dx} \left( \int Q(x) e^{\int P(x)dx} dx + C \right)
$$

（変数分離形もこの公式で解ける。同次形は変数変換が必要）

**2階線形微分方程式**
$$
  \frac{d^2y}{dx^2} + \textcolor{red}{P(x)} \frac{dy}{dx} + \textcolor{red}{Q(x)} y = \textcolor{red}{R(x)}
$$

$R(x)=0$のとき、2階線形**同次**微分方程式という。

2階線形微分方程式の一般解 -> 存在しない

$P(x)=p$、$Q(x)=q$、（ただし $p$、$q$ は定数）の2階線形微分方程式は解ける。

定数係数2階線形同次微分方程式
$$
 \frac{d^2 y}{d x^2} + \textcolor{red}{p} \frac{dy}{dx} + \textcolor{red}{q} = L(y) = \textcolor{red}{0}
$$
を解く <- 今回のテーマ

### 定理 3.1
$u(x)$、$v(x)$ が同次微分方程式の解ならば、
$$
 y = c_1 u(x) + c_2 v(x)
$$
も解である。ただし、$c_1$、$c_2$ は任意定数。

### 一次独立と一次従属
$u(x)$、$v(x)$ が一次独立 <-> $u(x)/v(x) \neq \text{定数}　(v(x) \neq 0)$ または $v(x)/u(x) \neq \text{定数}　(u(x) \neq 0)$

$u(x)$、$v(x)$ が一次従属 <-> $u(x)/v(x) = \text{定数}$

### 定理 3.2
2階線形同次微分方程式
$$
 \frac{d^2 y}{d x^2} + {p} \frac{dy}{dx} + {q} = L(y) = {0}
$$
の2つの解 $u(x)$、$v(x)$ が一次独立ならば、一般解は、
$$
 y = c_1 u(x) + c_2 v(x) \;\;（c_1, c_2\text{は任意定数}）
$$

### 定理 ３．３
スキップ

### 例題 1 （１階線形同次微分方程式）
$y' = 2 y$ の一般解は $y = c e^{2x}$ -> $y' = 2 c e^{2x}$ より、$y' - 2 y = 2 c e^{2x} - 2 \cdot c e^{2x} = 0$

### 練習 1
以下の微分方程式を解け（= 一般解を求めよ）
1. $y' = -3 y$
2. $y' + 5y = 0$
3. $2 y' + 5 y = 0$

## 微分演算子
$$
\begin{align*}
 \frac{dy}{dx} &= \frac{d}{dx} y = D y \\
 \frac{d^2y}{dx^2} &= \frac{d}{dx} \frac{dy}{dx} = DDy = D^2 y
\end{align*}
$$
と表す。このとき $D$ を **微分演算子** という。

### 例
$$
 \begin{align*}
  y'' + 3 y' -4 y &= 0 \\
  D^2 y + 3 D y -4 y &= (D^2 + 3D -4)y = 0
 \end{align*}
$$
上の微分方程式の非自明解（自明解は $y=0$） は、$D^2 + 3D = 4=0$ を満たす。

- 解いてみる
上の 例題1、練習1 の解から $y = e^{tx}$ と置く。ここで $t$ は定数。

$y' = t e^{tx}$、$y''= t^2 e^{tx}$ より、もとの微分方程式は以下となる。
$$
 y'' + 3 y' -4 y = t^2 e^{tx} + 3 t e^{tx} - 4 e^{tx} = (t^2 +3t -4) e^{tx} = 0
$$
$e^{tx} \neq 0$ より、$t^2 + 3t -4 = (t-1)(t+4) = 0$、$t=1, -4$。したがって、解は $\textcolor{red}{y = e^{x}, e^{-4x}}$。
$e^{x}$ と $e^{-4x}$ は一次独立なので、一般解は $\textcolor{red}{y = c_1 e^{x} + c_2 e^{-4x}}$。

微分演算子の方程式 $D^2 + 3D -4=0$ から上の補助方程式 $t^2 + 3t -4=0$ が導出できる。

### 定理 3.4 （の一部）
２階定数係数同次微分方程式 $y'' + b y' + c y = 0$ の一般解は、補助方程式 $t^2 + b t +c=0$ の解が
1. 2つ実数解 $\alpha, \beta \; (\alpha \neq \beta)$の場合、$y = c_1 e^{\alpha x} + c_2 e^{\beta x}$
