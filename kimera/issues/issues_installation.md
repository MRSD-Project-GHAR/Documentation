
## Issues while Installation
---
```
error: #error PCL requires C++14 or above
```
solution: catkin config --cmake-args -DCMAKE_BUILD_TYPE=Release -DCMAKE_CXX_STANDARD=14
- This will tell CMake to use C++ 14 and resolve the issue. 


---
```
error: no matching function for call to ‘dynamic_pointer_cast<gtsam::BetweenFactor<gtsam::Pose2> >(const std::shared_ptr<gtsam::NonlinearFactor>&)’
   82 |     auto factor = boost::dynamic_pointer_cast<BetweenFactor<Pose2>>(factor_);
```
solution: change branches of the following repos  
- gtsam to c4184e192b4605303cc0b0d51129e470eb4b4ed1
- Kimera-VIO to origin/feature/hydra

