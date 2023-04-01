## Running Kimera SLAM
---

### Using launch files for Realsense D435i

1. First, Disable IR sensor in realsense camera: 
```
rosrun dynamic_reconfigure dynparam set /camera/stereo_module emitter_enabled 0
```

2. Run custom Realsense-ros node: 
```
roslaunch realsense2_camera rs_camera_ghar.launch
```

3. Run Kimera-VIO online with Realsense:
```
roslaunch kimera_vio_ros kimera_vio_ros_realsense_IR.launch should_use_sim_time:=false
```

4 .Run Kimera-Semantics online with Realsense:
```
roslaunch kimera_seamntics_ros kimera_metric_realsense.launch should_use_sim_time:=false
```

### Using launch files for ROS Bags 

1. Run Kimera-VIO online with Realsense:
```
roslaunch kimera_vio_ros kimera_vio_ros_realsense_IR.launch should_use_sim_time:=true
```

2. Run Kimera-Semantics online with Realsense:
```
roslaunch kimera_seamntics_ros kimera_metric_realsense.launch should_use_sim_time:=true
```

3. Run rosbags with `clock` parameter: 
```
rosbag play ${bagName}.bag --clock
```
