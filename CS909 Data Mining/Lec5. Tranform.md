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