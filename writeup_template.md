# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image2]: ./test_images/average_test.jpg "average"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps. First, I converted the images to grayscale, then a canny transform, then region of interest filter, then hough lines, and then I display the weighted image combining the original image and the line pipeline results. On top of this I also use an average of the last 10 frames to develop an image which can then be used to draw lines, this has the effect of smoothing out the lane finding algorithm.

![alt text][image2]

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by using the slope of the line to figure out which line segments belong on each side. I then removed outliers on each side. 



### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be that it doesn't take big outliers into consideration.  

Another shortcoming could be that the viewpoint of where it should look for lane lines is very limited. Currently it really only supports field of views that match the test footage.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to detect objects that aren't lines so that footage with someone coming into your lane does not affect the lane detection.


Another potential improvement could be to add some sort of sanity check.
