# docker file for creating a spark development environment
FROM centos:centos7
MAINTAINER Leotis Buchanan <leotisbuchanan@gmail.com>

RUN yum -y update; yum clean all
RUN yum -y install epel-release; yum clean all


#install emacs
RUN yum -y install emacs
#install tmux
RUN yum -y install  tmux

#install git
RUN yum -y install git

#install wget
RUN yum -y install wget

# install bzip2
RUN yum install bzip2

#anaconda
RUN echo 'export PATH=/opt/conda/bin:$PATH' > /etc/profile.d/conda.sh
RUN wget --quiet https://repo.continuum.io/archive/Anaconda3-4.2.0-Linux-x86_64.sh -O ~/anaconda.sh
RUN /bin/bash ~/anaconda.sh -b -p /opt/conda
RUN  ~/anaconda.sh

#java
#
ARG JAVA_MAJOR_VERSION=8
ARG JAVA_UPDATE_VERSION=92
ARG JAVA_BUILD_NUMBER=14
ENV JAVA_HOME /usr/jdk1.${JAVA_MAJOR_VERSION}.0_${JAVA_UPDATE_VERSION}
ENV PATH $PATH:$JAVA_HOME/bin
RUN curl -sL --retry 3 --insecure \
  --header "Cookie: oraclelicense=accept-securebackup-cookie;" \
  "http://download.oracle.com/otn-pub/java/jdk/${JAVA_MAJOR_VERSION}u${JAVA_UPDATE_VERSION}-b${JAVA_BUILD_NUMBER}/server-jre-${JAVA_MAJOR_VERSION}u${JAVA_UPDATE_VERSION}-linux-x64.tar.gz" \
  | gunzip \
  | tar x -C /usr/ \
  && ln -s $JAVA_HOME /usr/java \
  && rm -rf $JAVA_HOME/man



# SPARK
RUN curl -s http://d3kbcqa49mib13.cloudfront.net/spark-2.0.1-bin-hadoop2.7.tgz | tar -xz -C /usr/local/ && curl -s http://www-us.apache.org/dist/zeppelin/zeppelin-0.6.2/zeppelin-0.6.2-bin-all.tgz | tar -xz -C /usr/local/

RUN cd /usr/local && ln -s spark-2.0.1-bin-hadoop2.7 spark && ln -s zeppelin-0.6.2-bin-all zeppelin

ADD scripts/*.sh /
ADD scripts/spark-defaults.conf /spark-defaults.conf

ENV SPARK_HOME /usr/local/spark

EXPOSE 8080 8081
