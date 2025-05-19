# Husky真机上开发

## 真机系统节点
这一节主要介绍如何修改真机系统节点的功能

### Husky模型
修改 `/opt/ros/indigo/share/husky_description/urdf` 中的文件

### 自定义工作区
![自定义工作区.png](自定义工作区.png)

进入Husky主控主机，编辑```/etc/ros/setup.bash ```
```Bash
    vim /etc/ros/setup.bash
```
添加新的工作区，比如husky_melodic_ws，向上文件中添加以下内容
```Bash
    source /home/administrator/husky_melodic_ws/devel/setup.bash
```

之后可正常在终端内使用```roslaunch```启动husky_melodic_ws中的节点。