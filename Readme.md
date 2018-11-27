# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[imageoriginal]: ./test_images/whiteCarLaneSwitch.jpg "original"
[imageGrayscale]: ./test_images_output/gray/whiteCarLaneSwitch.jpg "Grayscale"
[imageGaussian]: ./test_images_output/gaussian/whiteCarLaneSwitch.jpg "Gaussian"
[imageCanny]: ./test_images_output/canny/whiteCarLaneSwitch.jpg "Canny"
[imageHough]: ./test_images_output/hough/whiteCarLaneSwitch.jpg "Hough"
[imagemask]: ./test_images_output/mask/whiteCarLaneSwitch.jpg "mask"
[imageweighted]: ./test_images_output/weighted/whiteCarLaneSwitch.jpg "weighted"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps:- 

1) First, I converted the images to grayscale using opencv. This will help in edge detection.

* Original image

![alt text][imageOriginal]

* Grayscale image

![alt text][imageGrayscale]
  
2) Using Gaussian filter, Image was smoothen up.

* Gaussian image

![alt text][imageGaussian]

3) To detect edges & corners, Canny algorithm was used.

* Canny image

![alt text][imageCanny]

4) line detection using hough method & area of interest in image was selected using masking method.

* Masked image

![alt text][imagemask]

* Hough lines image

![alt text][imageHough]

5) The original image is overlaid with hough lines image  

* Final image

![alt text][imageweighted]


To draw the Single line on lane, i used following process:-

1) X & Y coordinates of lines stored in array & slope of each line is calculated.

2) Each slope checked with the threshold range limit & left/right side lane data seprated.

3) Interceptof each line calculated.

4) Using Numpy function line was averaged.

5) Color and thickness were then applied to the averaged lines. 


### 2. Identify potential shortcomings with your current pipeline

Followings are some potential shortcomings in my current pipeline:-
  * Current algorithm can not handle rain condition/snow condition/dark night/vehicle crossing/bad road.
  * Image should be clear with good resolution. Blurr image can cause a problem.
  * Algorithm will have problem in detecting sharp turn road.
  

### 3. Suggest possible improvements to your pipeline

Followings are some improvement area :- 
  * Dynamic area of interest on road.
  * Reduce nosie in lane detection
  * Adding curve road lane detection algorithm 
