# SFND 2D Feature Tracking

<img src="images/keypoints.png" width="820" height="248" />

The idea of the camera course is to build a collision detection system - that's the overall goal for the Final Project. As a preparation for this, you will now build the feature tracking part and test various detector / descriptor combinations to see which ones perform best. This mid-term project consists of four parts:

* First, you will focus on loading images, setting up data structures and putting everything into a ring buffer to optimize memory load. 

  The ring buffer optimize memory by processing only two pic at one time. I used vector erase function to limit the img number to 2.


* Then, you will integrate several keypoint detectors such as HARRIS, FAST, BRISK and SIFT and compare them with regard to number of keypoints and speed. 

  This task is to integrate several detectors, I use if and else function for each method for HARRIS, SHITOMASI AND SIFT

* In the next part, you will then focus on descriptor extraction and matching using brute force and also the FLANN approach we discussed in the previous lesson. 

 In this task we have to select usful keypoint from all point by limit the x,y value of the point. If the keypoint with in the boundingbox region, we count this is usful point, otherwise, we ignore it.

* In the last part, once the code framework is complete, you will test the various algorithms in different combinations and compare them with regard to some performance measures. 

  This is comparsion part for all method, and get the result.

See the classroom instruction and code comments for more details on each of these parts. Once you are finished with this project, the keypoint matching part will be set up and you can proceed to the next lesson, where the focus is on integrating Lidar points and on object detection using deep-learning. 

## Dependencies for Running Locally
* cmake >= 2.8
  * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1 (Linux, Mac), 3.81 (Windows)
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* OpenCV >= 4.1
  * This must be compiled from source using the `-D OPENCV_ENABLE_NONFREE=ON` cmake flag for testing the SIFT and SURF detectors.
  * The OpenCV 4.1.0 source code can be found [here](https://github.com/opencv/opencv/tree/4.1.0)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools](https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory in the top level directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./2D_feature_tracking`.

## My Method as follow:
* First, you will focus on loading images, setting up data structures and putting everything into a ring buffer to optimize memory load. 

  The ring buffer optimize memory by processing only two pic at one time. I used vector erase function to limit the img number to 2.


* Then, you will integrate several keypoint detectors such as HARRIS, FAST, BRISK and SIFT and compare them with regard to number of keypoints and speed. 

  This task is to integrate several detectors, I use if and else function for each method for HARRIS, SHITOMASI AND SIFT

* In the next part, you will then focus on descriptor extraction and matching using brute force and also the FLANN approach we discussed in the previous lesson. 

 In this task we have to select usful keypoint from all point by limit the x,y value of the point. If the keypoint with in the boundingbox region, we count this is usful point, otherwise, we ignore it.

* In the last part, once the code framework is complete, you will test the various algorithms in different combinations and compare them with regard to some performance measures. 

  This is comparsion part for all method, and get the result.
Here is my best result table:

No. 	Detector + Descriptor 	Total Keypoints 	Total Matches 	Total Time (ms) 	Ratio (matches/time)
1 	FAST + ORB 	17874 	4254 	20.8537 	203.993
2 	FAST + BRIEF 	17874 	4904 	28.2515 	173.584
3 	FAST + BRISK 	17874 	3170 	65.9564 	48.0621

