j360-docker
==============
j360系列集成spring-docker
使用docker集成j360-boot.jar/j360-boot.war
jdk1.7-x64因为太大不上传到soft，自行下载放到该目录

##j360-simple##
docker-simple/Dockerfile

##j360-simplewar##
docker-simplewar/Dockerfile

##j360-standard##
- **j360-standard需要redis服务器**
docker-standard/Dockerfile

====================
发布执行

- 服务器安装git
- git clone https://github.com/xuminwlt/j360-docker.git
- cd j360-docker
- ls
- docker images
- **执行redis，用于测试redis用**
- docker run -d -p 6379:6379 redis/j360 
- cd docker-redis
- docker build -t redis/j360 .
- docker run -d -p 6379:6379 redis/j360 

- **执行simple**
- cd docker-simple
- docker build -t simple/j360 .
- docker run -d -p 8080:8000 simple/j360
 

