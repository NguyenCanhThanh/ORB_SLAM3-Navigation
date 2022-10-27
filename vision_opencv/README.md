# vision_opencv
=============

[![image](https://travis-ci.org/ros-perception/vision_opencv.svg?branch=indigo)](https://travis-ci.org/ros-perception/vision_opencv)

Packages for interfacing ROS with OpenCV, a library of programming functions for real time computer vision.

1. First download the python build tool

```
sudo apt-get install python3-pip python-catkin-tools python3-dev python3-numpy 
sudo pip3 install rospkg catkin_pkg
```

2. Create a separate workspace to compile the bridge_cv ROS package
```
mkdir -p ~/cvbridge_build_ws/src
cd ~/cvbridge_build_ws/src
```

3. Clone the open_vision repository
```
git clone -b noetic https://github.com/ros-perception/vision_opencv.git
````

4. Open CMakeLists.txt with you favorite text editor and make the following modification at Line 11, changing:
```
find_package(Boost REQUIRED python37)
```
to
```
find_package(Boost REQUIRED python3)
```
Save and exit

5. Compilation
```
cd ~/cvbridge_build_ws
catkin config -DPYTHON_EXECUTABLE=/usr/bin/python3 -DPYTHON_INCLUDE_DIR=/usr/include/python3.6m -DPYTHON_LIBRARY=/usr/lib/aarch64-linux-gnu/libpython3.6m.so
catkin config --install
catkin build cv_bridge
```

To use the package, you could source it via
```
source install/setup.bash --extend
```
