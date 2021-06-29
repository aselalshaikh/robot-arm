#task1 
# Robot-arm
To control the robot's arm ROS meldoic version 1.14.11 should be download and the steps shown below for installation ROS on ubuntu 18.04.5 

## Install ROS melodic 
- before doing these steps you should download ubuntu 18.04.5 https://releases.ubuntu.com/18.04/
 
### 1.1 Configure Ubuntu repositories ( restricted,universe,and multiverse )
``` 
$ sudo add-apt-repository restricted
$ sudo add-apt-repository universe
$ sudo add-apt-repository multiverse
```

### 1.2 Setup the sources.list
``` 
$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'

``` 

### 1.3 Set the keys
```
$ curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

### 1.4 Check if the Debian package index is up-to-date:
```
$ sudo apt update
```
    Desktop-Full Installation command
```
$ sudo apt install ros-melodic-desktop-full
```

### 1.5 ROS environment variables are automatically added to your bash session every time a new shell is launched
```
$ echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
```

### 1.6 Install and initialize system dependencies in ROS
```
$ sudo apt install python-rosdep
$ sudo rosdep init
$ rosdep update
```

To test your installation
```
$ roscore
```

# Preparing ROS

### 1.1  Setup the workspace where ROS projects are built and stored
 ```
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/
$ catkin_make
```

### 1.2 Adding ardino robot arm package
```
$ cd ~/catkin_ws/src
$ sudo apt install git
$ git clone https://github.com/smart-methods/arduino_robot_arm 
$ cd ~/catkin_ws
$ rosdep install --from-paths src --ignore-src -r -y
$ sudo apt-get install ros-melodic-moveit
$ sudo apt-get install ros-melodic-joint-state-publisher ros-melodic-joint-state-publisher-gui
$ sudo apt-get install ros-melodic-gazebo-ros-control joint-state-publisher
$ sudo apt-get install ros-melodic-ros-controllers ros-melodic-ros-control
$ catkin_make
$ roslaunch robot_arm_pkg check_motors.launch
```
