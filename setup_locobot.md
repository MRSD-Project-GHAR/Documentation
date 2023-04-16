## ref link: https://www.trossenrobotics.com/docs/interbotix_xslocobots/ros_interface/index.html

### To start communicating with the robot 
`roslaunch interbotix_xslocobot_control xslocobot_control.launch robot_model:=locobot_wx200 use_base:=true use_camera:=true use_lidar:=false`


### To run teleop (make sure xslocobot_control is running)
`roslaunch kobuki_keyop keyop.launch __ns:=locobot`

### For elevation Mapping Using LoCoBOt:
`roslaunch interbotix_xslocobot_nav xslocobot_nav.launch robot_model:=locobot_wx200 use_lidar:=false rtabmap_args:=-d`   
`roslaunch kobuki_keyop keyop.launch __ns:=locobot`     
Then run `odom_to_pose.py`    
`roslaunch elevation_mapping_demos myrealsensetest.launch`
