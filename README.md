# installation guide SLAM REC-HV and dependencies
#### Ing. Brayan Andru Montenegro Embus
#### Popayán, Cauca, Colombia.
#### bamontenegro@unicauca.edu.co

## 1.ROS installation and dependencies.
```linux
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
sudo apt update
sudo apt install ros-melodic-desktop-full
echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc
sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
sudo apt install python-rosdep
sudo rosdep init
rosdep update
```
## 2.installation of python 3.6.
```linux
sudo apt-get install python3-pip python3-yaml python3-dev
sudo pip3 install rospkg catkin_pkg rosdep rosinstall_generator rosinstall wstool vcstools catkin_tools
sudo apt-get install python3.6-dev
```
## 3. Virtual environment setup.
```linux
mkdir -p ~/python36_ws/src
cd ~/python36_ws
pip3 install --user virtualenv
virtualenv --python=/usr/bin/python3.6 py36env
cd
```
#### Activation virtual environment.
```linux
cd ~/python36_ws
source py36env/bin/activate
```
## 4. Setup Workspace.
```
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/
catkin_make
source devel/setup.bash
echo $ROS_PACKAGE_PATH
/home/youruser/catkin_ws/src:/opt/ros/kinetic/share
```
## 5. Instal pip
```linux
sudo apt update
apt install python3-pip
```
## 6. Instalación OPENNI
```linux
sudo apt-get install ros-melodic-openni-camera
sudo apt-get update
```
## 7. Instalación de RPLIDAR
```linux
sudo apt-get install ros-melodic-rplidar-ros
sudo apt-get update
```
## 8. Instalación de opencv
```linux
sudo pip3 install scikit-build
sudo pip3 install opencv-python
```
## 9. librerias kinect
```linux
sudo apt-get install python-freenect
```
## 10. modulos sobre el entorno virtual
```linux
cd
pip install rospkg
pip3 install opencv-python
pip3 install matplotlib
pip3 install openpyxl
pip3 install pandas
pip3 install seaborn
pip3 install sklearn
pip3 install open3d-python
cd
git clone https://github.com/eric-wieser/ros_numpy.git
cd ros_numpy/
python setup.py install
cd catkin_ws
cd src
sudo git clone https://github.com/Slamtec/rplidar_ros.git
catkin_make
sudo apt-get install ros-melodic-openni-camera ros-melodic-openni-launch
```
## 11. ORB-SLAM
```linux
pip3 install pykalman
pip3 install serial
python -m pip install pyserial
sudo apt-get install cmake
sudo apt-get install g++
sudo apt-get install gcc
sudo apt-get install libglew-dev libpython2.7-dev
sudo apt-get install libeigen3-dev
sudo apt-get install -y doxygen libgl1-mesa-dev libglew-dev cmake libboost-all-dev
sudo apt-get update -y
sudo apt-get install -y libsdl-pango-dev
sudo apt-get install ros-indigo-libg2o
sudo apt-get install autoconf
sudo apt-get install wayland-protocols
sudo apt install libopenexr22
sudo apt install openexr
sudo apt install libopenexr-dev
cd catkin_ws
git clone https://github.com/raulmur/ORB_SLAM2.git ORB_SLAM2
cd ORB_SLAM2
chmod +x build.sh ./build.sh
```
## 12.Creating a catkin Package rdslam for Rec-HV execution
```linux
cd ~/catkin_ws/src
catkin_create_pkg rdslam std_msgs rospy roscpp
```
#### save and replace what is at this address in the project folder.
https://github.com/MAB1144-Python/SLAM-REC-HV-version-1.0-test/tree/main/rdslam
## 13.Build a catkin workspace and sourcing the setup file in ROS.
```linux
cd ~/catkin_ws
catkin_make
. ~/catkin_ws/devel/setup.bash
```
#Execution Rec_HV
#### now to run the code connect the RPLIDARA1 and Kinect sensors with adapter to USB type A.
#### and execute the following lines on a terminal.
```linux
cd ~/python36_ws
source py36env/bin/activate
cd
cd catkin_ws/src/rdslam/src
sudo chmod 666 /dev/ttyUSB0
roslaunch rdslam Rec_HV.launch
```

