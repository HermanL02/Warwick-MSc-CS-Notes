# Topics 
1. Background Modelling
2. Feature detection and Feature Matching
3. Estimate Motions using optical flow
4. View Geometry and Camera Calibration
# Background Subtraction Modelling
- First step is to separate foreground objects from stationary background
- Assume camera is fixed
## Hardness
1. illumination
2. shadows
3. stakes
4. background motions
5. occlusions'
6. Caption noise

# Camera Fixed
# Background Modelling, How? 
1. Frame Filtering
2. Running AVG, learn steady-state
3. statistically model background colour distribution: per-pixel
- Gaussian
- Mixture of Gaussians
- Likelihoods test to decide temporal changes from current model 
## Frame differencing and Thresholding
1. Treat the whole as array and apply filters on that
2. Things move repidly: see change
3. slowly: no change
```
# Background modelling with mixture gaussians
```

# Gaussian Model of Background 
- Aim is to model each pixel over time as being drawn from a normal
distribution: parameterise by mean and variance 对于视频中的每个像素，我们可以使用一组参数（均值和方差）来描述其随时间变化的特性。具体地，我们假设每个像素值的变化遵循正态分布
$B(x, y) \sim N(\mu_{x,y}, \sigma_{x,y}^2) = \frac{1}{\sigma \sqrt{2\pi}} e^{-\frac{(B-\mu)^2}{2\sigma^2}}$
- $\mu(t + 1) = \alpha F(t) + (1 - \alpha)$
- $\mu(t)\sigma^2(t + 1) = \alpha (F(t) - \mu(t))^2 + (1 - \alpha) \sigma^2(t)$
- 其中，F(t)是在时间t的像素值，α是一个学习率，它决定了新像素值与历史数据之间的权重
# GMM 高斯混合模型 
1. Each pixel using different Gaussian Distribution
2. Each frame provides new colour info (data)
3. Update model parameter
4. Test whether it matches the background

# On-Line EM Algorithm Using Learning Rule 
1. **确定像素颜色属于哪个模式**: 首先，需要确定当前像素颜色属于K个模式中的哪一个。这是通过在线EM算法和学习规则来完成的。
    
2. **测试‘归属’于组件k**: 为了确定像素值是否属于特定的组件k，我们使用以下条件：
$(f(t) - \mu_k)^2 < 2.5\sigma_k^2$
其中, f(t)是当前帧的像素值，μk​和2σk2​分别是组件k的均值和方差。

# Stauffer and Grimson: FG 前景Classification Test
1. 权重最大的component会被优先考虑
2. 权重大且方差小的组件更有可能是背景
3.  我们需要设置一个阈值T，通常大于0.5（例如0.8、0.9等）。然后，从权重最大的组件开始，累加这些组件的权重，直到总和超过阈值T。这些组件被认为是背景组件，而权重较小的组件被认为是前景组件。
- Stauffer和Grimson的方法可以有效地区分前景和背景，即使在背景中存在许多变化和噪声的情况下。这种方法的一个关键优点是它可以适应动态背景，如飘动的树叶或波动的水面，同时还能检测出前景物体，如行走的人或移动的车辆
