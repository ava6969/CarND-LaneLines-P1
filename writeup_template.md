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

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.


My pipeline consisted of 5 steps. First, I converted the images to grayscale, then I appied gaussian blur to the image before passin into a canny edge detection function. i masked the img using a polygon to detect area of interest. i passed the masked image into a hough transform to convert from image space to hough space, then i layered the lines detected over the image using the weighted img.

In order to draw a single line on the left and right lanes, I modified the draw_lines() function by usinf the numpy polyfit function to extrapolate a line from the edges detected already.


[image1]: ./test_images/output_solidWhiteCurve.jpg
[image1]: ./test_images/output_solidWhiteRight.jpg
[image1]: ./test_images/output_solidYellowCurve.jpg
[image1]: ./test_images/output_solidYellowCurve2.jpg
[image1]: ./test_images/output_solidYellowLeft.jpg
[image1]: ./test_images/output_solidCarLaneSwitch.jpg


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen whe i pass images with lots of curves into my pipeline. it doesnt accuratly place the lines over the alnes.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to make the pipeline work on curved track lanes
