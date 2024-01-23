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
```

Linux 下上传密钥到服务器

```
ssh-copy-id -i .ssh/id_rsa.pub username@ip
```









