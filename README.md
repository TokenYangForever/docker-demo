# docker-demo
docker

1.通过Dockerfile，构建image镜像
`docker image build -t nginx-demo-image .`

2.通过image镜像，运行容器
`docker container run -p 8088:80 -it nginx-demo-image`
docker run --name nginx-demo-image --rm -d -p 8080:80