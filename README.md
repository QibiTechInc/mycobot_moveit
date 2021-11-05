# mycobot_moveit
Unofficial myCobot moveit repositiry to be run on a local pc for myCobot Pi 

# Environment
| item |  |
|---|---|
| OS | Ubuntu 18.04 |
| ROS | melodic |
| Arm Robot | myCobot Pi |

# Preparation
1. Install Moveit in your lacal computer, for example for ros melodic:
  ```bash
  sudo apt-get install ros-melodic-moveit
  ```

2. clone the pkg into your local catkin workspace (use the branch pc-pkg)
  ```bash
  git clone -b pc-pkg https://github.com/QibiTechInc/mycobot_moveit.git
  ```
3. On the rpi clone the following repositories
  ```bash
  git clone -b rpi-pkg https://github.com/QibiTechInc/mycobot_moveit.git
  git cloen -b mycobot-pi https://github.com/QibiTechInc/mycobot_ros.git
  ```
4. build your local workspaces (catkin_make)
# Usage
Make sure both the PC and the rpi are running under the same ROS master. 
First on rpi lunch:
`roslaunch mycobot_moveit mycobot_rpi_control_v2.launch`

On the PC lunch: 
`roslaunch mycobot_moveit mycobot_moveit_control_master_v2.launch`

# License
This software is released under the MIT License, see LICENSE.txt.
