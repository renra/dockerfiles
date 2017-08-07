FROM debian:jessie

RUN apt-get -qy update
RUN apt-get -qy install build-essential git git-core libcurl3 curl
RUN apt-get install -qy zlib1g-dev
RUN apt-get install -qy libssl-dev
RUN apt-get install -qy libpq-dev
RUN apt-get install -qy libreadline-dev

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
