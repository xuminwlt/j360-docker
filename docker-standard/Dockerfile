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

RUN yum install -y curl wget tar bzip2 unzip vim-enhanced passwd sudo yum-utils hostname net-tools rsync man && \
    yum clean all

#java配置
ADD ../soft/jdk-7u80-linux-x64.tar.gz /usr/local/j360
ENV JAVA_HOME /usr/local/j360/jdk1.7.0_80
ENV CLASSPATH $JAVA_HOME/jre/lib/rt.jar:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
ENV PATH $PATH:$JAVA_HOME/bin

# install redis
ADD ../soft/redis-3.0.4.gz /usr/local/j360
RUN yum install -y curl tar make gcc && \
    cd /usr/local/j360 && \
    tar xf redis-3.0.4.gz && \
    cd redis-3.0.4 && \
    make && \
    make install

#j360-boot.jar
ADD j360-standard-1.3.0.BUILD-SNAPSHOT.jar /usr/local/j360
ENV JAR_HOME /usr/local/j360
WORKDIR $JAR_HOME

EXPOSE 8080 22 6379

CMD ["java -jar"，"j360-simple-1.3.0.BUILD-SNAPSHOT.jar"，"/usr/local/bin/redis-server"]