# RPLIDAR ROS2 Package

ROS2 node for RPLIDAR

Visit following Website for more details about RPLIDAR:

rplidar roswiki: http://wiki.ros.org/rplidar

rplidar HomePage:   http://www.slamtec.com/en/Lidar

rplidar SDK: https://github.com/Slamtec/rplidar_sdk

rplidar Tutorial:  https://github.com/robopeak/rplidar_ros/wiki

## How to [install ROS2](https://index.ros.org/doc/ros2/Installation)
[ubuntu](https://docs.ros.org/en/foxy/Installation/Ubuntu-Install-Debians.html)

## How to configuring your ROS 2 environment
[Configuring your ROS 2 environment](https://docs.ros.org/en/foxy/Tutorials/Configuring-ROS2-Environment.html)

## How to Create a ROS2 workspace
[Create a workspace](https://docs.ros.org/en/foxy/Tutorials/Workspace/Creating-A-Workspace.html)

## Compile & Install rplidar_ros2 package

1. Clone rplidar_ros2 package from github : 

   ```bash
   git clone -b ros2 https://github.com/slamtec/rplidar_ros.git
   ``` 

2. Build rplidar_ros2 package :

   ```bash
   cd <your_own_ros2_ws>
   colcon build --symlink-install
   ```
   if you find output like "colcon:command not found",you need separate [install colcon](https://docs.ros.org/en/foxy/Tutorials/Colcon-Tutorial.html#install-colcon) build tools. 

  
3. Package environment setup :
    ```bash
    source ./install/setup.bash
    ```

    Note: Add permanent workspace environment variables.
    It's convenientif the ROS2 environment variables are automatically added to your bash session every time a new shell is launched:
    ```bash
    $echo "source <your_own_ros2_ws>/install/setup.bash" >> ~/.bashrc
    $source ~/.bashrc
    ```


RPLIDAR ROS package
=====================================================================

ROS node and test application for RPLIDAR

Visit following Website for more details about RPLIDAR:

rplidar roswiki: http://wiki.ros.org/rplidar

rplidar HomePage:   http://www.slamtec.com/en/Lidar

rplidar SDK: https://github.com/Slamtec/rplidar_sdk

rplidar Tutorial:  https://github.com/robopeak/rplidar_ros/wiki

How to build rplidar ros package
=====================================================================
    1) Clone this project to your colcon workspace src folder
    2) Install Eloquent ROS2 and colcon compiler.
```bash
source /opt/ros/eloquent/setup.sh
colcon build --symlink-install
```
How to run rplidar ros package
=====================================================================
There're two ways to run rplidar ros package
Note! Just test for RPLIDAR A1/A2,not test A3 and S1,need your test.
I. Run rplidar node and view in the rviz
------------------------------------------------------------
At first console,
```bash
source ./install/setup.bash
ros2 run rplidar_ros rplidarNode 
```
At second console,
```bash
source ./install/setup.bash
ros2 run tf2_ros static_transform_publisher 0 0 0 0 0 0  world laser_frame  
```
At third console,
```bash
source ./install/setup.bash
rviz2 ./install/rplidar_ros/share/rplidar_ros/rviz/rplidar.rviz
```

Note: In Rviz settings, set "Fixed Frame" to `laser_frame`

You should see rplidar's scan result in the rviz.

II. Run rplidar node and view using test application
------------------------------------------------------------
```bash
source ./install/setup.bash
ros2 run rplidar_ros rplidarNodeClient 
```
You should see rplidar's scan result in the console

Notice: the different is serial_baudrate between A1/A2 and A3/S1

RPLidar frame
=====================================================================
RPLidar frame must be broadcasted according to picture shown in rplidar-frame.png
