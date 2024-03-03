# 上传密钥

Linux 下上传密钥到服务器

```bash
ssh-copy-id -i .ssh/id_rsa.pub username@ipbash
```

windows 下上传密钥到服务器

```bash
Get-Content $ewnv:USERPROFILE\\\\Users\\\\computername\\\\.ssh\\\\id_rsa.pub | ssh username@ip "cat >> .ssh/authorized_keys"
# 或者
type C:\path\to\id_rsa.pub | ssh user@server_ip "mkdir -p ~/.ssh && cat >> ~/.ssh/authorized_keys"bash
```
