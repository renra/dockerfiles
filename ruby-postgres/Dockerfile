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

ARG MAJOR=2.2
ARG MINOR=3
ARG VERSION=$MAJOR.$MINOR

RUN mkdir /ruby && \
  cd /ruby && \
  curl http://cache.ruby-lang.org/pub/ruby/$MAJOR/ruby-$VERSION.tar.gz | tar xz && \
  cd ruby-$VERSION && \
  ./configure --with-openssl-dir=/usr --with-readline-dir=/usr --with-zlib-dir=/usr && \
  make && \
  make install && \
  cd / && \
  rm -rf /ruby

RUN echo 'gem: --no-ri --no-rdoc' > ~/.gemrc
