# H-OBCA
Hierarchical Optimization-Based Collision Avoidance - An algorithm for generating dynamically feasible parking trajectories 
Paper describing the theory can be found [here](http://arxiv.org/abs/1711.03449).

## How to run the Parking code:

### Prepare Julia Environment

1. Install Julia from https://julialang.org/downloads/ (code tested on version 0.5.1 and 0.6.0) I use Julia-0.6.4 version,which can install the Packages successfully.
2. Open Julia in terminal
3. Change to the directory: cd("C:\\\Users\\\Administrator\\\Desktop\\\OBCA-master\\\AutonomousParking")
4. Install Julia package JuMP using Pkg.add("JuMP")
5. Install Julia package Ipopt using Pkg.add("Ipopt")
6. Install Julia package PyPlot using Pkg.add("PyPlot")
7. Install Julia package NearestNeighbors using Pkg.add("NearestNeighbors")
8. Install Julia package ControlSystems using Pkg.add("ControlSystems")

### Running the parking example 

1. Start Julia in terminal
2. Delete 'hold(1)' and 'hold(0)' in plotTraj.jl, because it's obsolete in new Pyplot.
2. Type in terminal: include("setup.jl")
3. Type in terminal: include("main.jl")

### modifying the code 

1. To play with start points, change x0 in main.jl and run the code by: include("main.jl")
2. If you change anything in one of the collision avoidance problems, you need to activate the changes by running:
include("setup.jl")
3. If you change the size of the car in main.jl, the change also need to be made in collision_check.jl

## 关于初始化

我尝试了几种情况：

1. 不使用混合A星，直接用Reeds-shepp曲线初始化，即初始路径不考虑障碍物，结果是优化后的路径与障碍物碰撞。不管是否把目标函数中的最后一项（与初始路径的距离）去掉都不行。

2. 使用混合A星，但是把目标函数中的最后一项去掉（与初始路径的距离），结果是优化后的路径不与障碍物碰撞，但是运动距离变长。






