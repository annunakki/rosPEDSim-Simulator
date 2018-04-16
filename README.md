# ee631_final_sample, Human Robot Interaction Environment
### Requirements:
* Ubuntu 16.04
* ROS – Kinetic
* The simulation environment is not guaranteed to work with any other ROS or Ubuntu environment.
### Pre-requisites:
1. C++11 compiler which is basically gcc/g++. Please check the version of gcc to make sure your installed version can support this feature.
2. Gazebo-ROS packages. Can be installed by executing command, 
    ```shell
    sudo apt-get install ros-kinetic-gazebo-ros-pkgs ros-kinetic-gazebo-ros-control
    ```
3. QT5. This can be installed by;
    ```shell
    sudo apt-get update
    sudo apt-get install qt5.1
    ```
4. Eigen3. It can be installed using command;
	sudo apt-get install libeigen3-dev libeigen3-doc
### Running Instructions:
1. Suppose you have made a catkin workspace named `catkin_ws`.
1. Once you are finished with all the dependencies, you can git clone this package from github into your ROS workspace and `catkin_make` it. Once you download it, shut down your machine and restart it before you run catkin_make. 
    ```shell
    cd ~/catkin_ws/src
    git clone --recursive https://github.com/mfahadrobotics/pedsim_ros.git
    cd ~/catkin_ws
    catkin_make
    ```
1. If you installed all dependencies correctly, you shouldn’t get any errors.
1. You can run the environment by executing
    ```shell
    roslaunch pedsim_simulator Altorfer_f1.launch
    ```
1. Once you successfully run the node, you will see topic related to laser range finder, Kinect camera and controlling the velocity of the robot. You can subscribe to and publish to these topics in your own controller to get the sensor information and publish the desired velocities to move the robot.
* Linear and angular velocity topic:
    ```shell
    /Pioneer3AT/cmd_vel
    ```
* Laser Range finder topic:
    ```shell
    /laser/scan
    ```
* Pose of each model in the world:
    ```shell
    /gazebo/model_states
    ```
* Kinect topics (There are several topics, you can choose the ones you need):
    ```shell
    /camera/*
    ```






## Acknowledgement
Part of this simulation is based on [pedsim_ros](https://github.com/srl-freiburg/pedsim_ros).
