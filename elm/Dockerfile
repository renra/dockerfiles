FROM debian:stretch-slim

RUN apt-get -qy update && apt-get -qy dist-upgrade && \
  apt-get -qy install build-essential git git-core libcurl3 curl wget && \
  apt-get install -qy zlib1g-dev && \
  apt-get install -qy libssl-dev && \
  apt-get install -qy libreadline-dev && \
  apt-get install -qy locales locales-all && \
  rm -rf /var/lib/apt/lists/*

RUN locale-gen en_GB.UTF-8

ENV LC_ALL=en_GB.UTF-8
ENV LANG=en_GB.UTF-8
ENV LANGUAGE=en_GB.UTF-8

ARG NODE_VERSION=10.16.0

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
  apt-get -qy autoremove && \
  rm -rf /var/lib/apt/lists/*

RUN apt-get install -qy wget

RUN wget https://github.com/Yelp/dumb-init/releases/download/v1.2.1/dumb-init_1.2.1_amd64.deb
RUN dpkg -i dumb-init_*.deb

ENV DIR /usr/src/app
RUN mkdir -p ${DIR}
WORKDIR ${DIR}

RUN npm install -g elm uglify-js --unsafe-perm

ENTRYPOINT ["/usr/bin/dumb-init", "--"]

