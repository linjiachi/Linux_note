* [Docker]()
    - [Docker 介紹]()
    - [Docker 使用]()
    - [Image 映象檔/鏡像檔 與 Container 容器]()
    - [Docker 容器三大特色]()
* [Docker 指令]()
* [Docker 實例]()
---
# Docker
## Docker 介紹
* 
## Docker 使用
* 到 [Dockerhub](https://hub.docker.com/) 申請一組帳號和密碼，如果將來在電腦裡有做好的 Image(映像檔/鏡像檔)，可以把映像檔/鏡像檔上傳自自己的 Dockerhub 上，公開給大家使用或者隱藏。
## Image 映象檔/鏡像檔 與 Container 容器
1. Image 是儲存在磁碟中的檔案，尚未運行
2. 當 Image 開始運行，他會變成 Container，換句話說 Container 是用 Image 建立出來執行的實例
3. 一個 Image 可以跑多個 Container，但 Image 的名字和本機 port 要改變
## Docker 容器三大特色
1. 命名空間隔離
2. aufs (advanced multi-layered unification filesystem)
    - 更動採用分層疊架的方式
    - 更動檔案的這個變動就成為一層
    - 每一層只記錄與上一層的差異
    - 儲存起來的只能讀不能寫，只有最上面那層才能進行寫入
3. cgroups：用來配送資源的 -> resources
# Docker 指令
* `docker pull [映像檔]:[版本]`：從 Dockerhub 下載映像檔
  - 映像檔有分和官方有作者的
    - 官方鏡像 -> httpd
    - 有作者的鏡像-> lin7/httpd (owner/image) 
  - 若沒有打版本則下載最新的版本
* `docker ps [option]`：列出容器的使用狀態
  - `-a`：all 顯示所有 容器Container，包含未運行的
  - `-a -q`：顯示所有執行的 容器 ID (CONTAINER ID)
* `docker start [容器ID或名稱]`：開始、復活 容器Container
* `docker stop [容器ID或名稱]`：暫停 容器Container
* `docker rm [容器ID或名稱]`：移除 容器Container (如果容器狀態已離開)
* `docker rm -f [容器ID或名稱]`：強制移除 容器Container (如果容器狀態還在運行)
* `docker rm -f $(docker ps -a -q)`：移除所有 容器Container
* `docker run [容器ID或名稱]`：執行 Image 變成 容器Container
* `docker run -it [容器ID或名稱] [指令]`：與 Image 互動，讓 Image 執行指令
* `docker inspect [容器ID或名稱]`：可以知道詳細的 容器Container 資訊
* `docker images`：顯示目前鏡像檔
* `docker rmi [鏡像TAG]`：移除 鏡像image
* `docker commit [鏡像TAG]`：從容器創建一個新的鏡像
* `docker info`：觀察正在用 docker 的資訊
* `docker search centos`：查詢 docker 有關 centos 的資訊
* `倉庫位置/owner/image_name:tag` ex. centos/mariadb-101-centos7
# Docker 實例

---
參考資料：
- [Docker Container 指令：Docker run & Docker exec](https://www.jinnsblog.com/2018/10/docker-container-command.html)
- [Docker 是什麼？實戰手札帶你認識 Docker](https://tw.alphacamp.co/blog/docker-introduction)
- [Docker 基礎教學與介紹 101](https://medium.com/unorthodox-paranoid/docker-tutorial-101-c3808b899ac6)