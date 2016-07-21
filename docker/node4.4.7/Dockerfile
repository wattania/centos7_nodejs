FROM centos:7.2.1511
MAINTAINER Wattana Inthaphong <wattaint@gmail.com>

ADD https://drive.google.com/uc?export=download&id=0B2eYeTF7nuSVMTc3b0FTUUVlb3M /etc/yum.repos.d/CentOS-Base.repo
RUN yum clean all \ 
&& yum update -y \
&& yum install -y make gcc gcc-c++ wget vim mlocate which tar bzip2 zip unzip net-tools telnet nc \
&& yum clean all
### NODE.JS #####################################################################
ENV NODE_VERSION v4.4.7
RUN wget https://nodejs.org/dist/$NODE_VERSION/node-$NODE_VERSION.tar.gz \
&& tar -xf node-$NODE_VERSION.tar.gz \
&& cd node-$NODE_VERSION \
&& ./configure \
&& make \
&& make install \
&& cd / \
&& rm -rf node-$NODE_VERSION \
&& rm -f node-$NODE_VERSION.tar.gz