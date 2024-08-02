# Hadi-ROS-W4-Task-1
We've got movement.
## Installing dependencies.
We start [Here](https://emanual.robotis.com/docs/en/platform/turtlebot3/quick-start/), and for our purposes we'll choose the noetic version, <br />
and by following step 1.1.3 we can get all our dependencies installed swiftly. <br />
```
sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
ros-noetic-rgbd-launch ros-noetic-rosserial-arduino \
ros-noetic-rosserial-python ros-noetic-rosserial-client \
ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
ros-noetic-compressed-image-transport ros-noetic-rqt* ros-noetic-rviz \
ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers
```
 <br />
and we install TurtleBot3 in step 1.1.4 <br />

```
sudo apt install ros-noetic-dynamixel-sdk
sudo apt install ros-noetic-turtlebot3-msgs
sudo apt install ros-noetic-turtlebot3
```
 <br />
 
We then clone this [repository](https://github.com/ROBOTIS-GIT) into our source folder in the catkin work space <br />

```git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3.git```

```git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations```

```catkin_make```

## Running the simulation.
To start it using gazebo we use <br />

```export TURTLEBOT3_MODEL=burger```

```roslaunch turtlebot3_gazebo turtlebot3_world.launch```

and ```export TURTLEBOT3_MODEL=burger``` ```roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch``` on a new terminal for controls. <br />
![Screenshot](https://github.com/user-attachments/assets/999fde82-4206-4d5a-9cf5-18f468b03bb2)

## Mapping.
To start the mapping program using RViz 

```export TURTLEBOT3_MODEL=burger``` 

```roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping```

![Screenshot](https://github.com/user-attachments/assets/55835d93-a470-4ecb-9303-dd56f43f1982)

and to save the newly scanned environment ```rosrun map_server map_saver -f ~/whatever-you-like``` and voilà. <br />
![Screenshot](https://github.com/user-attachments/assets/96182e17-b321-486a-a614-10523e5a9fea)

## Navigation.
and finally to start navigation we use

```export TURTLEBOT3_MODEL=burger``` 

```roslaunch turtlebot3_navigation turtlebot3_navigation.launch map_file:=$HOME/whatever-you-like.yaml```
![Screenshot](https://github.com/user-attachments/assets/486b34de-5593-4210-91d7-48e1b103f9f2)
