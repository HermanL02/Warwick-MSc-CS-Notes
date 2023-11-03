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
Treat the whole as array and apply filters on that
Things move repidly: see change
slowly: no change
```

```