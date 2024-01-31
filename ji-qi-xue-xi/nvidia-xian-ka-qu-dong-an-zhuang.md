---
description: Ubuntu系统下NVIDIA显卡驱动安装
---

# NVIDIA显卡驱动安装

## 1. 下载驱动

查看显卡型号

```bash
lspci | grep -i nvidia
```

从NVIDIA官网查看驱动版本号

{% embed url="https://www.nvidia.com/Download/index.aspx?lang=en-us" %}

安装驱动

```bash
# 在 Ubuntu 22.04 上, 直接使用该指令即可，后三位为官网上查到的对应版本号
sudo apt install nvidia-driver-535
# 重启系统
sudo reboot
```

## 2.  如何在容器中使用

安装NVIDIA Container Toolkit，官方文档：

{% embed url="https://docs.nvidia.com/datacenter/cloud-native/container-toolkit/latest/install-guide.html#next-steps" %}

安装

```bash
# 配置软件源
curl -fsSL https://nvidia.github.io/libnvidia-container/gpgkey | sudo gpg --dearmor -o /usr/share/keyrings/nvidia-container-toolkit-keyring.gpg \
  && curl -s -L https://nvidia.github.io/libnvidia-container/stable/deb/nvidia-container-toolkit.list | \
    sed 's#deb https://#deb [signed-by=/usr/share/keyrings/nvidia-container-toolkit-keyring.gpg] https://#g' | \
    sudo tee /etc/apt/sources.list.d/nvidia-container-toolkit.list

sudo apt-get update

sudo apt-get install -y nvidia-container-toolkit
```

docker配置

```
# 配置docker runtime
sudo nvidia-ctk runtime configure --runtime=docker
# 重启docker daemon
sudo systemctl restart docker
```

运行测试工作负载

```bash
sudo docker run --rm --runtime=nvidia --gpus all ubuntu nvidia-smi
```

