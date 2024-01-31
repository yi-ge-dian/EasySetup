# Ubuntu

## 新建用户并提升为root

1. 以 sudo 用户执行

```bash
adduser username
```

2. 提升权限

```bash
usermod -aG sudo username
```

3. 加入docker组（使用docker时不再需要sudo，并且vscode的Dev Containers插件能正常使用）

```bash
sudo usermod -aG docker <username>
```
