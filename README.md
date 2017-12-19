# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/00000.jpg "Grayscale image"
[image2]: ./examples/00001.jpg "Canny edge detection"
[image3]: ./examples/00002.jpg "Final output image"

---

### Reflection

### 1. My pipeline for image processing.

My pipeline consisted of 5 steps. 

1. I converted the images to grayscale and apply a mask for color(we are only interested in white and yellow) and a mask for region of interest(a trapezoid area) 
![alt text][image1]
2. Apply gaussian blur and Canny edge detection to find all edges in the image
![alt text][image2]
3. Apply Hough line transform to find all possible lines in the image, I choose a quite big 'max_line_gap' since there are dashed lines in the test

4. Try to separate the detected lines with K-means algorithm(K=2 here), average the slope and intercept for both clusters

5. The averaged lines are the representations of left lane and right lane, overlap them onto original image
![alt text][image3]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when ... 

Another shortcoming could be ...


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to ...

Another potential improvement could be to ...
