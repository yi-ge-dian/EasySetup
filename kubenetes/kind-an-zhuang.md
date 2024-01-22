# Kind 安装

kind 只是一个二进制文件，因此下载下来放到 bin 目录即可。

官方文档： [https://kind.sigs.k8s.io/](https://kind.sigs.k8s.io/)&#x20;

可以在 [Release](https://github.com/kubernetes-sigs/kind/releases) 页面找到bash相应的版本号，进行替换。

```bash
# For AMD64 / x86_64
[ $(uname -m) = x86_64 ] && curl -Lo ./kind <https://kind.sigs.k8s.io/dl/v0.20.0/kind-linux-amd64>
# For ARM64
[ $(uname -m) = aarch64 ] && curl -Lo ./kind <https://kind.sigs.k8s.io/dl/v0.20.0/kind-linux-arm64>
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind
```
