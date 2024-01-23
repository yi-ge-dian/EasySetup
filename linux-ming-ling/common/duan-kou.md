# 端口

## ufw

防火墙是否开放

```bash
sudo ufw status | grep 端口
```

开放端口

```bash
sudo ufw allow 端口号
```

## lsof

查看端口是否被占用

lsof （推荐） lsof（list open files）是一个查看当前系统文件的工具。在linux环境下，任何事物都以文件的形式存在，包括网络连接和硬件。

```bash
# 查看80端口占用
lsof -i:80
# kill 进程kill -9 {pid}
```

特点：

* 适用性广，centos，ubuntu，macOS都ok的。
* 会列出进程PID，方便kill。

## netstat

netstat  命令用于显示各种网络相关信息，如网络连接，路由表，接口状态 (Interface Statistics)，masquerade 连接，多播成员 (Multicast Memberships) 等等

```bash
# 查看8080端口占用
netstat -anp | grep 8080
```

| netstat 常用参数 | 解释                   |
| ------------ | -------------------- |
| -a           | 列出所有端口               |
| -l           | 仅列出监听端口（默认）          |
| -n           | 拒绝显示别名，能显示数字的全部转化成数字 |
| -p           | 显示建立相关链接的程序名/pid     |
| -t           | (tcp)仅显示tcp相关选项      |
| -u           | (udp)仅显示udp相关选项      |

{% hint style="warning" %}
以上命令都是查询当前用户的进程，要查看所有进程，需加上 sudo，或者登录 root 用户。
{% endhint %}

```bash
netstat -ntlp
```
