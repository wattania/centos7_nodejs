FROM centos:7.2.1511
MAINTAINER Wattana Inthaphong <wattana@angstromsolutions.net>

ENV LC_ALL en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LC_TIME en_US.UTF-8

# Setup Timezone
ENV TZ "Asia/Bangkok"
RUN rm -f /etc/localtime && ln -s /usr/share/zoneinfo/Asia/Bangkok /etc/localtime
ENV PATH /opt/bin:$PATH

# Enable EPEL
RUN yum install -y epel-release \ 
&& yum update -y \ 
&& yum clean all

RUN yum update -y \
&& yum install -y make gcc gcc-c++ wget vim mlocate which tar bzip2 zip unzip net-tools telnet nc file git \
&& yum clean all
### NODE.JS #####################################################################
ENV NODE_VERSION v6.9.1
RUN wget https://nodejs.org/dist/$NODE_VERSION/node-$NODE_VERSION.tar.gz \
&& tar -xf node-$NODE_VERSION.tar.gz \
&& cd node-$NODE_VERSION \
&& ./configure \
&& make \
&& make install \
&& cd / \
&& rm -rf node-$NODE_VERSION \
&& rm -f node-$NODE_VERSION.tar.gz