FROM centos:7.3.1611
MAINTAINER Wattana Inthaphong <wattana@angstromsolutions.net>

ENV LANG en_US.UTF-8
ENV LC_TIME en_US.UTF-8 

# Setup Timezone
ENV TZ "Asia/Bangkok"
ENV PATH /opt/bin:$PATH
ENV NODE_VERSION v6.9.2
# Enable EPEL
RUN yum install -y epel-release \ 
&& yum update -y \
&& yum install -y autoconf make gcc gcc-c++ wget vim mlocate which tar bzip2 zip unzip net-tools telnet nc file git \
&& yum clean all \
&& wget https://nodejs.org/dist/$NODE_VERSION/node-$NODE_VERSION.tar.gz \
&& tar -xf node-$NODE_VERSION.tar.gz \
&& cd node-$NODE_VERSION \
&& ./configure \
&& make \
&& make install \
&& cd / \
&& rm -rf node-$NODE_VERSION \
&& rm -f node-$NODE_VERSION.tar.gz