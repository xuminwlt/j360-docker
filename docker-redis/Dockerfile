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

# install redis
ADD ../soft/redis-3.0.4.gz /usr/local/j360
RUN yum install -y curl tar make gcc && \
    cd /usr/local/j360 && \
    tar xf redis-3.0.4.gz && \
    cd redis-3.0.4 && \
    make && \
    make install

EXPOSE 6379
CMD ["/usr/local/bin/redis-server"]
