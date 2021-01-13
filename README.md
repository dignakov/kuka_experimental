# Starting ROS2 Demo

## Install foxy version of ros2_control or check its sourc

## Checkout repositories
**Note**: you can use relese of the ros2_control repository

  ```
  git clone https://github.com/ros-controls/ros2_control.git
  ```

Checkout changed version of `JointTrajectoryController`
  ```
  git clone https://github.com/ros-controls/ros2_controllers.git
  cd ros2_controllers
  git remote add denis https://github.com/destogl/ros2_controllers.git
  git fetch denis
  git checkout denis/jtc_versions
  ```

Checkout changed version of ros2_demos repository
  ```
  git clone -b add_demo_nodes https://github.com/ros-controls/ros2_control_demos.git
  ```

Checkout KUKA demo driver and changed `kuka_experimental` repositories
  ```
  git clone https://github.com/dignakov/kuka_experimental.git
  git clone https://github.com/dignakov/ros2_control_demo_drivers.git
  ```
**Attention**: remove `ros2_control_abb_demo_driver` package for `ros2_control_demo_drivers` if needed.

Compile everything using:
  ```
  colcon build --symlink-install
  ```

## Starting Robot
1. In a terminal start ros2_control framework with KUKA RSI system hardware:
  ```
  ros2 launch kuka_kr5_support kr5_rsi.launch.py
  ```

2. In the second terminal start KUKA RSI simulator:
  ```
  ros2 run kuka_rsi_simulator kuka_rsi_simulator
  ```

3. In the third terminal start `rviz2`.
   And add RobotModel from the `/robot_description` topic.
   You can also just open rviz config from `kuka_kr5_support`/config/test_controllers.rviz

4. Follow the test case for one of the controllers.


### Test with ForwardCommandController (it will not work on the hardware if positions are not interpolated)
1. Load and start controllers:
  ```
  ros2 control load_start_controller joint_state_controller
  ros2 control load_start_controller forward_position_controller
  ```
2. Start a test node which sends commmands in a loop to the controller:
  ```
  ros2 launch kuka_kr5_support test_forward_position_controller.launch.py
  ```

### Test with JointTrajectoryController
1. Load and start controllers:
  ```
  ros2 control load_start_controller joint_state_controller
  ros2 control load_start_controller position_trajectory_controller
  ```

2. Start a test node which sends commmands in a loop to the controller:
  ```
  ros2 launch kuka_kr5_support test_position_trajectory_controller.launch.py
  ```

# Kuka experimental

[![Build Status](http://build.ros.org/job/Kdev__kuka_experimental__ubuntu_xenial_amd64/badge/icon)](http://build.ros.org/job/Kdev__kuka_experimental__ubuntu_xenial_amd64)

[![support level: community](https://img.shields.io/badge/support%20level-community-lightgray.png)](http://rosindustrial.org/news/2016/10/7/better-supporting-a-growing-ros-industrial-software-platform)

Experimental packages for Kuka manipulators within [ROS-Industrial][].
See the [ROS wiki][] page for more information.


## Contents

This repository contains packages that will be migrated to the [kuka][]
repository after they have received sufficient testing. The contents of 
these packages are subject to change, without prior notice. Any available 
APIs are to be considered unstable and are not guaranteed to be complete 
and / or functional.


[ROS-Industrial]: http://wiki.ros.org/Industrial
[ROS wiki]: http://wiki.ros.org/kuka_experimental
[kuka]: https://github.com/ros-industrial/kuka
