FROM registry.angsoln.net/angstroms/centos7_nodejs:node4.2.2
MAINTAINER Wattana Inthaphong <wattaint@gmail.com>

### RUBY #####################################################################
RUN yum update -y \
&& yum install -y git bison libtool automake patch\
 zlib-devel libxml2-devel openssl-devel libyaml-devel libffi-devel readline-devel gdbm-devel ncurses-devel libcurl-devel pcre-devel \
&& yum clean all

ENV RUBY_SERIES 2.2
ENV RUBY_VERSION 2.2.3

RUN wget https://cache.ruby-lang.org/pub/ruby/$RUBY_SERIES/ruby-$RUBY_VERSION.tar.gz \
&& tar -xf /ruby-$RUBY_VERSION.tar.gz \
&& cd /ruby-$RUBY_VERSION \
&& ./configure \
&& make && make install \
&& cd / \
&& rm -rf /ruby-$RUBY_VERSION \
&& rm -f /ruby-$RUBY_VERSION.tar.gz
