---
layout: default
title: Optimization
description: Several optimization problems in robot perception
---

Keywords: Convex optimization; Mixted-integer programming; McCormick relaxation; Julia

<h3>
  Point cloud registration - find the correspondence
</h3>

One problem in the previous NBV for pose estimation project is to find the transformation matrix between two point clouds, i.e., point cloud registration. For objects with planar features, one way to calculate such a transformation matrix is to first find the correspondences between the planes in the measured point cloud and the planes in the CAD model point cloud. The key optimization techniques are:
1. Relax the rotation matrix constraint $\small \mathbf{R}\in \text{SO}(3)$ using the convex hull of rotation matrices
2. Lift the multiplications of integer variables and contineous variables using the McCormick relaxation
3. Solve the mixed-integer convex problem using solver [Pajarito](https://github.com/JuliaOpt/Pajarito.jl)

Details of the problem formulation can be found in [this paper](https://github.com/jhugj/jhugj.github.io/blob/da4930c33be3e7253ecc1f5662f5cb04a50fc574/files/Hu2021CDC.pdf).

<h3>
  View planning - find optimal sensor views
</h3>

Again, mixed-integer programming is very useful in finding the optimal sensor views for data collection. The key takeaways are:
1. Solver [Alpine](https://github.com/lanl-ansi/Alpine.jl) is able to find the global optimal solutions for mixed-integer nonlinear programming problems.
2. [Pyomo](http://www.pyomo.org/) has [Mixed-Integer Nonlinear Decomposition Toolbox](https://pyomo.readthedocs.io/en/stable/contributed_packages/mindtpy.html), but the performance depends on the problem formulations, and sometimes the global optimal may not be obtainable. McCormick relaxation is used to better formulate my problem in order to find the global optimal solutions.  


<h2>
  The assignment problem - find the correspondence
</h2>
Keywords: the assignment problem; linear programming

Another approach to find the correspondence in point cloud registration is to formulate an [assignment problem](https://en.wikipedia.org/wiki/Assignment_problem), which can be solved through [linear programming](https://en.wikipedia.org/wiki/Linear_programming). There are available solvers, such as the one from [scipy](https://docs.scipy.org/doc/scipy/reference/generated/scipy.optimize.linear_sum_assignment.html).

Details of the problem formulation can be found in [this paper](https://github.com/jhugj/jhugj.github.io/blob/da4930c33be3e7253ecc1f5662f5cb04a50fc574/files/Hu2021AIM.pdf).

<h2>
  The set cover problem - find minimum number of views
</h2>
Keywords: the set cover problem; view planning

Sometimes we need to determine how many sensor views are enough to collect point clouds. And the problem can be formulated as a [set cover problem](https://en.wikipedia.org/wiki/Set_cover_problem). The determination of the subsets, the universe can be problem specific. The constraints from the hardware can be used to form such subsets and universe.

<h2>
  Nonlinear programming - solve the inverse kinematics
</h2>
Keywords: nonlinear programming; inverse kinematics

A common, fundamental problem in almost all my previous projects is to solve the robot [inverse kinematics](https://en.wikipedia.org/wiki/Inverse_kinematics) given the target robot end-effector pose. For the robot perception problem that I'm studying, there are many constraints that a certain robot pose has to satisfy, such as the field-of-view, field-of-distance constraints of the vision sensor. Thus formulating a constrained [nonlinear optimization](https://en.wikipedia.org/wiki/Nonlinear_programming) problem and solve it for the robot joint angles fits the purpose very well. Even though the local minimum could potentially be an issue.

[Back to main](https://jhugj.github.io/web-repo/)