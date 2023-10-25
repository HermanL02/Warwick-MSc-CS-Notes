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


