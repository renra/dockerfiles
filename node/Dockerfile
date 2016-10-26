FROM debian:jessie

RUN apt-get -qyy update
RUN apt-get -qyy install build-essential git git-core libcurl3 curl
RUN apt-get install -qyy zlib1g-dev
RUN apt-get install -qyy libssl-dev

RUN apt-get -qyy install python && \
  mkdir /node && \
  cd /node && \
  curl http://nodejs.org/dist/v6.9.1/node-v6.9.1.tar.gz | tar xz && \
  cd node-v6.9.1 && \
  ./configure && \
  make && \
  make install && \
  cd / && \
  rm -rf /node && \
  apt-get -qyy remove python && \
  apt-get -qyy autoremove
