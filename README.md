# Installation_guide

## installation guide SLAM REC-HV

## Guía instalacion ROS completa

## Ing. Brayan Andru Montenegro Embus

## bamontenegro@unicauca.edu.co

## 1.Instalaciòn de ROS

#### https://www.youtube.com/watch?v=9uyiYlgkrRY

#### http://wiki.ros.org/melodic/Installation/Ubuntu

## 2.instalación de python 3,6

#### https://medium.com/@inderpreetsinghchhabra/using-python3-with-ros-kinetic-2488354efece

## Activación cada vez que se va a trabajar
```linux
cd ~/python36_ws
```
#### source py36env/bin/activate

## 3.Configuración espacio de trabajo

#### http://wiki.ros.org/es/ROS/Tutoriales/catkin/CreateWorkspace

## 4.Instal pip

```linux
sudo apt update
apt install python3-pip
```

## 5.Instalación OPENNI
```linux
sudo apt-get install ros-melodic-openni-camera
sudo apt-get update
```

## 6.Instalación de RPLIDAR
```linux
sudo apt-get install ros-melodic-rplidar-ros
sudo apt-get update
```

## 7.Instalación de opencv
```linux
sudo pip3 install scikit-build
sudo pip3 install opencv-python
```
#### https://linuxize.com/post/how-to-install-opencv-on-ubuntu-18-04/

## 8.librerias kinect

```linux
sudo apt-get install python-freenect
```

## 9.modulos sobre el entorno virtual
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

## 10.ORB-SLAM
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
```
#### https://programmerclick.com/article/7166838330/

#### https://medium.com/@mhamdaan/implementing-orb-slam-on-ubuntu-18-04-ros-melodic-606e668deffa

```linux
cd catkin_ws
git clone https://github.com/raulmur/ORB_SLAM2.git ORB_SLAM2
cd ORB_SLAM2
chmod +x build.sh ./build.sh
```
## 11.Creating a catkin Package rdslam for Rec-HV execution
```linux
cd ~/catkin_ws/src
catkin_create_pkg rdslam std_msgs rospy roscpp
```
## save and replace what is at this address in the project folder.
https://github.com/MAB1144-Python/SLAM-REC-HV-version-1.0-test/tree/main/rdslam
## 12.Build a catkin workspace and sourcing the setup file in ROS.
```linux
cd ~/catkin_ws
catkin_make
. ~/catkin_ws/devel/setup.bash
```
## now to run the code connect the RPLIDARA1 and Kinect sensors with adapter to USB type A.
## and execute the following lines on a terminal.


