---
layout: default
title: Robotic chamfering
description: Automate gear chamfering using a robot arm.
---

## Gear chamfering

## Challenges

## Hybrid motion-force control

Keywords: robotic chamfering; robotic deburring; force/motion control; ROS

To control the amount of material being removed, hybrid force/motion control is used to obtain the exact locations of the gear teeth. Force/torque sensor from [ATI](https://www.ati-ia.com/) is used.
<br/>
<center>
<img src="/images/rootID.gif" width="480" height="270"/>
</center>
<br/>
Dual-edge chamfering: using abrasives to chamfer two edges simultaneously. The following is an external gear from ITAMCO. The robot end-effector is a pneumatic tool from ATI that has axial compliance.
<br/>
<center>
<img src="/images/part-chamfering.gif" width="480" height="270"/>
</center>
<br/>
Deburring is necessary after chamfering to remove sharp edges.
<br/>
<center>
<img src="/images/part-deburring.gif" width="480" height="270"/>
</center>
<br/>
Tool changing is automated to switch between different end-effectors for different tasks. The pneumatic tool changer is from ATI. The tool changing process includes the control of the compressed air valves and the control of the robot motion. A [microcontroller](https://beagleboard.org) is used to control the open and close of the valves. And the robot motion control and the valve control are synchronized in [ROS](https://www.ros.org/). 
<br/>
<center>
<img src="/images/toolChange.gif" width="480" height="270"/>
</center>
<br/>
The same chamfering approach is implemented on an internal gear.
<br/>
<center>
<img src="/images/part-chamfering-outside.gif" width="480" height="270"/>
</center>
<br/>
Space is contrained when operating the robot inside of the internal gear. Our partner from USC did the trajectory planning and obstacle avoidance checking. The abrasives used here have different geometries due to the change of chamfering trajectory.
<br/>
<center>
<img src="/images/part-chamfering-inside.gif" width="480" height="270"/>
</center>
<br/>
Deburring the inside of the internal gear.
<br/>
<center>
<img src="/images/deburringInside.gif" width="480" height="270"/>
</center>
<br/>
Developed a compressed air control module for the power tools using: electric solenoid valves, microcontroller, compressed air filter, etc.
<br/>
<center>
<img src="/images/compressedAirRegulator.png" width="480" height="270"/>
</center>
<br/>


[Back](https://jhugj.github.io/web-repo/)
