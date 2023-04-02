## Record a Ros Bag for Kimera

### Filter out compressed topics 
```
rosbag record -a -O data.bag -x "/(.*)/theora/(.*)|(.*)/theora|/(.*)/compressed/(.*)|(.*)/compressed|/(.*)/compressedDepth/(.*)|(.*)/compressedDepth"
```


## Play Ros Bags

### Filter a certain topic while playing

