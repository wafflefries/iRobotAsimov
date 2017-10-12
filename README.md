# iRobotAsimov
iRobot Roomba Controls Development

roombaCtrl.slx contains the library blocks for the Roomba range sensors and wheel velocity control.

RoombaWheelsControl block:
The wCtrl input takes either a 0 or 1. A 0 means no input to the wheels. A 1 calls the function SetWheelVelRoomba() function which takes values of -0.5 to 0.5 for each wheel. 0.5 is the maximum forward velocity, 0 is stop, and -0.5 is maximum reverse velocity. The stat output can be connected to a display to see the current status of the state flow.

RoombaRangeSensor block:
The getData input takes either a 0 or 1. A 1 calls the RangeStateRoomba() function which grabs the sensor values and placed it in a 1x6 matrix. These values can be used for the purpose of collision avoidance.
