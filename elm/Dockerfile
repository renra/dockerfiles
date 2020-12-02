FROM node:14.15.0-buster-slim

WORKDIR /opt

RUN apt-get -qy update && \
  apt-get -qy install build-essential git git-core libcurl4 curl && \
  apt-get install -qy zlib1g-dev && \
  apt-get install -qy libssl-dev && \
  apt-get install -qy libreadline-dev && \
  apt-get install -qy locales locales-all && \
  rm -rf /var/lib/apt/lists/*

RUN locale-gen en_GB.UTF-8

ENV LC_ALL=en_GB.UTF-8
ENV LANG=en_GB.UTF-8
ENV LANGUAGE=en_GB.UTF-8

RUN curl -L -o dumb-init.deb https://github.com/Yelp/dumb-init/releases/download/v1.2.1/dumb-init_1.2.1_amd64.deb && \
  dpkg -i dumb-init.deb && \
  rm dumb-init.deb

RUN curl -L -o elm.gz https://github.com/elm/compiler/releases/download/0.19.1/binary-for-linux-64-bit.gz && \
  gunzip elm.gz && \
  chmod +x elm && \
  mv elm /usr/local/bin/

RUN yarn global add uglify-js@3.12.1

ENTRYPOINT ["/usr/bin/dumb-init", "--"]

