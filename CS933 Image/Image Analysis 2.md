# Interpolation and Measurements
- Interpolation
- Linear interpolation
- Bilinear interpolation
- Sinc interpolation
-  Geometric Measurements on Images
- Distances
- Neighbourhoods
- Centroids and Principal Axes
- Distances Transforms
- Boundary descriptions

# Nearest-neighbour Interpolation

The simplest way to up sample by a given factor, say n, is to repeat each value n-times


## Linear Interpolation

求两点中间值公式 f[x] = f[i]+(x − i)(f[i + 1] − f[i])

## Bilinear Interpolation

![[Pasted image 20231013093609.png]]
Bilinear Interpolation using Matrix: 
![[Pasted image 20231013094203.png]]
- 矩形格点的四个角点值是你想估算相邻四个点的值？四个点？
- Δx 和 Δy 是你想要估算的点相对于左上角（或其他参考点）的相对位置

这个公式基本上首先在X轴方向进行两次线性内插，然后在Y轴方向进行一次线性内插。



