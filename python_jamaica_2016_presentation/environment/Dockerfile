# docker file for creating a spark development environment
# use command "docker build -t sparkdvev . " to create the image
# i should switch this to debian-8 or centos-7
FROM centos:centos7
MAINTAINER Leotis Buchanan <leotisbuchanan@gmail.com>

RUN yum -y update; yum clean all
RUN yum -y install epel-release; yum clean all



#install and configure zeppelin

#get the zepellin
RUN curl -s http://www-eu.apache.org/dist/zeppelin/zeppelin-0.6.2/zeppelin-0.6.2-bin-all.tgz | tar -xz -C /usr/local/
#verify with checksum, dont want to get hack
RUN cd /usr/local && ln -s zeppelin-0.6.2-bin-all zeppelin

ENV ZEPPELIN_HOME /usr/local/zeppelin
#expose zepellin ports
EXPOSE 8080 8081

#get spark

#http://d3kbcqa49mib13.cloudfront.net/spark-2.0.1-bin-hadoop2.7.tgz
RUN curl -s http://d3kbcqa49mib13.cloudfront.net/spark-2.0.1-bin-hadoop2.7.tgz | tar -xz -C /usr/local/
RUN cd /usr/local && ln -s spark-2.0.1-bin-hadoop2.7 spark
#verify with checksum
# expose the spark ports
ENV SPARK_HOME /usr/local/spark


#install emacs
RUN yum -y install emacs
#install tmux
RUN yum -y install  tmux
#install sbt
#anaconda
#java


#scala
