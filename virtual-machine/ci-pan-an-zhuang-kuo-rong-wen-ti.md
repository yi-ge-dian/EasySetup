# 磁盘安装扩容问题

为虚拟机装了50g，但实际上看只有30g左右，虚拟机只有一半左右的使用量。

1. df-h命令，查看磁盘使用情况。

<figure><img src="https://uestc.feishu.cn/space/api/box/stream/download/asynccode/?code=YzY0ZTJlMTQyZGI2NGVhZWFmMDI4ZGZmNGY1ZGZmZTVfQ2tVQ3I2S01mV2ZGeGFFZ0VpdUVuUGExTDlNRXA0UjZfVG9rZW46WXVLdmIyWDVEb2pDcXJ4dlk3NmNZdkwxblRlXzE3MDU5MjY1ODY6MTcwNTkzMDE4Nl9WNA" alt=""><figcaption><p>磁盘占用情况</p></figcaption></figure>

2. vgdisplay命令，来查看磁盘空闲情况。

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p>磁盘空闲情况</p></figcaption></figure>

3. 扩充磁盘

```bash
lvextend -l +100%FREE /dev/mapper/ubuntu--vg-ubuntu--lv
bashresize2fs /dev/mapper/ubuntu--vg-ubuntu--lv
```

4. 如果不存在磁盘空闲的情况，手动对磁盘扩容

安装图形化显示界面

```bash
apt install slim
```

安装桌面

```bash
apt install ubuntu-desktop
```

安装分区工具

```bash
apt install gparted
```

{% hint style="info" %}
如果sbin没有加入环境变量 export PATH=$PATH:/sbin
{% endhint %}

选中要扩充的磁盘，向右拉满，resize

继续执行 <mark style="color:green;">上面的虚拟机只有一半的使用量</mark> 的过程。
