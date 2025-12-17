# 第11回 連立微分方程式
これまで、
- 独立変数 $x$
- 未知関数 $y(x)$

ここでは、
- 独立変数 $t$
- 未知関数 $x(t)$, $y(t)$

とする。つまり、**連立微分方程式**を扱う。

例：
$$
 \left\{
  \begin{align*}
    x' - 2x + y &= e^t \\
    x' + y' + 4x &= 0
  \end{align*}
 \right.
$$
これは、微分演算子$D$を用いて以下のように表せる。
$$
 \left\{
  \begin{align*}
    (D - 2) x + y &= e^t \;\;\;\;\; \tag{1}\\
    (D + 4) x + D y &= 0 \tag{2}
  \end{align*}
 \right.
$$

(1)を$x$, $y$ についての連立一次方程式として解く。

<!-- ## <span style="color: red; ">教科書とは違う解法</span>
### (2) = (2) - D(1)
$$
 \left\{
  \begin{align*}
    (D - 2) x & + y = e^t \tag{1'}\\
    (-D^2 + 3D + 4) x & \;\;\;\;\;\;\;= -D e^t = -e^t\;\;\;\; \tag{2'}
  \end{align*}
 \right.
$$
(2)の$y$の項が消えていることに注意（←こうなるよう操作を行った）

### (1')と(2')の入れ替えと(2')の符号反転
$$
 \left\{
  \begin{align*}
    (D^2 - 3D - 4) x  \;\;\;\;\; &= e^t \;\;\;\; \tag{a} \\
    (D - 2) x + y &= e^t \tag{b}\\
  \end{align*}
 \right.
$$

### 二階非同次微分方程式(a)を解く
$t^2-3t-4=(t+1)(t-4)=0$の解$t=-1,4$から、同次方程式の一般解$x_f$は、 
$$
 x_f = c_1 e^{-t} + c_2 e^{4t}
$$

特殊解$f_p$は、
$$
 f_p = \frac{1}{D^2-3D-4} e^t = \frac{1}{f(1)} e^t = -\frac{1}{6} e^t
$$

(a)の一般解 $x$ は、
$$
 x = x_f + x_p = c_1 e^{-t} + c_2 e^{4t} -\frac{1}{6} e^t
$$

### (b)から$y$を求める
(b)より、
$$
 \begin{align*}
  y &= e^t - (D-2) x \\
    &= e^t - (D-2) \left\{ c_1 e^{-t} + c_2 e^{4t} -\frac{1}{6} e^t \right\} \\
    &= e^t - \left\{ c_1 (-1-2) e^{-t} + c_2 (4-2) e^{4t} -\frac{1}{6} (1-2) e^t \right\} \\
    &= 3c_1 e^{-t} -2 e^{-4t} + \frac{5}{6} e^t
 \end{align*}
$$

## <span style="color: red; ">ここから教科書の解法</span> -->

### $y$を消去すると、
$$
 \begin{align*}
  (D(D-2) - (D+4)) x &= D e^t \\
  (D+1)(D-4) x &= e^t
 \end{align*}
$$

### $(D+1)(D-4) x =0$の一般解
補助方程式 $(t+1)(t-4)=0$の解は$t=-1,4$（2つの実数解）なので、一般解は以下となる。
$$
 x = c_1 e^{-t} + c_2 e^{4t} 
$$

### $(D+1)(D-4) x = e^t$の特殊解
【逆演算子】

$$
 \frac{1}{D+1} \frac{1}{D-4} e^t = - \frac{1}{6} e^t
$$
p.44 公式(2)を2回適用した。
これは、
$$
 \frac{1}{D^2-3D-4} e^t = \frac{1}{1-3-4} e^t = - \frac{1}{6} e^t
$$
このように、直接公式(2)を適用した方がよい。

【未定係数法】

補助方程式の解は $-1,4$ であり、$\alpha=1$ より、p.54 定理3.7 (i)より、この非同次形微分方程式は $A e^{t}$ の形の特殊解を持つ。
$A e^{t}$を元の微分方程式に代入して、
$$
 -\frac{1}{6}e^t
$$
を得る。

 ### $(D+1)(D-4) x = e^t$の一般解
 $$
  x = c_1 e^{-t} + c_2 e^{4t} -\frac{1}{6}e^t\tag{3}
 $$

 ### 得られた $x$ から $y$ を求める
 $x$ を(1)の上式に代入して、
 $$
  \begin{align*}
   y &= e^t - (D-2) \left[ c_1 e^{-t} + c_2 e^{4t} -\frac{1}{6}e^t \right] \\
   &= 3 c_1 e^{-t} -2 c_2 e^{4t} + \frac{5}{6} e^t\tag{4}
  \end{align*}
 $$

## 教科書の[別解]
### $x$を消去して $y$ を求める
連立微分方程式(1)から$x$を消去すると、次の$y$の非同時系微分方程式が得られる。
$$
  (D+1)(D-4) y = -5 e^t
$$
これを解くと、次の一般解が得られる。
$$
  y = b_1 e^{-t} + b_2 e^{4t} + \frac{5}{6}e^t \tag{5}
$$

任意定数 $c_1, c_2, b_1, b_2$ を $c_1, c_2$ に**集約しなければならない**。← なぜ集約できるかは後で説明する

(3), (5) を (1) へ代入
$$
  \begin{align*}
   (D-2) \left[ c_1 e^{-t} + c_2 e^{4t} -\frac{1}{6}e^t \right] + \left[ b_1 e^{-t} + b_2 e^{4t} + \frac{5}{6}e^t \right] \\
   = (-3 c_1 + b_1) e^{-t} + (2c_2 + b_2) e^{4t} + e^t = e^t \\
   -3 c_1 + b_1 = 0 , \;\;\;\; 2c_2 + b_2=0 \\
   b_1 = 3c_1 , \;\;\;\; b_2 = -2 c_2
  \end{align*}
$$

これで、(5)は(4)と等しくなる。

## 例題2（初期値問題）
初期条件から、任意定数の値を決定する。

$t=0, x=-1/6, y=5/6$ を(3)に代入して、 $c_1 = -1/3, c_2 = 1/3$を得る。

「解け」＝「微分方程式の解を求めよ」なので、
$$
 \left\{
  \begin{align*}
    x &= -\frac{1}{3} e^{-t} + \frac{1}{3} e^{4t} -\frac{1}{6}e^t \\
    y &= -e^{-t} -\frac{2}{3} e^{4t} + \frac{5}{6}e^t
  \end{align*}
 \right.
$$
が例題2の答えとなる。

## 任意定数の数
連立微分方程式(1), (2)の任意定数は $c_1, c_2$の2つだった。

次の連立微分方程式を考える。
$$
 \left\{
  \begin{align*}
    f_{11}(D) x + f_{12}(D) y &= h_1 \\
    f_{21}(D) x + f_{22}(D) y &= h_2
  \end{align*}
 \right.
$$
$$
 \left[ \begin{array}{cc} f_{11}(D) & f_{12}(D) \\ f_{21}(D) & f_{22}(D) \end{array} \right]
 \left[ \begin{array}{c} x \\ y \end{array} \right] =
 \left[ \begin{array}{c} h_1 \\ h_2 \end{array} \right]
$$
$$
 （行列式）　\Delta(D) = \left| \begin{array}{cc} f_{11}(D) & f_{12}(D) \\ f_{21}(D) & f_{22}(D) \end{array} \right|
$$
とすると、
$$
 \left[ \begin{array}{c} x \\ y \end{array} \right] = \frac{1}{\Delta(D)} 
 \left[ \begin{array}{rr} f_{22}(D) & -f_{12}(D) \\ -f_{21}(D) & f_{11}(D) \end{array} \right]
 \left[ \begin{array}{c} h_1 \\ h_2 \end{array} \right]
$$
と表せる。

ここで、
- $\Delta(D)$が<span style="color: red; ">$k$次式</span>ならば、連立微分方程式の一般解は<span style="color: red; ">$k$個の任意定数</span>を含む
- $\Delta(D)$が<span style="color: red; ">定数</span>ならば、連立微分方程式の一般解は<span style="color: red; ">任意定数を含まない</span>

p.59 例題3は任意定数を含まない例

### p.60 例題4は未知関数が3つの例