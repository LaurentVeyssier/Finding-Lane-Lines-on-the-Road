# Finding-Lane-Lines-on-the-Road
Create a Lane Finding pipeline that finds lane lines on the road

## Description

When we drive, we use our eyes to decide where to go. The lines on the road act as our constant reference for where to steer the vehicle. Naturally, one of the first things we would like to do in developing a self-driving car is to automatically detect lane lines using an algorithm.

In this project a line detection algorithm is proposed to detect lane lines in images using Python and OpenCV. OpenCV means "Open-Source Computer Vision", which is a package that has many useful tools for analyzing images. Recognizing lane markings on roads is possible using well known computer vision techniques.

This project is part of UDACITY's Self-Driving Car Engineer Nanodegree.

## Issue Statement

The objective is to be able to detect lane lines in images and videos real-time. Images present various difficult levels with varying levels of shade, solid and dotted lines, of different colors and various x-y dimensions. A sample of the training set is shown below.

![](asset/sample.PNG)


## Detection Pipeline Workflow 

I started by exploring the training images and looking at various color spaces to indetify the best detection strategy. The images come with yellow and white lane lines. I opted for:
- Using LAB color space, and more particularly the B channel, as the yellow lines stand neatly out. This strategy proved to perform superbly on images with shades while other color spaces could not perform similarly.
- Using HLS color space for white lines.

Pipeline:
- Extract yellow lines using LAB B channel
- Extract white lines using HLS color space.
In both approaches, I used a filtring approach with `cv2.inRange()`. I validated the approach testing `cv2.HoughLinesP` 


## Results
