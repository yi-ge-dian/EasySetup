# 虚拟机代理脚本

把下面的脚本放到 .zshrc 或者 .bashrc 中，source 一下，使用命令即可

把 ip 换为自己的主机的 ip

```
proxy(){
    export http_proxy="http://ip:7890"
    export https_proxy=$http_proxy
    export socks5_proxy="socks5://ip:7890"
    echo "HTTP Proxy on"
}
noproxy(){
    unset http_proxy
    unset https_proxy
    echo "HTTP Proxy off"
}
```
