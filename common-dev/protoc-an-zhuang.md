# Protoc 安装

安装go（备注：go版本需要1.16及以上）

{% content-ref url="../language/go-yu-yan-an-zhuang.md" %}
[go-yu-yan-an-zhuang.md](../language/go-yu-yan-an-zhuang.md)
{% endcontent-ref %}

Protocol buffer complier 安装

{% embed url="https://github.com/protocolbuffers/protobuf/releases" %}
proto
{% endembed %}

```bash
# linux
wget <https://github.com/protocolbuffers/protobuf/releases/download/v23.3/protoc-23.3-linux-x86_64.zip>
unzip protoc-23.3-linux-x86_64.zip -d $HOME/.local

# 修改 .bashrc or .zshrc
export PATH="$PATH:$HOME/.local/bin"

# mac
brew install protobuf
```

**Go plugins** for the protocol compiler

```bash
go install google.golang.org/protobuf/cmd/protoc-gen-go@v1.28
go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@v1.2

export PATH="$PATH:$(go env GOPATH)/bin"bash
```

protoc —go\_out=. message.proto&#x20;

protoc —go-grpc\_out=. message.proto

