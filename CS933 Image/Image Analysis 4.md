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
g(x) 输出图像, f(x) 输入图像, h(p)卷积核, M(卷积核一半的宽度), x and p, 