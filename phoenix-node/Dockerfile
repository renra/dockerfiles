FROM renra/phoenix:1.3.2_elx1.7_erlang19

RUN apt-get -qq -y update && \
  apt-get -qy install libcurl3 curl && \
  rm -rf /var/lib/apt/lists/*

ARG NODE_VERSION=10.10.0

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

CMD ["bin/bash"]

