[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
---

# TurtleBot3 Walker

## Overview 

Implementation of a simple turtlebot to move in the world trying to avoid obstacles. 

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
* ```turtlebot3```
* ```gazebo```
* ```turtlebot3_simulations```
* ```turtlebot3_msgs```
* ```dynamixel-sdk```

---

## Build Instructions
```
cd <path-to-ROS2-workspace>/ros2_ws/src
git clone 
cd ..  
rosdep install -i --from-path src --rosdistro humble -y
colcon build --packages-select turtlebot3_walker
```
---
## Run Instructions

### Simulation

In a terminal, navigate to your ROS2 workspace (```ros2_ws```) and source the setup files,
```
cd <path-to-ROS2-workspace>/ros2_ws
. install/setup.bash
export TURTLEBOT3_MODEL=waffle_pi
export GAZEBO_MODEL_PATH=$GAZEBO_MODEL_PATH:`ros2 pkg prefix turtlebot3_gazebo `/share/turtlebot3_gazebo/models/
ros2 launch turtlebot3_walker tb3_walker.launch.py
```
To run :
```
ros2 run turtlebot3_walker walker
```

To play ros bag
```
ros2 bag play walker_bag
```
---
Results
cpplint

Change to the root directory of the package, /turtlebot3_walker, and run:
```
cpplint --filter=-build/c++11,+build/c++17,-build/namespaces,-build/include_order ./src/*.cpp ./include/turtlebot3_walker/*.hpp > ./results/cpplint.txt
```
The results of running cpplint can be found in /results/cpplint.txt.
cppcheck

Change to the root directory of the package, /turtlebot3_walker, and run:
```
cppcheck --enable=all --std=c++17 ./src/*.cpp ./include/turtlebot3_walker/*.hpp --suppress=missingIncludeSystem --suppress=unmatchedSuppression --suppress=unusedFunction --suppress=missingInclude --suppress=useInitializationList > results/cppcheck.txt
```
The results of running cppcheck can be found in /results/cppcheck.txt.
