# tianchi-docker-notes

#### create docker repo online


#### Dockerfile
`
# Base Images  
## 从天池基础镜像构建  
FROM registry.cn-shanghai.aliyuncs.com/tcc-public/python:3  
  
## 把当前文件夹里的文件构建到镜像的根目录下  
ADD . /  
  
## 指定默认工作目录为根目录（需要把run.sh和生成的结果文件都放在该文件夹下，提交后才能运行）  
WORKDIR /  
  
## 镜像启动后统一执行 sh run.sh  
CMD ["sh", "run.sh"]
`


#### pull base image python3

`
docker pull registry.cn-shanghai.aliyuncs.com/tcc-public/python:3
`

#### login
`
sudo docker login --username=*** registry.cn-shanghai.aliyuncs.com/****
`
#### build 
`
sudo docker build -t registry.cn-shanghai.aliyuncs.com/XXX/XXX:XXX（版本号）.

`
#### install dependencies
`
$ docker run -it XXX /bin/bash #XXX为镜像名称 #这时会进入终端 
root@:/# exit #这就可以退出终端了 


$ docker ps #查看正在运行的容器. 
$ docker exec –it XXXXXXXXXX bash #进入正在运行的容器内，XXXXXXXXXX是镜像ID #进入容器后，就可以修改镜像了

pip3 install XXXX 

exit 退出容器 

$ docker commit 3abcde132456 IMAGENAME:TAG

`

#### push
`
docker tag [ImageId] [repo]:[tag]

docker push [repo]:[tag]
`


#### rm images
`
sudo docker image rm [opt] <img1 [<img2> ...]
`



### github
`
git tag -a release-v[tag] -m "Update ...."
git push origin --tags
`


