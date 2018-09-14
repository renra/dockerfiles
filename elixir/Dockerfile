FROM renra/erlang:stretch

RUN apt-get -qq -y update && \
  apt-get install -qy git-core

ARG ELIXIR_VERSION=1.7

RUN git clone https://github.com/elixir-lang/elixir.git && \
  cd elixir && \
  git fetch origin --tags && \
  git checkout v$ELIXIR_VERSION && \
  make clean test install

RUN apt-get -qy remove git-core && \
  apt-get -qy autoremove && \
  rm -rf /var/lib/apt/lists/*

CMD ["iex"]
