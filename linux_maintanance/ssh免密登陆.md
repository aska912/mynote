1. 在客户端生成一个公钥
```shell
# ssh-keygen  //一路回车
# ls ~/.ssh
authorized_keys  id_rsa  id_rsa.pub  known_hosts
```

2. 上传公钥至服务器
```shell
# ssh-copy-id -i ~/.ssh/id_rsa.pub xxx@srv_ip
```