# **Finding Lane Lines on the Road** 

[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

<img src="examples/laneLines_thirdPass.jpg" width="480" alt="Combined Image" />

Overview
---

When we drive, we use our eyes to decide where to go.  The lines on the road that show us where the lanes are act as our constant reference for where to steer the vehicle.  Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project we will detect lane lines in images using Python Modules (MatPlotLib, Numpy, MoviePy and IPython) and OpenCV.  

* OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images.
* MoviePy is a Python module for video editing, which can be used for basic Operations (like custs, concatenations, title insertions), Video Composing (a.k.a. non-linear editing), Video Processing or create advanced effects.
* MatPlotLib is a Python 2D plotting library which produces pulication quality figures in a variety of hardcopy formats and interactive environments across platforms. 
* Numpy is the fundamental package for scientific computing with Python.
* IPython means "Interactive Python" is a command shell for interactive computing in multiple prgoramming launguages, Originally developed for the Python Programming.

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

My pipeline consisted of 8 steps. 

1. Extracted blue channel from a color image.
2. Added noise to the image by using gaussian with kernel of size 5. 
3. Detected edges using canny edge detection algorithm.
4. Applied a mask to the image with edges to eliminate not important regions.
5. Extracted lines using hough line detection algorithm.
6. Determined slopes of lane lines by averaging and separting left/right line segments.
7. Extrapolated lane lines.
8. Drawn lane lines on the original image.


### 2. Identify potential shortcomings with your current pipeline


1. Several times the detected lane lines are unstable - fluctuating value of line slope. 
2. Hardcoded values for region of interest and all parameters.
3. Variable performance on different light/weather conditions.


### 3. Suggest possible improvements to your pipeline

1. Adaptive parameter values.
2. Smooth out lane lines (kalman filter)
