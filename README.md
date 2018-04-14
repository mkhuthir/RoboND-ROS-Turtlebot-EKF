# RoboND Turtlebot EKF
ROS Turtlebot with Extended Kalman Filters


### Turtlebot Simulator Package:

* Original package was cloned from https://github.com/turtlebot/turtlebot_simulator into **src** folder

* Install Dependencies:
```bash
$ rosdep -i install turtlebot_gazebo
```
* launch file:
```bash
$ roslaunch turtlebot_gazebo turtlebot_world.launch
```

### Robbot Pose EKF Package:

* Original package was cloned from https://github.com/udacity/robot_pose_ekf into **src** folder

* Modified launch file to be as following:

```xml
<launch>

<node pkg="robot_pose_ekf" type="robot_pose_ekf" name="robot_pose_ekf">
  <param name="output_frame" value="odom_combined"/>
  <param name="base_footprint_frame" value="base_footprint"/>
  <param name="freq" value="30.0"/>
  <param name="sensor_timeout" value="1.0"/>  
  <param name="odom_used" value="true"/>
  <param name="imu_used" value="true"/>
  <param name="vo_used" value="false"/>

  <remap from="imu_data" to="/mobile_base/sensors/imu_data" />    

</node>

</launch>
```

* launch file:
```bash
$ roslaunch robot_pose_ekf robot_pose_ekf.launch
```

### Odometry to Trajectory Package:

* Original package was cloned from https://github.com/udacity/odom_to_trajectory into **src** folder

* launch file:
```bash
$ roslaunch odom_to_trajectory create_trajectory.launch
```

### TurtleBot Teleop Package:

* Original package was cloned from https://github.com/turtlebot/turtlebot into **src** folder

* Install Dependencies:
```bash
$ rosdep -i install turtlebot_teleop
```

* launch file:
```bash
$ roslaunch turtlebot_teleop keyboard_teleop.launch
```
