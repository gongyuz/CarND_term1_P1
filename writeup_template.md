# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"
[image2]: ./examples/canny_gaussian.jpg "Canny_Gaussian"
[image3]: ./examples/mask.jpg "Mask"
[image4]: ./examples/hough_lines.jpg "Hough_Lines"
[image5]: ./examples/merge.jpg "Merge"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I apply the canny transform and apply a Gaussian noise kernel. The next step is masking the image with the interest region, within which the lane lines stand. Then I draw the lines and converted the image with Hough lines drawn. The last step is combining the lane lines image with the original image. 

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by conducting an weighted average of all the left and right lane line segments to get a single left and right lane line for each image. Taking left lane averaging as an example: All the line segments with negative slope are taken as left line segments. Since the absolute value of slope of the left lane shouldn't be either very low or very high, the line segments with sharp or slow slopes are dropped when calculating the averages. 

If you'd like to include images to show how the pipeline works, here is how to include an image: 

![Grayscal][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
