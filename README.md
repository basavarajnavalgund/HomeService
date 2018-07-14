
## References
This project utilizes the following ROS packages, cloned all of them on July 14, 2018.

[gmapping](http://wiki.ros.org/gmapping)
[turtlebot_teleop](http://wiki.ros.org/turtlebot_teleop)
[turtlebot_rviz_launchers](http://wiki.ros.org/turtlebot_rviz_launchers)
[turtlebot_gazebo](http://wiki.ros.org/turtlebot_gazebo)


## Package Tree
```
    ├──                                # Official ROS packages
    |
    ├── slam_gmapping                  # gmapping_demo.launch file
    │   ├── gmapping
    │   ├── ...
    ├── turtlebot                      # keyboard_teleop.launch file
    │   ├── turtlebot_teleop
    │   ├── ...
    ├── turtlebot_interactions         # view_navigation.launch file
    │   ├── turtlebot_rviz_launchers
    │   ├── ...
    ├── turtlebot_simulator            # turtlebot_world.launch file
    │   ├── turtlebot_gazebo
    │   ├── ...
    ├──                                # Your packages and direcotries
    |
    ├── World                          # world files
    │   ├── ...
    ├── ShellScripts                   # shell scripts files
    │   ├── ...
    ├──RvizConfig                      # rviz configuration files
    │   ├── ...
    ├──wall_follower                   # wall_follower C++ node
    │   ├── src/wall_follower.cpp
    │   ├── ...
    ├──pick_objects                    # pick_objects C++ node
    │   ├── src/pick_objects.cpp
    │   ├── ...
    ├──add_markers                     # add_marker C++ node
    │   ├── src/add_markers.cpp
    │   ├── ...
    └──
```
## Launch file
```
$ sudo apt-get install xterm
```

Create launch.sh file with the following content
```
#!/bin/sh
xterm  -e  " gazebo " &
sleep 5
xterm  -e  " source /opt/ros/kinetic/setup.bash; roscore" &
sleep 5
xterm  -e  " rosrun rviz rviz"
```

## Install Packages
```
TODO ADD $ EXCEPT #
$
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/src
catkin_init_workspace
cd ..
catkin_make
sudo apt-get update
cd ~/catkin_ws/src
git clone https://github.com/ros-perception/slam_gmapping
git clone https://github.com/turtlebot/turtlebot
git clone https://github.com/turtlebot/turtlebot_interactions
git clone https://github.com/turtlebot/turtlebot_simulator
cd ~/catkin_ws/
source devel/setup.bash
rosdep -i install gmapping
#All required rosdeps installed successfully
rosdep -i install turtlebot_teleop
#All required rosdeps installed successfully
rosdep -i install turtlebot_rviz_launchers
#All required rosdeps installed successfully
rosdep -i install turtlebot_gazebo
#All required rosdeps installed successfully
catkin_make
source devel/setup.bash
```

