# 外置PC上的协同开发

## 系统时间同步
参照Ubuntu系统时间同步的方法，以下介绍一种方法，不可行则尝试其他方法。
### 使用 systemd-timesyncd（默认方案）
Ubuntu 20.04+ 默认启用了 systemd-timesyncd，只需开启 NTP 功能即可：
```Bash
# 启用 NTP 同步
sudo timedatectl set-ntp true

# 重启 timesyncd 服务（通常不必）
sudo systemctl restart systemd-timesyncd

# 检查服务状态
sudo systemctl status systemd-timesyncd
````
如果你有自定义的 NTP 服务器，可编辑 /etc/systemd/timesyncd.conf，取消注释并填写：
```ini
[Time]
NTP=ntp1.example.com ntp2.example.com
FallbackNTP=0.ubuntu.pool.ntp.org 1.ubuntu.pool.ntp.org
```
修改后重启服务：
```Bash
sudo systemctl restart systemd-timesyncd
```

