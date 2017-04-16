FROM centos:7.3.1611
MAINTAINER Wattana Inthaphong <wattana@angstromsolutions.net>

ENV LANG en_US.UTF-8
ENV LC_TIME en_US.UTF-8 

# Setup Timezone
ENV TZ "Asia/Bangkok"
ENV PATH /opt/bin:$PATH
ENV NODE_VERSION v6.9.4
# Enable EPEL
RUN yum install -y epel-release \ 
&& yum update -y \
&& yum install -y autoconf make gcc gcc-c++ wget vim mlocate which tar bzip2 zip unzip net-tools telnet nc file \
&& yum install -y git bison libtool automake patch \
 zlib-devel libxml2-devel openssl-devel libyaml-devel libffi-devel readline-devel gdbm-devel ncurses-devel libcurl-devel pcre-devel\
 sqlite-devel libxslt libxslt-devel \
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