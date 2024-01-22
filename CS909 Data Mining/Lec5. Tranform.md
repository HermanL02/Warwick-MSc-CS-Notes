## 为什么需要Transform
使用线性支持向量机（SVM）处理一个非线性可分问题的案例, 转换数据到高维空间可以帮助在这个新空间中实现线性可分，使线性分类器（如线性SVM）有效。
## Kernels
$$d_{\phi}(a, b) = \|\phi(a) - \phi(b)\|^2
               = (\phi(a) - \phi(b))^T (\phi(a) - \phi(b))
               = \phi(a)^T \phi(a) + \phi(b)^T \phi(b) - 2 \phi(a)^T \phi(b)$$
We call dot products in the transformed space “Kernels”. 
$d_{\phi}(a, b) = k_{\phi}(a, a) + k_{\phi}(b, b) - 2k_{\phi}(a, b)$
$k_{\phi}(a, b) = \phi(a)^T \phi(b)$
这只是x, y转x, y, z，那么如果有indefinite dimensional的话，就是叫RBF

## SVM判别函数
$f(\mathbf{x}) = \mathbf{w}^T \mathbf{x} + b$
## Representer Theorem
$根据表达定理，权重向量 \mathbf{w} 可以表示为输入向量的线性组合$
$\mathbf{w} = \sum_{i=1}^{N} \alpha_i \mathbf{x}_i$
所以目前公式是
$f(\mathbf{x}) = b + \sum_{j=1}^{N} \alpha_j \mathbf{x}_j^T \mathbf{x}$
我们还可以引入Kernel，之后是

$f(\mathbf{x}) = b + \sum_{j=1}^{N} \alpha_j k(\mathbf{x}_j, \mathbf{x})$

## Kernel SVM's Optimization
优化问题的目的是最小化一个包含正则化项（wTw）和损失项（误分类的代价）的函数

核SVM的优化问题
$$
\min_{\mathbf{w}} \frac{1}{2} \mathbf{w}^T \mathbf{w} + C \sum_{i=1}^{N} \max\left(0, 1 - y_i f(\mathbf{x}_i; \mathbf{w})\right)
\min_{\boldsymbol{\alpha}, b} \frac{1}{2} \sum_{i,j=1}^{N} \alpha_i \alpha_j k(\mathbf{x}_i, \mathbf{x}_j) + C \sum_{i=1}^{N} \max\left(0, 1 - y_i \left( b + \sum_{j=1}^{N} \alpha_j k(\mathbf{x}_i, \mathbf{x}_j) \right)\right)
$$
权重向量的表示
$$
\mathbf{w} = \sum_{i=1}^{N} \alpha_i \mathbf{x}_i
\mathbf{w}^T \mathbf{w} = \sum_{i=1}^{N} \alpha_i \mathbf{x}_i^T \sum_{j=1}^{N} \alpha_j \mathbf{x}_j = \sum_{i,j=1}^{N} \alpha_i \alpha_j k(\mathbf{x}_i, \mathbf{x}_j)
$$
判别函数的表示
$$
f(\mathbf{x}) = b + \mathbf{w}^T \mathbf{x} = b + \sum_{j=1}^{N} \alpha_j k(\mathbf{x}_j, \mathbf{x})
$$
优化问题使用梯度下降
$$
\min_{\boldsymbol{\alpha}, b} D(\boldsymbol{\alpha}, b) = \frac{1}{2} \sum_{i,j=1}^{N} \alpha_i \alpha_j k(\mathbf{x}_i, \mathbf{x}_j) + C \sum_{i=1}^{N} \max\left(0, 1 - y_i \left( b + \sum_{j=1}^{N} \alpha_j k(\mathbf{x}_i, \mathbf{x}_j) \right)\right)
$$
梯度计算
$$
\nabla_{\alpha_i} D = \sum_{j=1}^{N} \alpha_j k(\mathbf{x}_i, \mathbf{x}_j) - C \sum_{j=1}^{N} y_j k(\mathbf{x}_i, \mathbf{x}_j) \text{ if } 1 - y_i \left( b + \sum_{j=1}^{N} \alpha_j k(\mathbf{x}_i, \mathbf{x}_j) \right) > 0 \text{, else } 0
\nabla_b D = - C \sum_{j=1}^{N} y_j \text{ if } 1 - y_i \left( b + \sum_{j=1}^{N} \alpha_j k(\mathbf{x}_i, \mathbf{x}_j) \right) > 0 \text{, else } 0
$$
梯度下降更新规则
$$
\boldsymbol{\alpha}^{(m)} \leftarrow \boldsymbol{\alpha}^{(m-1)} - \eta \nabla D_{\boldsymbol{\alpha}}(\boldsymbol{\alpha}^{(k-1)})
$$

