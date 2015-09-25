#
# MAINTAINER        j360,xumin <xumin_wlt@163.com>
# DOCKER-VERSION    1.7.1
#
# Dockerizing CentOS7: Dockerfile for building CentOS images
#
FROM       centos:centos7.1.1503
MAINTAINER j360,xumin <xumin_wlt@163.com>

ENV TZ "Asia/Shanghai"
ENV TERM xterm

RUN yum update -y
RUN yum -y install gcc gcc-c++ autoconf  zlib zlib-devel glibc glibc-devel glib2 glib2-devel l curl curl-devel vim rpm
RUN rpm -ivh http://nginx.org/packages/centos/6/noarch/RPMS/nginx-release-centos-6-0.el6.ngx.noarch.rpm
RUN yum -y  install nginx

EXPOSE 80
CMD nginx
