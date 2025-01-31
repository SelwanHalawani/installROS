# Installing ROS Melodic on Jetson Nano

This repository provides instructions on how to install ROS Melodic on a Jetson Nano running Ubuntu 18.04.

## Prerequisites

Before you begin installing ROS Melodic on your Jetson Nano, make sure you have the following:

- **Jetson Nano** device with **Ubuntu 18.04** installed.
- An active **internet connection** to download the necessary packages.
- A system with **sufficient storage space**.

## Steps

### 1. Update the System

First, make sure your system is up-to-date:

    sudo apt update
    sudo apt upgrade

### 2. Install Required Dependencies
**You need to install some necessary tools for installing ROS:**
        
    sudo apt install -y curl gnupg2 lsb-release
### 3. Add the ROS Repository
**Add the ROS repository to your system:**
    
    curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
    sudo sh -c 'echo "deb [arch=arm64] http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
### 4. Install ROS Melodic
**Now, you can install ROS Melodic:**

    sudo apt update
    sudo apt install ros-melodic-desktop-full
### 5. Set Up the Environment
**After installing ROS, you need to set up the environment:**

    echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
    source ~/.bashrc
### 6. Install Essential Tools
**To install essential ROS tools, run:**

    sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
### 7. Set Up rosdep
**To install any missing dependencies, set up rosdep:**

    sudo rosdep init
    rosdep update
### 8. Verify the Installation
**Finally, verify that ROS is installed correctly by running:**

    roscore











