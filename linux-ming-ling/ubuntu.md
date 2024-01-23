# Ubuntu

## 新建用户并提升为root

1. 以 sudo 用户执行

```bash
adduser username
```

2. 提升权限

```bash
usermod -aG sudo usernamebash
```
