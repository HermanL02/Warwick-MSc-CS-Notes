• Point or Pixel level 像素级
  - contrast enhancement
  - pseudo-colour

• Local level Local级
  - convolution with local spatial operators
  - Gaussian kernels and derivative operators

• Block transforms: Block级
  - Discrete Cosine Transform (DCT)

• Global level 全局级
  - image transforms: Discrete Fourier Transform (DFT)

• Hierarchical 多级多尺度
  - Pyramids and Wavelet Transforms
# Contrast Modification
修改对比度，修改前x，修改后为T(x)

Log(1+x) mapping -> Lighter
Gamma mapping: λ > 1 ->Darker

# Histogram Equalisation

1. Equalization
2. Cumulative Histogram
3. Equalisation Mapping
4. Overlay the two Cumulative Histograms
5. Histogram Matching
![[Pasted image 20231020095301.png]]
Map from given image X (green) to reference image Y (blue)

举例:
  
这些概念在图像处理中的关系可以简洁地表示为一个直观的步骤流程：

1. **开始**: 你有一幅图像，你想提高它的对比度。
    
2. **Histogram (直方图)**: 首先，你会计算图像的直方图，这可以展示图像中每个像素值的分布情况。
    
3. **Cumulative Histogram (累积直方图)**: 然后，你计算累积直方图，这表示小于或等于某一像素值的像素的累积数量。
    
4. **Equalisation Mapping (均衡化映射)**: 使用累积直方图为图像中的每个像素值产生一个新的像素值。这个映射是为了使新的直方图尽可能均匀地分布。
    
5. **Equalization (直方图均衡化)**: 然后，你将均衡化映射应用到原始图像，产生一个新的、对比度增强的图像。
    
6. **Overlay the two Cumulative Histograms (叠加两个累积直方图)**: 为了比较原始图像和增强后的图像的效果，你可以叠加两个图像的累积直方图。这将展示前后对比度的变化。
# 卷积Convolution
## Def

Convolution is the combination of two functions. We consider one 

$g(x) = \sum_{p=-M}^{M} h(p)f(x-p)$
g(x) 输出图像, f(x) 输入图像, h(p)卷积核, M(卷积核一半的宽度)
x 代表了输出信号或图像 g(x) 的一个特定位置。
p是与核（或滤波器）相关的一个偏移量，用于指示在输入信号或图像 f(x) 中与当前 x 位置相对应的点。
当我们想计算输出 g(x) 在位置 x 的值时，我们需要查看输入f(x) 在周围的位置。具体地，我们会考虑从 x−M 到 x+M 的位置（这就是为什么求和的范围是从 −M 到 M）。对于每一个这样的位置，我们都使用 h(p) 来加权这个位置的值，然后加到 g(x) 上。p 的值就是告诉我们查看输入 f(x) 的哪个位置。

## Simple Example part 
When the kernel is 3* 3 and the value is 1/9 then we use 1/9 * (102 + 75 + 27 + 135 + 111 + 95 + 107 + 4 + 51)
## Boundary Extension in Convocation 
1. 方法1: Use **ZERO** for the outside pixels
2. 方法2: Wrap Kernel to the other side 举例来说，如果我们在一个水平维度上处理一个图像，并且滤波器从右边界超出，那么滤波器超出的部分会在图像的左侧开始。
3. 方法3: **扩展输入图像**：在每个方向上，将图像扩展半个滤波器的大小。然后，可以使用以下方法来填充新增的像素：
- **复制边界值**：这意味着对于新增的像素，我们简单地复制最近的边界像素的值。
- **镜像边界值**：这意味着对于新增的像素，我们使用与边界相反方向的像素值，创建一种镜像效果。
## Kernel Types
Kernels have different effects
Smoothing: low-pass filtering
Sharpening: high-pass filtering
Gradient detection: bandpass filtering

## Gaussian Kernels
$g(x; \sigma) = \exp\left(-\frac{x^2}{2\sigma^2}\right)$ 
Through sigma we can adjust the effect

2D Gaussian: $g(x, y; \sigma) = \exp\left(-\frac{x^2 + y^2}{2\sigma^2}\right)$

SD 2.5 is more blur than SD = 0.5

## Gradient Operators
1. Gradient 定义: 
$f_0(x) = \lim_{{a \to 0}} \frac{f(x + a) - f(x)}{a}$ : Gradient

$\Delta f(x) = f(x + 1) - f(x)$  有限差分近似，当a=1
$\Delta c f(x) = \frac{f(x + 1) - f(x - 1)}{2}$ 中心差分近似，当a=2
$\frac{\partial f(x, y)}{\partial x}, \frac{\partial f(x, y)}{\partial y}$ 对于图像，我们只能估计给定方向的梯度，比如x或者y，对其进行Partial Derivatives

## Sobel Kernel 用于检测边缘
$S(x, y) = \begin{bmatrix} Gx(x, y) \\ Gy(x, y) \end{bmatrix}$ 把这个和图像卷积
Magnitude or edge strength: 边缘强度
$m(x, y) = \lVert S(x, y) \rVert = \sqrt{Gx(x, y)^2 + Gy(x, y)^2}$
Argument or edge direction: 边缘方向
$\theta(x, y) = \arctan\left(\frac{Gy(x, y)}{Gx(x, y)}\right)$

## Derivative of Gaussian Function
**高斯函数的第一导数**描述了这个函数如何随着x的变化而变化。
这个导数在x=0时为0，并在x增加或减少时变得更大。这使得它非常适合于检测边缘，因为边缘是图像中亮度变化最大的地方。
**高斯函数的第二导数**描述了函数的曲率是如何随着x的变化而变化的。
这个导数在x=0的值最大，并且随着x增加或减少而减小。这意味着它对于检测像“线”这样的特征非常有用，因为这些特征在图像中通常有很高的二阶导数。

## Laplacian of Gaussian Operator
The Lapacian is the sum of the partial second derivatives in x and y