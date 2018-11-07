# docker-demo
docker

1.通过Dockerfile，构建image镜像
`docker image build -t nginx-demo-image .`

2.通过image镜像，运行容器
`docker container run -p 8088:80 -it --rm nginx-demo-image /bin/bash`


##### 编写Dockerfile
* `FROM 镜像:版本号`  从某个版本号的镜像复制一个副本
* `COPY . /app` 把当前目录下的文件都复制到app文件夹目录下


#### docker run
* [https://docs.docker.com/engine/reference/run/#general-form](https://docs.docker.com/engine/reference/run/#general-form)
* `docker run [OPTIONS] IMAGE[:TAG|@DIGEST] [COMMAND] [ARG...]`
* -d: 后台运行容器，并返回容器ID
* -i: 以交互模式运行容器，通常与 -t 同时使用
* -t: 为容器重新分配一个伪输入终端，通常与 -i 同时使用
* -p: 端口映射，格式为：主机(宿主)端口:容器端口
* --rm: 默认情况下，容器退出后，仍然会保留分配给它的文件系统(保留final state 利于debug)，设置`--rm`后，只要容器退出，就会删除它的file system
* -m: 分配给容器的最大内存限制，`-m 300M`，单位可以是:b、k、m、g，最小为4M

#### docker image build
* [https://docs.docker.com/engine/reference/commandline/image_build/#related-commands](https://docs.docker.com/engine/reference/commandline/image_build/#related-commands)
* `docker image build [OPTIONS] PATH | URL | -`
* options:
    *  -t: 镜像的名字及标签，通常 name:tag 或者 name 格式；可以在一次构建中为一个镜像设置多个标签。