# Multiresolution
- Hierarchical Computations
- Pyramids
- Discrete Cosine Transforms

# Smoothing and Subsampling
We can combine the subsample and smooth to build a image ==Pyramid==

# REDUCE operation

## Def
REDUCE is done by smoothing and sub-sampling
it recursively to build a set of pyramid levels. 
$P(f, 0) = f(x, y)$
$P(f,l + 1) = REDUCE [P(f,l)] = (P(f,l) ~ G) ⬇2$
G代表Gaussian
⬇代表缩小
# EXPAND operation

## Def

$Pˆ(f,l) = EXP AND [P(f,l + 1)] = G ~ (P(f,l + 1) ⬆2)?$

## Laplacian Level by Difference of Gaussians
### How to build 
- The difference between L Level's Photo - The expanded version of the next level's (L+1) 's photo.  Then we can get the **high-pass** photo. 
- We can also add the difference to the expanded version to get the original photo. 
1. 首先对下一层P(f, 1)执行EXPAND操作，然后将结果与当前层的拉普拉斯表示L(f, 0)相加 $P(f, 0) = \text{EXPAND} [P(f, 1)] + L(f, 0)$

2. 对更低的层级P(f, 2)执行EXPAND操作，并将结果与拉普拉斯表示L(f, 1)相加 $P(f, 1) = \text{EXPAND} [P(f, 2)] + L(f, 1)$

# The Laplacian Pyramid based Image Compression
1. Build Laplacian Pyramid, each level represents the details of a magnitude
2. Keep the Top Gaussian Picture (It is the lowest resolution picture in Laplacian.)
3. Threshold Laplacian Level and **discard the coefficients near zero**
4. Invert to reconstruct, expand, add, expand
5. Quantization 
6. Low Pass Coefficient More bits: Low Pass means general structure(shape, boundary, and large area colors)
7. High Pass Coefficient Less bits

# Pyramid viewed as a Filter Bank  

• The Laplacian Pyramid operation (+ Gaussian Level) can be viewed as filter bank decomposition of the image

# Transform Domain Analysis
DCT: Transform the signal from spatial domain to frequency domain, used for compression
FT: Used to transform time to Frequency

## Basis Projection 

How: Multiply and add two signals


## Discrete Transform Basis functions

[How do you find the integral of cos(mx)⋅cos(nx)? ](https://socratic.org/questions/how-do-you-find-the-integral-of-cos-mx-cos-nx)

## DCT is invertible 
DCT functions for synthesis are same as for analysis!












 