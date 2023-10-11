## Acquisition of images

- Sensors acquire image data
- Visible Spectrum
- Non-visible modalities (X-ray, Radar, Lidar)

## Image dimensions

- Spatial: 2D, 3D
- Spatial and time: 2D+t (video), 3D+t (dynamic MRI)
- Spatial with depth: 2D+depth (Kinect, time-of-flight: Radar, Lidar)
- Stereo: 2D cameras or Multiple cameras (Light-field)
- Multi-spectral, e.g. satellite images, biomedical imagery

## Data rates and data compression

- Data rates: in bps
- CD 44.1KHz (44,100 times per second)
- Each sample is 16-bits
- Total: 705.6 Kbps
- 127Mb for a 3 minute song => **Large**
- MP3: Trade off **Quality** and **Compression Rate** => Distortion

## Challenges of sampling, quantisation and size

- Size and Compression
- Denoising
- Interpretation: Detection and Understanding

## Domain and range

### Domain will be sampled. 
- "Domain" 在这里可以理解为一系列的输入数据或信号。
- "Sampled" 在这里指的是对这些数据或信号进行取样，也就是从连续的信号中选择特定的点。比如，音频信号的采样率可能是44.1kHz，意味着每秒会取44,100个样本点。
所以，输入数据或信号将被取样，从而获得离散的数据点集合。

### The range will be quantized. 
- "Range" 在这里可以理解为取样后得到的数据或信号的输出值的集合。
- "Quantilized" (我想你可能是指 "Quantized") 是量化的意思。量化是把连续的值范围映射到有限数量的离散值上的过程。在数字信号处理中，这通常意味着把连续的信号转换为有限级别的数字信号。例如，8位灰度图像的像素值是量化到0至255的整数上的。

输出的数据值将被量化到特定的、有限的级别或值上。


## Spatial Frequency

### Modulated sine grating 

视觉科学研究中的一个常见工具，尤其是在研究视觉系统的空间频率响应时。这是因为，通过展示不同的正弦波纹并观察视觉系统的反应，研究人员可以了解视觉系统对于不同空间频率和对比度的敏感性。

在图像分析和处理中，正弦波纹也经常被用作工具，尤其是在频率分析和滤波器设计中。例如，如果你想了解一个图像处理算法如何影响不同的空间频率，你可能会使用正弦波纹作为输入，然后分析输出的结果。


## Spatial Frequency has direction 

They got horizontal frequency rate and vertical frequency rate. The lowest frequency is 0. 

## Subsampling and Aliasing 
![[Pasted image 20231011102933.png]]
欠采样（Subsampling) resulting Aliasing

### Low-pass filtering 

Through Low-pass filtering we can filter the high frequency part to avoid aliasing. 

	