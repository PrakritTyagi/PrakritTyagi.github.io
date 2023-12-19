---
title: "Super Visual Lidar Odometry and Mapping"
excerpt: "Implemented a robust real-time ROS-based framework for accurate trajectory estimation, 3D Mapping, and Localization by augmenting the feature extraction and matching algorithm with Super-Point descriptor and SuperGlue matching algorithm. <br/><img src='/images/SVLOAM.png'>"
collection: portfolio
---


* State of the art technique for localizing and mapping an environment in real time using both camera and LIDAR sensors by fusing visual features and LIDAR data to estimate robots movements with higher precision.
* Implemented a robust real-time ROS-based framework for accurate trajectory estimation, 3D Mapping, and Localization by fusing stereo RGB image and LiDAR data using ICP in a non-linear optimization framework to achieve an ATE of 1.773m
* VLOAM used feature extractors such as ShiTomasi, ORB, BRIEF, FAST etc. The descriptor matching was done using Brute-force, L2-Norm and FLANN based matching.
* Augmented the feature extraction and matching algorithm with Super-Point descriptor and SuperGlue matching algorithm.



Full Report [Here](/files/SVLOAM_report.pdf){: .btn}


[![!!!BROKEN!!!](/images/SVLOAM.png)](/files/SVLOAM_report.pdf){: .linked-image}
<style>
.linked-image {
  position: relative;
}

.linked-image:hover::after {
  content: "Read More...";
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: rgba(255, 255, 255, 0.8);
  padding: 10px;
  border-radius: 5px;
  backdrop-filter: blur(5px);
  font-weight: bold;
  color: #333;
}
</style>
<style>
.linked-image img {
  width: 600px; /* Adjust the width as needed */
  height: auto;
}
</style>
