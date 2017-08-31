FROM centos:7.3.1611
MAINTAINER Wattana Inthaphong <wattana@angstromsolutions.net>

#ENV LANG en_US.UTF-8
#ENV LC_TIME en_US.UTF-8
#RUN localedef -i en_US -f UTF-8 en_US.UTF-8
#RUN echo "export LANG=en_US.UTF-8" >> /etc/profile.d/locale.sh && echo "export LANGUAGE=en_US.UTF-8" >> /etc/profile.d/locale.sh

# Setup Timezone
#ENV TZ "Asia/Bangkok"

ENV NODE_VERSION v8.2.1
# Enable EPEL
RUN localedef -i en_US -f UTF-8 en_US.UTF-8 &&\
  yum install -y epel-release &&\
  yum update -y &&\
  yum install -y python-pip bind-utils openssl haveged autoconf make gcc gcc-c++ wget vim mlocate which tar bzip2 zip unzip net-tools telnet nc file \
    git bison libtool automake patch \
    zlib-devel libxml2-devel openssl-devel libyaml-devel libffi-devel readline-devel gdbm-devel ncurses-devel libcurl-devel pcre-devel\
    sqlite-devel libxslt libxslt-devel &&\
  yum clean all &&\
  wget https://nodejs.org/dist/$NODE_VERSION/node-$NODE_VERSION.tar.gz &&\
  tar -xf node-$NODE_VERSION.tar.gz &&\
  cd node-$NODE_VERSION &&\
  ./configure &&\
  make &&\
  make install &&\
  cd / &&\
  rm -rf node-$NODE_VERSION &&\
  rm -f node-$NODE_VERSION.tar.gz

ENV PATH $PATH:/node_modules/.bin
### RUBY #####################################################################

RUN yum install -y git bison libtool automake patch\
 zlib-devel libxml2-devel openssl-devel libyaml-devel libffi-devel readline-devel gdbm-devel ncurses-devel libcurl-devel pcre-devel\
 sqlite-devel libxslt libxslt-devel \
&& yum clean all 

ENV RUBY_SERIES=2.4
ENV RUBY_VERSION=2.4.1
RUN wget https://cache.ruby-lang.org/pub/ruby/$RUBY_SERIES/ruby-$RUBY_VERSION.tar.gz &&\
  tar -xf ruby-$RUBY_VERSION.tar.gz &&\
  cd ruby-$RUBY_VERSION &&\
  ./configure --disable-install-doc --disable-install-rdoc --enable-shared &&\
  make && make install &&\
  cd / &&\
  rm -rf ruby-$RUBY_VERSION.tar.gz &&\
  rm -rf ruby-$RUBY_VERSION 
