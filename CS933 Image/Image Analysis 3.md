# Image as Random Variables
Image can be regarded as random variable. 
## Shuffled image
Means and Variance
N = 512 * 512
µ = 91.2
σ2 = 1642.3
The image means and variance data does not change if we shuffle the image. 

The histogram gives us an estimate of the distribution of colours. 
![[Pasted image 20231018102930.png]]
The histogram does not change if we shuffle the image. 

## What happens if we noise to the image? 
Histogram
![[Pasted image 20231018104109.png]]
Sample and Mean/Variance
![[Pasted image 20231018103506.png]]
N = 512 * 512
µ = 90.8 (Slightly change)
σ2 = 1850.6 (Increased)

Histograms of simple images
![[Pasted image 20231018104212.png]]
![[Pasted image 20231018104217.png]]
# Optimal Threshold using MAP decision rule 
最大后验概率， 
Set Pixel Label = (
1 if p(1|fi) > p(0|fi)
0 else }
# PDF

# Entropy and Redundancy

![[Pasted image 20231020092533.png]]
1. 对于图像，我们可以从其直方图估计其像素值的概率分布p(k)。这里的意思是，通过分析图像中像素值的分布，我们可以估算图像的熵。
2. 熵的值是以比特（bits）为单位的。这意味着，一个信号的熵值越大，它包含的信息量就越大。
3. 冗余描述的是一个信号或数据的“多余”的部分。在这里，冗余被定义为量化位数减去实际的熵。举个例子，对于一个8位图像（即图像的像素值介于0到255之间），如果其熵值为H，那么冗余就是8减去H。
