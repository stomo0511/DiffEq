# 第3回 1階微分方程式
## 線形微分方程式
次の微分方程式を**線形微分方程式**という
$$
 \frac{dy}{dx} + \textcolor{red}{P(x)} y = \textcolor{red}{Q(x)}
$$

線形微分方程式の一般解
$$
 y = e^{- \int P(x)dx} \left( \int Q(x) e^{\int P(x)dx} dx + C \right)
$$

### P.13 例題1 (1)
$$
\begin{align*}
 xy' - y &= x(1+2x^2) \\
 y' - \frac{1}{x} y &= 1+2x^2 \; \textcolor{red}{←} \; \text{\textbf{線形微分方程式}} \\
 P(x) &= - \frac{1}{x}, \; Q(x) = 1+2x^2 \\
 \int P(x) dx &= \int - \frac{1}{x} dx = - \log x ,\;\; - \int P(x) dx = \log x \\
 e^{- \int P(x)dx} &= e^{\log x} = x^{\text{*1}}, \;\;
 e^{\int P(x)dx} = e^{- \log x} = \frac{1}{x}^{\text{*2}} \\
 \int Q(x) e^{\int P(x)dx} dx + C &= \int (1+2x^2) \frac{1}{x} dx +C = \int \left( \frac{1}{x} + 2x \right) dx +C \\
 &= \log x + x^2 +C \\
  y &= x (\log x + x^2 +C )
\end{align*}
$$

*1, *2
$$
\begin{align*}
 a = e^{\log x} \text{とする} & \\
 \text{両辺の対数をとる} & \; \textcolor{red}{→} \; \log a = \log x \; \textcolor{red}{→} \; a=x \\
 b = e^{-\log x} = e^{\log x^{-1}} = e^{\log \frac{1}{x}} \text{とする} & \\
 \text{両辺の対数をとる} & \; \textcolor{red}{→} \; \log b = \log \frac{1}{x} \; \textcolor{red}{→} \; b=\frac{1}{x}
\end{align*}
$$

### P.13 例題1 (2)
$$
\begin{align*}
 (1+x^2) y' &= xy +1 \\
 y' - \frac{x}{1+x^2} y &= \frac{1}{1+x^2}\; \textcolor{red}{←} \; \text{\textbf{線形微分方程式}} \\
 P(x) &= - \frac{x}{1+x^2}, \; Q(x) = \frac{1}{1+x^2} \\
 \int P(x) dx &= \int - \frac{x}{1+x^2} dx = - \frac{1}{2} \log (1+x^2) ,\;\; - \int P(x) dx = \frac{1}{2} \log (1+x^2) \\
 e^{\int P(x) dx} &= e^{- \frac{1}{2} \log (1+x^2)} = \frac{1}{\sqrt{1+x^2}} , \;\;
 e^{-\int P(x) dx} = e^{\frac{1}{2} \log (1+x^2)} = \sqrt{1+x^2} \\
 \int Q(x) e^{\int P(x)dx} dx + C &= \int \frac{1}{1+x^2} \frac{1}{\sqrt{1+x^2}} dx +C = \frac{x}{\sqrt{1+x^2}}^{*3}+C \\
 y &= \sqrt{1+x^2} \left( \frac{x}{\sqrt{1+x^2}}+C \right) \\
 &= x + \sqrt{1+x^2}C
\end{align*}
$$

*3
$$
\begin{align*}
x = \tan t \text{とすると、} dx = \frac{1}{\cos^2 x} dt \\
 \int \frac{1}{1+x^2} \frac{1}{\sqrt{1+x^2}} dx &= 
 \int \frac{1}{(1 + \tan^2 t) \sqrt{1 + \tan^2 t}} \cdot \frac{1}{\cos^2 t} dt \\
 \text{ここで} 1 + tan^2 t = 1 + \frac{\sin^2 t}{\cos^2 t} = \frac{1}{\cos^2 t} \\
 上式 &= \int \cos t dt = \sin t = \frac{x}{\sqrt{1+x^2}}^{*4}
\end{align*}
$$

*4
$$
 x = \tan t = \frac{\sin t}{\cos t} = \frac{\sin t}{\sqrt{1 - \sin^2 t}} \\
 x^2 (1 - \sin^2 t) = \sin^2 t \\
 \sin t = \frac{x}{\sqrt{1+x^2}}
$$

## ベルヌーイの微分方程式
次の微分方程式を**ベルヌーイの微分方程式**という
$$
 \frac{dy}{dx} + {P(x)} y = {Q(x)} \textcolor{red}{y^n}
$$

ベルヌーイの微分方程式で $\textcolor{red}{z=y^{1-n}}$ とおいて、$x$ と $z$ の微分方程式にすると、これは**線形微分方程式**となる。

### p.15 例題２
$$
\begin{align*}
 2xy' - y &= y^3 \log x \\
 y' - \frac{1}{2x} y &= \frac{\log x}{2x} y^3 \; \textcolor{red}{←} \; \text{\textbf{ベルヌーイの微分方程式}} \\
 P(x) &= - \frac{1}{2x}, \; Q(x) = \frac{\log x}{2x}, \; n=3 \\
 z=y^{-2} \text{とすると、} & \frac{dz}{dx} = -2 y^{-3} \frac{dy}{dx} \; \textcolor{red}{→} \;
 \frac{dy}{dx} = -\frac{y^3}{2} \frac{dz}{dx} \\
 -\frac{y^3}{2} \frac{dz}{dx} - \frac{1}{2y} y &= \frac{\log x}{2x} y^3 \\
  \frac{dz}{dx} + \frac{1}{x} z &= - \frac{\log x}{x} \; \textcolor{red}{←} \; \text{線形微分方程式} \\
  P'(x) &=  \frac{1}{x}, \; Q'(x) = \frac{\log x}{x} \\
  \int P'(x) dx &= \int \frac{1}{x} dx = \log x ,\;\; - \int P'(x) dx = - \log x \\
  e^{- \int P'(x)dx} &= e^{- \log x} = \frac{1}{x}, \;\;
 e^{\int P'(x)dx} = e^{\log x} = x \\
 z & = \frac{1}{x} \left( - \int \frac{\log x}{x} x dx + C \right) \\
 \frac{1}{y^2} &= \frac{1}{x} (-x \log x + x + C)^{*5} \\
 & (x - x \log x +C) y^2 = x
\end{align*}
$$

*5
$$
\begin{align*}
 \int \log x dx &= \int (x)' \log x dx \\
 &= x \log x - \int x \frac{1}{x} dx \\
 &= x \log x - x +C
\end{align*}
$$