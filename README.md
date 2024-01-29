## Info
Extended Kalman Filter (EKF) to estimate the state of the robot, PID for control to track a desired trajectory based on the estimated state.

## Requirements
- ROS2 Humble
- C++ 17
- Eigen
- tf2
- turtlebot3_gazebo



## Installation with Cmake
 ```
ros2 pkg create --build-type ament_cmake ekf_yck
Move src and include files into the created package
colcon build
source install/setup.bash
ros2 run diff_drive diff_drive
 ```

In another terminal, install gazebo: <br>

 ```
sudo apt install ros-humble-turtlebot3*
 ```

 ```
source /opt/ros/humble/setup.bash
source /usr/share/gazebo/setup.sh
ros2 launch turtlebot3_gazebo empty_world.launch.py
 ```

- If you get an error related to "/usr/lib/x86_64-linux-gnu/libi2c.so"

    - Install *apt-file*: <br>
```
sudo apt-get install apt-file  <br>
apt-file update
```

 ```
apt-file search /usr/lib/x86_64-linux-gnu/libi2c.so
 ```

Install the package from the result of the above code (apt-file search) <br>
You can find the detailed explanation [here](https://askubuntu.com/questions/939526/make-problem-no-rule-to-make-target-usr-lib-x86-64-linux-gnu-libpcl-common-so)  <br>
You can see *libi2c-dev* as one of the results of the *apt-file search*. For installation of *libi2c-dev* package, find [here](https://installati.one/install-libi2c-dev-ubuntu-22-04/)




## Standalone Installation via Code::Blocks

To run the code propely in Code::Blocks 20.03, you need to add: <br>
linkers files (.so) in *Linker settings* <br>
paths in the *Search directories* <br>

- If you get an error "xyz.so2: cannot open shared object file: No such file or directory" when press the run button on Code::Blocks : 
    - Find the path of "xyz.so"
    - Add this path to Search directories-->Linker
    - In my case, click [here](https://github.com/Yigit-Kuyu/EKF_Control_Cpp/blob/main/AddLinkerLibrary.png)   
  





