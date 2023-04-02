## Running Kimera SLAM With Euroc dataset
---

### In Simulation (with semantics)

2. Run Kimera-Semantics online with Realsense:
```
roslaunch kimera_semantics_ros kimera_semantics.launch play_bag:=true
```
3. Vizualize:
```
rviz -d $(rospack find kimera_semantics_ros)/rviz/kimera_semantics_gt.rviz
```

### In Euroc dataset (without semantics)
```
roslaunch kimera_vio_ros kimera_vio_ros_euroc.launch run_stereo_dense:=true
```
```
roslaunch kimera_semantics_ros kimera_semantics_euroc.launch
```
```
rosbag play V1_01_easy.bag --clock
```
```
rviz -d $(rospack find kimera_semantics_ros)/rviz/kimera_semantics_euroc.rviz
```