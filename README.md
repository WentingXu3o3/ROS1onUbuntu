# ROS1onUbuntu

Here is a briefly instruction to install Ros1: Noetic on Ubuntu 20.04 (NOT INSIDE DOCKER CONTIANER: inside docker contaienr, with ubutnu20.04, ROS1 can be installed but meet errors for rviz which requires OpenGL with GPU enabled to render, if anyone knows how to fix it plz contact me!)

BEFORE START: Noetic is the ROS for Ubuntu20.04 if your host with different ubuntu this README doesn't help

1. Check Ubuntu Universe repository Enabled
   ```
   sudo apt install software-properties-common
   sudo add-apt-repository universe
   ```
2. Setup your sources.list
  ```
  sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
  ```

3. Set up your keys
   ```
   sudo apt install curl # if you haven't already installed curl
    curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
   ```


4. install desktop-full noetic
   ```
   sudo apt update
   sudo apt install ros-noetic-desktop-full
   ```
   
   
5. ```
   source /opt/ros/noetic/setup.bash
   ```
   for one time OR
   ```
   echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
   source ~/.bashrc
   ```
   for every time
   (only one version ROS installed for this case)

6. run ```roscore``` (in a separated terminal) and ```rviz```
  if meet ros master error
  change
  ```export ROS_MASTER_URI=http://<YourHostIP>:11311```
  ```export ROS_IP=<YourHostIP>```
