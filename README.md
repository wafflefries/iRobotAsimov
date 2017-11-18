# iRobotAsimov
## iRobot Roomba Controls Development
This project aims to provide a simple method to control the iRobot Create® 2 Programmable Robot. This is done through ROS on Ubuntu Mate, running on Raspberry Pi 3. The scripts in the 'ros' directory have been tested to work on ROS Kinetic.

## 1: Install Ubuntu Mate For Raspberry Pi
Download and installation instructions can be found here: [https://ubuntu-mate.org/raspberry-pi/](https://ubuntu-mate.org/raspberry-pi/). 

## 2: Install ROS Kinetic For armhf Architecture
Installation instructions can be found here: [http://wiki.ros.org/kinetic/Installation/Ubuntu](http://wiki.ros.org/kinetic/Installation/Ubuntu).

## 3: Install pyCreate2 Library
Installation and application instructions can be found here: [https://pypi.python.org/pypi/pycreate2/0.7.3](https://pypi.python.org/pypi/pycreate2/0.7.3).

## 4: Install Git
Enter the following into a terminal(you may need to enter a password):
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install git
```
## 4: Working With ROS
### Create Workspace
Creates a workspace called 'robot' in the home directory:
```
mkdir -p ~/robot/src 
cd ~/robot
catkin_init_workspace
catkin_make
source devel/setup.bash
```
### Create a Publisher Package
Creates a package called "pub_sensors":
```
cd ~/robot/src
catkin_create_pkg pub_sensors rospy
```
### Clone "pub_sensors.py"
Grabs the pub_sensors.py file from github, place it in the pub_sensors/src directory, and make it excutable:
```
cd ~/robot/src/pub_sensor/src
curl -o pub_sensors.py https://raw.githubusercontent.com/wafflefries/iRobotAsimov/master/ros/pub_sensors.py
```
### Create a Subscriber Package
Creates a package called "sub_wheels":
```
cd ~/robot/src
catkin_create_pkg sub_wheels rospy
```
