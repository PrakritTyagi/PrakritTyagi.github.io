---
title: "Super Visual Lidar Odometry and Mapping"
excerpt: "Implemented a robust real-time ROS-based framework for accurate trajectory estimation, 3D Mapping, and Localization by augmenting the feature extraction and matching algorithm with Super-Point descriptor and SuperGlue matching algorithm. <br/><img src='/images/SVLOAM.png'>"
collection: portfolio
---


* State of the art technique for localizing and mapping an environment in real time using both camera and LIDAR sensors by fusing visual features and LIDAR data to estimate robots movements with higher precision.
* Implemented a robust real-time ROS-based framework for accurate trajectory estimation, 3D Mapping, and Localization by fusing stereo RGB image and LiDAR data using ICP in a non-linear optimization framework to achieve an ATE of 1.773m
* VLOAM used feature extractors such as ShiTomasi, ORB, BRIEF, FAST etc. The descriptor matching was done using Brute-force, L2-Norm and FLANN based matching.
* Augmented the feature extraction and matching algorithm with Super-Point descriptor and SuperGlue matching algorithm.


