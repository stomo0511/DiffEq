# 第2回 1階微分方程式
## 変数分離形
$$
\begin{align*}
 \frac{d\textcolor{red}{y}}{dx} &= \frac{f(x)}{g(\textcolor{red}{y})} \\
 g(y) dy &= f(x) dx \\
 \int g(y) dy &= \int f(x) dx +C \\
\end{align*}
$$

### 例題1（一般解）
$$
\begin{align*}
 (1+x) & \frac{dy}{dx} = 1+y \\
 \frac{dy}{dx} &= \frac{1+y}{1+x} = \displaystyle{\frac{\frac{1}{1+x}}{\frac{1}{1+y}}} = \frac{f(x)}{f(y)} \text{← 変数分離形} \\
 \int \frac{1}{1+y} dy &= \int \frac{1}{1+x} dx \\
 \log |1+y| &= \log |1+x| + C_1 \\
 \log \frac{|1+y|}{|1+x|} &= C_1 \; \textcolor{red}{→} \; \frac{|1+y|}{|1+x|} = e^{C_1}\; \textcolor{red}{→} \; \frac{1+y}{1+x} = \pm e^{C_1} = C \\
 y &= C(1+x) -1 \; \textcolor{red}{←} \; \text{\textbf{一般解}}
\end{align*}
$$

### 例題１の検算
解を微分して、
$$
 y' = \frac{dy}{dx} = C
$$
これを解に代入して変形
$$
\begin{align*}
 y &= \frac{dy}{dx} (1+x) -1 \\
 & (1+x) \frac{dy}{dx} = y+1 \; \textcolor{red}{←} \; \text{任意定数$C$を消去して、元の微分方程式が得られた}
\end{align*}
$$

### 対数関数内の絶対値記号について（教科書 注意2）
上の例では、$e^{C_1}$ が正負両方の場合を含めて任意定数$C$としている。
計算途中で絶対値をつけて正確な計算をしても、教科書のように絶対値記号を省略しても、最終的な一般解は同じになるので、絶対値記号を省略してもよい。（絶対値記号を付けなくても減点されることはない）

### 例題２（特殊解）
例題1の微分方程式の解で $x=1$、$y=3$ となるものを求めよ。

$$
\begin{align*}
 y &= C(1+x)-1 \; \textcolor{red}{←} (x,y)=(1,3) \text{を代入} \\
 \textcolor{red}{3} &= C(\textcolor{red}{1}+1)-1 \\
 C &= 2 \\
 y &= 2x+1 \; \textcolor{red}{←} \; \textcolor{red}{特殊解}
\end{align*}
$$

### 例題3（変数分離形の導出）
$$
\begin{align*}
 (xy^2+y^2) dx & + (x^2 + x^2 y) dy = 0 \\
 \frac{y+1}{y^2} dy &= - \frac{x+1}{x^2} dx \; \textcolor{red}{←} \; \text{変数分離形} \\
 
\end{align*}
$$