# Preliminaries

## Gradient Descent
### Gradients
Find minima and maxima of functions (use derivative)
### Definition
通过沿着目标函数梯度的相反方向迭代更新参数，以寻找函数的最小值。

# Convex Functions
任意函数两点间画一线，始终位于函数上方，他们只有一个minima

# Linear Discriminants

寻找能够区分两个或多个类别的对象或事件的特征的线性组合。这种组合可以作为线性分类器使用，或者更常见的是，在后续分类之前用于降维。
## Representation
1. Features
2. Linear Function
## Evaluation
- Contains misclassification
## Optimization
- Find minimal misclassification's line
- How? Visual Reckoning / Constraint Satisfaction 约束条件和视觉判断
## Why LD? 
Easy to understand and achieve

# Classification Loss Function

Label: y = +1, meaning f(x) is positive meaning that it is correctly classified

Label: y = -1, not correctly classified


## 0-1 Loss Function
计算假设函数 h 在训练集上犯了多少错误

1. 损失不可Differentiate, If one value close to the threshold of positive response, it still disconnected. 
2. Poor optimization
3. 替代函数- 连续，平滑 - continuous and over-approximation AND should be CONVEX
## Surrogate Classification Loss

– A convex over-approximation of the 0-1 loss

$\min_{w} L(X, Y; w) = \sum_{i=1}^{N} \max\{0, 1 - y_i f(x_i; w)\}$
How to solve this function? 
- take derivative and substitute 0
- Gradient Descent
## Optimization
