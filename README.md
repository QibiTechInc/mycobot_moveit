# mycobot_moveit
Unofficial myCobot moveit repositiry to be run on the local raspberry Pi for myCobot Pi 

This is a forked project of what is developed [here](https://github.com/nisshan-x/mycobot_moveit) to make myCobot Pi work with MoveIt

# Environment
| item |  |
|---|---|
| OS | Ubuntu 18.04 |
| ROS | melodic/Noetic |
| Arm Robot | myCobot Pi |

# Preparation
1. Install Moveit in your local computer, for example for ros melodic:
  ```bash
  sudo apt-get install ros-melodic-moveit
  ```

2. clone the pkg into your local catkin workspace (use the branch pc-pkg)
  ```bash
    git clone -b  mycobot-pi https://github.com/QibiTechInc/mycobot_ros.git
    git clone -b pc-pkg https://github.com/QibiTechInc/mycobot_moveit.git
  ```
3. On the rpi clone the following repositories
  ```bash
    git clone -b  mycobot-pi https://github.com/QibiTechInc/mycobot_ros.git
    git clone -b rpi-pkg  https://github.com/QibiTechInc/mycobot_moveit.git
  ```
4. build your local workspaces (catkin_make)
5. Make sure that both the rpi and the PC are in the same network and they can see each other. 
  * use the command `hostname -I` to get the IP of your local machine, and by using the command `ping THE_OTHER_MACHINE_IP` make sure that your local machines have access to each other. 
  * On the PC run:
    ```bash
    export ROS_MASTER_URI=http://PC_IP_ADDRESS:11311
    export ROS_IP=PC_IP_ADDRESS        
    ```
    Note that here PC_IP_ADDRESS is the address that you have received from `hostname -I` command
  * On the rpi run:
    ```bash
    export ROS_MASTER_URI=http://PC_IP_ADDRESS:11311
    export ROS_IP=RPI_IP_ADDRESS        
    ```
    Now you can run roscore on your PC, and the rpi should be able to launch any node without having roscore.
# Usage
Make sure both the PC and the rpi are running under the same ROS master. 
First on rpi lunch:
```bash
roslaunch mycobot_moveit mycobot_rpi_control_v2.launch
```
On the PC launch: 
```bash
roslaunch mycobot_moveit mycobot_moveit_control_master_v2.launch
```

You can use MoveIt on your PC now!

https://user-images.githubusercontent.com/35629121/144708609-14c3878b-ed23-47bf-9bdd-18927d8877e1.mp4

# License
This software is released under the MIT License, see LICENSE.txt.
