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

## 5: Working With ROS
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
cd ~/robot/src/pub_sensors/src
curl -o pub_sensors.py https://raw.githubusercontent.com/wafflefries/iRobotAsimov/master/ros/pub_sensors.py
sudo chmod u+x pub_sensors.py
```
### Create a Subscriber Package
Creates a package called "sub_wheels":
```
cd ~/robot/src
catkin_create_pkg sub_wheels rospy
```
### Clone "sub_wheels.py"
Grabs the sub_wheels.py file from github, place it in the sub_wheels/src directory, and make it excutable:
```
cd ~/robot/src/sub_wheels/src
curl -o sub_wheels.py https://raw.githubusercontent.com/wafflefries/iRobotAsimov/master/ros/sub_wheels.py
sudo chmod u+x sub_wheels.py
```
### Connect the Raspberry Pi to the Roomba
Connect the Raspberry Pi to the Roomba using the serial cable.

### Run ROS
```
cd ~/robot
catkin_make
source devel/setup.bash
roscore
```
### Run Publisher
Open a second terminal/session and paste the following:
```
cd ~/robot
source devel/setup.bash
rosrun pub_sensors pub_sensors.py
```
### Run Subscriber
Open a third terminal/session and paste the following:
```
cd ~/robot
source devel/setup.bash
rosrun sub_wheels sub_wheels.py
```
