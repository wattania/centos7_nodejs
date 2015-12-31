FROM centos:7.1.1503
MAINTAINER Wattana Inthaphong <wattaint@gmail.com>

RUN yum update -y \
&& yum install -y make gcc gcc-c++ wget vim mlocate which tar bzip2 zip unzip net-tools \
&& yum clean all
### NODE.JS #####################################################################
ENV NODE_VERSION v4.2.4
RUN wget https://nodejs.org/dist/$NODE_VERSION/node-$NODE_VERSION.tar.gz \
&& tar -xf node-$NODE_VERSION.tar.gz \
&& cd node-$NODE_VERSION \
&& ./configure \
&& make \
&& make install \
&& cd / \
&& rm -rf node-$NODE_VERSION \
&& rm -f node-$NODE_VERSION.tar.gz