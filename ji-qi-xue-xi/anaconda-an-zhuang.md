# Anaconda 安装

```bash
wget https://repo.anaconda.com/archive/Anaconda3-2023.09-0-Linux-x86_64.sh
bash Anaconda3-2023.09-0-Linux-x86_64.sh

vim .bashrc
export PATH=/root/anaconda3/bin:$PATH
```

创建环境

```bash
conda create -n env_name package_name
```

删除环境

```
conda remove --name env_name --all
```

