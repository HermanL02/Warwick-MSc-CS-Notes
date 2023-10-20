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