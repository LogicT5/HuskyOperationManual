# Husky连接以太网

Husky设置了局域网，且内部设备为静态ip。所有让Husky连接到以太网的方式有限：
1、连接网线
2、通过子网中的联网设备(此设备需要至少两个网口)进行转发。原理为手动设置路由。

## route命令设置路由
在Husky终端中使用以下命令：
```Bash
    # 列出路由表
    route -n 
```
![Husky_route.png](Husky_route.png "Huaky 默认路由表")

以外部连接的PC(以下称外置PC)为例，此PC有一个网线接口，一个无线网卡。<br/>
以下设置以网线连接Husky，wifi连接以太网为例。<br/>
PC在Husky子网内部的IP为192.168.1.100；wifi的IP为192.168.1.104。
>这是一个复杂情况的示例，此PC在Husky子网内部的IP和wifi的IP都是192.168.1.0/24网段，但是在两个不同的物理接口上。
>注意区分以下：<br/>
>Husky子网内部的IP: 192.168.1.100 接口: enp0s31f6, 不能连接以太网<br/>
>wifi的IP: 192.168.1.104 接口: wlp4s0, 能连接以太网<br/>

### 使用```ifconfig```确认外置PC的网络连接       [外置PC中]
![外置PC_ifconfig_1.png](外置PC_ifconfig_1.png)

说明：
* **enp0s31f6** , **wlp4s0** 为网络物理接口； **lo** 为回环检测接口(本例中不涉及)
* **inet** 为对应网口的IP； **netmask** 为对应网口的网络掩码。

### 使用```route -n```确认外置PC的路由表       [外置PC中]





![sysctl.png](sysctl.png)