---
date: 2021-01-05 05:20:35 +0300
title: Multi-Agent Path Finding
subtitle: Planning and Decision Making
image: '/images/MAPF/cover_multi_robot.jpg'
---
<p style="text-align: center; font-size: 0.7em; color: gray; margin-top: 0; margin-bottom: 40px;">Source: Image generated using DALL·E</p>

Multi-agent path finding (MAPF) is an NP-hard problem with practical applications in areas like surveillance, search and rescue, and warehouse logistics. In one-shot MAPF, the goal is to compute collision-free paths for agents from their starting positions to target locations while minimizing a predefined objective, such as makespan or path length. Lifelong multi-agent pathfinding (LMAPF) extends this by requiring agents to continuously adapt to new goals and replan paths dynamically, increasing complexity, especially in dense environments. Conflict-Based Search (CBS) algorithm addresses these challenges by using a two-level approach: a high-level Conflict Tree tracks agent conflicts, while a low-level single-agent search resolves constraints. This project implemented a lifelong variant of CBS in a small-scale environment, inspired by the League of Robot Runners competition by Amazon Robotics.

## Problem statement

Given a 4 connected Grid, N-agents are trying to maximize task completion under time constraint while avoiding path conflict.

![MAPF problem statement](/images/MAPF/MAPF_problem_statement.svg){: width="900" height="675"}
<!-- *Source: M. Daman et. al., "PRIMAL_2: Pathfinding Via Reinforcement and Imitation Multi-Agent Learning - Lifelong."* -->
<p style="text-align: center; font-size: 0.7em; color: gray; margin-top: 0; margin-bottom: 40px;">Source: M. Daman et. al., "PRIMAL_2: Pathfinding Via Reinforcement and Imitation Multi-Agent Learning - Lifelong."</p>

Our robot can move forward, or rotate 90 degrees at one location. This means that our action, state
and goal variables are as follows:

![MAPF variables](/images/MAPF/MAPF_variables.svg){: width="900" height="675"}

Our planner algorithm will generate paths that will cause conflict. In our case we will consider two types of conflicts, which are edge and vertex conflicts.

## Planning Algorithm: Conflict Based Search

Conflict Based Search (CBS) is a two-level algorithm that diverges from converting the problem into a single ’joint agent’ model. Instead, it adopts a distinctive approach where, at the high level, a search is conducted on a Conflict Tree. This tree is structured based on conflicts between individual agents, with each node in the CT representing a set of constraints on the agent's motion. Simultaneously, at the low level, swift single-agent searches are executed to find new paths as to fulfill the constraints dictated by the high-level CT node. The unique two-level formulation of CBS often results in the examination of fewer states compared to A*, all while maintaining optimality in many cases.

![MAPF BT image](/images/MAPF/MAPF_binary_tree.svg){: width="900" height="675"}

## Pseudo Code

The pseudo code for life-long MAPF and CBS function is given below.

![MAPF pseudo code lifelong](/images/MAPF/MAPF_pseudo_lifelong.svg){: width="550" height="400"}

![MAPF_pseudo CBS function](/images/MAPF/MAPF_pseudo_CBS.svg){: width="550" height="400"}

## Demostration Video

To visualize we used an open source tool called [PlanViz](https://github.com/MAPF-Competition/PlanViz). The video below shows the demonstration of the life-long CBS algorithm in action.

![MAPF video](/images/MAPF/Planviz.gif){: width="800"}

## Results

The results of the CBS algorithm are shown below. The algorithm was able to find the optimal paths for the agents in the given environment.

![MAPF results](/images/MAPF/MAPF_results.svg){: width="900" height="675"}

## Conclusion

The results show that in a larger map (33x57 cells) with more agents (25), task completion was higher (3666 tasks) but at the cost of increased computational time (72.722 seconds) and more CBS calls. In contrast, a smaller map (32x32 cells) with fewer agents (20) led to fewer tasks completed (3416) but required less time (70.821 seconds) and fewer CBS calls (2492). The algorithm performed more efficiently in the smaller, organized warehouse environment, where structured paths reduced tree size during planning, leading to faster, more optimal solutions. In contrast, the larger, more complex environment required more CBS calls and time to find optimal paths, highlighting the trade-off between task completion and computational efficiency.

## Future Work

* Implementing Improved Conflict Based Search (ICBS)
* Implementing Explicit Estimation Conflict-Based Search (EECBS)
* Scaling of existing pipeline for solving more than 10k agents

## References

Read Full Report [HERE](/files/planning_project_paper.pdf)
and find the code [GITHUB](https://github.com/PrakritTyagi/MAPF) !!!
