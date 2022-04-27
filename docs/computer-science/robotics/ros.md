# ROS

## 环境

先在软件&更新，勾选`源代码`，选择一个国内的源。

> 安装指北 [http://wiki.ros.org/melodic/Installation/Ubuntu](http://wiki.ros.org/melodic/Installation/Ubuntu)

### 1. 添加源

```bash
sudo sh -c '. /etc/lsb-release && echo "deb http://mirrors.tuna.tsinghua.edu.cn/ros/ubuntu/ $DISTRIB_CODENAME main" > /etc/apt/sources.list.d/ros-latest.list'
```

### 2. 添加密钥

```bash
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key C1CF6E31E6BADE8868B172B4F42ED6FBAB17C654
```

### 3. 更新一下源

```bash
sudo apt update
```

### 4. 下载 ros

```bash
sudo apt install ros-melodic-desktop-full // 大概2g
```

### 5. 配置环境变量

```bash
echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
source ~/.bashrc
```

### 6. 一些其他的依赖

```bash
sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
```

### 7. 安装 proto

```sh
sudo apt install libprotobuf-dev protobuf-compiler
```

### 8. 安装 nng

```bash
git clone https://github.com/nanomsg/nng.git
cd nng
mkdir build
cd build
cmake ..
cmake --build .
```

### 9. 更新 cmake

```bash
wget https://cmake.org/files/v3.13/cmake-3.13.5.tar.gz
tar zxvf cmake-3.13.5.tar.gz
cd cmake-3.13.5
./configure
make
sudo make install
```

### 10. 安装 json

```bash
git clone https://github.com/nlohmann/json.git
cd json
mkdir build
cd build
cmake .. -DJSON_buildTest=ON
cmake --build .
```

### 11. 安装 pcap

```bash
sudo apt install libpcap-dev
```

### 12. 安装 gtsam

```bash
git clone https://github.com/borglab/gtsam.git
cd gtsam
mkdir build
cd build
cmake ..
make -j4
sudo make install
```

### 13. 创建 ROS 工作空间

```bash
mkdir -p ~/catkin_ws/src
cd ~/catkin_ws/src
catkin_init_workspace
cd ~/catkin_ws/
catkin_make -jl
source devel/setup.bash
echo $ROS_PACKAGE_PATH
```
