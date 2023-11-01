# Previous Complex Exponential Knowledge
![[Pasted image 20231030124101.png]]
1. 指数函数的泰勒级数展开：
$e^x = 1 + x + \frac{x^2}{2!} + \frac{x^3}{3!} + \frac{x^4}{4!} + \ldots$
2. 代入 \( ix \) 到上面的公式中：
$e^{ix} = 1 + ix - \frac{x^2}{2!} - i\frac{x^3}{3!} + \frac{x^4}{4!} + \ldots$
3. 拆分为实部和虚部：
$e^{ix} = \left( 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \ldots \right) + i\left( x - \frac{x^3}{3!} + \frac{x^5}{5!} - \ldots \right)$
4. 正弦和余弦函数的泰勒级数展开：
$\cos(x) = 1 - \frac{x^2}{2!} + \frac{x^4}{4!} - \ldots$
$\sin(x) = x - \frac{x^3}{3!} + \frac{x^5}{5!} - \ldots$
5. 结合上述等式得到欧拉公式：
$e^{ix} = \cos(x) + i\sin(x)$
$i = \sqrt{-1}$

So, what is $e^{jwt}$, in this case, j is i: complex number, w is frequency, t is the time point

$F(u) = \frac{1}{N} \sum_{x=0}^{N-1} f(x)e^{-j2\pi ux/N}$
$$
\begin{align*}
\text{Data samples are } & f(x), \quad 0 \leq x < N \\
\text{Frequency sampled at } & 0 \leq u < N \\
\text{Exponent } & \frac{2\pi ux}{N} \text{ is in radians, } 0 \leq \omega < 2\pi
\end{align*}
$$
$F(u) = \frac{1}{N} \sum_{x=0}^{N-1} f(x)\cos(2\pi ux/N) - j \frac{1}{N} \sum_{x=0}^{N-1} f(x)\sin(2\pi ux/N)$

# Fourier Coefficients are Complex 

Through Fourier Transform, we can decompose a function to multiple sine and cosine functions. There are imaginary part in the Fourier Transform.





