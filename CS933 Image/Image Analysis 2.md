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

# Interpolation as weighted combinations

Interpolation can indeed be viewed as a process of taking weighted combinations of neighbouring values.
# Sinc Interpolation 
Higher order interpolation will take weighted combinations of neighbours of neighbours

# Measurements
Shortest or Euclidean Distance
D<sub>E</sub>(p, q) = ||p − q||
City block distance
D<sub>4</sub>(p, q) = |p<sub>x</sub> − q<sub>x</sub>| + |p<sub>y</sub> − q<sub>y</sub>|
Chess-board distance
D<sub>8</sub>(p, q) = max(|px − qx|, |py − qy|)

## Neighbourhoods 
![[Pasted image 20231016124339.png]]
## Thresholding and Binarizations
Binarization: Only keep the most important features
Thresholding: **使用一个或多个阈值来将像素标记为不同的类别**
## Connected Component Labelling
• n = 0
• For each foreground pixel [i, j] not visited
• Set label n+1
• Set labels of neighbours also in F to n+1
• Visit neighbours not visited
• Repeat until while unvisited neighbours

![[Pasted image 20231016125351.png]]

1. **我们可以找到一组像素的“质量中心”或质心，以及其主轴。**
    
    - 质心：是指一组像素的平均坐标位置。通常被视为物体的“重心”。在二维图像中，质心的坐标可以由像素坐标的平均值获得。        
2. **I 是惯性张量（矩阵）或协方差矩阵。**
    - 惯性张量或协方差矩阵描述了像素集合分布的形状和方向。通过这个矩阵，我们可以确定物体的方向，以及哪个方向的分散最大或最小。
3. **角度 θ 是 I 的主特征向量的角度。**
    - 通过对协方差矩阵进行特征值分解，我们可以获得主轴（即主特征向量）。这个向量指示了像素分布最广的方向。角度 θ 描述了这个主轴与水平轴的角度。
4. **这是否可以扩展到3D？**
    - 是的，这些概念可以扩展到3D。在三维中，质心将有三个坐标值 (x, y, z)。惯性张量或协方差矩阵将是一个3x3的矩阵。主特征向量也会有三个，描述了3D对象在三个主方向上的分布。