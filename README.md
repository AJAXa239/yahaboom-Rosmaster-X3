# Yahboom ROSMASTER X3
 
ROS 2 package for the Yahboom ROSMASTER X3 mobile robot, featuring autonomous navigation with SLAM, Nav2, and AprilTag-based docking.
 
## Overview
# Docking
[!image](Slam.gif)
 
This project integrates:
- **SLAM** — real-time mapping of the environment
- **Nav2** — autonomous path planning and navigation
- **AprilTag Detection** — fiducial marker detection for precise docking
## Requirements
 
- ROS 2 (Humble/Jazzy)
- Yahboom ROSMASTER X3 hardware
- Nav2 stack
- `apriltag_ros` (or equivalent AprilTag detection package)
- SLAM toolbox (e.g., `slam_toolbox`)
## Package Structure
 
```
yahboom_rosmaster/
├── config/          # Navigation, SLAM, and sensor config files
├── launch/          # Launch files for bringup, SLAM, and Nav2
├── maps/            # Saved maps
├── src/             # Source code
├── urdf/            # Robot description files
└── README.md
```
 
## Setup
 
Clone into your ROS 2 workspace `src` directory:
 
```bash
cd ~/ros2_ws/src
git clone https://github.com/AJAXa239/yahaboom-Rosmaster-X3.git yahboom_rosmaster
```
 
Build the workspace:
 
```bash
cd ~/ros2_ws
colcon build --packages-select yahboom_rosmaster
source install/setup.bash
```
 
## Quick Start (Aliases)
 
For convenience, add these aliases to your `~/.bashrc`:
 
```bash
alias yahboom='ros2 launch urdf_tutorial display.launch.py model:=/home/ajaybisht/ros2_ws/src/yahboom_rosmaster/yahboom_rosmaster_description/urdf/robots/rosmaster_x3.urdf.xacro'
alias robot='bash ~/ros2_ws/src/mycobot_ros2/mycobot_bringup/scripts/mycobot_280_gazebo.sh'
alias x3='bash ~/ros2_ws/src/yahboom_rosmaster/yahboom_rosmaster_bringup/scripts/rosmaster_x3_gazebo.sh'
alias nav='bash ~/ros2_ws/src/yahboom_rosmaster/yahboom_rosmaster_bringup/scripts/rosmaster_x3_navigation.sh'
```
 
Then reload with `source ~/.bashrc`.
 
| Alias     | Description                                      |
|-----------|---------------------------------------------------|
| `yahboom` | Visualize the URDF in RViz via `urdf_tutorial`     |
| `robot`   | Launch myCobot 280 in Gazebo                       |
| `x3`      | Launch ROSMASTER X3 in Gazebo                      |
| `nav`     | Launch ROSMASTER X3 Nav2 navigation stack           |
 
## Status
 
🚧 Under active development.
 
