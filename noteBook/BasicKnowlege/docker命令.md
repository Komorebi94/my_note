### docker命令

> + <span style="color: red">Docker容器命令</span>
>
>     + 查看正在运行容器列表
>
>         ```
>         docker ps
>         ```
>
>     + 查看所有的容器包括正在运行的和已经停止的
>
>         ```
>         docker ps -a
>         ```
>
>     + 拉取镜像
>
>         ```
>         docker pull 镜像名
>         ```
>
>     + 运行一个容器
>
>         ```
>         docker run -itd --name 容器别名  -p 宿主端口:容器端口 --restart=always 容器名
>         ```
>         
>     + run optiosns
>     
>         ``` 
>         --restart=always: 该容器随着docker服务启动而自启动
>         -v: 宿主机文件存储位置:容器内文件位置 -v 宿主机文件存储位置:容器内文件位置 (可挂载多个)
>         -a stdin: 指定标准输入输出内容类型，可选 STDIN/STDOUT/STDERR 三项； 
>         -d: 后台运行容器，并返回容器ID； 
>         -i: 以交互模式运行容器，通常与 -t 同时使用； 
>         -t: 为容器重新分配一个伪输入终端，通常与 -i 同时使用； 
>         –name=”nginx-lb”: 为容器指定一个名称； 
>         –dns 8.8.8.8: 指定容器使用的DNS服务器，默认和宿主一致； 
>         –dns-search example.com: 指定容器DNS搜索域名，默认和宿主一致； 
>         -h “mars”: 指定容器的hostname； 
>         -e username=”ritchie”: 设置环境变量； 
>         –env-file=[]: 从指定文件读入环境变量； 
>         –cpuset=”0-2” or –cpuset=”0,1,2”: 绑定容器到指定CPU运行； 
>         -m :设置容器使用内存最大值； 
>         –net=”bridge”: 指定容器的网络连接类型，支持 bridge/host/none/Container: 四种类型； 
>         –link=[]: 添加链接到另一个容器； 
>         –expose=[]: 开放一个端口或一组端口；
>         ```
>     
>         
>     
>     + 停止容器
>     
>         ```
>         docker stop 容器名/id
>         ```
>     
>     + 删除容器
>     
>         ``` 
>         docker rm -f 容器名/id  容器名/id  容器名/id
>         ```
>     
>     + 删除全部的容器(循环删除)
>     
>         ```
>         docker rm -f $(docker ps -aq)
>         ```
>     
>     + 进入容器
>     
>         ```
>         docker exec -it 容器名/id  /bin/bash | /bin/sh
>         ```
>     
>     + 启动容器
>     
>         ```
>         docker start 容器名/id
>         ```
>     
>     + 重启容器
>     
>         ```
>         docker restart 容器名/id
>         ```
>     
>     + kill容器
>
>         ```
>         docker kill 容器名/id
>         ```
>     
>     + 更换容器名
>     
>         ```
>         docker rename 容器名/id  新容器名
>         ```
>     
>     + 容器文件拷贝
>     
>         ```
>         # 从容器内拷出
>         docker cp 容器名/id:容器内路径 容器外路径(路径需要存在，不会自动创建)
>         docker cp 9e943aabc52a:/etc/nginx/nginx.conf /home/docker-nginx/nginx.conf
>         # 从外部拷贝到容器内
>         docker cp 容器外路径 容器名/id 容器内路径
>         ```
>     
>     + 查看容器日志
>     
>         ```
>         docker logs -f --tail=要查看末尾行数 默认all  容器id
>         ```



> + <span style="color: red;">docker镜像命令</span>
>
>     + 查看镜像列表
>
>         ```
>         docker images
>         ```
>
>     + 搜索镜像
>
>         ```
>         # 搜索stars大于9000的mysql镜像
>         docker search --filter=STARTS=9000 mysql
>         ```
>
>     + 拉取镜像
>
>         ```
>         docker pull 镜像名：tag
>         ```
>
>         