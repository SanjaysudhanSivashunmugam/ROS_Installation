### Starting ArduPilot with Gazebo
---
##### To start working with ArduPilot and Gazebo, follow these steps:

###### Terminal 1:
Launch Gazebo with the specified world for ArduPilot:
```bash
gazebo --verbose ~/ardupilot_gazebo/worlds/iris_arducopter_runway.world
```
###### Terminal 2:
Navigate to the ArduCopter directory within the ArduPilot directory and Start the simulation vehicle with the Gazebo model and map:
```bash
cd ardupilot
cd ArduCopter
../Tools/autotest/sim_vehicle.py -f gazebo-iris --map
```
This setup allows you to simulate the drone environment using ArduPilot and Gazebo, providing a robust platform for testing and development.

