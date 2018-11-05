# docker-demo
docker

1.通过Dockerfile，构建image镜像
`docker image build -t nginx-demo-image .`

2.通过image镜像，运行容器
`docker container run -p 8088:80 -it --rm nginx-demo-image /bin/bash`


##### 编写Dockerfile
* `FROM 镜像:版本号`  从某个版本号的镜像复制一个副本
* `COPY . /app` 把当前目录下的文件都复制到app文件夹目录下