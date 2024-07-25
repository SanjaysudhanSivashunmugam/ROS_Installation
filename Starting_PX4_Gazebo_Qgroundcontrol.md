### Starting PX4 with Gazebo and QGroundControl
---
##### To start working with PX4, Gazebo, and QGroundControl, follow these steps:

###### Terminal 1:
Navigate to the PX4-Autopilot directory and Start the PX4 SITL (Software In The Loop) with Gazebo:
```bash
cd PX4-Autopilot
make px4_sitl gazebo
```
###### Terminal 2:
Navigate to the directory where the QGroundControl AppImage is located (e.g., Downloads) and Run QGroundControl:
```bash
cd Downloads
./QGroundControl.AppImage
```
This setup allows you to simulate the drone environment using PX4 and Gazebo, while QGroundControl serves as the ground control station to monitor and control the drone.
