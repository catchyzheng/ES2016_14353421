# lab5 ROS安装配置

## 1.确认Ubuntu的配置
由于虚拟机本身软件仓库的设置就已经满足要求了，所以这一步可以省略。
## 2.设置source.list
### 2.1 在命令行输入如下指令
    sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
### 2.2 设置keys
    sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 0xB01FA116
## 3. 安装
### 3.1 首先更新指令
    sudo apt-get update
### 3.2 选择安装全部包的指令
    sudo apt-get install ros-jade-desktop-full
## 4.初始化rosdep
sudo rosdep init
rosdep update
## 5. 设置环境
echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
source ~/.bashrc


// If you just want to change the environment of your current shell, you can type:
source /opt/ros/jade/setup.bash
## 6. 安装rosinstall
    sudo apt-get install python-rosinstall
## 7.获取source源码
    apt-get source ros-jade-laser-pipeline
## 8.验证ROS的安装
可以先查找ros的软件包相关信息

    rospack find stereo_msgs

可以找到文件包。

![image](https://raw.githubusercontent.com/catchyzheng/ES2016_14353421/master/ros1.png)

然后可以查看环境变量

    export | grep ROS
![image](https://raw.githubusercontent.com/catchyzheng/ES2016_14353421/master/ros2.png)

可以检查ros系统情况

    roswtf
![image](https://raw.githubusercontent.com/catchyzheng/ES2016_14353421/master/ros3.png)

至此ROS的验证基本完成了。
