# SmartMethodsTASK2-Robotics
Robot Operating System (ROS):
To set up ros on our VM we need to follow the steps:
![image](https://user-images.githubusercontent.com/107816408/181071497-5f986c8c-2d71-44de-9c93-7ab48feccea7.png)
Open the terminal and insert these commands:
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
sudo apt-get update
sudo apt-get install ros-kinetic-desktop-full
apt-cache search ros-kinetic
echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
sudo apt install python-rosdep
sudo rosdep init
rosdep update
sudo apt-get install ros-noetic-catkin
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/
catkin_make
cd ~/catkin_ws/src
git clone https://github.com/smart-methods/arduino_robot_arm.git 
cd ~/catkin_ws
rosdep install --from-paths src --ignore-src -r -y
sudo apt-get install ros-kinetic-moveit
sudo apt-get install ros-kinetic-joint-state-publisher ros-kinetic-joint-state-publisher-gui
sudo apt-get install ros-kinetic-gazebo-ros-control joint-state-publisher
sudo apt-get install ros-kinetic-ros-controllers ros-kinetic-ros-control
sudo nano ~/.bashrc
at the end of the (bashrc) file add the follwing line
(source /home/KhalidAbdullahb01/catkin_ws/devel/setup.bash)
then 
ctrl + o
source ~/.bashrc

and finally the next command will launch ros:

roslaunch robot_arm_pkg check_motors.launch
![image](https://user-images.githubusercontent.com/107816408/181072967-44075884-cf40-48ac-914b-d9845d337892.png)

and we can move the arm by using the joint state

