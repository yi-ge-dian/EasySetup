# SSH



服务器端设置仅通过密钥登陆

1. 修改服务器SSH配置文件`vim  /etc/ssh/sshd_config`
2.  修改为如下



    ```
    PubkeyAuthentication yes
    PasswordAuthentication no
    ```
3.  重启服务器SSH服服务



    ```bash
    sudo systemctl restart ssh
    ```
