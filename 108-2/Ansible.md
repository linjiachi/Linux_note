* [自動化管理](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E8%87%AA%E5%8B%95%E5%8C%96%E7%AE%A1%E7%90%86)
* [Ansible](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#ansible)
    - [環境設置](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%92%B0%E5%A2%83%E8%A8%AD%E7%BD%AE)
    - [ansible 安裝](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#ansible-%E5%AE%89%E8%A3%9D)
        - [`command` 無法執行系統環境變數或特殊指令](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#command-%E7%84%A1%E6%B3%95%E5%9F%B7%E8%A1%8C%E7%B3%BB%E7%B5%B1%E7%92%B0%E5%A2%83%E8%AE%8A%E6%95%B8%E6%88%96%E7%89%B9%E6%AE%8A%E6%8C%87%E4%BB%A4)
        - [`shell` 可以解決 `command` 無法執行系統環境變數或特殊指令的問題](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#shell-%E5%8F%AF%E4%BB%A5%E8%A7%A3%E6%B1%BA-command-%E7%84%A1%E6%B3%95%E5%9F%B7%E8%A1%8C%E7%B3%BB%E7%B5%B1%E7%92%B0%E5%A2%83%E8%AE%8A%E6%95%B8%E6%88%96%E7%89%B9%E6%AE%8A%E6%8C%87%E4%BB%A4%E7%9A%84%E5%95%8F%E9%A1%8C)
        - [`creates` 和 `removes` 比較](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#creates-%E5%92%8C-removes-%E6%AF%94%E8%BC%83)
        - [當 SSH port 不是 22 port](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%95%B6-ssh-port-%E4%B8%8D%E6%98%AF-22-port)
    - [ansible 用法](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#ansible-%E7%94%A8%E6%B3%95)
        - [格式](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E6%A0%BC%E5%BC%8F)
    - [常用模組](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E5%B8%B8%E7%94%A8%E6%A8%A1%E7%B5%84)
        - [`command`：預設的模組，執行指令的命令](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#command%E9%A0%90%E8%A8%AD%E7%9A%84%E6%A8%A1%E7%B5%84%E5%9F%B7%E8%A1%8C%E6%8C%87%E4%BB%A4%E7%9A%84%E5%91%BD%E4%BB%A4)
        - [`shell`：較複雜的指令建議使用此模組](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#shell%E8%BC%83%E8%A4%87%E9%9B%9C%E7%9A%84%E6%8C%87%E4%BB%A4%E5%BB%BA%E8%AD%B0%E4%BD%BF%E7%94%A8%E6%AD%A4%E6%A8%A1%E7%B5%84)
        - [`ansible-doc`：模組的說明文件](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#ansible-doc%E6%A8%A1%E7%B5%84%E7%9A%84%E8%AA%AA%E6%98%8E%E6%96%87%E4%BB%B6)
        - [`script`：在遠端寫一個腳本，在 Server 端執行](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#script%E5%9C%A8%E9%81%A0%E7%AB%AF%E5%AF%AB%E4%B8%80%E5%80%8B%E8%85%B3%E6%9C%AC%E5%9C%A8-server-%E7%AB%AF%E5%9F%B7%E8%A1%8C)
        - [`copy`：複製](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#copy%E8%A4%87%E8%A3%BD)
        - [`fetech`：從遠端擷取檔案至本地端](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#fetech%E5%BE%9E%E9%81%A0%E7%AB%AF%E6%93%B7%E5%8F%96%E6%AA%94%E6%A1%88%E8%87%B3%E6%9C%AC%E5%9C%B0%E7%AB%AF)
        - [`file`：針對檔案進行操作](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#file%E9%87%9D%E5%B0%8D%E6%AA%94%E6%A1%88%E9%80%B2%E8%A1%8C%E6%93%8D%E4%BD%9C)
            - [重點補充](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E9%87%8D%E9%BB%9E%E8%A3%9C%E5%85%85)
        - [`yum`：模組安裝](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#yum%E6%A8%A1%E7%B5%84%E5%AE%89%E8%A3%9D)
        - [`service`：針對模組在開機時啟動與否](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#service%E9%87%9D%E5%B0%8D%E6%A8%A1%E7%B5%84%E5%9C%A8%E9%96%8B%E6%A9%9F%E6%99%82%E5%95%9F%E5%8B%95%E8%88%87%E5%90%A6)
        - [`user`：創建使用者](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#user%E5%89%B5%E5%BB%BA%E4%BD%BF%E7%94%A8%E8%80%85)
        - [`group`：創建群組](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#group%E5%89%B5%E5%BB%BA%E7%BE%A4%E7%B5%84)
* [ansible-playbook - ansible 的腳本檔](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#ansible-playbook---ansible-%E7%9A%84%E8%85%B3%E6%9C%AC%E6%AA%94)
  - [範例一：Hello World](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E4%B8%80hello-world)
  - [範例二：自動產生網頁](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E4%BA%8C%E8%87%AA%E5%8B%95%E7%94%A2%E7%94%9F%E7%B6%B2%E9%A0%81)
  - [範例三：複製更改過的配置檔，要增加 `notify`、`handlers`](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E4%B8%89%E8%A4%87%E8%A3%BD%E6%9B%B4%E6%94%B9%E9%81%8E%E7%9A%84%E9%85%8D%E7%BD%AE%E6%AA%94%E8%A6%81%E5%A2%9E%E5%8A%A0-notifyhandlers)
  - [範例四：LINE Notify](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E5%9B%9Bline-notify)
  - [範例五：`tags` 標籤，執行某一項工作](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E4%BA%94tags-%E6%A8%99%E7%B1%A4%E5%9F%B7%E8%A1%8C%E6%9F%90%E4%B8%80%E9%A0%85%E5%B7%A5%E4%BD%9C)
  - [範例六：`Setup` 模組可以看系統配置資訊](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E5%85%ADsetup-%E6%A8%A1%E7%B5%84%E5%8F%AF%E4%BB%A5%E7%9C%8B%E7%B3%BB%E7%B5%B1%E9%85%8D%E7%BD%AE%E8%B3%87%E8%A8%8A)
  - [範例七：parameter 透過 `{{}}` 包著](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E4%B8%83parameter-%E9%80%8F%E9%81%8E--%E5%8C%85%E8%91%97)
  - [範例八：如果要安裝兩個一樣的 package，可以取不同名字](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E5%85%AB%E5%A6%82%E6%9E%9C%E8%A6%81%E5%AE%89%E8%A3%9D%E5%85%A9%E5%80%8B%E4%B8%80%E6%A8%A3%E7%9A%84-package%E5%8F%AF%E4%BB%A5%E5%8F%96%E4%B8%8D%E5%90%8C%E5%90%8D%E5%AD%97)
  - [範例九：更改 hostname](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E4%B9%9D%E6%9B%B4%E6%94%B9-hostname)
  - [範例十：如果劇本設定和手動設定，手動>劇本](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E5%8D%81%E5%A6%82%E6%9E%9C%E5%8A%87%E6%9C%AC%E8%A8%AD%E5%AE%9A%E5%92%8C%E6%89%8B%E5%8B%95%E8%A8%AD%E5%AE%9A%E6%89%8B%E5%8B%95%E5%8A%87%E6%9C%AC)
  - [範例十一：`fqdn`：`Setup` 模組中的變數，完整的網域名字](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E5%8D%81%E4%B8%80fqdnsetup-%E6%A8%A1%E7%B5%84%E4%B8%AD%E7%9A%84%E8%AE%8A%E6%95%B8%E5%AE%8C%E6%95%B4%E7%9A%84%E7%B6%B2%E5%9F%9F%E5%90%8D%E5%AD%97)
  - [範例十二：`vars_files` 引入腳本來傳遞變數](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E5%8D%81%E4%BA%8Cvars_files-%E5%BC%95%E5%85%A5%E8%85%B3%E6%9C%AC%E4%BE%86%E5%82%B3%E9%81%9E%E8%AE%8A%E6%95%B8)
  - [範例十三：自定義網頁伺服器](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E5%8D%81%E4%B8%89%E8%87%AA%E5%AE%9A%E7%BE%A9%E7%B6%B2%E9%A0%81%E4%BC%BA%E6%9C%8D%E5%99%A8)
  - [範例十四：在 playbook 設定條件 `when`](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E5%8D%81%E5%9B%9B%E5%9C%A8-playbook-%E8%A8%AD%E5%AE%9A%E6%A2%9D%E4%BB%B6-when)
  - [範例十五：`with_items` 一次執行多件事](https://github.com/linjiachi/Linux_note/blob/master/108-2/Ansible.md#%E7%AF%84%E4%BE%8B%E5%8D%81%E4%BA%94with_items-%E4%B8%80%E6%AC%A1%E5%9F%B7%E8%A1%8C%E5%A4%9A%E4%BB%B6%E4%BA%8B)
* [Roles]()
  - [Roles 是什麼?]()
  - [如何使用 Roles]()
    - [Galaxy 是什麼?]()
    - [`ansible-galaxy` 是什麼?]()
  - [環境介紹]()
  - [範例一：可以從 [Galaxy](https://galaxy.ansible.com/) 中找尋套件 - Apache]()
---
# 自動化管理
* 常見的自動化管理工具有ansible、puppet、saltstack
# Ansible
* 由 python 所撰寫的軟體
* 可以運用在管理中小型規模的機器
* 不需要安裝代理人 agent，主控端和被控端管理透過 ssh 連線
## 環境設置
1. 準備三台虛擬機：到設定去手動設定 Network -> Host-Only -> IPv4 Method -> Address
* 更改 hostname 指令：`hostnamectl set-hostname vm1`


-|主控端|被控端|被控端
-|:-:|:-:|:-:
hostname|vm1|vm2|vm3
IP|192.168.56.101|192.168.56.102|192.168.56.103
Address|192.168.56.101|192.168.56.102|192.168.56.103
Network|255.255.255.0|255.255.255.0|255.255.255.0
Getway|10.0.2.2|10.0.2.2|10.0.2.2

2. 到 etc/hosts 增加三台虛擬機的 IP hostname
3. 三台設定 [ssh](https://github.com/linjiachi/Linux_note/blob/108-1/ssh.md) 免密登入
* 藉由 ssh 的遠端檔案傳輸剛設定的 /etc/hosts：`scp /etc/hosts root@vm1:/etc/hosts`
```sh
[root@vm2 ~]# scp /etc/hosts root@vm1:/etc/hosts
hosts                                         100%  215    55.6KB/s   00:00
[root@vm2 ~]# scp /etc/hosts root@vm3:/etc/hosts
hosts                                         100%  215    22.6KB/s   00:00
```
* `ssh root@vm1 ifconfig`
> 測試 ssh 是否成功
```sh
[root@vm2 ~]# ssh root@vm1 ifconfig
docker0: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
        inet 172.17.0.1  netmask 255.255.0.0  broadcast 172.17.255.255
        ether 02:42:09:b4:b5:c2  txqueuelen 0  (Ethernet)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

enp0s3: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.0.2.15  netmask 255.255.255.0  broadcast 10.0.2.255
        inet6 fe80::6544:effb:46f5:805f  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:a8:d8:1f  txqueuelen 1000  (Ethernet)
        RX packets 1842  bytes 1685415 (1.6 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 1442  bytes 128598 (125.5 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

enp0s8: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.56.101  netmask 255.255.255.0  broadcast 192.168.56.255
        inet6 fe80::a405:e8db:4a2f:96ba  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:0f:ba:f0  txqueuelen 1000  (Ethernet)
        RX packets 24042  bytes 2284929 (2.1 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 21303  bytes 1641238 (1.5 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

enp0s9: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        ether 08:00:27:18:ed:c9  txqueuelen 1000  (Ethernet)
        RX packets 3  bytes 276 (276.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 533  bytes 87894 (85.8 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 31620  bytes 1860583 (1.7 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 31620  bytes 1860583 (1.7 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

virbr0: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
        inet 192.168.122.1  netmask 255.255.255.0  broadcast 192.168.122.255
        ether 52:54:00:c3:58:e8  txqueuelen 1000  (Ethernet)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```
## ansible 安裝
> 以下指令由超級使用者執行
1. 在**主控端**(Ansible Managment Node)和**被控端**安裝 ansible
```sh
yum install -y ansible
```
2. 在 `/etc/ansible/hosts` 設置群組 
```md
[app0]  # 本機
192.168.56.101

[app1]
192.168.56.102

[app2]
192.168.56.103

[myapp]
192.168.56.101
192.168.56.102
192.168.56.103
```
3. 針對 myapp 群組進行操作 \
`ansible myapp -m command -a "ifconfig enp0s8"`：
    - `-m`：module
    - `command`：為預設模組
    - `c`：cheak，檢查指令是否正確
    - `-v`,`-vv`,`-vvv`：顯示詳細過程(由少到多)
```sh
[root@vm1 ~]# ansible myapp -m command -a "ifconfig enp0s8"
192.168.56.102 | SUCCESS | rc=0 >>
enp0s8: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.56.102  netmask 255.255.255.0  broadcast 192.168.56.255
        inet6 fe80::a405:e8db:4a2f:96ba  prefixlen 64  scopeid 0x20<link>
        inet6 fe80::65a7:2a8d:e87f:7d5f  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:46:2b:8c  txqueuelen 1000  (Ethernet)
        RX packets 55390  bytes 5383436 (5.1 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 52505  bytes 4073501 (3.8 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

192.168.56.103 | SUCCESS | rc=0 >>
enp0s8: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.56.103  netmask 255.255.255.0  broadcast 192.168.56.255
        inet6 fe80::7019:6913:1b5e:e488  prefixlen 64  scopeid 0x20<link>
        inet6 fe80::a405:e8db:4a2f:96ba  prefixlen 64  scopeid 0x20<link>
        inet6 fe80::65a7:2a8d:e87f:7d5f  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:9f:c6:d7  txqueuelen 1000  (Ethernet)
        RX packets 4387  bytes 814493 (795.4 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 5073  bytes 1464688 (1.3 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

192.168.56.101 | SUCCESS | rc=0 >>
enp0s8: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.56.101  netmask 255.255.255.0  broadcast 192.168.56.255
        inet6 fe80::a405:e8db:4a2f:96ba  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:0f:ba:f0  txqueuelen 1000  (Ethernet)
        RX packets 59049  bytes 5620487 (5.3 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 52143  bytes 4454012 (4.2 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```
* `ansible app2 -m ping`：查看 ansible 與被控端之前的通訊
```md
[root@vm1 ~]# ansible app2 -m ping
192.168.56.103 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```
* `ansible-doc 模組名稱`
    - `ansible-doc -l | grep command`：`ansible-doc -l`：用來顯示可以用的模組
```sh
[root@vm1 ~]# ansible-doc -l | grep command
aireos_command                            Run commands on remote devices ru...
aruba_command                             Run commands on remote devices ru...
asa_command                               Run arbitrary commands on Cisco A...
bigip_command                             Run arbitrary command on F5 devic...
ce_command                                Run arbitrary command on HUAWEI C...
ce_netconf                                Run an arbitrary netconf command ...
cnos_command                              Execute a single command on devic...
.
.
sros_command                              Run commands on remote devices ru...
vyos_command                              Run one or more commands on VyOS ...
vyos_system                               Run `set system` commands on VyOS...
win_command                               Executes a command on a remote Wi...
win_psexec                                Runs commands (remotely) as anoth...
win_shell                                 Execute shell commands on target ...
```
* `ansible-doc -l | wc -l`：計算所有已安裝的模組文檔行數
    - `wc`：word count
```sh
[root@vm1 ~]# ansible-doc -l | wc -l
1378
```
### `command` 無法執行系統環境變數或特殊指令
* `env | grep HOSTNAME`：查詢系統環境變數
* `ansible app1 -m command -a "echo $HOSTNAME"`
```sh
# 第一台虛擬機(192.168.56.101)
[root@vm1 ~]# HOSTNAME=centos7-1
[root@vm1 ~]# echo $HOSTNAME
centos7-1
[root@vm1 ~]# env | grep HOSTNAME
HOSTNAME=centos7-1
```
```sh
# 第二台虛擬機(192.168.56.102)
[root@vm2 ~]# HOSTNAME=centos7-2
[root@vm2 ~]# echo $HOSTNAME
centos7-2
[root@vm2 ~]# env | grep HOSTNAME
HOSTNAME=centos7-2
```
```sh
# 第一台虛擬機(192.168.56.101)     
                # app1 = 192.168.56.102  
[root@vm1 ~]# ansible app1 -m command -a "echo $HOSTNAME"
192.168.56.102 | SUCCESS | rc=0 >>
centos7-1      # 不是 centos7-2
```
```sh
# 第二台虛擬機(192.168.56.102)
                # app1 = 192.168.56.101
[root@vm2 ~]# ansible app1 -m command -a "echo $HOSTNAME"
192.168.56.101 | SUCCESS | rc=0 >>
centos7-2      # 不是 centos7-1
```
> 結論：`command`可以遠端執行指令，但無法執行系統環境變數或特殊指令
### `shell` 可以解決 `command` 無法執行系統環境變數或特殊指令的問題
```sh
# 第二台虛擬機
[root@vm2 ~]# ansible app1 -m shell -a "echo hi > /tmp/a.txt"
192.168.56.101 | SUCCESS | rc=0 >>

```
```sh
# 第一台虛擬機
[root@vm1 /]# cd tmp/
[root@vm1 tmp]# ls
a.txt
ssh-oRT4rKTPM3Ol
systemd-private-4a87598168a345f88a3963a52bc1c45f-bolt.service-BCHR7u
systemd-private-4a87598168a345f88a3963a52bc1c45f-chronyd.service-xwzaJh
.
.
[root@vm1 tmp]# cat a.txt
hi
```
* `ansible app1 -m command -a "chdir=/tmp ls"`：先切換到 /tmp 資料夾，再執行命令
	- `chdir`：切換資料夾
```sh
[root@vm2 ~]# ansible app1 -m command -a "chdir=/tmp ls"
192.168.56.101 | SUCCESS | rc=0 >>
ansible_aI3lkM
a.txt
ssh-oRT4rKTPM3Ol
systemd-private-4a87598168a345f88a3963a52bc1c45f-bolt.service-BCHR7u
systemd-private-4a87598168a345f88a3963a52bc1c45f-chronyd.service-xwzaJh
.
.
```
### `creates` 和 `removes` 比較
* `ansible-doc -s module`
    - `-s`：較精簡的方式
* `ansible app1 -m command -a "creates=/tmp/a.txt ls"`：
```sh
# 1
[root@vm2 ~]# ansible app1 -m command -a "creates=/tmp/a.txt ls"
192.168.56.101 | SUCCESS | rc=0 >>
skipped, since /tmp/a.txt exists
# 因為在 vm1 的 /tmp 資料夾中已經存在 a.txt，故不會執行接下來的 ls

# 2
[root@vm2 ~]# ansible app1 -m command -a "creates=/tmp/b.txt ls"
192.168.56.101 | SUCCESS | rc=0 >>
anaconda-ks.cfg
ca.csr
ca.key
initial-setup-ks.cfg
# 因為在 vm1 的 /tmp 資料夾沒有 b.txt，故 ls 會執行
```
> `creates`：要創建 /tmp/a.txt，若執行可以成功，就執行 ls 指令；若執行失敗，就不會執行 ls 指令
* `ansible app1 -m command -a "removes=/tmp/a.txt pwd"`
```sh
# 1
[root@vm2 ~]# ansible app1 -m command -a "removes=/tmp/a.txt pwd"
192.168.56.101 | SUCCESS | rc=0 >>
/root
# 因為在 vm1 的 /tmp 資料夾下有存在 a.txt，故可以執行刪除指令，並且執行 pwd

# 2
[root@vm2 ~]# ansible app1 -m command -a "removes=/tmp/b.txt pwd"
192.168.56.101 | SUCCESS | rc=0 >>
skipped, since /tmp/b.txt does not exist
#  因為在 vm1 的 /tmp 資料夾下沒有 b.txt，故不能執行刪除指令且不能執行 pwd
```
> `removes`：要刪除 /tmp/a.txt，若檔案存在可以刪除，就執行 pwd 指令；若檔案不存在，則不會繼續執行指令
### 當 SSH port 不是 22 port
1. 在 vm1 下 /etc/ssh/sshd_config 手動更改 port：
```sh
# If you want to change the port on a SELinux system, you have to tell
# SELinux about this change.
# semanage port -a -t ssh_port_t -p tcp #PORTNUMBER
#
#Port 22    # 修改成 Port 2222
```
2. 重新啟動 sshd：`systemctl restart sshd`
3. 因為 port 更改，所以無法執行成功
```sh
[root@vm1 ~]# ansible app2 -m command -a "pwd"
192.168.56.103 | UNREACHABLE! => {
    "changed": false,
    "msg": "Failed to connect to the host via ssh: ssh: connect to host 192.168.56.103 port 2222: Connection refused\r\n",
    "unreachable": true
}
```
#### 解決：
1. 先檢查 app2群組 是否關閉防火牆：`systemctl disable firewalld`
2. `ssh root@vm3 -p 2222`：ssh 連線指定 port
3. 在 vm3 下 /etc/ansible/hosts，手動在 ip 後加上 2222 port
```sh
[app0]
192.168.56.103:2222

[app1]
192.168.56.101

[app2]
192.168.56.102

[myapp]
192.168.56.101
192.168.56.102
192.168.56.103:2222
```
4. 可測試是否能連上：`ansible app2 -m command -a "pwd"`
```sh
[root@vm1 ~]# ansible app2 -m command -a "pwd"
192.168.56.103 | SUCCESS | rc=0 >>
/root
```
## ansible 用法
* `ansible all --list-hosts`：列出目前所有在 /etc/ansible/hosts 下所有管理的機器
* `ansible app1 --list-hosts`：列出 app1群組 所管理的機器
### 格式
* `192.168.56.[01:10]`：代表 `192.168.56.01`~`192.168.56.10`
## 常用模組
### `command`：預設的模組，執行指令的命令
* 常用選項
	- `-a`：模組的參數
```sh
ansible app1 -m command -a "rpm -e httpd"	# 移除 httpd 套件
ansible app1 -m command -a "rpm -q httpd"	# 查詢是否有安裝 httpd 套件
ansible app1 -m command -a "systemctl status httpd"	# 重新啟動 httpd 服務

# 查詢系統是否已經存在 user 使用者
ansible app1 -m command -a "getent passwd user"	# 以 "x" 隱藏密碼
						   "getent shadow user"	# 查看加密後的密碼
						   "getent group mary"	# 判斷 mary 群組是否存在
```
```sh
[root@vm1 ~]# ansible app1 -m command -a "getent passwd user"
192.168.56.102 | SUCCESS | rc=0 >>
user:x:1000:1000:user:/home/user:/bin/bash
```
### `shell`：較複雜的指令建議使用此模組
* `creates`：當檔案存在時，不執行後面的指令
```sh
ansible app1 -m command -a "creates=/tmp/a.txt ls"
```
* `removes`：當檔案存在時，執行後面的指令
```sh
ansible app1 -m command -a "removes=/tmp/a.txt pwd"
```
### `ansible-doc`：模組的說明文件
* `ansible-doc command`：查詢 `command` 模組的說明
* `ansible-doc -l`：列出所有的模組
* `ansible-doc -l | wc -l`：計算所有的模組的行數
	- `wc`：word count
	- `-l`：line
### `script`：在遠端寫一個腳本，在 Server 端執行
1. 先在 Client 端寫一個 a.sh 腳本
```sh
#!/usr/bin/bash

echo "hello world"
hostname
```
2. 測試執行
```sh
ansible app1 -m script -a a.sh
```
### `copy`：複製
#### 範例
1. 在 vm1 執行對 app1群組 新建 /data 資料夾
```sh
ansible app1 -m command -a "mkdir /data -p"
```
* `-p`：如果資料夾已存在就覆蓋
2. 在 vm1 的 /home/user 下新建一個 hi.txt
```sh
[root@vm1 user]# echo "hi" > hi.txt
``` 
3. 將 vm1 hi.txt 複製到 app1群組 並改名為 hello.txt \
 (前提：在 app1群組中的 /data 資料夾中，已存在 hello.txt 檔案)
```sh
ansible app1 -m copy -a "src=hi.txt dest=/data/hello.txt backup=yes owner=user group=user mode=600"

# src：來源檔案
# dest：目的檔案
# backup=yes：將原本檔案重新命名，然後貼上新的檔案
# owner：擁有者權限
# group：群組
# mode：讀寫的模式
```
```sh
[root@vm1 user]# ansible app1 -m copy -a "src=hi.txt dest=/home/user/data/hello.txt backup=yes owner=user group=user mode=600"
192.168.56.102 | SUCCESS => {
    "backup_file": "/home/user/data/hello.txt.9983.2020-06-28@12:56:15~",
    "changed": true,
    "checksum": "55ca6286e3e4f4fba5d0448333fa99fc5a404a73",
    "dest": "/home/user/data/hello.txt",
    "gid": 1000,
    "group": "user",
    "md5sum": "764efa883dda1e11db47671c4a3bbd9e",
    "mode": "0600",
    "owner": "user",
    "size": 3,
    "src": "/root/.ansible/tmp/ansible-tmp-1593320174.16-222670022695633/source",
    "state": "file",
    "uid": 1000
}
```
* 查看 vm2
```sh
# 指令執行前
[root@vm2 data]# ls
hello.txt
[root@vm2 data]# cat hello.txt
111

# 指令執行後
[root@vm2 data]# ls
hello.txt  hello.txt.9983.2020-06-28@12:56:15~
[root@vm2 data]# cat hello.txt
hi
[root@vm2 data]# cat hello.txt.9983.2020-06-28@12\:56\:15~
111
```
### `fetech`：從遠端擷取檔案至本地端
* `ansible app1 -m fetch -a "src=/home/user/data/hello.txt dest=/root"`：到 app1群組 找到/home/user/data/hello.txt，拷貝回本地的/root資料夾
```sh
[root@vm1 user]# ansible app1 -m fetch -a "src=/home/user/data/hello.txt dest=/root"
192.168.56.102 | SUCCESS => {
    "changed": true,
    "checksum": "55ca6286e3e4f4fba5d0448333fa99fc5a404a73",
    "dest": "/root/192.168.56.102/home/user/data/hello.txt",
    "md5sum": "764efa883dda1e11db47671c4a3bbd9e",
    "remote_checksum": "55ca6286e3e4f4fba5d0448333fa99fc5a404a73",
    "remote_md5sum": null
}
[root@vm1 /]# cd ~
[root@vm1 ~]# ls
192.168.56.102   ca.csr  initial-setup-ks.cfg  uname.txt
anaconda-ks.cfg  ca.key  mydata
[root@vm1 ~]# cd 192.168.56.102/
[root@vm1 192.168.56.102]# ls
home
[root@vm1 192.168.56.102]# tree
.
└── home
    └── user
        └── data
            └── hello.txt

3 directories, 1 file

# 192.168.56.102 是剛剛從 app1群組 擷取的檔案，ansible 會根據 IP 自動產生相對應的目錄
```

* `ansible myapp -m fetch -a "src=/var/log/dmesg dest=/root"`：到　myapp群組 找到/var/log/dmesg，拷貝回本地的/root資料夾
```sh
[root@vm1 ~]# ansible myapp -m fetch -a "src=/var/log/dmesg dest=/root"
192.168.56.102 | SUCCESS => {
    "changed": true,
    "checksum": "e5f3aca722593b88c3d41edc76e050560ae847a7",
    "dest": "/root/192.168.56.102/var/log/dmesg",
    "md5sum": "6f100444fb2dc33e3e48329cbeb02197",
    "remote_checksum": "e5f3aca722593b88c3d41edc76e050560ae847a7",
    "remote_md5sum": null
}
192.168.56.103 | SUCCESS => {
    "changed": true,
    "checksum": "e6e0dd6aec54ddbb1c181ad58a0aeb6061205cfe",
    "dest": "/root/192.168.56.103/var/log/dmesg",
    "md5sum": "13326e64e4d0673ee34e3ea827c86566",
    "remote_checksum": "e6e0dd6aec54ddbb1c181ad58a0aeb6061205cfe",
    "remote_md5sum": null
}
192.168.56.101 | SUCCESS => {
    "changed": true,
    "checksum": "be7f8a8243300c7907a3411ca5e57de0a58bce4e",
    "dest": "/root/192.168.56.101/var/log/dmesg",
    "md5sum": "f21ea2ff81e052d380b7c963344fd3d1",
    "remote_checksum": "be7f8a8243300c7907a3411ca5e57de0a58bce4e",
    "remote_md5sum": null
}
[root@vm1 ~]# tree
.
├── 192.168.56.101
│   └── var
│       └── log
│           └── dmesg
├── 192.168.56.102
│   ├── home
│   │   └── user
│   │       └── data
│   │           └── hello.txt
│   └── var
│       └── log
│           └── dmesg
└── 192.168.56.103
    └── var
        └── log
　　         └── dmesg
```
* `ansible app1 -m command -a "ls -l /home/user/data/hello.txt"`：
```sh
[root@vm1 ~]# ansible app1 -m command -a "ls -l /home/user/data/hello.txt"
192.168.56.102 | SUCCESS | rc=0 >>
-rw------- 1 user user 3 Jun 28 12:56 /home/user/data/hello.txt
```
### `file`：針對檔案進行操作
* `ansible app1 -m file -a "path=/data/hello.txt owner=root group=root mode=666"`：修改 /data/hello.txt 檔案的讀寫模式
```sh
[root@vm1 ~]# ansible app1 -m file -a "path=/home/user/data/hello.txt owner=root group=root mode=666"
192.168.56.102 | SUCCESS => {
    "changed": true,
    "gid": 0,
    "group": "root",
    "mode": "0666",
    "owner": "root",
    "path": "/home/user/data/hello.txt",
    "size": 3,
    "state": "file",
    "uid": 0
}

[root@vm2 data]# ls -l
total 8
-rw-rw-rw- 1 root root 3 Jun 28 12:56 hello.txt
-rw-r--r-- 1 root root 4 Jun 28 12:44 hello.txt.9983.2020-06-28@12:56:15~
```
> ### 重點補充
* 使用 `ansible`、`copy`、`fetch` 模組的時候，只能針對一個檔案進行拷貝，若是要多個檔案拷貝，則可以先把檔案進行 tar 打包，之後再執行 `copy` or `fetch` 動作
### `yum`：模組安裝
```sh
ansible app1 -m yum -a "name=httpd status=present"  # ansible 使用 yum module 進行 httpd 的安裝
# status=present 可省略，因為原本預設值是 present
ansible app1 -m yum -a "name=httpd state=removed"`  # 進行移除 httpd 套件
```
### `service`：針對模組在開機時啟動與否
* `service` 模組的預設值為 no
* `name` 後面接套件名稱
* `state` 可替換成以下幾種：
    - started
    - restarted
    - reloaded：若更改配置檔可用
```sh
ansible app1 -m service -a "name=httpd state=started enabled=yes"   # 使用 service module，啟動 httpd 並且 enabled=yes 開機會自動啟動
ansible app1 -m service -a "name=httpd state=restarted"  # 重新啟動 httpd 服務
```
### `user`：創建使用者
* `ansible app1 -m user -a "name=tom comment='Tom Hank' uid=1111 group=tom home=/home/tom"`：創造 tom 使用者
```sh
[root@vm1 ~]# ansible app1 -m user -a "name=tom comment='Tom Hank' uid=1111 group=tom home=/home/tom"
192.168.56.102 | SUCCESS => {
    "changed": true,
    "comment": "Tom Hank",
    "createhome": true,
    "group": 1001,
    "home": "/home/tom",
    "name": "tom",
    "shell": "/bin/bash",
    "state": "present",
    "system": false,
    "uid": 1111
}
```
* `ansible app1 -m command -a "getent passwd tom"`
```sh
[root@vm1 ~]# ansible app1 -m command -a "getent passwd tom"
192.168.56.102 | SUCCESS | rc=0 >>
tom:x:1111:1001:Tom Hank:/home/tom:/bin/bash
```
* `ansible app1 -m user -a "name=tom state=absent remove=yes"`：刪除帳號，同時也把家目錄內容刪除
```sh
[root@vm1 ~]# ansible app1 -m user -a "name=tom state=absent remove=yes"
192.168.56.102 | SUCCESS => {
    "changed": true,
    "force": false,
    "name": "tom",
    "remove": true,
    "state": "absent"
}
```
### `group`：創建群組
* `ansible app1 -m group -a "name=tom"`：創造 tom群組
```sh
[root@vm1 ~]# ansible app1 -m group -a "name=tom"
192.168.56.102 | SUCCESS => {
    "changed": true,
    "gid": 1001,
    "name": "tom",
    "state": "present",
    "system": false
}
```
* `ansible app1 -m command -a "getent group tom"`：查看 tom群組 是否存在
```sh
[root@vm1 ~]# ansible app1 -m command -a "getent group tom"
192.168.56.102 | SUCCESS | rc=0 >>
tom:x:1001:
```
* `ansible app1 -m group -a "name=tom state=absent"`：移除 tom群組
```sh
[root@vm1 ~]# ansible app1 -m group -a "name=tom state=absent"
192.168.56.102 | SUCCESS => {
    "changed": true,
    "name": "tom",
    "state": "absent"
}
[root@vm1 ~]# ansible app1 -m command -a "getent group tom"
192.168.56.102 | FAILED | rc=2 >>
non-zero return code
```
# ansible-playbook - ansible 的腳本檔
* ansible 的腳本檔為 YAML 格式
## 範例一：Hello World
1. 寫一個腳本 `vim hello.yml`
```yml
---
- hosts: app1   # hosts 應用於哪台主機，hosts 前後需空格 app2：vm2(192.168.56.102)
  remote_user: root     # 遠端由超級使用者來操作

  tasks:
    - name: hello world     # 工作名稱
      command: /usr/bin/wall hello world    # 執行的指令
```
2. 檢查腳本是否有寫錯：`ansible-playbook -C hello.yml`
    - `-C`：check
```sh
[root@vm1 user]# ansible-playbook -C hello.yml

PLAY [app1] ********************************************************************

TASK [Gathering Facts] *********************************************************
ok: [192.168.56.102]

TASK [hello world] *************************************************************
skipping: [192.168.56.102]

PLAY RECAP *********************************************************************
192.168.56.102             : ok=1    changed=0    unreachable=0    failed=0
```
3. 執行腳本：`ansible-playbook hello.yml`
* vm1
```
[root@vm1 user]# ansible-playbook hello.yml

PLAY [app1] ********************************************************************

TASK [Gathering Facts] *********************************************************
ok: [192.168.56.102]

TASK [hello world] *************************************************************
changed: [192.168.56.102]

PLAY RECAP *********************************************************************
192.168.56.102             : ok=2    changed=1    unreachable=0    failed=0
```
* vm2
```
[root@vm2 data]#
Broadcast message from root@vm2 (Sun Jun 28 15:14:51 2020):

hello world
```
## 範例二：自動產生網頁
1. 新增一個 `hi.html`
```sh
Hi
```
2. 寫一個腳本 `vim 1.yml`
```yml
---
- hosts: app1
  remote_user: root
  
  tasks:
    - name: create new file                     # 新建一個文件
      file: name=/data/newfile state=touch
    - name: create new file 2                   # 新建第二個文件
      file: name=/data/newfile2 state=touch
    - name: create new user                     # 新建一個使用者
      user: name=tom 
    - name: install package                     # 安裝 httpd 套件
      yum: name=httpd
    - name: copy html                           # 複製文件
      copy: src=hi.html dest=/var/www/html
    - name: start service                       # 開啟 httpd 套件
      service: name=httpd state=started enabled=yes
```
- `name`：代表一個執行任務
- 一個 `name` 搭配一個 `file`
- 即使工作內容相似，也要有不同的 `name`
3. 檢查並執行腳本
```sh
ansible-playbook -C 1.yml
ansible-playbook 1.yml
```
4. 在 Client 端執行測試
```sh
curl 192.168.56.102/hi.html
```
## 範例三：複製更改過的配置檔，要增加 `notify`、`handlers`
* 由於 ansible 不論執行一次或多次結果都相同，會導致儘管修改了 httpd 的 Port 後，Port 一樣是 80
* 解決方法是增加 notify、handlers
1. 到 /etc/httpd/conf 下更改 httpd.conf 檔
```sh
# 將 Listen 80 改為 8099
Listen 8099
```
2. 寫一個腳本 `vim 2.yml`
```yml
---
- hosts: app1
  remote_user: root
  
  tasks:
    - name: create new file
      file: name=/data/newfile state=touch
    - name: create new file 2
      file: name=/data/newfile2 state=touch
    - name: create new user
      user: name=tom 
    - name: install package
      yum: name=httpd
    - name: copy html
      copy: src=hi.htm dest=/var/www/html
    - name: copy configuration file     # 複製更改過的配置檔
      copy: src=httpd.conf dest=/etc/httpd/conf
      notify: restart httpd service
    - name: start service
      service: name=httpd state=started enabled=yes

# 用來重開系統服務 (Service)
  handlers: 
    - name: restart httpd service
      service: name=httpd state=restarted
```
* notify 的 `restart httpd service` 會觸發 handlers 中 name 為 `restart httpd service` 的 service
3. 檢查並執行腳本
```sh
ansible-playbook -C 2.yml
ansible-playbook 2.yml
```
4. 在 Client 端執行測試
```sh
netstat -tunlp | grep httpd
```
## 範例四：LINE Notify
> [LINE Notify](https://notify-bot.line.me/zh_TW/)
1. 先在 LINE 創建一個自己與 Notify 的群組
2. 登入 LINE 後，點選個人頁面 -> 發行權杖
3. 複製權杖
4. 到 `/home/user/usr/lib/zabbix/alertscripts/` 新建一個腳本 `vim line.sh`，並增加執行權限 `chmod +x line.sh`
```sh
#!/usr/bin/bash
# LINE Notify Token - Media > "Send to".
TOKEN="複製的權杖"

# {ALERT.SUBJECT}
subject="$1"

# {ALERT.MESSAGE}
message="$2"

curl https://notify-api.line.me/api/notify -H "Authorization: Bearer ${TOKEN}" -d "message=${message}"
```
5. 執行命令：`./line.sh "Test" "Hello"` "群組：Test" "訊息：Hello"
* 執行結果： \
![](Image/Ansible/line.PNG)

## 範例五：`tags` 標籤，執行某一項工作 
1. 新建一個腳本 `vim httpd.yml`
```yml
---
- hosts: app1
  remote_user: root
  tasks:
    - name: install httpd     # 安裝 httpd 套件
      yum: name=httpd 
    - name: copy hi.htm
      copy: src=files/hi.htm dest=/var/www/html
      tags: hi                # -t 標籤的判斷
    - name: start httpd service
      tags: service
      service: name=httpd state=started enabled=yes
```
2. 執行腳本 `ansible-playbook httpd.yml`
```sh      
[root@vm1 user]# ansible-playbook httpd.yml

PLAY [app1] **********************************************   **********************

TASK [Gathering Facts] ***********************************   **********************
ok: [192.168.56.102]

TASK [install httpd] *************************************   **********************
ok: [192.168.56.102]

TASK [copy hi.htm] ***************************************   **********************
changed: [192.168.56.102]

TASK [start httpd service] *******************************   **********************
ok: [192.168.56.102]

PLAY RECAP ***********************************************   **********************
192.168.56.102             : ok=4    changed=1    unreacha   ble=0    failed=0
```
3. 執行結果
```sh
[root@vm1 user]# tree files/
files/
└── hi.htm
```
4. 假如修改 hi.htm 檔案，如果執行 playbook 會從頭執行一次，這樣效率很低，因為我們只需要執行某一項工作，於是可以使用 `-t`：判斷 tags
```sh
ansible-playbook -t hi httpd.yml
ansible-playbook -t hi,service httpd.yml    # 有多項 tags 可以用逗號隔開
```
## 範例六：`Setup` 模組可以看系統配置資訊
```sh
[root@vm1 user]# ansible app1 -m setup | grep hostname
        "ansible_hostname": "vm2",
```
## 範例七：parameter 透過 `{{}}` 包著
1. 新建一個腳本 `vim app.yml`
```yml
---
- hosts: app1
  remote_user: root
  tasks:
    - name: install package
      yum: name={{ pkname }}    # parameter 透過 {{}} 包著
    - name: start service
      service: name={{ pkname }} state=started enabled=yes
```
2. 執行指令：`ansible-playbook -e 'pkname=vsftpd' app.yml`
- `-e`：傳參數
- `pkname`：變數名稱
```sh
[root@vm1 user]# ansible-playbook -e 'pkname=vsftpd' app.yml

PLAY [app1] ********************************************************************

TASK [Gathering Facts] *********************************************************
ok: [192.168.56.102]

TASK [install package] *********************************************************
changed: [192.168.56.102]

TASK [start service] ***********************************************************
changed: [192.168.56.102]

PLAY RECAP *********************************************************************
192.168.56.102             : ok=3    changed=2    unreachable=0    failed=0
```
## 範例八：如果要安裝兩個一樣的 package，可以取不同名字
1. 新建一個腳本 `vim app2.yml`
```yml
---
- hosts: app1
  remote_user: root
  tasks:
    - name: install package
      yum: name={{ pkname1 }}
    - name: install package
      yum: name={{ pkname2 }}
```
2. 執行指令：`ansible-playbook -C -e "pkname1=httpd pkname2=vsftpd" app2.yml`
## 範例九：更改 hostname
1. 到 `/etc/ansible/hosts` 下增加 `http_port`
```sh
[myapp]
192.168.56.101 http_port=80
192.168.56.102 http_port=81
192.168.56.103 http_port=82
```
2. 新建一個腳本 `vim test1.yml`
```yml
---
- hosts: myapp
  remote_user: root
  tasks:
   - name: change hostname
     hostname: name=centos-{{ http_port }}.example.com
    # 用來改變主機的名稱
```
3. 執行指令：`ansible-playbook test1.yml`
## 範例十：如果劇本設定和手動設定，手動>劇本
1. 到 `/etc/ansible/hosts` 下增加 `[myapp:vars]`
```sh
[myapp]
192.168.56.101 http_port=80
192.168.56.102 http_port=81
192.168.56.103 http_port=82

# 劇本定義
[myapp:vars]
nodename=centos
domainname=example.com
```
2. 新建一個腳本 `vim test2.yml`
```yml
---
- hosts: myapp
  remote_user: root
  tasks:
    - name: change hostname
      hostname: name={{ nodename }}-{{ http_port }}.{{ domainname }}
```
3. 執行指令：`ansible-playbook -e "nodename=test domainname=test.com" test2.yml` 手動定義
```sh
[root@vm1 user]# ansible-playbook -e "nodename=test domainname=test.com" test2.yml

PLAY [myapp] *******************************************************************

TASK [Gathering Facts] *********************************************************
ok: [192.168.56.103]
ok: [192.168.56.102]
ok: [192.168.56.101]

TASK [change hostname] *********************************************************
changed: [192.168.56.102]
changed: [192.168.56.103]
changed: [192.168.56.101]

PLAY RECAP *********************************************************************
192.168.56.101             : ok=2    changed=1    unreachable=0    failed=0
192.168.56.102             : ok=2    changed=1    unreachable=0    failed=0
192.168.56.103             : ok=2    changed=1    unreachable=0    failed=0
```
> * 如果手動設定 `nodename=test domainname=test.com`，與劇本中設定的 `[myapp:vars]`，手動 > 劇本，故會執行手動的設定
* `ansible myapp -m setup -a "filter=ansible_fqdn"`
  - `filter`：搜尋
  - `fqdn`：`setup` 模組中的變數，完整的網域名字，可以識別主機
## 範例十一：`fqdn`：`Setup` 模組中的變數，完整的網域名字
1. 新建一個腳本 `vim test3.yml`
```yml
---
- hosts: app1
  remote_user: root
  tasks:
    - name: create log file     # 產生的紀錄檔與網域名有關
      file: name=/data/{{ ansible_fqdn }}.log state=touch
```
2. 執行指令：`ansible-playbook test3.yml`
## 範例十二：`vars_files` 引入腳本來傳遞變數
1. 新建一個腳本 `vim test4.yml`
```yml
---
- hosts: app1
  remote_user: root
  vars_files:       # 引用 vars.yml 檔
    - vars.yml

  tasks:
    - name: create log file
      file: name=/data/{{ var1 }}.log state=touch
    - name: create log file
      file: name=/data/{{ var2 }}.log state=touch
```
2. 準備一個 vars.yml 檔
```yml
var1: httpd
var2: vsftpd
```
## 範例十三：自定義網頁伺服器
1. 新建一個腳本 `vim test5.yml`
```yml
---
- hosts: app1
  remote_user: root
  tasks:
    - name: install package
      yum: name=httpd
    - name: copy config file
      template: src=httpd.conf.j2 dest=/etc/httpd/conf/httpd.conf   # 模組
    - name: start service
      service: name=httpd state=started enabled=yes
```
2. 在 vm1 新增一個 templates 資料夾
```sh
mkdir templates
```
3. 將檔案 `/etc/httpd/conf/httpd.conf` 複製到 templates 資料夾
```sh
cp /etc/httpd/conf/httpd.conf templates
```
4. 改名為 httpd.conf.j2
```sh
mv httpd.conf httpd.conf.j2   # .j2：Jinja2 是一個模板
```
5. 更改文件內容
```sh
# Change this to Listen on specific IP addresses as shown below to
# prevent Apache from glomming onto all bound IP addresses.
#
#Listen 12.34.56.78:80
#Listen 80
Listen {{ http_port }}
```
6. 執行指令：`ansible-playbook test5.yml`
7. 測試是否成功，查看 port 號
```sh
netstat -tunlp | grep httpd
```
## 範例十四：在 playbook 設定條件 `when`
* 讓虛擬機(vm3:192.168.56.103)關機
1. 新建一個腳本 `vim test6.yml`
```yml
- hosts: myapp
  remote_user: root
  tasks:
    - name: shutdown the computer
      command: /sbin/shutdown -h now
      when: ansible_fqdn=="vm3"
```
2. 執行指令：`ansible-playbook test6.yml`
```sh
[root@vm1 user]# ansible-playbook test6.yml

PLAY [myapp] *******************************************************************

TASK [Gathering Facts] *********************************************************
ok: [192.168.56.102]
ok: [192.168.56.101]
fatal: [192.168.56.103]: UNREACHABLE! => {"changed": false, "msg": "Failed to connect to the host via ssh: ssh: connect to host 192.168.56.103 port 22: Connection timed out\r\n", "unreachable": true}

TASK [shutdown the computer] ***************************************************
skipping: [192.168.56.101]
fatal: [192.168.56.102]: UNREACHABLE! => {"changed": false, "msg": "Failed to connect to the host via ssh: Shared connection to 192.168.56.102 closed.\r\n", "unreachable": true}
        to retry, use: --limit @/home/user/test6.retry

PLAY RECAP *********************************************************************
192.168.56.101             : ok=1    changed=0    unreachable=0    failed=0
192.168.56.102             : ok=1    changed=0    unreachable=1    failed=0
192.168.56.103             : ok=0    changed=0    unreachable=1    failed=0
```
## 範例十五：`with_items` 一次執行多件事
* 執行變數使用 `item`，`with_items` 一次執行多件事
* 由於 `htop`、`sl` 是第三方套件，故 vm2(192.168.56.102)、vm3(192.168.56.103) 需先執行
```sh
yum install epel-release
```

1. 新建一個腳本 `vim test7.yml`
```yml
- hosts: app1
  remote_user: root
  tasks:
    - name: create some files
      file: name=/data/{{ item }} state=touch
      with_items:
        - file1
        - file2
        - file3
    - name: install some packages
      yum: name={{ item }}
      with_items: 
        -  htop
        -  sl
```
2. 執行指令：`ansible-playbook test7.yml`
```sh
[root@vm1 user]# ansible-playbook test7.yml

PLAY [app2] ********************************************************************

TASK [Gathering Facts] *********************************************************
ok: [192.168.56.103]

TASK [create some files] *******************************************************
changed: [192.168.56.103] => (item=file1)
changed: [192.168.56.103] => (item=file2)
changed: [192.168.56.103] => (item=file3)

TASK [install some packages] ***************************************************
changed: [192.168.56.103] => (item=[u'htop', u'sl'])

PLAY RECAP *********************************************************************
192.168.56.103             : ok=3    changed=2    unreachable=0    failed=0
```
3. 執行結果：
* 執行 `htop`：
```sh
[root@vm3 data]# htop
```
![](Image/Ansible/htop.PNG)

* 執行 `sl`：
```sh
[root@vm3 data]# sl
```
![](Image/Ansible/sl1.PNG)
![](Image/Ansible/sl2.PNG)

# Roles
## Roles 是什麼?
* Roles 可以降低 playbook 的複雜性，更可以增加 playbook 的可用性
* 簡言之，Roles 就是把許多 playbook 整合在一起
## 如何使用 Roles
* 我們可以透過 Galaxy 和 `ansible-galaxy` 來使用 Roles
###  Galaxy 是什麼?
* [Ansible Galaxy](https://galaxy.ansible.com/) 是官方維護的網站，我們可以在上面取得社群成員所維護的 Roles
### `ansible-galaxy` 是什麼?
* `ansible-galaxy` 是管理 Roles 的指令，我們可以在 Terminal 上用它搜尋、安裝、移除 Roles 等，可以說它是 Ansible 世界的 pip
## 環境介紹
1. ansible 資料夾中，有 httpd_role.yml 檔和 roles 資料夾
* roles 資料夾下的 httpd 資料夾有 tasks、templates 資料夾
```sh
[root@vm1 user]# tree ansible
ansible
├── httpd_role.yml
└── roles
    └── httpd
        ├── tasks
        │   ├── conf.yml
        │   ├── install.yml
        │   ├── main.yml
        │   └── service.yml
        └── templates
            └── httpd.conf.j2

4 directories, 6 files
```
2. 當執行 httpd_role.yml，會執行 httpd 資料夾裡的資料
* 執行指令：`ansible-playbook httpd_role.yml`
```sh
[root@vm1 ansible]# cat httpd_role.yml
- hosts: app1
  remote_user: root
  roles:
  - role: httpd   # 會執行 httpd 資料夾裡的資料
[root@vm1 httpd]# tree
.
└── tasks
    ├── conf.yml
    ├── install.yml
    ├── main.yml    # 主要先執行
    └── service.yml

1 directories, 4 files
```
3. tasks 資料夾內的檔案內容
  * conf.yml
  ```yml
  - name: copy conf
  template: src=httpd.conf.j2 dest=/etc/httpd/conf/httpd.conf
  ```
  * install.yml
  ```yml
  - name: install package
  yum: name=httpd
  ```
  * main.yml
  ```yml
  - include: install.yml
  - include: conf.yml
  - include: service.yml
  ```
  * service.yml
  ```yml
  - name: start service
  service: name=httpd state=started
  ```
> 會先執行 main.yml，再按照內容順序執行
## 範例一：可以從 [Galaxy](https://galaxy.ansible.com/) 中找尋套件 - Apache
* [Galaxy apache](https://galaxy.ansible.com/geerlingguy/apache)
1. 下載 apache：`ansible-galaxy install geerlingguy.apache`
2. 檢視
```sh
[root@vm1 roles]# tree
.
├── geerlingguy.apache
│   ├── defaults
│   │   └── main.yml
│   ├── handlers
│   │   └── main.yml
│   ├── LICENSE
│   ├── meta
│   │   └── main.yml
│   ├── molecule
│   │   └── default
│   │       ├── molecule.yml
│   │       ├── playbook.yml
│   │       └── yaml-lint.yml
│   ├── README.md
│   ├── tasks
│   │   ├── configure-Debian.yml
│   │   ├── configure-RedHat.yml
│   │   ├── configure-Solaris.yml
│   │   ├── configure-Suse.yml
│   │   ├── main.yml
│   │   ├── setup-Debian.yml
│   │   ├── setup-RedHat.yml
│   │   ├── setup-Solaris.yml
│   │   └── setup-Suse.yml
│   ├── templates
│   │   └── vhosts.conf.j2
│   └── vars
│       ├── AmazonLinux.yml
│       ├── apache-22.yml
│       ├── apache-24.yml
│       ├── Debian.yml
│       ├── RedHat.yml
│       ├── Solaris.yml
│       └── Suse.yml
└── httpd
    ├── tasks
    │   ├── conf.yml
    │   ├── install.yml
    │   ├── main.yml
    │   └── service.yml
    └── templates
        └── httpd.conf.j2
```
---
參考資料：
- [使用 Ansible 实现数据中心自动化管理](https://www.ibm.com/developerworks/cn/opensource/os-using-ansible-for-data-center-it-automation/index.html)
- [ansible教程-马哥2019全新ansible入门到精通](https://www.bilibili.com/video/BV18t411f7CN?from=search&seid=2332676631451641625)
- [林柏億的學長的 Linux 筆記 - ansible](https://github.com/istar0me/linux-note/blob/107-2/Ansible.md)
- [Ansible中文权威指南](https://ansible-tran.readthedocs.io/en/latest/docs/modules_intro.html)
- [ansible自动化运维 cryptography 0.8.2 版本兼容性报错解决办法](https://blog.csdn.net/codemacket/article/details/80911149)
- [透過LINE接收其他網站服務通知](https://notify-bot.line.me/zh_TW/)
- [YAML 簡介](http://www.wl-chuang.com/blog/2011/11/06/yaml-tutorial/)
- [現代 IT 人一定要知道的 Ansible 自動化組態技巧](https://chusiang.gitbooks.io/automate-with-ansible/15.how-to-use-handlers-in-playbooks.html)