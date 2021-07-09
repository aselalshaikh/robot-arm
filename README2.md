#task1 
# robot-arm
This project will use ROS to create robot arm
Here is the second method to use ROS if ubuntu did not work with using a website https://www.theconstructsim.com
# Steps
## 1- Creating acount
## 2- click on ( My projects → Create a new project )
## 3- open a Shell web 
( first icon in the left of the screen )
### To installing the package arduino_robot_arm write these commands:
```
$ cd ~/catkin_ws/src
$ sudo apt install git
$ git clone https://github.com/smart-methods/arduino_robot_arm 
$ cd ~/catkin_ws
```
### Install all the dependencies
To run the packge these commands will use
```
$ rosdep install --from-paths src --ignore-src -r -y
$ sudo apt-get install ros-melodic-moveit
$ sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui
$ sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher
$ sudo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control
$ roslaunch robot_arm_pkg check_motors.launch
```
To see the robot arm click on graphicak tool
![t1 robot arm](https://user-images.githubusercontent.com/85528449/125073508-be8c2700-e0c4-11eb-94fa-22dc5374d331.png)

### Simulate the motors
open a new shell web to write these commands to simulate the arm on Gazebo and Rvis
#### Gazebo
```
$ roslaunch robot_arm_pkg check_motors.launch
$ roslaunch robot_arm_pkg check_motors_gazebo.launch
$ rosrun robot_arm_pkg joint_states_to_gazebo.py
```
#### Rvis
```
$ roslaunch moveit_pkg demo.launch
```

![rvis](https://user-images.githubusercontent.com/85528449/125081466-b507bc80-e0ce-11eb-8c29-be8236d05b52.png)


