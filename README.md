# Installation Guide

## 10.1 Installing ROS Noetic

1. **Update Package List**
    ```bash
    sudo apt update
    ```

2. **Install Required Packages**
    ```bash
    sudo apt install curl gnupg lsb-release
    ```

3. **Add ROS Repository**
    ```bash
    sudo sh -c 'echo "deb http://packages.ros.org/ros2/ubuntu $(lsb_release -cs) main" > /etc/apt/sources.list.d/ros2-latest.list'
    ```

4. **Add the ROS Key**
    ```bash
    curl -sSL http://packages.ros.org/ros2/ubuntu/ros.asc | sudo apt-key add -
    ```

5. **Install ROS Noetic**
    ```bash
    sudo apt update
    sudo apt install ros-noetic-desktop-full
    ```

6. **Set Up ROS Environment**
    Add the following line to your `~/.bashrc` file:
    ```bash
    source /opt/ros/noetic/setup.bash
    ```
    Then, update your environment:
    ```bash
    source ~/.bashrc
    ```

## 10.2 Installing Gazebo

1. **Add Gazebo Repository**
    ```bash
    sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu-stable $(lsb_release -cs) main" > /etc/apt/sources.list.d/gazebo-latest.list'
    ```

2. **Add Gazebo Key**
    ```bash
    curl -sSL http://packages.osrfoundation.org/gazebo.key | sudo apt-key add -
    ```

3. **Install Gazebo**
    ```bash
    sudo apt update
    sudo apt install gazebo11
    ```

4. **Install Gazebo ROS Packages**
    ```bash
    sudo apt install ros-noetic-gazebo-ros-pkgs
    ```

## 10.3 Installing PX4

1. **Install Required Dependencies**
    ```bash
    sudo apt update
    sudo apt install git zip unzip python3-pip python3-venv
    ```

2. **Clone PX4 Repository**
    ```bash
    git clone https://github.com/PX4/PX4-Autopilot.git
    cd PX4-Autopilot
    ```

3. **Install PX4 Dependencies**
    ```bash
    ./Tools/setup_gazebo.bash $(pwd) $(pwd)/build/px4_sitl_default
    ```

4. **Build PX4**
    ```bash
    make px4_sitl_default
    ```

## 10.4 Installing ArduPilot

1. **Clone ArduPilot Repository**
    ```bash
    git clone https://github.com/ArduPilot/ardupilot.git
    cd ardupilot
    ```

2. **Install Required Dependencies**
    ```bash
    sudo apt-get update
    sudo apt-get install python3-pip python3-dev python3-venv
    pip3 install -r Tools/python_requirements.txt
    ```

3. **Build ArduPilot**
    ```bash
    ./waf configure
    ./waf build
    ```

## 10.5 Installing QGroundControl

1. **Download QGroundControl**
    Visit the [QGroundControl website](https://qgroundcontrol.com/) and download the latest version for your operating system.

2. **Install QGroundControl**
    For Ubuntu, you can use the `.deb` package:
    ```bash
    sudo dpkg -i qgroundcontrol.deb
    sudo apt-get install -f
    ```

3. **Run QGroundControl**
    After installation, you can start QGroundControl from the application menu or by running:
    ```bash
    qgroundcontrol
    ```

## 10.6 Setting Up Environment

1. **Update Environment Variables**
    Add the following to your `~/.bashrc` file to include paths for ROS and PX4:
    ```bash
    source /opt/ros/noetic/setup.bash
    source ~/PX4-Autopilot/build/px4_sitl_default/install_isolated/setup.bash
    ```

2. **Source Environment**
    ```bash
    source ~/.bashrc
    ```

## 10.7 Testing Installation

1. **Verify ROS Installation**
    ```bash
    roscore
    ```

2. **Verify Gazebo Installation**
    ```bash
    gazebo
    ```

3. **Verify PX4 Installation**
    ```bash
    make px4_sitl_default gazebo
    ```

4. **Verify ArduPilot Installation**
    ```bash
    ./arducopter -A udp:127.0.0.1:14550
    ```

5. **Verify QGroundControl Installation**
    Launch QGroundControl and ensure it connects to the simulation environment.

