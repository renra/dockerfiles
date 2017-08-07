FROM debian:jessie

RUN apt-get -qy update
RUN apt-get -qy install build-essential git git-core libcurl3 curl
RUN apt-get install -qy zlib1g-dev
RUN apt-get install -qy libssl-dev

RUN mkdir /ruby && \
  cd /ruby && \
  curl http://cache.ruby-lang.org/pub/ruby/2.4/ruby-2.4.1.tar.gz | tar xz && \
  cd ruby-2.4.1 && \
  ./configure && \
  make && \
  make install && \
  cd / && \
  rm -rf /ruby

RUN apt-get -qyy install python && \
  mkdir /node && \
  cd /node && \
  curl http://nodejs.org/dist/v8.1.2/node-v8.1.2.tar.gz | tar xz && \
  cd node-v8.1.2 && \
  ./configure && \
  make && \
  make install && \
  cd / && \
  rm -rf /node && \
  apt-get -qyy remove python && \
  apt-get -qyy autoremove


RUN echo 'gem: --no-ri --no-rdoc' > ~/.gemrc
