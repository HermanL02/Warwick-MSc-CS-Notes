# Feature Detection and Matching
- Used on describe, search and recognise objects in image and videos
- How to Describe? 
	- colour, texture, shape, size
 No, these are high level, so how about low levels? 
# Cluttered Scene
- Surf Feature
- Note that any feature representation has to be invariant to transformations: **rotation, translation, scale, projective**
# Visual Features 
- Distinctive
- Pose Invariant: Even if it is rotated, scaled or skewed
- Local: small part so even there is a partial photo we can understand
- Repeatable: Invariant to all the objects
# Harris-Stephens Corner Detector
1. Low-level features
2. $E(u, v) = \sum_{(x,y) \in W} w(x, y) [I(x + u, y + v) - I(x, y)]^2$
3. 这个方程代表对一个图形进行移动shift，x，y是原始值，u，v是移动值，这样来判断特征，w是一个window，为x，y分配权重？
## Harris using Taylor Expansion 
- 这是能量函数 E(u,v) 的近似，它通过最小化整个窗口 W 内的像素强度差的平方来寻找最佳的位移
- 这个公式与双线性插值（bilinear interpolation）的关系在于它们都是基于局部近似的方法。在双线性插值中，我们在两个方向上进行线性插值来估计非整数坐标位置的像素值，这也基于了图像强度在局部区域内相对平滑的假设。这种插值方法通常用于图像放大、几何变换等操作。
$$
I(x + u, y + v) \approx I(x, y) + uI_x + vI_y
$$
$$
\begin{bmatrix}
    \sum I_x^2 & \sum I_xI_y \\
    \sum I_xI_y & \sum I_y^2
\end{bmatrix}
\begin{bmatrix}
    u \\
    v
\end{bmatrix}
$$

$$
E(u, v) \approx \sum_{(x,y) \in W} [I(x, y) + uI_x + vI_y - I(x, y)]^2

= \sum_{(x,y) \in W} [uI_x + vI_y]^2

= \sum_{(x,y) \in W} u^2I_x^2 + 2uvI_xI_y + v^2I_y^2

= (u, v) 
$$

# Scale Invariant Feature Transform: SIFT

- Robust Feature Detection 识别特征点
- Feature Size and Orientation Estimation 识别大小和方向
- Invariance of Scale 大小不变
- HoG(Histograms of Oriented Gradients)
- Fast to Compute

