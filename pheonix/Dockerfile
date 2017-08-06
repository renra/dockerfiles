FROM elixir:1.5.1-slim

RUN apt-get -qy update
RUN apt-get -qy install build-essential git git-core libcurl3 curl
RUN apt-get install -qy zlib1g-dev
RUN apt-get install -qy libssl-dev

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

RUN yes | mix local.hex && \
  yes | mix archive.install https://github.com/phoenixframework/archives/raw/master/phx_new-1.3.0.ez


