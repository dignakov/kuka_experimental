# WIP ros2_control Kuka Driver

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
