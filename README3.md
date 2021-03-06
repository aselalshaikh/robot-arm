task 2
# Turtlebot3
To create map using Turtlebot3 with SLAM approach using commands to install TurtleBot3 in this website https://www.theconstructsim.com/
- install ubuntu and ROS on PC with these commands
```
$ sudo apt update
$ sudo apt upgrade
$ wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_melodic.sh
$ chmod 755 ./install_ros_melodic.sh
$ bash ./install_ros_melodic.sh
$ sudo apt-get install ros-melodic-joy ros-melodic-teleop-twist-joy
$ ros-melodic-teleop-twist-keyboard ros-melodic-laser-proc
$ ros-melodic-rgbd-launch ros-melodic-depthimage-to-laserscan
$ ros-melodic-rosserial-arduino ros-melodic-rosserial-python
$ ros-melodic-rosserial-server ros-melodic-rosserial-client
$ ros-melodic-rosserial-msgs ros-melodic-amcl ros-melodic-map-server
$ ros-melodic-move-base ros-melodic-urdf ros-melodic-xacro
$ ros-melodic-compressed-image-transport ros-melodic-rqt*
$ ros-melodic-gmapping ros-melodic-navigation ros-melodic-interactive-markers
```
## Install TurtleBot3 Packages

```
$ sudo apt-get install ros-melodic-dynamixel-sdk
$ sudo apt-get install ros-melodic-turtlebot3-msgs
$ sudo apt-get install ros-melodic-turtlebot3
```
## Set TurtleBot3 Model Name
### TurtleBot3 Burger:
```
$ echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
```
### TurtleBot3 Waffle Pi:
```
$ echo "export TURTLEBOT3_MODEL=waffle_pi" >> ~/.bashrc
```
### Connect PC to a WiFi:
```
$ ifconfig
$ source ~/.bashrc
```
## Gazebo Simulation
```
$ cd ~/catkin_ws/src/
$ git clone -b melodic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
$ cd ~/catkin_ws
$ catkin_make
````
## Launch Simulation 

### TurtleBot3 World
```
$ export TURTLEBOT3_MODEL=waffle
$ roslaunch turtlebot3_gazebo turtlebot3_world.launch
```
![R1](https://user-images.githubusercontent.com/85528449/125207183-8e46b300-e293-11eb-8581-8e488ee032a1.png)

### SLAM Simulation
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```
#### Run SLAM Node
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapp
```
#### Run Teleoperation Node
```
$ export TURTLEBOT3_MODEL=burger
$ roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
![R2](https://user-images.githubusercontent.com/85528449/125207067-ecbf6180-e292-11eb-8922-7d17d04262ea.png)
To complete all the map move the robot by using (a,w,d,x,s)
![R3](https://user-images.githubusercontent.com/85528449/125207079-f2b54280-e292-11eb-970d-c7d6e57841e9.png)
![image](https://user-images.githubusercontent.com/85528449/125347978-4e033580-e364-11eb-883c-10d440858fad.png)


## Save Map
```
$ rosrun map_server map_saver -f ~/map
```
![r5](https://user-images.githubusercontent.com/85528449/125348218-9cb0cf80-e364-11eb-94f8-d1763cd1f079.png)
