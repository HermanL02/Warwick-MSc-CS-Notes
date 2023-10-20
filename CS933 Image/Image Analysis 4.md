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
## Histogram Matching
![[Pasted image 20231020095301.png]]
Map from given image X (green) to reference image Y (blue)
