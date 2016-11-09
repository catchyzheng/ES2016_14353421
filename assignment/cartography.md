# 在ROS基础上安装cartographer

姓名：郑铠奇

学号:14353421
## 1.安装依赖项
    sudo apt-get install -y google-mock libboost-all-dev  libeigen3-dev libgflags-dev libgoogle-glog-dev liblua5.2-dev libprotobuf-dev  libsuitesparse-dev libwebp-dev ninja-build protobuf-compiler python-sphinx  ros-indigo-tf2-eigen libatlas-base-dev libsuitesparse-dev liblapack-dev  
## 2.安装ceres solver
    git clone https://github.com/hitcm/ceres-solver-1.11.0.git
    cd ceres-solver-1.11.0
    mkdir build
    cd build
    cmake ..
    make –j
    sudo make install
## 3.安装cartographer
    git clone https://github.com/hitcm/cartographer.git
    cd cartographer/build
    cmake .. -G Ninja
    ninja
    ninja test

test结果如下：

![image](https://raw.githubusercontent.com/catchyzheng/ES2016_14353421/master/carto0.png)

之后再运行如下代码：

    sudo ninja install

install后结果如下：

![image](https://raw.githubusercontent.com/catchyzheng/ES2016_14353421/master/carto1.png)

安装cartographer——ros，进入catkin_ws的src目录下，执行以下指令：

    git clone https://github.com/hitcm/cartographer_ros.git  
在catkin_ws下执行指令：

    catkin_make

## 4.下载数据

选择较小的数据放入Download文件夹下

    wget https://storage.googleapis.com/cartographer-public-data/bags/backpack_2d/cartographer_paper_deutsches_museum.bag

下载完之后,根据实际设置路径,运行launch文件即可

    roslaunch cartographer_ros demo_backpack_2d.launch bag_filename:=${HOME}/Downloads/cartographer_paper_deutsches_museum.bag

运行效果大致如下：

![image](https://raw.githubusercontent.com/catchyzheng/ES2016_14353421/master/carto2.png)
