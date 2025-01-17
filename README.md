# ORB-SLAM3-Underwater

[ORB-SLAM3](https://github.com/UZ-SLAMLab/ORB_SLAM3) but for underwater environments.

Currently only implemented with monocular setups.

## To-do:
- ~~Implement depth readings with mono setup~~
- ~~Add CLAHE image preprocessing~~
- Implement depth readings with mono-inertial setup
- Add underwater ORB vocabulary
- Add prerequisites used in installing ROS + standard packages
This instruction require ROS to already be installed: [install ROS Noetic](http://wiki.ros.org/noetic/Installation/Ubuntu)

Uses the ROS implementation written by tien94. [The implementation can be found here.](https://github.com/thien94/orb_slam3_ros)

The instructions are copied from the same repo.
```
sudo apt install git ros-noetic-catkin python3-catkin-tools
```
This package uses ```catkin build```. Tested on Ubuntu 20.04.
## 1. Prerequisites
### Eigen3
```
sudo apt install libeigen3-dev
```
### Pangolin
```
cd ~
git clone https://github.com/stevenlovegrove/Pangolin.git
cd Pangolin
mkdir build && cd build
cmake ..
make
sudo make install
sudo ldconfig
```
### OpenCV
Check the OpenCV version on your computer (required [at least 3.0](https://github.com/UZ-SLAMLab/ORB_SLAM3)):
```
python3 -c "import cv2; print(cv2.__version__)" 
```
On a freshly installed Ubuntu 20.04.4 LTS with desktop image, OpenCV 4.2.0 is already included. If a newer version is required (>= 3.0), follow [installation instruction](https://docs.opencv.org/4.x/d0/d3d/tutorial_general_install.html) and change the corresponding OpenCV version in `CMakeLists.txt`

### `hector-trajectory-server`
Technically this package is optional, but is used by default within the project. TODO: Make this optional.

Install `hector-trajectory-server` to visualize the real-time trajectory of the camera/imu. Note that this real-time trajectory might not be the same as the keyframes' trajectory.
```
sudo apt install ros-noetic-hector-trajectory-server
```
## 2. Installation
```
mkdir catkin_ws .... bla 
cd ~/catkin_ws/src
git clone https://github.com/einatomter/orb_u
cd ../
catkin build
```

## 3. Run Examples

### VP mode
Dataset [aqualoc Harbour](https://seafile.lirmm.fr/d/79b03788f29148ca84e5/?p=%2FHarbor_sites_sequences&mode=list)

### VIP mode
