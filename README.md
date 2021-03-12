# WIP ros2_control support

ported:

- kr6_support
- kuka_resources
- kuka_rsi_hw_interface
- kuka_rsi_simulator

# ros2_control Kuka Driver

## Dependencies:

- https://github.com/dignakov/kuka_experimental

## Compiling:

Please follow the directions here https://github.com/ros-controls/ros2_control_demos to set up ros2_control, ros2_controllers, and ros2_control_demos.

## Kuka Driver:

The minimal ros2 fork of kuka_experimental has a, somewhat rough, adaptation of the RSI simulator. It can be used to test the driver by callig:

```
ros2 run kuka_rsi_simulator kuka_rsi_simulator
```

In combination with launching the robot hardware (see https://github.com/ros-controls/ros2_control_demos for details on starting the driver).

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
