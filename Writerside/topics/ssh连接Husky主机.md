# ssh连接Husky主机

husky上已经安装了ssh服务器，可以直接连接。

## 连接设备
ssh连接可以通过无线子网和有线子网连接，需要注意的用来连接设备的IP。Husky的IP固定为192.168.1.11, 即无论你在哪个子网使用ssh连接，连接的IP固定为192.168.1.11。

## ssh连接Husky主机
```Bash
    ssh administrator@192.168.1.11
```
husky的密码为： clearpath

## 设置HuskyConcent命令
1. 下载ssh密码输入工具
    ```Bash
        sudo apt install sshpass
    ```
2. 设置HsukyConcent命令 <br/>
   向```~/.bashrc```中添加以下命令
    ```Bash
        alias HuskyConcent='sshpass -p "clearpath" ssh administrator@192.168.1.11'
    ```
    保存后，运行```source ~/.bashrc```
3. 测试<br/>
    在终端中运行命令```HuskyConcent```
    > 第一次使用 ```HuskyConcent``` 命令前，一定要手动ssh连接一次，以初始化本地的sshconfig。