---
permalink: /
title: "Hi!! I am Prakrit"
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---


🎓 I am a second-year master’s student at Carnegie Mellon University (CMU).

🕵️‍♂️ My research interests lie in Optimal control, simulations and robotics.

💼 I am currently looking to grab PhD opportunnities in field of robotics.

[Resume](/files/PrakritTyagi_resume.pdf){: .btn}
<!-- 👇 Read through this page to know more about me.  -->





Education
======
* **Carnegie Mellon University**            2022-2024
  * M.S. in Mechanical Engineering
  * GPA: 4.00/4.0 
* **Delhi Technological University**        2017-2021
  * B.Tech in Mechanical Engineering
  * GPA: 8.75/10.0 

Research Interests
======
I am focused on optimal control and simulations. I feel that learning based methods
could have eased my burden as they could be trained to learn the physical parameters of the physical system when I could have just focused on software implementation and left some hardware tasks to learning models. Sim2Real is also another pipeline that hopes to seamlessly transfer effort made on simulations to real world experiments, preventing embarrassments of multiple failures before success. 

Projects
======

### [Warebots: Multi Agent Path Finding](/portfolio/portfolio-1)

The project explores the Multi-Agent Pathfinding (MAPF) problem, focusing on one-shot MAPF and its dynamic counterpart, Lifelong MAPF (LMAPF). It delves into the Conflict-Based Search Algorithm (CBS), a two-level approach for resolving conflicts between agents, showcasing its effectiveness in small-scale environments inspired by the League of Robot Runners competition.

[![!!!BROKEN!!!](/images/MAPF.gif)](/portfolio/portfolio-1){: .linked-image}

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


### [LQR based Thrust control of Quadcopter](/portfolio/portfolio-2)
Implemented an LQR controller, which is linearized depending on the quadrotor’s state, unifies the control of rotational and translational states, handles time-varying system dynamics, control parameters and does direct motor control. 

[![!!!BROKEN!!!](/images/LQR.gif)](/portfolio/portfolio-2){: .linked-image}


### [Human Facial Emotion Recognition & Classification](/portfolio/portfolio-3)
As part of a semester-long machine learning team project, built a CNN model that could recognize and classify human emotions from facial images. The objective was to train the model to identify the emotion of a person from their faces.


[![!!!BROKEN!!!](/images/Facial_recog.gif)](/portfolio/portfolio-3){: .linked-image}
<style>
.linked-image img {
  width: 600px; /* Adjust the width as needed */
  height: auto;
}
</style>

### [Super Visual Lidar Odometry and Mapping](/portfolio/portfolio-4)
Implemented a robust real-time ROS-based framework for accurate trajectory estimation, 3D Mapping, and Localization by augmenting the feature extraction and matching algorithm with Super-Point descriptor and SuperGlue matching algorithm.

[![!!!BROKEN!!!](/images/SVLOAM.png)](/portfolio/portfolio-4){: .linked-image}
<style>
.linked-image img {
  width: 600px; /* Adjust the width as needed */
  height: auto;
}
</style>