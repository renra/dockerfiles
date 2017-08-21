FROM debian:jessie

RUN apt-get -qy update && \
  apt-get -qy install build-essential git git-core libcurl3 curl && \
  apt-get install -qy zlib1g-dev && \
  apt-get install -qy libssl-dev && \
  apt-get install -qy libpq-dev && \
  apt-get install -qy libreadline-dev && \
  apt-get install -qy locales locales-all && \
  rm -rf /var/lib/apt/lists/*

RUN locale-gen en_GB.UTF-8

ENV LC_ALL=en_GB.UTF-8
ENV LANG=en_GB.UTF-8
ENV LANGUAGE=en_GB.UTF-8

ARG RUBY_MAJOR=2.1
ARG RUBY_MINOR=7
ARG RUBY_VERSION=$RUBY_MAJOR.$RUBY_MINOR

RUN mkdir /ruby && \
  cd /ruby && \
  curl http://cache.ruby-lang.org/pub/ruby/$RUBY_MAJOR/ruby-$RUBY_VERSION.tar.gz | tar xz && \
  cd ruby-$RUBY_VERSION && \
  ./configure --with-openssl-dir=/usr --with-readline-dir=/usr --with-zlib-dir=/usr && \
  make && \
  make install && \
  cd / && \
  rm -rf /ruby


ARG NODE_VERSION=4.5.0

RUN apt-get -qy update && \
  apt-get -qy install python && \
  mkdir /node && \
  cd /node && \
  curl http://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION.tar.gz | tar xz && \
  cd node-v$NODE_VERSION && \
  ./configure && \
  make && \
  make install && \
  cd / && \
  rm -rf /node && \
  apt-get -qy remove python && \
  apt-get -qy autoremove


RUN echo 'gem: --no-ri --no-rdoc' > ~/.gemrc
