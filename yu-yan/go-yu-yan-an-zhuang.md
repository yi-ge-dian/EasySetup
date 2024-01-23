# Go语言安装

通过 gvm 来安装 go 语言，可以控制 go 的版本。

```bash
bash < <(curl -s -S -L https://raw.githubusercontent.com/moovweb/gvm/master/binscripts/gvm-installer)
```

安装完成后，重启终端或者运行以下命令，使GVM生效

```bash
source ~/.gvm/scripts/gvm
```

查看安装的go版本列表

```bash
gvm list
```

安装 go 的版本（先通过 apt install go 安装一个低版本作为工具才可以）

```bash
gvm install go1.21.1
```

使用某个 go 版本

```bash
gvm use go1.21.1
```
