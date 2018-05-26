FROM renra/build-essential-utf8:stretch

RUN apt-get -qy update && \
  apt-get install -qy erlang && \
  rm -rf /var/lib/apt/lists/*

CMD ["erl"]
