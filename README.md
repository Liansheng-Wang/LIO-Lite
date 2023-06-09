# LIO-Lite
A lightweight LIO (Lidar Odometry) system was deployed on a UAV utilizing the Livox Mid-360 sensor.  
* The project incorporates incremental refinements to the existing [faster-lio](https://github.com/gaoxiang12/faster-lio.git) framework.  
* Add location node.

## classification
This project has several different branches. The optimize the based branch, using graph optimization. Testing on the X86 is OK, but the processing speed on the Nvidia NX is very low.  
ESKF based performs well on Nvidia NX.

## Illustrate
c++ == 17
The project is developed using C++17 standard.  

## Dependence

1. ROS (melodic or noetic)
2. glog: ```sudo apt-get install libgoogle-glog-dev```
3. eigen: ```sudo apt-get install libeigen3-dev```
4. pcl: ```sudo apt-get install libpcl-dev```
5. yaml-cpp: ```sudo apt-get install libyaml-cpp-dev```


## Build
```
  git clone https://github.com/Liansheng-Wang/LIO-Lite.git  
  cd LIO-Lite  
  catkin_make  
```

## Run
```
  mkdir src/LIO-Lite/maps  src/LIO-Lite/logs
  source devel/setup.zsh
  roslaunch lio_lite mapping_360.launch  
```
After rebuilding the map, you can follow the following command to load the map for relocation  
```
  roslaunch lio_lite location_360.launch  
```

### note:
If it is not at the starting point during the repositioning process, it needs to be manually repositioned in rviz


## Reference
* [FAST-LIO2](https://github.com/hku-mars/FAST_LIO.git)
* [LIO-SAM](https://github.com/TixiaoShan/LIO-SAM.git)
* [faster-lio](https://github.com/gaoxiang12/faster-lio.git)