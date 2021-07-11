task 2
# Turtlebot
To create map using Turtlebot3 with SLAM approach 
## Install TurtleBot3 Packages
Using this commands to install TurtleBot3 in this website https://www.theconstructsim.com/
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

## Save Map
```
$ rosrun map_server map_saver -f ~/map
```
