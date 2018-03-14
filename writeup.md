# **Finding Lane Lines on the Road** 

## Writeup

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

### Reflection

### 1. Describe your pipeline. As part of the description, see my process_img_helper() function.

My pipeline consisted of the following steps. 

1. Gaussian Blur the image;
2. Then apply grayscale;
3. Use Canny's edge detector on the grascaled image;
4. Mask only interested field region for line detection;
5. Use Hugh's line detection
6. Separate the line pixels into two parts, left and right, and do regression on either part;
7. Use OpenCV to plot the line based on the two lines from regression.

### 2. Identify potential shortcomings with your current pipeline


One shortcoming would be when the lane is not straight, then the Hugh detection would simply fail. 

Another shortcoming is that hard coded region of interest would be very bad for generalizing accross cars. One bug I experienced was due to that my region of interest is too small and lanes were not in the hard-coded region so the pipeline might fail.




### 3. Suggest possible improvements to your pipeline

A possible improvement would be to stabilize the lane by using moving average techniques in the video, though this doesn't matter for single image processing.
