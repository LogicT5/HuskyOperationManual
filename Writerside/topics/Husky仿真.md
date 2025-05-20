# Husky仿真

安装包：

```Bash
    sudo apt-get install ros-noetic-fath-pivot-mount-description \
                         ros-noetic-flir-camera-description \
                         ros-noetic-lms1xx \
                         ros-noetic-velodyne-description \
                         ros-noetic-robot_localization \
                         ros-noetic-interactive-marker-twist-server \
                         ros-noetic-teleop-twist-joy \
                         ros-noetic-joint-trajectory-controller \
                         ros-noetic-teleop-twist-keyboard \
                         ros-noetic-amcl \
                         ros-noetic-gmapping \
                         ros-noetic-move-base \
                         ros-noetic-navfn \
                         ros-noetic-base-local-planner \
                         ros-noetic-dwa-local-planner \
                         ros-noetic-hector-gazebo-plugins \
                         ros-noetic-pointcloud-to-laserscan \
                         ros-noetic-map-server \
                         ros-noetic-realsense2-description 
```

下载Gazebo模型：

方法一、`sudo sh -c 'echo "deb http://packages.osrfoundation.org/gazebo/ubuntu trusty main" > /etc/apt/sources.list.d/gazebo'`

方法二、```$ wget -r -R "index\.html*" http://models.gazebosim.org/ ```，然后创建```cd ~ mkdir -p .gazebo/models```，把下载的模型文件夹放入就可以了。

方法三、执行以下命令
```bash
mkdir ~/.gazebo/models
cd ~/.gazebo/models/
wget http://file.ncnynl.com/ros/gazebo_models.txt
wget -i gazebo_models.txt
ls model.tar.g* | xargs -n1 tar xzvf
```