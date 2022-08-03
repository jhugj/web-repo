---
layout: default
title: Next-best-view for object pose estimation
description: Finding the next-best-view to collect data for object pose estimation
---
Keywords: next-best-view; point cloud processing; object pose estimation; robot perception

There are several key components in finding the NBVs: 
1. Processing the point clouds, including segmentation, normal estimation, registration, etc.
2. Finding information rich view directions: which directions are better for object pose estimation?
3. Evaluting the robot workspace: which regions have [inverse kinematics](https://en.wikipedia.org/wiki/Inverse_kinematics) solutions?
4. Finding the NBV: the view that brings the most information for object pose estimation while being feasible to the robot

The following is an examples of the NBV process.
<br/>
<center>
<img src="../images/robot-perception-opt.gif"/>
</center>
<br/>
The point cloud processing here uses a combination of the Point Cloud Library ([PCL](https://pointclouds.org/)) and [Open3D](http://www.open3d.org/). Simulation and visualization are done in ROS, implemented on a UR5 with a Ensenso camera [N35](https://www.optonic.com/en/products/ensenso/n30-n35/).