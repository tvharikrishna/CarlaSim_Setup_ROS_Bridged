# Introduction to Carla Simulator & Setup Guide

<p align="center">
  <img src="data/project_title.png" alt="Project Logo Cover" width="1500"/>
</p>

---------------------------------------------

## What is Carla Simulator
The CARLA simulator is an open-source platform designed to support the development, training, and validation of autonomous driving systems. It provides a highly realistic and flexible simulation environment with customizable scenarios, built on Unreal Engine and OpenDRIVE. CARLA includes a range of features such as a sensor suite, traffic manager, and the ability to distribute workloads across multiple GPUs for enhanced performance. It's widely used for generating synthetic training data not only for autonomous vehicles but also for other robotics applications, simulating real-world urban and highway environments

---------------------------------------------

## Installation Prerequisites
1) **A compatible operating system:** You will need an ***Ubuntu version that supports*** the specific version of CARLA you wish to install. For instance, CARLA `0.9.13` is compatible with `ROS-bridge` as well as `ROS-Noetic`, which operates on `Ubuntu 20.04`.

2) **Operating System and GPU:** Ensure that your operating system meets the necessary specifications to run CARLA, including a compatible `GPU` that the CARLA simulator can utilize. ***Set up and update the required graphics drivers accordingly***. In my case, if you enter the command `nvidia-smi`, it will display my NVIDIA drivers.

3) **Clean and Fresh OS:** This installation guide is designed to assist with a from-scratch installation, which means starting with a clean slate,         
 `(1 and 2 Completed)`, then installing ROS, required libraries, and finally the CARLA simulator. It is ***advisable to begin with no pre-installed packages to avoid conflicts*** with the installation steps outlined in this guide.

---------------------------------------------

---------------------------------------------

---------------------------------------------

# Installation Phases

| Phase | Description |
| ----- | ----------- |
| **PHASE 1** | Install all basic/common libraries and `ROS Noetic` Setup. |
| **PHASE 2** | Installation of the `Carla Simulator`. |
| **PHASE 3** | Addressing any `errors` that may occur post-installation or during the initial run of Carla. |
| **PHASE 4** | Installation of the `ROS-Bridge`. |

---------------------------------------------

# PHASE 1 = Install all essential libraries and set up ROS Noetic.
The commands provided are useful for setting up a Linux-based development environment. They include updating the system, installing common tools and libraries, setting up Git, Python, and Visual Studio Code, and installing ROS Noetic. Although not all these steps are directly related to the CARLA simulator, they are necessary when configuring a fresh system to ensure that all dependencies and tools are in place for a smooth installation.


    #!/bin/bash
    
    # System setup
    echo "Update"
    yes | sudo apt-get update
    
    echo "Upgrade"
    yes | sudo apt-get upgrade
    
    echo "Installing Terminator"
    yes | sudo apt install terminator
    
    echo "Installing tmux"
    yes | sudo apt-get install tmux
    
    echo "Setting up SSH Server, net tools, GIT"
    yes | sudo apt-get install openssh-server net-tools git htop
    
    echo "Github Credential Save"
    git config --global credential.helper store
    
    echo "Installing pip and other python packages"
    yes | sudo apt install python3-pip 
    yes | pip3 install opencv-python
    yes | pip3 install numpy
    yes | pip3 install matplotlib
    yes | pip3 install pandas
    yes | pip3 install opencv-contrib-python
    yes | pip3 install scipy
    
    echo "Installing VSCode"
    wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
    yes | sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
    sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
    rm -f packages.microsoft.gpg
    yes | sudo apt install apt-transport-https
    sudo apt-get update
    yes | sudo apt install code # or code-insiders
    
    echo "Installing ROS Noetic"
    sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
    yes | sudo apt install curl # if you haven't already installed curl
    curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
    sudo apt-get update
    yes | sudo apt install ros-noetic-desktop-full
    
    sudo apt-get install -y ros-noetic-navigation ros-noetic-teb-local-planner* ros-noetic-ros-control ros-noetic-ros-controllers ros-noetic-gazebo-ros-control ros-noetic-ackermann-msgs ros-noetic-serial 
    
    sudo apt-get install -y ros-noetic-turtlebot3*
    sudo apt-get install -y ros-noetic-rosserial*
    sudo apt-get install -y ros-noetic-rosbridge-suite
    sudo pip3 install -U catkin_tools
    
    echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
    source ~/.bashrc
    
    mkdir -p ~/catkin_ws/src
    cd ~/catkin_ws/
    catkin build

---------------------------------------------

# PHASE 2 = Installation of the `Carla Simulator`
For this phase, you should refer to the official documentation provided by the Carla Simulator, which has proven effective for all users. <br> Pay close attention and meticulously follow the instructions from the `Before you begin` section to `Running CARLA`.

    https://carla.readthedocs.io/en/0.9.13/start_quickstart/
    
If you run into any problems, especially when trying to run Carla, that's what PHASE 3 is for—to help fix those issues.

---------------------------------------------

# PHASE 3 = Addressing any `errors` that may occur post-installation or during the initial run of Carla.
In this phase, some individuals might encounter errors, whereas others might not, because errors do not occur universally. For a number of users, the process will be seamless from the start, but there will be cases where errors arise. <br> <br>
To address this, we have outlined some common errors and their respective troubleshooting steps below, ensuring you have the guidance needed to resolve any issues that may come up while running Carla for the first time.

## ERROR 1 == HARI KRISHNA LOL

















































































