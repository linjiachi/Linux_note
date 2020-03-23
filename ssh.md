## ssh 遠端主機登入
> 在SSH中，有一台 server(被連接的)，和一台 client(連別人的)

> 需要用到兩台虛擬機 server->VM1，client->VM2

* 參考：https://blog.gtwang.org/linux/linux-ssh-public-key-authentication/

* VM1、VM2 (要用root權限下執行)
```shell
  systemctl stop firewalld
  systemctl disable firewalld
  vim /etc/selinux/config
    SELINUX=disabled -> reboot
```
* VM1
<img src="https://github.com/linjiachi/Linux_note/blob/109-1/image/1.PNG">

* VM2
```
  mkdir -p ~/.ssh
  chmod 700 ~/.ssh
  ssh-keygen
  ssh-copy-id root@192.168.56.101 (VM1 的ip)
  ssh user@192.168.56.101
  exit
  echo 1 > test
  scp test root@192.168.56.107:/home/user/
```
