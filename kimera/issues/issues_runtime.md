
## Issues while running the pkgs
----
if error is related to rosbag,
- Add rosbag path in kimera_vio_ros_euroc.launch file. 
   - like this  <arg name="rosbag_path" default="/home/mrsd-lab/ghar/V1_01_easy.bag" unless="$(arg online)"/>
- or enable the online parameter to true

if error is related to autoInitialize is false
- autoInitialize: 1 in /home/mrsd-lab/ghar/kimera_ws/src/Kimera-VIO/params/Euroc/BackendParams.yaml