# ubuntu-standard


sudo apt update -y
sudo apt full-upgrade -y

#########

locale  # check for UTF-8

sudo apt update && sudo apt install locales

sudo locale-gen en_US en_US.UTF-8

sudo update-locale LC_ALL=en_US.UTF-8 LANG=en_US.UTF-8

export LANG=en_US.UTF-8

locale  # verify settings

#########

sudo apt install software-properties-common

sudo add-apt-repository universe

#########

sudo apt update && sudo apt install curl -y
sudo curl -sSL https://raw.githubusercontent.com/ros/rosdistro/master/ros.key -o /usr/share/keyrings/ros-archive-keyring.gpg

#########

echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/ros-archive-keyring.gpg] http://packages.ros.org/ros2/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) main" | sudo tee /etc/apt/sources.list.d/ros2.list > /dev/null

#########

sudo apt update && sudo apt install ros-dev-tools

sudo apt update -y
sudo apt upgrade -y

#########

sudo apt install ros-jazzy-desktop

#########

sudo apt install ros-jazzy-ros-base

#########

echo "source /opt/ros/jazzy/setup.bash" >> ~/.bashrc
source ~/.bashrc

#########

sudo apt update -y
sudo apt upgrade -y

#########

sudo apt install git

sudo apt update
sudo apt install python3-pip python3-colcon-common-extensions


mkdir -p ~/uros_ws/src
cd ~/uros_ws
git clone -b $ROS_DISTRO https://github.com/micro-ROS/micro_ros_setup.git src/micro_ros_setup


sudo rosdep init
rosdep update
rosdep install --from-path src --ignore-src -y
colcon build

echo "source ~/uros_ws/install/local_setup.bash" >> ~/.bashrc
source ~/.bashrc

sudo apt update
ros2 run micro_ros_setup create_agent_ws.sh
ros2 run micro_ros_setup build_agent.sh
source install/local_setup.bash

sudo apt install -y \
  ros-jazzy-rclcpp \
  ros-jazzy-rclpy \
  ros-jazzy-tf2 \
  ros-jazzy-tf2-geometry-msgs \
  ros-jazzy-cv-bridge \
  ros-jazzy-yaml-cpp-vendor \
  ros-jazzy-geometry-msgs \
  ros-jazzy-std-msgs \
  ros-jazzy-sensor-msgs \
  ros-jazzy-rclcpp-action \
  ros-jazzy-ament-index-cpp \
  python3-colcon-common-extensions


sudo apt install -y \
  python3-pip \
  python3-opencv \
  python3-numpy \
  python3-yaml \
  python3-setuptools \
  build-essential \
  cmake \
  libopencv-dev \
  libyaml-cpp-dev \
  libeigen3-dev

  sudo apt install -y \
  python3-pytest \
  ros-jazzy-ament-lint \
  ros-jazzy-ament-lint-auto


sudo apt update
sudo apt install -y python3-pip python3-dev git cmake protobuf-compiler libprotoc-dev

sudo apt update
sudo apt install -y git cmake build-essential python3-dev python3-pip
sudo apt-get update
sudo apt-get install libgtest-dev

sudo apt install python3.12-venv
