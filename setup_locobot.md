## ref link: https://www.trossenrobotics.com/docs/interbotix_xslocobots/ros_interface/index.html
https://www.trossenrobotics.com/docs/interbotix_xslocobots/ros_packages/index.html

### To start communicating with the robot 
`roslaunch interbotix_xslocobot_control xslocobot_control.launch robot_model:=locobot_wx200 use_base:=true use_camera:=true use_lidar:=false`


### To run teleop (make sure xslocobot_control is running)
`roslaunch kobuki_keyop keyop.launch __ns:=locobot`

### For elevation Mapping Using LoCoBOt:
`roslaunch interbotix_xslocobot_nav xslocobot_nav.launch robot_model:=locobot_wx200 use_lidar:=false rtabmap_args:=-d`   
`roslaunch kobuki_keyop keyop.launch __ns:=locobot`     
Then run `odom_to_pose.py`    
`roslaunch elevation_mapping_demos myrealsensetest.launch`



### For remote operation and running RTABMap    
> Connect the base and camera to Xavier      
> Make sure your laptop and xavier are connected to the same wifi newtork.      
> `ssh -X vfa@vfa`run this command on your laptop terminal to ssh into LocoBot       
> `roslaunch interbotix_xslocobot_nav xslocobot_nav.launch robot_model:=locobot_wx200 use_lidar:=false rtabmap_args:=-d` run this command to start SLAM    
> To open a new ssh'ed terminal run `/usr/bin/dbus-launch /usr/bin/gnome-terminal &` after doing ssh for the first time, and now you can just usr `ctrl+shift+t` to open a new terminal.        
> Open another ssh'ed terminal and run `roslaunch kobuki_keyop keyop.launch __ns:=locobot` for teleop         
> Open another ssh'ed terminal and run `roslaunch interbotix_xslocobot_descriptions remote_view.launch rviz_frame:=map`      
