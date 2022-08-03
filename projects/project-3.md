---
layout: default
title: Robotic sanding
description: Automate sanding using a robot arm.
---

Keywords: robotic sanding; force/motion control; ROS

[Screw theory](https://en.wikipedia.org/wiki/Screw_theory) is used to find the robot end-effector pose in order to orient the sanding tool perpendicularly to the surface. Again, the force normal to the surface should be regulated at a constant level for both safety and surface finish quality reasons. The robot motion is decoupled so that both the force and motions can be controlled at the same time.<br/>

Checking the identified curvatures at the measured points.
<br/>
<center>
<img src="../images/freeform-pot.gif"/>
</center>
<br/>
Applying force/motion control after the curvature identification.
<br/>
<center>
<img src="../images/freeform-wood.gif"/>
</center>
<br/>