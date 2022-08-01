---
layout: default
title: Robotic chamfering
description: Automate gear chamfering using a robot arm.
---

Keywords: robotic grinding; Iterative learning control (ILC); ROS

A UR5 robot arm is used for the proof of concept. 3D printed fixtures are designed to hold a Dremel tool. A rusty tube is mounted in the robot work cell and its location is found by using contact measurement. A force/torque sensor from [Robotiq](https://robotiq.com/) is used. 
<br/>
<center>
<img src="https://github.com/jhugj/web-repo/blob/main/images/tube-grinding-id.gif"/>
</center>
<br/>
Another approach to find the tube location is to use a [laser sensor](https://www.sick.com/us/en/) to scan a bounding box in the work cell to obtain a coarse location, followed by a more accurate contact measurement. 
<br/>
<center>
<img src="https://github.com/jhugj/web-repo/blob/main/images/tube-grinding-id-laser.gif"/>
</center>
<br/>
During grinding, the normal force $\small F_n$ should be regulated for both the safety of the system and obtaining good surface finish. Nominal robot trajectories for grinding are generated based on the tube geometry and location. Iterative Learning Control (ILC) is applied such that the normal force $\small F_n$ can be maintained at a constant level during grinding.
<br/>
<center>
<img src="https://github.com/jhugj/web-repo/blob/main/images/tube-grinding-force.png"/>
</center>
<br/>



[Back](https://jhugj.github.io/web-repo/)
