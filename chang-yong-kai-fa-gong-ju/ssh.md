---
description: ssh连接和配置相关文档
---

# SSH

远程连接时，虚拟机需要 ssh 服务

```bash
sudo apt-get install openssh-server
sudo /etc/init.d/ssh startbash
```

生成密钥

```bash
ssh-keygen -t rsa
```

windows 下上传密钥到服务器

```powershell

Get-Content $ewnv:USERPROFILE\\\\Users\\\\computername\\\\.ssh\\\\id_rsa.pub | ssh username@ip "cat >> .ssh/authorized_keys"
# 或者
type C:\path\to\id_rsa.pub | ssh user@server_ip "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"
```

Linux 下上传密钥到服务器

```
ssh-copy-id -i .ssh/id_rsa.pub username@ip
```

服务器端设置仅通过密钥登陆

1. 修改服务器SSH配置文件`vim  /etc/ssh/sshd_config`
2.  修改为如下



    ```
    PubkeyAuthentication yes
    PasswordAuthentication no
    ```
3.  重启服务器SSH服服务



    ```
    PubkeyAuthentication yes
    PasswordAuthentication no
    ```
