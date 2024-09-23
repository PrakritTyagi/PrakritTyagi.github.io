---
date: 2021-01-09 07:30:35 +0300
title: N-MPC Formulation For UAV Target Tracking
subtitle: MPC and UAV
image: '/images/NMPC/cover_nmpc.png'
---

## Motivation

Persistent target tracking using fixed-wing unmanned aerial vehicles (UAVs) in urban areas is an important application. However, due to the kinematic constraints of the UAV coupled with the visibility obstruction due to terrain impose hard constraints on the UAV motion for persistent tracking. In this project, we propose a nonlinear model predictive control (NMPC) based controller with a gimballed camera to persistently track a target on the ground. The controller determines the control commands for the UAV and the gimbal azimuth and elevation angles. Simulations results show that the proposed approach can efficiently track the target compared to the NMPC framework without gimbal.

The target tracking involves

- Persistent tracking with limited camera field-of-view (FOV)
- Obstacle avoidance
- Avoiding paths that obstruct visibility
- Satisfy physical vehicle motion constraints
- Maximize fight time

## Problem Formulation

Consider a fixed-wing UAV with a camera mounted on a gimbal at its center of gravity. The target is moving on the ground with constant velocity and its position, heading angle, velocity and angular velocity are available to the UAV.


### UAV modelling and Prediction equations

![CNN Model](/images/NMPC/dynamics.png){: width="900" height="675"}

![CNN Model](/images/NMPC/gimbal_target.png){: width="900" height="675"}

### NMPC Formulation

![CNN Model](/images/NMPC/NMPC.png){: width="900" height="675"}

### Objective Function

![CNN Model](/images/NMPC/objective.png){: width="900" height="675"}

#### Energy Function

![CNN Model](/images/NMPC/energy.png){: width="900" height="675"}

#### Distance Function

![CNN Model](/images/NMPC/distance.png){: width="900" height="675"}

#### Ellipse Function

![CNN Model](/images/NMPC/ellipse.png){: width="900" height="675"}

#### LOS Function

![CNN Model](/images/NMPC/los.png){: width="900" height="675"}

#### Obstacle Avoidance Function

![CNN Model](/images/NMPC/obstacle.png){: width="900" height="675"}

### Simulation Setup

![CNN Model](/images/NMPC/simulation_env.png){: width="900" height="675"}

### Results

![CNN Model](/images/NMPC/results.png){: width="900" height="675"}


![MAPF video](/images/NMPC/NMPC.gif){: width="800"}

## References

Read Full Report [Here](https://ieeexplore.ieee.org/document/9476710) and code [GITHUB](https://github.com/PrakritTyagi/MPC_Target-Tracking_UAV)
