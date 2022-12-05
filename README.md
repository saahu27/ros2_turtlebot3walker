[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
---

# TurtleBot3 Walker

## Overview 

Implementation of a simple walker algorithm where the TurtleBot3 moves in the world trying to avoid obstacles and collisions. 

## Assumptions
* OS: Ubuntu Linux Focal (20.04) 64-bit
* ROS2 Distro: Humble Hawksbill (built from source)
* ROS2 Workspace name: ros2_ws 
* ROS2 Installation Directory: ros2_humble

## ROS2 Dependencies
* ```ament_cmake```
* ```rclcpp```
* ```geometry_msgs```
* ```sensor_msgs```

### Environment Setup
```
. <path-to-ROS2-installation>/ros2_humble/install/local_setup.bash
```

### Clang
```
sudo apt install clang
export CC=clang
export CXX=clang++
colcon build --cmake-force-configure
```


## Build Instructions
```
cd <path-to-ROS2-workspace>/ros2_ws/src
git clone https://github.com/adarshmalapaka/turtlebot3_walker.git
cd ..  
rosdep install -i --from-path src --rosdistro humble -y
colcon build --packages-select turtlebot3_walker
```

## Run Instructions

### Simulation

In a terminal, navigate to your ROS2 workspace (```ros2_ws```) and source the setup files,
```
cd <path-to-ROS2-workspace>/ros2_ws
. install/setup.bash
ros2 launch turtlebot3_walker tb3_walker.launch.py
```
