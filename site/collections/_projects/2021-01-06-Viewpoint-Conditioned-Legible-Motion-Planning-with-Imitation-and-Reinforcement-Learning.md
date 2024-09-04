---
date: 2021-01-06 05:20:35 +0300
title: Viewpoint-Conditioned Legible Motion Planning with Imitation and Reinforcement Learning
subtitle: AI and Manipulation
image: '/images/IM_RL/cover_xarm.png'
---
<!-- In robotics, **legible motion planning** is crucial for effective human-robot interaction and shared autonomy. It involves designing robotic movements that are easily interpretable by humans, promoting intuitive anticipation of a robot's actions. This is essential in settings where robots and humans work closely together, such as in collaborative manufacturing or healthcare.

![legible motion pictorial description](/images/IM_RL/xarm_lmp.png){: width="900" height="675"} -->

<!-- <div style="display: flex; align-items: center;">
  <img src="/images/IM_RL/xarm_lmp.png" alt="xarm_lmp" style="margin-right: 20px;">
  <p>In robotics, <strong>legible motion planning</strong> is crucial for effective human-robot interaction and shared autonomy. It involves designing robotic movements that are easily interpretable by humans, promoting intuitive anticipation of a robot's actions. This is essential in settings where robots and humans work closely together, such as in collaborative manufacturing or healthcare.</p>
</div> -->

<div style="display: flex; width: 100%; height: 100%;">
  <div style="flex: 1; padding: 10px;">
    <p>In robotics, <strong>legible motion planning</strong> is crucial for effective human-robot interaction and shared autonomy. It involves designing robotic movements that are easily interpretable by humans, promoting intuitive anticipation of a robot's actions. This is essential in settings where robots and humans work closely together, such as in collaborative manufacturing or healthcare.</p>
  </div>
  <div style="flex: 1; padding: 10px; display: flex; align-items: center; justify-content: center;">
    <img src="/images/IM_RL/xarm_lmp.png" alt="legible motion pictorial description" style="width: 100%; max-width: 900px; height: auto;">
  </div>
</div>

Two key learning-based methods for achieving legible motion are **reinforcement learning (RL)** and **imitation learning (IL)**:

* **Reinforcement Learning (RL)** uses a trial-and-error approach with rewards and penalties to teach robots optimal behaviors, allowing for adaptive and autonomous learning.
* **Imitation Learning (IL)** involves teaching robots by mimicking human demonstrations, aligning robotic actions with human-like patterns.

However, both methods have been applied largely ignoring the influence of the observer's viewpoint, which affects how clearly the robot's intent is communicated. The research aims to integrate viewpoint conditioning into these learning algorithms to improve the alignment of robotic behavior with human perception.

The project introduces:

* A universal planning architecture that incorporates both RL and IL for learned legibility.
* A new model of legible motion planning that considers the human viewpoint.
* Evaluations demonstrating the effectiveness of these approaches in real-world scenarios.

The goal is to enhance human-robot collaboration by making robotic actions more predictable and understandable.

## System Overview

![System Overview diagram](/images/IM_RL/xarm_overview.png){: width="900" height="675"}

We propose a universal learning-based architecture for legible motion planning that can be applied across both reinforcement learning (RL) and imitation learning (IL) setups, differing primarily in the policy learning pipeline. Our focus is on goal-reaching manipulation tasks where the robot must choose between two objects: a goal and a distraction. To ensure legibility, the robot's movements must be easily understandable and predictable by humans, indicating which object it aims to reach. Furthermore, the robot’s actions are adjusted based on the human’s perspective of the task environment, whether viewed from above or the side.

In our proposed framework, the policy—trainable via either imitation learning or reinforcement learning—generates legible motions that allow human collaborators to clearly grasp the robot's intent. At each time step, the policy receives inputs including the state of the robot, the goal, potential distractions that could confuse human collaborators, and the viewpoint of the human collaborators. It then predicts an action in the form of joint torques for the robot to execute. While our focus is on the planning side, all observations except the robot state are specified manually. In practical applications, these observations can be obtained from a perception module to facilitate full shared autonomy.

## Technical Approaches

### Reinforcement Learning-Based Approach

![Reinforcement learning approach](/images/IM_RL/xarm_rl.png){: width="900" height="675"}

