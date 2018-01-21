# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps:
1. Convert the images to grayscale
2. Apply the canny transform and apply a Gaussian noise kernel. 
3. Masking the image with an interest region, within which the left and right lane lines usually show up. 
4. Draw the Hough lines on an image.
5. Combine the lane lines image with the original image. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by:
1. Sort all the line segments into left or right line segments. If the slope is negative, the line segment is considered as left line segment.
2. Average all the left and right line segments' slope and intercept. If the line slope is too sharp or too slow, the line segments will be discarded.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the vehicle wants to change to another lane.  

Another shortcoming would be what could happen when some other line edges (such as curb or road hedge) are mis-detected as lane lines.

Another shortcoming could be when the left or right lane line suddenly changes its direction, i.e. the lane changes its direction or becomes wider/narrower. (the slope of left lane might also be positive as well) 

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to also apply color detection to the pipeline, and combine the color detection with edge detection.

another potential improvement could be to classifying all the line segments by their relative position in the image, and fitting all the left/right line segments on a single line by regression. 
