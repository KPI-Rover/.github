# KPI Rover

**An open mobile robot platform on ROS 2 for teaching and student projects at KPI.**

The platform builds a map of indoor spaces from lidar data, localizes itself on it and navigates autonomously with Nav2. The same software stack runs in Gazebo simulation and on the real robot, which has a Raspberry Pi 5 and a custom STM32 chassis controller. Students build their own applications on top of it, such as patrolling, object search or delivery, without having to deal with drivers or motor control.

## Repositories

| Repository | Purpose |
| --- | --- |
| [ros_sw](https://github.com/KPI-Rover/ros_sw) | ROS 2 Jazzy: robot model, ros2_control, localization, SLAM, navigation, simulation, Docker images |
| [ecu_hw](https://github.com/KPI-Rover/ecu_hw) | STM32 chassis controller PCB |
| [ecu_sw](https://github.com/KPI-Rover/ecu_sw) | Chassis controller firmware: motors, encoders, PID control, IMU |
| [ecu_pts](https://github.com/KPI-Rover/ecu_pts) | Test application for the ECU firmware |
| [rpi-power-hat](https://github.com/KPI-Rover/rpi-power-hat) | Raspberry Pi power board (6–40 V in, 5.1 V / 5 A out) |
| [chassis-cad](https://github.com/KPI-Rover/chassis-cad) | Chassis design |
| [KPI-Rover.github.io](https://github.com/KPI-Rover/KPI-Rover.github.io) | Project website and documentation |

## Quick start

The simulation runs in Docker on a regular PC with Linux or Windows (WSL2). Requirements and work with the real robot are described in [ros_sw](https://github.com/KPI-Rover/ros_sw).

```bash
git clone https://github.com/KPI-Rover/ros_sw.git
cd ros_sw
./rover.sh deps
./rover.sh pc
# inside the container:
colcon build --symlink-install
source install/setup.bash
ros2 launch kpi_rover_bringup sim.launch.py
```