<div style="display: flex; width: 100%; height: 100%;">
  <div style="flex: 1; padding: 10px;">
    <p>Simulation setup for RL with the xArm robot. We use Mujoco as
        the physics engine and interface it through Gym for learning algorithms. The
        blue, green and red dots represent the positions of the end effector, goal and
        distraction, respectively. In human evaluation, we create videos of the same
        setup with the side and the top view.</p>
  </div>
  <div style="flex: 1; padding: 10px; display: flex; align-items: center; justify-content: center;">
    <img src="/images/IM_RL/gym_sim_view.png" alt="Gym simulationn setup" style="width: 100%; max-width: 900px; height: auto;">
  </div>
</div>

### Imitation Learning-Based Approach

![Imitation Learning approach](/images/IM_RL/xarm_im.png){: width="900" height="675"}

<div style="display: flex; width: 100%; height: 100%;">
  <div style="flex: 1; padding: 10px;">
    <p>Toy experimental setup for testing IL model with the xArm robot. The
        setup shows a reaching task towards the object as goal while legibly avoid the
        red object as distraction. The model also accommodate to different viewpoint
        condition as we have the same set up with the top and the side view in human
        evaluation.</p>
  </div>
  <div style="flex: 1; padding: 10px; display: flex; align-items: center; justify-content: center;">
    <img src="/images/IM_RL/xarm_setup_view.png" alt="Experimental setup" style="width: 100%; max-width: 900px; height: auto;">
  </div>
</div>

## Results

### Reinforcement Learning Results

<div style="display: flex; justify-content: space-between; align-items: center; width: 100%;">
  <div style="flex: 1; padding: 10px;">
    <img src="/images/IM_RL/gym_sideview.gif" alt="gym_sideview" style="width: 100%; max-width: 800px; height: auto;">
    <p style="text-align: center; font-size: 0.7em; color: gray; margin-top: 0; margin-bottom: 10px;">Side view of reinforcement learning trajectory.</p>
  </div>
  <div style="flex: 1; padding: 10px;">
    <img src="/images/IM_RL/gym_topview.gif" alt="gym_topview" style="width: 100%; max-width: 800px; height: auto;">
    <p style="text-align: center; font-size: 0.7em; color: gray; margin-top: 0; margin-bottom: 10px;">Top view of reinforcement learning trajectory.</p>
  </div>
</div>

### Imitation Learning Results

<div style="display: flex; justify-content: space-between; align-items: center; width: 100%;">
  <div style="flex: 1; padding: 10px;">
    <img src="/images/IM_RL/xarm_sideview.gif" alt="xarm_sideview" style="width: 100%; max-width: 800px; height: auto;">
    <p style="text-align: center; font-size: 0.7em; color: gray; margin-top: 0; margin-bottom: 10px;">Side view of imitation learning legible trajectory.</p>
  </div>
  <div style="flex: 1; padding: 10px;">
    <img src="/images/IM_RL/xarm_topview.gif" alt="xarm topview" style="width: 100%; max-width: 800px; height: auto;">
    <p style="text-align: center; font-size: 0.7em; color: gray; margin-top: 0; margin-bottom: 10px;"> Top view of imitation learning legible trajectory.</p>
  </div>
</div>

### Evaluation

Since legibility refers to the ability to generate motion sequences that are easily understood by humans, creating a metric that accurately reflects human preferences is challenging. Therefore, it is essential to include human evaluation alongside the metrics used in our RL and IL training processes. A group of 10 participants was asked to watch all 8 videos, pausing when they believed they had identified the robot's intention, and then reporting which object they thought the robot was targeting. We developed a scoring system to balance these considerations.

<div style="text-align: justify;">
  <img src="/images/IM_RL/eval.png" alt="Evaluation bar graph">
  <p style="font-style: italic; font-size: 0.7em; color: gray;">Human-based evaluation results on the recorded legible motions. While IL-trained agent performed competitively well compared to the expert demonstrations, RL-trained one outperformed the others by 15%. Without proper viewpoint conditioning, RL-trained agent obtained a low score.</p>
</div>

<!-- ![Evaluation bar graph](/images/IM_RL/eval.png){: width="900" height="675"}

Human-based evaluation results on the recorded legible motions. While
our IL-trained agent performed competitively well compared to the expert
demonstrations, our RL-trained one outperformed the others by 15%. Without
proper viewpoint conditioning, RL-trained agent obtained a low score. -->

## Conclusion

* Accomplished goal-oriented tasks with legible motion plans considering observer’s viewpoint
* Evaluated two learning-based methods with humans and compared with expert baseline

## Future Work

* Bridge the gap between simulation and real world for RL.
* Integrate multi-modal sensory inputs for adaptive and dynamic legible motion.

## References

Read Full Report [Here](/files/ML_AI_Project_paper.pdf) !!!