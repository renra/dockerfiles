FROM debian:stretch

RUN apt-get -qyy update
RUN apt-get -qyy install build-essential git git-core libcurl3 curl
RUN apt-get install -qyy zlib1g-dev
RUN apt-get install -qyy libssl-dev

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

RUN mkdir /ruby && \
  cd /ruby && \
  curl http://cache.ruby-lang.org/pub/ruby/2.3/ruby-2.3.0.tar.gz | tar xz && \
  cd ruby-2.3.0 && \
  ./configure && \
  make && \
  make install && \
  cd ext/zlib && \
  ruby extconf.rb && \
  make && \
  make install && \
  cd / && \
  rm -rf /ruby

RUN echo 'gem: --no-ri --no-rdoc' > ~/.gemrc
