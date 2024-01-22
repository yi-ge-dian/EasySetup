# Linux 安装 oh-my-zsh

安装 zsh

```Bash
sudo apt install zsh
```

验证是否成功

```Bash
zsh --version
```

查看当前shell

```Bash
echo $SHELL
sudo chsh -s /bin/zsh
```

安装 oh-my-zsh

```bash
sh -c "$(wget https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"
```

更换主题，主题地址：

{% embed url="https://github.com/ohmyzsh/ohmyzsh/wiki/Themes" %}
themes
{% endembed %}

```bash
vim ~/.zshrc

# 修改主题bash
```

不关闭终端立即配置生效
